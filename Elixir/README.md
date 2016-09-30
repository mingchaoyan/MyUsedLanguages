# Elixir

## 1. hello, world
```
parent = self()

# Spawns an Elixir process (not an operating system one!)
spawn_link(fn ->
send parent, {:msg, "hello world"}
end)

# Block until the message is received
receive do
{:msg, contents} -> IO.puts contents
end
```
