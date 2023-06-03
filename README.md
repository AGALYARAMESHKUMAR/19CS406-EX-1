# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

# DATE : 08-03-2023
# AIM :
To write a python program to perform client server model.

# ALGORITHM :

Start the program.
Get the frame size from the user
To create the frame based on the user request.
To send frames to server from the client side.
If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
Stop the program
# CLIENT PROGRAM:
Developed By : Agalya R
Reg No :212222040003
```
import socket

s=socket.socket()

s.bind(('localhost',8080))

s.listen(5)

c,addr=s.accept()

while True:

i=input("ENter a data:")

c.send(i.encode())

ack=c.recv(1024).decode()

if ack:

	print(ack)

	continue

else:

	c.close()

	break
  ```
# SERVER PROGRAME:
```
import socket

s=socket.socket()

s.connect(('localhost',8080))

while True:

print(s.recv(1024).decode())

s.send("Recieved".encode())
```
# CLIENT OUTPUT:

![image](https://github.com/AGALYARAMESHKUMAR/19CS406-EX-1/assets/119394395/7b151cd0-8391-447f-b988-bdaa1003fae4)

# SERVER OUTPUT:
![image](https://github.com/AGALYARAMESHKUMAR/19CS406-EX-1/assets/119394395/0c2c381c-be01-4d3d-986b-8bfb795b78f2)

# RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.


