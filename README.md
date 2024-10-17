# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL

##NAME:R SAKETRAM

##REGISTER NUMBER:212223230181

## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## CLIENT: 

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
## SERVER:

import socket    
s=socket.socket()   
s.connect(('localhost',8000))   
while True:    
 print(s.recv(1024).decode())    
 s.send("acknowledgement recived from the server".encode())

## OUTPUT:

## CLIENT:
![Screenshot 2024-04-11 150934](https://github.com/saxxxxxxx/2b_SLIDING_WINDOW_PROTOCOL/assets/154911090/148ba4fb-a8b9-406e-b5d8-2760f7903e9f)

## SERVER:
![Screenshot 2024-04-11 150944](https://github.com/saxxxxxxx/2b_SLIDING_WINDOW_PROTOCOL/assets/154911090/c4bec69f-1a49-4678-8145-ff8b702606b7)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
