# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
```
CLIENT:
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

SERVER:
 
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True:    
    print(s.recv(1024).decode()) 
    s.send("acknowledgement recived from the server".encode())





```
## OUPUT
![Screenshot 2024-03-12 153839](https://github.com/DHARANIDHARAN03K/2b_SLIDING_WINDOW_PROTOCOL/assets/144870858/aba1f4b6-a006-4976-8da1-c08cd295f669)
![Screenshot 2024-03-12 153955](https://github.com/DHARANIDHARAN03K/2b_SLIDING_WINDOW_PROTOCOL/assets/144870858/990c808e-45e1-4c34-b68f-214dfb11a6d3)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
