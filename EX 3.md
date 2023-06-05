# EX-3 IMPLEMENTATION OF SLIDING WINDOW PROTOCOL

# DATE : 20-03-2023


# AIM :
### To write a python program to perform sliding window protocol

# ALGORITHM :
### 1. Start the program.
### 2. Get the frame size from the user
### 3. To create the frame based on the user request.
### 4. To send frames to server from the client side.
### 5. If your frames reach the server it will send ACK signal to client otherwise it will send NACKsignal to client.
### 6. Stop the program.



# CLIENT PROGRAM :
```PY
## Developed : Ziyavudeen A
## Reg no : 212221040189
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
# SERVER PROGRAM :
```PY

import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("acknowledgement recived from the server".encode())

```




# SERVER OUTPUT :
![S_3](https://github.com/Javith-farkhan/EX-3/assets/94296805/692d95b4-60a1-40e1-961d-5c4c33af5721)

# CLIENT OUTPUT : 
![C_3](https://github.com/Javith-farkhan/EX-3/assets/94296805/b0d746b8-3a2b-4cd0-86ed-225a124af8ba)




# RESULT:
### Thus, python program to perform stop and wait protocol And Sliding Window Protocol was successfully executed.


