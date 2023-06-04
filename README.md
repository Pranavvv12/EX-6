# EX-6 IMPLEMENTATION OF PING COMMAND
# EXP: 6
## DATE:12-04-2023
### AIM:
To write the python program for simulating ping command.
### ALGORITHM:
## Step 1: start the program.
## Step 2: Include necessary package in java.
## Step 3: To create a process object p to implement the ping command.
## Step 4: declare one Buffered Reader stream class object.
## Step 5: Get the details of the server
## 5:1: length of the IP address.
## 5:2: time required to get the details.
## 5:3: send packets, receive packets and lost packets.
## 5.4: minimum, maximum and average times.
## Step 6: print the results.
## Step 7: Stop the program.

### PROGRAM:
## CLIENT:
```
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost'8000))
s.listen(5)
c,addr=s.accept()
while True:
   hostname=c.recv(1024).decode()
try:
   c.send(str(ping(hostname, verbose=False)).encode())
except KeyError:
   c.send("Not Found".encode())
```
## SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
   ip=input("Enter the website you want to ping ")
   s.send(ip.encode())
   print(s.recv(1024).decode())
```
## SERVER OUTPUT :
![image](https://github.com/Pranavvv12/EX-6/assets/121292280/337bfd29-9214-41ca-85fe-8349f0b40287)


## CLIENT OUTPUT :
![image](https://github.com/Pranavvv12/EX-6/assets/121292280/e2073bdd-e014-418a-ae9d-2b23afccb12d)


### RESULT:
Thus, the python program for simulating ping command was successfully executed.

