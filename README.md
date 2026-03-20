# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM:
server.py
~~~
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)

print("Server is waiting for connection...")

c, addr = s.accept()
print("Connected to:", addr)

while True:
    msg = c.recv(1024).decode()
    print("Client >", msg)
    reply = input("Server > ")
    c.send(reply.encode())
~~~
client.py:
~~~
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    msg = input("Client > ")
    s.send(msg.encode())
    print("Server >", s.recv(1024).decode())
~~~
## OUPUT:

<img width="1918" height="1198" alt="image" src="https://github.com/user-attachments/assets/77eea534-d065-48bf-b660-7283bd0bf115" />


## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
