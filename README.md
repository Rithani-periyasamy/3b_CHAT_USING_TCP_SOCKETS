# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM

#Server program:

import socket

host = "localhost"

port = 12345

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

s.bind((host, port))

s.listen(1)

print("Server waiting for connection...")

conn, addr = s.accept()

print("Connected to:", addr)

while True:
   
   msg = conn.recv(1024).decode()
    
   print("Client:", msg)

   reply = input("Server: ")
    
   conn.send(reply.encode())

#Server output:

PS C:\Users\acer\OneDrive\Attachments>  & 'c:\Users\acer\AppData\Local\Microsoft\WindowsApps\python3.13.exe' 'c:\Users\acer\.vscode\extensions\ms-python.debugpy-2025.18.0-win32-x64\bundled\libs\debugpy\launcher' '57575' '--' 'C:\Users\acer\OneDrive\Attachments\3b server.py' 

Server waiting for connection...

Connected to: ('127.0.0.1', 57577)

Client: How are you

Server: Yeah I am good

Client: bye

Server: okay

#Client program:

import socket

host = "localhost"

port = 12345

c = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

c.connect((host, port))

while True:

   msg = input("Client: ")
    
   c.send(msg.encode())

   reply = c.recv(1024).decode()
    
   print("Server:", reply)

#Client output:

PS C:\Users\acer\OneDrive\Attachments>  & 'c:\Users\acer\AppData\Local\Microsoft\WindowsApps\python3.13.exe' 'c:\Users\acer\.vscode\extensions\ms-python.debugpy-2025.18.0-win32-x64\bundled\libs\debugpy\launcher' '57563' '--' 'C:\Users\acer\OneDrive\Attachments\3b client.py' 

Client: How are you

Server: Yeah I am good

Client: bye

Server: okay

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
