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
##server
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)

print("Server Waiting for Connection...")

c, addr = s.accept()
print("Connected to:", addr)

while True:
    ClientMessage = c.recv(1024).decode()

    if not ClientMessage or ClientMessage.lower() == "exit":
        print("Connection Closed")
        break

    print("Client >", ClientMessage)

    c.send((ClientMessage).encode())

c.close()
s.close()
```
##client
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

print("Connected to Server")

while True:
    msg = input("Client > ")

    s.send(msg.encode())

    if msg.lower() == "exit":
        print("Connection Closed")
        break

    data = s.recv(1024).decode()
    print("Server >", data)

s.close()
```
## OUPUT
<img width="1553" height="1058" alt="image" src="https://github.com/user-attachments/assets/b12c3e49-e023-4a46-8672-c125aece50ee" />
<img width="1556" height="1020" alt="image" src="https://github.com/user-attachments/assets/acd221f9-a23a-499c-b4f2-24f4296b9dbe" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
