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
### Server side
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
    print("Client >", clientMessage)
    reply = input("Server > ")
    c.send(reply.encode())
c.close()
s.close()
```
### Client side
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
    print("Server >", s.recv(1024).decode())
s.close()

```
## OUPUT
### Server side
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4b3953bf-343d-4d35-8b12-82574d93ae6d" />
### Client side
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ff35d1e6-2cd5-4123-890f-215b9ab3e92f" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
