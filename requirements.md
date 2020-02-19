Chat-thing Requirements Document
https://github.com/boylebryce/chat-thing


1.	Purpose
a.	Problem
People want to communicate with each other since they are not able to see each other in person due to work or other reasons. Other people want to make new friends using chat rooms.

b.	Goal
Our goal is to build a free, easy, and private chat room application that allows people to communicate with one another or a group of people in a chat room.

c.	Background
This is a group project for CS401 Software Engineering. We have been tasked with a semester-long software engineering project that requires us to implement a substantial piece of software using engineering principles and techniques learned in class. We have selected a chat room application running over a network in a client-server model because it is a useful tool demonstrating network programming, information security, and object-oriented design.

d.	Definitions
i.	Client – The software that runs on the end user’s machine, allowing them to connect to a chat room and send messages.

ii.	Server – The software that runs on a remote machine and allows clients to communicate with each other in chat rooms and direct messages.

iii.	Database – The software the stores information about users, chat rooms, and message histories.

iv.	User – A representation of an end user within the application, including a username for identification in chat rooms and a password for authentication.

v.	Message – A representation of a text-based communication within the application, including a text body, a timestamp, and a chat room that the message goes in.

vi.	Chatroom – A collection of Users who can send messages that will be sent to all other Users in the same collection (room).

vii.	DirectMessage (DM) – A special chatroom that contains two Users who can send messages that will be sent to the other User.

2.	Environment and system requirements
a.	System overview / Abstract
This application will be a simple chat room and messaging system using a client-server model. It will allow users on the client side to create an account, using a username and password, join a chat room, and send messages in that chat room. The server will maintain each chat room and forward messages from clients in a chat room to all other clients in the same chat room. The server will use a database to maintain user accounts, chat rooms, and chat room message histories. The client application will present controls to create an account, log in, select a chat room to chat with other people, view the chat room's message history once you have entered that specific chat room, and send messages. Also, be able to send private messages between two users. This chat will make a smoother communication for people. Broadcast general notifications, such as user logins and logouts.

b.	Environment
i.	Client environment
1.	System running a modern version of the Java Runtime Environment
2.	Connected to a network with a server (local or Internet)
3.	Capable of displaying a GUI
4.	Capable of capturing user input with mouse and keyboard for interacting with GUI

ii.	Server environment
1.	System running a modern version of the Java Runtime Environment and a database system that works with Java
2.	Connected to a network that clients can also connect to (local or Internet)
3.	Capable of displaying a command line interface
4.	Capable of capturing user input with mouse and keyboard for interacting with CLI


3.	Functional requirements
a.	Client
i.	Connect to the server over a network automatically on launch
ii.	Allow the user to create a new account with a username and password
iii.	Allow the user to log in with a username and password
iv.	Get list of available chatrooms from server and display in GUI
v.	Allow a logged in user to select and join an available chatroom from the list
vi.	Get the chat log and user list for a chatroom and display them on screen when user selects a chatroom
vii.	Allow the user to send text messages to the chatroom
viii.	Receive messages from the server and asynchronously update the chat log displayed on screen to show the new messages
ix.	Allow the user to send text messages to other users in the chatroom by selecting them from the user list (DirectMessage)
x.	Display a system notification when:
1.	A user joins the chat room
2.	A user leaves the chat room
3.	The user receives a direct message
xi.	Allow the user to leave the chatroom and display the list of available chatrooms to join another
xii.	Allow the user to log out and exit the application, closing the server connection

b.	Server
i.	Allow connections from clients over a network
ii.	Maintain client connections until the client closes the connection
iii.	Connect to a database on the local system
iv.	Allow connected clients to create new accounts
v.	Allow connected clients to log in to existing accounts
vi.	Send list of available chatrooms to clients on request from client
vii.	Manage users in each chatroom, adding and removing as needed based on client connection status
viii.	Broadcast messages from users in chatrooms to all other users in the same chatroom
ix.	Maintain a chat log for each chatroom, stored in the database
x.	Allow system administrator to create and delete chatrooms via a command line interface

c.	Database
i.	Store user account information – username, password
ii.	Store chatroom message history for each chatroom

4.	Non-functional requirements

a.	Platform and technology to be used
i.	All code will be written in Java without relying on system-dependent calls in order to keep the application usable on all platforms that support a modern version of the Java Runtime Environment.
ii.	Server component will require a local database that the server interacts with using the JDBC interface. Therefore, the database system must support JDBC.

b.	System-wide requirements
i.	Usernames must be unique

c.	Client
i.	Client should handle network errors (inability to connect to server, loss of connection, etc) without crashing
d.	Server
i.	Server should handle network errors without crashing
e.	Database
i.	Passwords must be encrypted
ii.	When a chatroom is deleted from the server, the chatroom message history must be deleted from the database
