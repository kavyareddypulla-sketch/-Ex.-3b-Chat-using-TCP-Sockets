## DATE:- 19/11/2026
## NAME:- PULLA KAVYA
## REG NO:- 212225240110

# Ex.-3b-Chat-using-TCP-Sockets
## AIM

To write a python program for creating Chat using TCP Sockets Links.

## ALGORITHM:

Import the necessary modules in python

Create a socket connection to using the socket module.

Send message to the client and receive the message from the client using the Socket module in server

Send and receive the message using the send function in socket.

## PROGRAM
## SERVER
```
import socket

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.bind(('localhost', 8000))
s.listen(1)

c, addr = s.accept()
print("Connected:", addr)

while True:
    data = c.recv(1024).decode()
    print("Client > ", data)

    reply = input("Server > ")
    c.sendall(reply.encode())
```
## CILENT
```
import socket

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.connect(('localhost', 8000))

while True:
    data = input("Client > ")
    s.sendall(data.encode())

    reply = s.recv(1024).decode()
    print("Server > ", reply)
```
## OUPUT
## SERVER

<img width="848" height="276" alt="image" src="https://github.com/user-attachments/assets/eea71ce4-761f-4e87-88da-300d0bf7f9a5" />

## CILENT

<img width="931" height="272" alt="image" src="https://github.com/user-attachments/assets/9b6d9c2b-dbf9-42fe-91f1-356742378798" />

## RESULT

Thus, the python program for creating Chat using TCP Sockets Links was successfully created and executed.
