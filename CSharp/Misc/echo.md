# Echo

## 支持多个同时连接，但每个连接只支持一次读写
```
using System;
using System.Net;
using System.Net.Sockets;

namespace ConsoleApplication
{
    public class Program
    {
        public static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
            // Socket
            Socket listenfd = new Socket(AddressFamily.InterNetwork, SocketType.Stream, ProtocolType.Tcp);
            // Bind
            IPAddress ipAdr = IPAddress.Parse("127.0.0.1");
            IPEndPoint ipEp = new IPEndPoint(ipAdr, 1234);
            listenfd.Bind(ipEp);
            //listen
            listenfd.Listen(0);
            Console.WriteLine("服务器启动成功");
            while(true)
            {
                // accept
                Socket connfd = listenfd.Accept();
                Console.WriteLine("服务器Accept");
								//Recv
                byte[] readBuff = new byte[1024];
                int count = connfd.Receive(readBuff);
                string str = System.Text.Encoding.UTF8.GetString(readBuff, 0, count);
                Console.WriteLine("服务器接收" + str);
                //Send
                byte[] bytes = System.Text.Encoding.Default.GetBytes("serv echo " + str);
                connfd.Send(bytes);
            }
        }
    }
}
```

## 多个连接，多次读写(聊天服务器)
```cs
using System;

namespace ConsoleApplication
{
    public class Program
    {
        public static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
            Serv serv = new Serv();
            serv.Start("192.168.3.235", 1234);

            while (true)
            {
                string str = Console.ReadLine();
                switch (str)
                {
                    case "quit":
                        return;
                }

            }
        }
    }
}

```

```
using System;
using System.Net;
using System.Net.Sockets;

public class Serv
{
    public Socket listenfd;
    public Conn[] conns;
    public int maxConn = 50;

    public int NewIndex()
    {
        if (conns == null)
        {
            return -1;
        }
        for (int i = 0; i < conns.Length; ++i)
        {
            if (conns[i] == null)
            {
                conns[i] = new Conn();
                return i;
            }
            else if (conns[i].isUse == false)
            {
                return i;
            }
        }
        return -1;
    }

    public void Start(string host, int port)
    {
        conns = new Conn[maxConn];
        for (int i = 0; i < maxConn; ++i)
        {
            conns[i] = new Conn();
        }
        listenfd = new Socket(AddressFamily.InterNetwork, SocketType.Stream, ProtocolType.Tcp);
        IPAddress ipAddr = IPAddress.Parse(host);
        IPEndPoint ipEp = new IPEndPoint(ipAddr, port);
        listenfd.Bind(ipEp);
        listenfd.Listen(maxConn);
        listenfd.BeginAccept(AcceptCb, null);
        Console.WriteLine("服务器启动成功");
    }

    private void AcceptCb(IAsyncResult ar)
    {
        try
        {
            Socket socket = listenfd.EndAccept(ar);
            int index = NewIndex();
            if (index < 0)
            {
                socket.Close();
                Console.Write("警告连接已满");
            }
            else
            {
                Conn conn = conns[index];
                conn.Init(socket);
                string adr = conn.GetAddress();
                Console.WriteLine("客户端连接 " + adr + "conn 池 ID: " + index);
                conn.socket.BeginReceive(conn.readBuff, conn.bufferCount, conn.BufferRemain(), SocketFlags.None, ReceiveCb, conn);
            }
            listenfd.BeginAccept(AcceptCb, null);
        }
        catch (System.Exception e)
        {
            Console.WriteLine("AcceptCb 失败:" + e.Message);
        }
    }

    private void ReceiveCb(IAsyncResult ar)
    {
        Conn conn = (Conn)ar.AsyncState;
        try
        {
            int count = conn.socket.EndReceive(ar);
            if (count <= 0)
            {
                Console.WriteLine(conn.GetAddress() + "  断开连接");
                conn.Close();
                return;
            }
            string str = System.Text.Encoding.UTF8.GetString(conn.readBuff, 0, count);
            Console.WriteLine("收到" + conn.GetAddress() + str);
            byte[] bytes = System.Text.Encoding.UTF8.GetBytes(str);
            for (int i = 0; i < conns.Length; ++i)
            {
                if (conns[i] == null)
                {
                    continue;
                }
                if (!conns[i].isUse)
                {
                    continue;
                }
                Console.WriteLine("将消息传播给" + conns[i].GetAddress());
                conns[i].socket.Send(bytes);
            }
            conn.socket.BeginReceive(conn.readBuff, conn.bufferCount, conn.BufferRemain(), SocketFlags.None, ReceiveCb, conn);
        }
        catch (System.Exception)
        {
            Console.WriteLine(conn.GetAddress() + "断开连接");
            conn.Close();
        }
    }
}
```

```
using System;
using System.Net.Sockets;

public class Conn
{
    public const int BUFFER_SIZE = 1024;
    public Socket socket;
    public bool isUse = false;
    public byte[] readBuff = new byte[BUFFER_SIZE];
    public int bufferCount = 0;

    public Conn()
    {
        readBuff = new byte[BUFFER_SIZE];
    }

    public void Init(Socket socket)
    {
        this.socket = socket;
        isUse = true;
        bufferCount = 0;
    }

    public int BufferRemain()
    {
        return BUFFER_SIZE - bufferCount;
    }

    public string GetAddress()
    {
        if (!isUse)
            return "无法获取地址";
        return socket.RemoteEndPoint.ToString();
    }

    public void Close()
    {
        if (!isUse)
            return;
        Console.WriteLine("断开连接" + GetAddress());
        socket.Shutdown(SocketShutdown.Both);
        isUse = false;
    }
}
```
