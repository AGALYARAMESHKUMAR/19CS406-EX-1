# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

# DATE : 09-03-2023
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
# Developed By : Agalya R
# Reg No : 212222040003
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
![image](https://github.com/sujathamohankumar/19CS406-EX-1/assets/119394395/92aa6c84-d22e-4a31-ac20-960c78bcf618)


# SERVER OUTPUT:
![image](https://github.com/sujathamohankumar/19CS406-EX-1/assets/119394395/2d348829-0155-4e43-a988-297c9dd8779f)


# RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
