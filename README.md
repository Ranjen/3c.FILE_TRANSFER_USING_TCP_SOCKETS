# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM:
fileserver.py
```
import socket
server=socket.socket()
server.bind(("127.0.0.1",5555))
server.listen(1)
print("Server waiting for connection...")
client,addr=server.accept()
print("Connected to:",addr)
filename=input("Enter file name to send: ")
with open(filename,"rb") as file:
    data=file.read()
    client.send(data)
print("File sent successfully")
client.close()
server.close()
```
fileclient.py
```
import socket
client=socket.socket()
client.connect(("127.0.0.1",5555))
save_name=input("Enter name to save file: ")
data=client.recv(1000000)
with open(save_name,"wb") as file:
    file.write(data)
print("File received successfully")
client.close()
```
## OUPUT:
<img width="892" height="372" alt="image" src="https://github.com/user-attachments/assets/0ba9493a-bdef-4e94-b24d-f0acfbfdc00f" />
<img width="886" height="378" alt="image" src="https://github.com/user-attachments/assets/7286b94b-ab87-402a-9afc-6a14e7e1bb5a" />

## RESULT:
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
