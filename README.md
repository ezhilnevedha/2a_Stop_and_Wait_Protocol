# 2a_Stop_and_Wait_Protocol
### NAME: EZHIL NEVEDHA K
### REG.NO: 212223230055
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:
### server.py:
```
import socket
s=socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()   
        break
```
### client.py:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/01941143-b1d8-4f26-91e9-6021b7afbcbc)

![image](https://github.com/user-attachments/assets/e2a590de-6e17-49a5-88fe-94900608cfab)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
