# tcp服务端代码
``` python
import socket
a=0
b=0
def cishu():
    global a

def sum():
    global b
# 新建一个tcp socket
tcp_sock=socket.socket(socket.AF_INET,socket.SOCK_STREAM)

# 绑定端口
address=("0.0.0.0",7000)
tcp_sock.bind(address)
# 监听
tcp_sock.listen(10)
while True:
    # 等待连接
    conn,addr=tcp_sock.accept()
    print(f"{addr}connected!")
    # 接受客服端发来的数据
    data=conn.recv(1024)
    a=a+1
    print(f"接收到的数据{data}")
    b=b+len(data)
    msg1=("我累计接受了%d次数据，总的字节数为%d，此次数据为")%(a,b)
    # 发送数据到客服端
    conn.send(msg1.encode("utf-8")+data)
    # 断开连接
    conn.close()

```


# tcp客户端代码
```python
import socket

tcp_sock  = socket.socket(socket.AF_INET,socket.SOCK_STREAM)

# 建立连接
address = ("127.0.0.1",7000)
tcp_sock.connect(address)

# 发送数据
tcp_sock.send(b"hello world,hello")

# 接收一下数据
data = tcp_sock.recv(1024)
st=data.decode("utf-8")
print(f"接收到{address}数据: {st}")

# 关闭连接
tcp_sock.close()
```