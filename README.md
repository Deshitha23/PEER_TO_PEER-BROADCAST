# PEER_TO_PEER-BROADCAST
Peer-to-peer messaging and broadcast message
This client-server program supports broadcast messages in addition to peer-to-peer communications. The client can connect to the server, log in using a password, and view the list of clients that are currently active. Any current client can be selected as the connection point, and the distant client will be prompted to accept the new connection. Once a connection has been established successfully, clients can communicate with one another without the server. Additionally, a client can ask the server to send a message to every client in its database by making a broadcast request. The broadcast message should be received by all clients who will be online in the next 30 minutes.

Two Applications: Server and Client

Server

* The server program accepts at least 50 simultaneous connections and listens on port 4400. 
* A socket is created by the server, both for TCP and UDP. UDP sockets are used to broadcast messages, while TCP sockets are used for client-to-client communication.
* Client authentication is stored in and retrieved from the CSV file.
* Connection of the client to the server: The server asks the client to login or register in response to the client's connection request.
* Active clients list: The server displays only the username and IP address of each current client. 
* By entering a client's IP address, the client can ask the server to grant it permission to connect to that client.
* Send a message through broadcast: If a client selects this option, the server will send the message over its UDP socket.

Client

Connecting to the server (fixed IP address and port 4400) is done by the client application. The following features are available in the client application:
* Create a TCP socket: The client begins by establishing a connection to the server using a client-side TCP socket.
* P2P messaging: To send messages, the client establishes a fresh TCP (persistent) connection.
* Message broadcast received: The server sends a message broadcast to the client.
* Status of the connection: The client consistently keeps a TCP and UDP connection open to the server.

Build the Project
* On your local system, clone the repository.
* Go to the project directory in the terminal after opening it.
* To create the project, type “make” into your terminal.
* There will be two executable files produced once the project has been properly built: client and server.
      
 How to Compile and Run the Source code
* Open the terminal and navigate to the project directory.
* Run the command “ g++ server.cpp -o  server -pthread ” to compile the server and use command “./server”
* Run the command “ g++ client.cpp -o  client -pthread ” to compile the server and use command “./client <ip address> <port>”.
* When the client is up and running, it will ask you for the IP address and port number of the server before allowing you to connect.
* You will be asked to sign up or log in after connecting.
* The client will prompt you to provide a new username and password (requested twice, including the password confirmation) if you decide to join up.
* The client will request your username and password if you decide to log in.
* Following authentication, you have the option to broadcast a message or
 list all active clients.
 
<img width="366" alt="image" src="https://user-images.githubusercontent.com/125763130/235827395-167bda70-c80e-4701-9deb-fbfc62718b72.png">

<img width="398" alt="image" src="https://user-images.githubusercontent.com/125763130/235827698-19d68586-362c-4d2e-9529-66c46bdcfc36.png">

<img width="174" alt="image" src="https://user-images.githubusercontent.com/125763130/235827764-c6b97ff4-1833-402f-818a-6382d06037d1.png">

<img width="397" alt="image" src="https://user-images.githubusercontent.com/125763130/235827897-dd170196-cee5-4303-ad69-b2ee38653d2c.png">

Libraries Used
* #include <arpa/inet.h>
* #include <netinet/in.h>
* #include <unistd.h>
* #include <pthread.h>
* #include <iostream>
* #include <cstring>
* #include <string.h>
* #include <cstring>
* #include <unistd.h>
* #include <netdb.h>
* #include <map>
* #include <thread>
* OpenSSL library: Used for encryption and decryption of data.
