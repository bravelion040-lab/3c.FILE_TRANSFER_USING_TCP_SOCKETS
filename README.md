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


<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/61d2038b-f2bb-4c94-981c-cf36a199b6ef" />




## Sample.txt


<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/7649942f-5b92-4ab2-a78d-5f4ef16b7895" />





## CLIENT

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/db81e48b-82cc-48f0-9a4a-2a6173de0c59" />


## Received.txt






<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8a287ea3-f447-47d6-ba74-6eec40d1ae30" />






## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
