# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

## Client:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
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
## Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```
## OUTPUT

## Client:
![Screenshot 2025-05-11 083547](https://github.com/user-attachments/assets/3c479f6d-4ae0-450d-93a5-979a92a89a7e)

## Serevr:
![Screenshot 2025-05-11 083600](https://github.com/user-attachments/assets/3935bd67-5c02-4ad6-b5d6-bf54179327b8)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
