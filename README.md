# Multi Client Chat Application

## Overview
This project is a console-based multi-client chat application built in Java using TCP sockets and multi-threading. The server listens for incoming client connections and broadcasts messages to all connected clients in real-time. Each client runs in its own terminal and can send and receive messages simultaneously. This project demonstrates network programming, concurrency, and object-oriented design, simulating a small-scale real-world messaging system.

---

## Features
- Real-time messaging between multiple clients
- Multi-threaded server handling concurrent client connections
- Broadcast system: all clients receive messages from everyone
- Console-based interface for simplicity
- Demonstrates networking, OOP, and concurrency concepts

---

## Code Explanation
The project consists of two main Java files: `Server.java` and `Client.java`.

**Server.java**
- Opens a ServerSocket on port 5000 and waits for client connections.
- Each connection is handled in a separate thread (`ClientHandler`) to allow simultaneous clients.
- Incoming messages are read using `BufferedReader` and broadcasted to all connected clients via `PrintWriter`.
- This ensures real-time message delivery and prevents blocking other clients while one client is sending messages.

**Client.java**
- Creates a Socket connection to the server.
- Uses `BufferedReader` to receive messages and `PrintWriter` to send messages.
- A separate thread continuously listens for messages from the server so the client can receive messages while typing.
- The main thread waits for user input (`Scanner.nextLine()`) and sends messages to the server.

Together, this architecture demonstrates multi-threading, socket programming, and synchronized message distribution, simulating a realistic chat application.

---

## Sample Output

### Client 1
```
Connected to server.
Hello everyone!
Message: Hello everyone!
Message: Hi Alice!
Message: Good morning!
```

### Client 2
```
Connected to server.
Hi Alice!
Message: Hello everyone!
Message: Hi Alice!
Message: Good morning!
```
### Client 3
```
Connected to server.
Good morning!
Message: Hello everyone!
Message: Hi Alice!
Message: Good morning!
```
Each message typed by any client appears on all other clients’ screens, demonstrating the broadcast functionality.
