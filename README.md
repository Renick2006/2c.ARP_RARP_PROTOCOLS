# 2c.SIMULATING ARP /RARP PROTOCOLS
## NAME: RENICK FABIAN RAJESH
## REG NO: 212224230227
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
## Client:
```
 
import socket 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"}; 
while True: 
            ip=c.recv(1024).decode() 
            try: 
                c.send(address[ip].encode()) 
            except KeyError: 
                c.send("Not Found".encode())
```
## Server:
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter logical Address : ") 
    s.send(ip.encode()) 
    print("MAC Address",s.recv(1024).decode())
```
## OUPUT - ARP
![Screenshot 2025-04-30 123001](https://github.com/user-attachments/assets/caf40f1d-b8c8-4af9-9463-04a8b836972c)
![Screenshot 2025-04-30 123012](https://github.com/user-attachments/assets/91c21d50-6adb-4949-9be7-8725aa571d49)
![Screenshot 2025-04-30 123023](https://github.com/user-attachments/assets/f9fe9322-cd0e-4e4c-92e6-72bde2e93461)
![Screenshot 2025-04-30 123035](https://github.com/user-attachments/assets/3cc97289-7bbe-4e16-bbb2-4399d9bfb748)

## PROGRAM - RARP
## Client:
```
import socket 
s=socket.socket() 
s.bind(('localhost',9000)) 
s.listen(5) 
c,addr=s.accept() 
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"}; 
while True: 
            ip=c.recv(1024).decode() 
            try: 
                c.send(address[ip].encode()) 
            except KeyError: 
                c.send("Not Found".encode())
```
## Server:
```
import socket 
s=socket.socket() 
s.connect(('localhost',9000)) 
while True: 
   ip=input("Enter MAC Address : ") 
   s.send(ip.encode()) 
   print("Logical Address",s.recv(1024).decode())
```
## OUPUT -RARP
![Screenshot 2025-04-30 123205](https://github.com/user-attachments/assets/bccfc417-78dc-4bee-821a-7da9d79d7bc3)
![Screenshot 2025-04-30 123214](https://github.com/user-attachments/assets/22b5b2a2-6e48-43a8-bbf2-3ed1de23ba1a)
![Screenshot 2025-04-30 123224](https://github.com/user-attachments/assets/e0fddff9-9aaa-41af-be34-4c6a66827689)
![Screenshot 2025-04-30 123234](https://github.com/user-attachments/assets/8db8e6c7-f026-419f-8427-a49cec003aa1)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
