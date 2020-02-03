# chat-thing

## Abstract

This is a school project for CS401 - Software Engineering. This project will be a simple chat room / messaging system using a client-server model. The project will allow users on the client side to create an account, join a chat room, and send messages in that chat room. The server will maintain each chat room and forward messages from clients in a chat room to all other clients in the same chat room. The server will use a database to maintain user accounts, chat rooms, and chat room message histories. The client application will present controls to create an account, log in, select a chat room, view the chat room's message history, and send messages.This chat would make a smoother communication for people. Broadcast general notifications, such as user logins and logouts. Also, be able to send private messages between two users.

## Requirements

The project will consist of three major components: client, server, and database. The requirements for each component are as follows:

### Client
- Connect to the server over a network
- Allow the user to create new accounts
- Allow the user to log in with an existing account
- On successful login, allow the user to select a chat room to join
- Display the chat log and connected users
- Have a text input for the user to send messages to the chat room
- Allow the user to send direct messages to other users in the chat room
- Display some sort of notification when..
  - A user joins the chat room
  - A user leaves the chat room
  - The user receives a direct message
  
### Server
- Connect to clients over a network
- Connect to a database on the local system
- Allow connected clients to create new accounts
  - Ensure that accounts have unique usernames
  - Encrypt passwords so they aren't stored in plain text
- Allow connected clients to log in to existing accounts
  - Validate credentials against user account database
- On successful login, send list of existing chat rooms to clients
- Allow clients to join a chat room from the list of existing chat rooms
- Maintain list of connected users in each chat room
- Forward messages from clients to all other users in the same chat room
- Maintain a chat log for each chat room
- Forward direct messages between two users

### Database
- Maintain a table of user accounts with unique usernames and encrypted passwords
- Maintain a chat log for each chat room
- Only communicates with the server, never directly with the client

## High-level diagram
![High-level diagram](https://raw.githubusercontent.com/boylebryce/chat-thing/master/high%20level%20diagram.png)

## UML diagram
![UML diagram](https://raw.githubusercontent.com/boylebryce/chat-thing/master/uml%20diagram.png)
