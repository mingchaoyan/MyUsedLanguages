# Echo

## 不支持多个同时连接，但每次连接支持多次读写
```erlang
-module(echo_server).
-export([start_seq_server/0]).
start_seq_server() ->
    {ok, Listen} = gen_tcp:listen(2345, [binary, {packet, 0},
                                         {reuseaddr, true},
                                         {active, true}]),
    seq_loop(Listen).
seq_loop(Listen) ->
    {ok, Socket} = gen_tcp:accept(Listen),
    loop(Socket),
    seq_loop(Listen).
loop(Socket) ->
    receive
        {tcp, Socket, Bin} ->
            io:format("received binary ~p~n", [Bin]),
            gen_tcp:send(Socket, Bin),
            loop(Socket);
        {tcp_closed, Socket} ->
            io:format("server socket closed~n")
    end.
```

## 支持多个同时连接，每个连接多次读写
```erlang
-module(echo_server).
-export([start_parallel_server/0, 
        start/0]).
start() ->
    spawn(fun() -> start_parallel_server() end) .

start_parallel_server() ->
    {ok, Listen} = gen_tcp:listen(2345, [binary, {packet, 0},
                                         {reuseaddr, true},
                                         {active, true}]),
    io:format("~p~n", [Listen]),
    spawn(fun() -> par_connect(Listen) end),
    %% gen_tcp will link to the process that call gen_tcp:listen. When this process goes down after spawn(fun() -> par_connect(Listen) end). then the listen socket will be closed too. I think we should add timer:sleep(infinity) at the end of start_parallel_server() so it doesn't finish.
    timer:sleep(infinity).
par_connect(Listen) ->
    {ok, Socket} = gen_tcp:accept(Listen),
    spawn(fun() -> par_connect(Listen) end),
    loop(Socket).
loop(Socket) ->
    receive
        {tcp, Socket, Bin} ->
            io:format("received binary ~p~n", [Bin]),
            gen_tcp:send(Socket, Bin),
            loop(Socket);
        {tcp_closed, Socket} ->
            io:format("server socket closed~n")
    end.
```

