# Trivial File Transfer Protocol (TFTP) Implementation  

## Introduction  
The Trivial File Transfer Protocol (TFTP) is a lightweight protocol designed to transfer files between devices in a secure environment without authentication. It is particularly useful for applications such as booting nodes in a local area network.  

This implementation focuses on simplicity and user-friendliness, adhering to the specifications defined in [RFC 1350](https://tools.ietf.org/html/rfc1350).  

---

## Features  
- Server runs in the background without a user interface.  
- Client provides a prompt to interact with the server using simple commands.  
- Supports basic TFTP operations:  
  - **connect**: Connect to the server using its IP address.  
  - **get**: Retrieve a file from the server.  
  - **put**: Upload a file to the server.  
  - **mode**: Set the file transfer mode (octet, netascii, or mail).  
  - **bye/quit**: Exit the client and close the connection.  
- Automatic allocation of unique ports for clients starting from port 20000.  
- Error handling and timeout retransmission.  

---

## Requirements  
- **Server**: Runs continuously in the background, awaiting client requests.  
- **Client**: Provides a user prompt to execute commands for interacting with the server.  

---

## Commands  
| Command    | Description                           | Example                       |  
|------------|---------------------------------------|-------------------------------|  
| `connect`  | Connect to the server by IP address.  | `connect 192.168.1.1`         |  
| `get`      | Retrieve a file from the server.      | `get example.txt`             |  
| `put`      | Upload a file to the server.          | `put upload.txt`              |  
| `mode`     | Set the file transfer mode.           | `mode octet`                  |  
| `bye/quit` | Exit the client.                      | `bye`                         |  

---

## How It Works  
1. **Server**:  
   - Starts and runs in a continuous loop.  
   - Waits for incoming requests on specified ports.  
2. **Client**:  
   - Runs until the user exits using `bye` or `quit`.  
   - Handles commands for connecting to the server, transferring files, and changing modes.  

---

## Sample Output  

### Server Running in Background  
