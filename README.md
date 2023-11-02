# octo-dollop
chatroom

#COSC 4333 Group Project (multithreaded chatroom)

The goal of this project is to create a multithreaded chatroom service which features a chat server, at least one chat room, and multiple chat client.
By achieving this goal, this project will demonstrate the usefulness of socket programming.

## Table of contents
- How to run the project and what to expect
- Running server.c (ideal scenario)
- Running client.c (ideal scenario)

# How to run the project and what to expect
1. Start up ChatroomServer.c with a port number (ex. 12345)
2. Start up ChatroomClient.c and connect that client to the server using the server's port number (can repeat this step to have multiple clients active)
3. If there is no chatroom currently running, server will create a chatroom. Otherwise the clients are directed to that chatroom.
4. From here, you can have the clients send messages which should show up in the chatroom similar to an actual chat system.
5. Clients will eventually leave the chatroom. When the chatroom has no clients remaining, it is deleted.
6. Server will close when user is done.

# Running server.c (ideal scenario)
1. Server starts up with a name and a port number
2. Server will wait and listen for JOIN requests from clients and accept them
3. If there is no chatroom available, server will create one. Otherwise server directs incoming clients to that chatroom
4. A new socket connection is formed when a client joins
5. Server will send a welcome message when a client joins a chatroom
6. As clients leave, the server will close the appropriate sockets
7. Server will delete a chatroom when all its clients leave
8. Server will close when user is done

# Running client.c (ideal scenario)
1. Client starts up and uses a server's port number to send a request to join the server
2. Client will create a new socket and connect to the server
3. Client joins a chatroom in the server
4. Client is able to send messages that will be displayed to other clients in the chatroom
5. Client will eventually leave the chatroom and close the connecting socket
