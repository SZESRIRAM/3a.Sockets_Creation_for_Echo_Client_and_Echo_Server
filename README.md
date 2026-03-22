# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
server
```
import socket
s=socket.socket()
s.bind(('localhost', 8001))
s.listen(1)
print("Waiting for connection...")
c, addr=s.accept()
print("Connected to", addr)
while True:
    clientMessage=c.recv(1024).decode()
    if clientMessage=="exit":
        print("Client disconnected")
        break
    print("Echo of Client >", clientMessage)
    reply = input("Server > ")
    c.send(reply.encode())
c.close()
s.close()
```
client
```
import socket
s=socket.socket()
s.connect(('localhost', 8001))
while True:
    msg=input("Client > ")
    s.send(msg.encode())
    if msg=="exit":
        print("Disconnected")
        break
    print("Echo of Server >", s.recv(1024).decode())
s.close()
```
## OUPUT
server
<img width="321" height="103" alt="image" src="https://github.com/user-attachments/assets/fc0bc726-1c5f-49e8-96f1-5510049d24fa" />
client
<img width="245" height="91" alt="image" src="https://github.com/user-attachments/assets/e5939e36-340a-409f-957a-1d84732a1e2c" />
## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
