# IMPLEMENTATION-OF-SLIDING-WINDOW-PROTOCOL
IMPLEMENTATION OF SLIDING WINDOW PROTOCOL    



EXP: 3

DATE: 20/03/2023


AIM:

To write a python program to perform sliding window protocol


ALGORITHM:

1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it
will send NACKsignal to client.
6. Stop the program
PROGRAM:


CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
 while(i<len(l)):
 st+=s
 c.send(str(l[i:st]).encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 i+=s
 ```
 
 
 
SERVER:

```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
 ```
 
 
OUTPUT:


CLIENT:

![1bclient](https://github.com/MaheshMuthuL/IMPLEMENTATION-OF-SLIDING-WINDOW-PROTOCOL/assets/135570619/6fd2bd0f-7aaa-4ca6-a92a-10597dcffb62)









SERVER:


![1bserver](https://github.com/MaheshMuthuL/IMPLEMENTATION-OF-SLIDING-WINDOW-PROTOCOL/assets/135570619/cac98003-fb46-4ee5-97e4-aeec4da5c65a)











RESULT:

Thus, python program to perform stop and wait protocol was successfully executed.
