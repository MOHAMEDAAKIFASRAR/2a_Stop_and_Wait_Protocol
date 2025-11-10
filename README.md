# 2a_Stop_and_Wait_Protocol
### Name : MOHAMED AAKIF ASRAR S
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
### Client Program
```.py
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

### Server Program
```.py
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```

## OUTPUT
<img width="1841" height="1017" alt="image" src="https://github.com/user-attachments/assets/c161ec90-084a-40c5-9eab-5392c9b7cb3a" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
