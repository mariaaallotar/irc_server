# Irc server

A server that manages Internet Relay Chat written in C++, allowing users to connect, join channels, and exchange real-time text messages.  

The project is done by me,   
- [Helmi Pirkola](https://github.com/hpirkola) and  
- [Milad Rahmat Abadi](https://github.com/miladrahmat)  

## Features

- authenticate on connection
- set a username on connection
- set a nickname
- join a channel
- send and receive messages on channels and as private messages
- regular and operator users
- the following commands
  - KICK - Eject a client from the channel
  - INVITE - Invite a client to a channel
  - TOPIC - Change or view the channel topic
  - PING - Used to find out the latency on the network
  - MODE - Change the channel’s mode:
    - i: Set/remove Invite-only channel
    - t: Set/remove the restrictions of the TOPIC command to channel operators
    - k: Set/remove the channel key (password)
    - o: Give/take channel operator privilege
    - l: Set/remove the user limit to channel
  - QUIT - Terminates the connection  

- We did not create a client program and used IRSSI as our reference
- We did not handle server-to-server communication

## Usage  
### Running the server and connecting via irssi:  
<img width="1231" height="417" alt="Screenshot of server and irssi" src="https://github.com/user-attachments/assets/c48812eb-0e79-4317-8ba3-4b67267a2dea" />

### Connection established:  
<img width="1576" height="736" alt="Screenshot of server and irssi" src="https://github.com/user-attachments/assets/4bf969c8-9b7d-4d0c-abb9-d9a54382c1d5" />

### Joining a channel:  
<img width="1546" height="598" alt="Screenshot of server and irssi" src="https://github.com/user-attachments/assets/9efe2201-1fab-449d-a0c2-a9e28326a651" />

### Sending message to channel and checking channel modes:
<img width="1247" height="509" alt="Screenshot of server and irssi" src="https://github.com/user-attachments/assets/a3726877-2fcb-4497-917d-64ca1f6b67a3" />


## Allowed external functions

- everything in C++
- socket, close, setsockopt, getsockname
- getprotobyname, gethostbyname, getaddrinfo, freeaddrinfo
- bind, connect, listen, accept
- htons, htonl, ntohs, ntohl, inet_addr, inet_ntoa,
- send, recv, signal
- lseek, fstat, fcntl, poll (or equivalent)

## My contribution

Everybody in the team did a bit of everything. When we were able to allow new connections, receive and send messages, then everybody implemented some commands. But to make creating new commands easy I created an interface for a generic command, ACommand, that was designed based on the behavioral design pattern: command pattern. This allowed us to handle commands as objects.  

## Technologies Used

- `C`, `C++`, `Makefile`, `Git`

## What I learned

- object orineted design
- that object oriented programming is quite nice
- following a protocol
- that small commits are **very** nice when hunting a bug
