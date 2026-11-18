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
FILE SERVER (fileserver.py)
```
import socket

# Create socket
server = socket.socket()

# Bind IP and port
server.bind(("127.0.0.1", 5555))

# Listen for client
server.listen(1)
print("Server waiting for connection...")

# Accept client
client, addr = server.accept()
print("Connected to:", addr)

# Ask filename
filename = input("Enter file name to send: ")

# Open and send file:
 data = file.read()
 client.send(data)
print("File sent successfully")

# Close connections
client.close()
server.close()
```
FILE CLIENT (fileclient.py)
```
import socket

# Create socket
client = socket.socket()

# Connect to server
client.connect(("127.0.0.1", 5555))

# Save file name
save_name = input("Enter name to save file: ")

# Receive data
data = client.recv(1000000)

# Save file
with open(save_name, "wb") as file:
 file.write(data)
print("File received successfully")

# Close connection
client.close()
```

## OUPUT
Client:
<img width="1917" height="1023" alt="image" src="https://github.com/user-attachments/assets/2223e83b-04a3-4cd6-a17b-f1303b9233d3" />

Server:
<img width="1496" height="965" alt="image" src="https://github.com/user-attachments/assets/c2f0bfc5-9c75-4755-bda9-44910081df25" />

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
