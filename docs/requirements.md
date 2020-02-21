# Chat-thing Requirements Document


## Purpose
### Problem
People want to communicate with each other since they are not able to see each other in person due to work or other reasons. Other people want to make new friends using chat rooms.

### Goal
Our goal is to build a free, easy, and private chat room application that allows people to communicate with one another or a group of people in a chat room.

### Background
This is a group project for CS401 Software Engineering. We have been tasked with a semester-long software engineering project that requires us to implement a substantial piece of software using engineering principles and techniques learned in class. We have selected a chat room application running over a network in a client-server model because it is a useful tool demonstrating network programming, information security, and object-oriented design.

### Definitions
1. Client – The software that runs on the end user’s machine, allowing them to connect to a chat room and send messages.

2. Server – The software that runs on a remote machine and allows clients to communicate with each other in chat rooms and direct messages.

3. Database – The software the stores information about users, chat rooms, and message histories.

4. User – A representation of an end user within the application, including a username for identification in chat rooms and a password for authentication.

5. Message – A representation of a text-based communication within the application, including a text body, a timestamp, and a chat room that the message goes in.

6. Chatroom – A collection of Users who can send messages that will be sent to all other Users in the same collection (room).

7. DirectMessage (DM) – A special chatroom that contains two Users who can send direct/private messages between each other.

## Environment and system requirements
### System overview / Abstract
This application will be a simple chat room and messaging system using a client-server model. It will allow users on the client side to create an account, using a username and password, join a chat room, and send messages in that chat room. The server will maintain each chat room and forward messages from clients in a chat room to all other clients in the same chat room. The server will use a database to maintain user accounts, chat rooms, and chat room message histories. The client application will present controls to create an account, log in, select a chat room to chat with other people, view the chat room's message history once you have entered that specific chat room, and send messages. Also, be able to send private messages between two users. This chat will make a smoother communication for people. Broadcast general notifications, such as user logins and logouts.

### Environment
#### Client environment
1.	System running a modern version of the Java Runtime Environment
2.	Connected to a network with a server (local or Internet)
3.	Capable of displaying a GUI
4.	Capable of capturing user input with mouse and keyboard for interacting with GUI

#### Server environment
1.	System running a modern version of the Java Runtime Environment and a database system that works with Java
2.	Connected to a network that clients can also connect to (local or Internet)
3.	Capable of displaying a command line interface
4.	Capable of capturing user input with mouse and keyboard for interacting with CLI


### Functional requirements
#### Client
1.	Connect to the server over a network automatically on launch
2.	Allow the user to create a new account with a username and password
3.	Allow the user to log in with a username and password
4.	Get list of available chatrooms from server and display in GUI
5.	Allow a logged in user to select and join an available chatroom from the list
6.	Get the chat log and user list for a chatroom and display them on screen when user selects a chatroom
7.	Allow the user to send text messages to the chatroom
8.	Receive messages from the server and asynchronously update the chat log displayed on screen to show the new messages
9.	Allow the user to send text messages to other users in the chatroom by selecting them from the user list (DirectMessage)
10.	Display a system notification when:
  -	A user joins the chat room
  -	A user leaves the chat room
  -	The user receives a direct message
11.	Allow the user to leave the chatroom and display the list of available chatrooms to join another
12.	Allow the user to log out and exit the application, closing the server connection

#### Server
1.	Allow connections from clients over a network
2.	Maintain client connections until the client closes the connection
3.	Connect to a database on the local system
4.	Allow connected clients to create new accounts
5.	Allow connected clients to log in to existing accounts
6.	Send list of available chatrooms to clients on request from client
7.	Manage users in each chatroom, adding and removing as needed based on client connection status
8.	Broadcast messages from users in chatrooms to all other users in the same chatroom
9.	Maintain a chat log for each chatroom, stored in the database
10.	Allow system administrator to create and delete chatrooms via a command line interface

#### Database
1.	Store user account information – username, password
2.	Store chatroom message history for each chatroom

### Non-functional requirements

#### Platform and technology to be used
1.	All code will be written in Java without relying on system-dependent calls in order to keep the application usable on all platforms that support a modern version of the Java Runtime Environment.
2.	Server component will require a local database that the server interacts with using the JDBC interface. Therefore, the database system must support JDBC.

#### System-wide requirements
1.	Usernames must be unique

#### Client
1.	Client should handle network errors (inability to connect to server, loss of connection, etc) without crashing

#### Server
1.	Server should handle network errors without crashing

#### Database
1.	Passwords must be encrypted
2.	When a chatroom is deleted from the server, the chatroom message history must be deleted from the database
