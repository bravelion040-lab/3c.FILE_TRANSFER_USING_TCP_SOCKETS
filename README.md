# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
## SERVER
```
import socket
server = socket.socket()
server.bind(("127.0.0.1", 5555))
server.listen(1)
print("Server waiting for connection...")
client, addr = server.accept()
print("Connected to:", addr)
filename = input("Enter file name to send: ")
with open(filename, "rb") as file:
    data = file.read()
    client.send(data)
print("File sent successfully")
client.close()
server.close()
```
## CLIENT
```
import socket
client = socket.socket()
client.connect(("127.0.0.1", 5555))
save_name = input("Enter name to save file: ")
data = client.recv(1000000)
with open(save_name, "wb") as file:
    file.write(data)
print("File received successfully")
client.close()
```
## OUTPUT
## SERVER


<img width="1920" height="1080" alt="Screenshot 2026-05-20 113916" src="https://github.com/user-attachments/assets/91d39135-29ab-40d9-b79f-d6a7bd6af08a" />



## Sample.txt


<img width="1920" height="1080" alt="Screenshot 2026-05-20 113942" src="https://github.com/user-attachments/assets/d5cc35dc-634b-407f-8289-d3735f1d7c7d" />





## CLIENT

<img width="1920" height="1080" alt="Screenshot 2026-05-20 113930" src="https://github.com/user-attachments/assets/30853e31-f3c5-4ca7-a1bb-723a3bcb35db" />

## Received.txt






<img width="1920" height="1080" alt="Screenshot 2026-05-20 113955" src="https://github.com/user-attachments/assets/1712a4e0-8bbc-4411-9809-f4bc40d5839e" />





## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
