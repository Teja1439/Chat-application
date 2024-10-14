# Chat Application with Flask, SocketIO, and User Authentication

This project is a real-time chat application built using **Flask**, **SocketIO**, and **Flask-Login** for user authentication. The application allows users to register, log in, and participate in a real-time chat room where messages are exchanged and stored in a database.

## Features

- **User Registration**: Users can create an account by registering with a username and password.
- **User Authentication**: Secure login and logout functionality using hashed passwords.
- **Real-time Messaging**: Users can send and receive messages in real time using SocketIO.
- **Message Persistence**: Messages are stored in an SQLite database for each chat room.
- **User Sessions**: Flask-Login manages user sessions, ensuring only authenticated users can participate in the chat.
- **Database Management**: SQLite database is used to store user credentials and chat messages.

## Technologies Used

- **Flask**: Python web framework used for routing and handling HTTP requests.
- **Flask-Login**: For user session management and authentication.
- **SocketIO**: For real-time bidirectional communication between clients and server.
- **SQLite**: Lightweight database for storing users and chat messages.
- **Werkzeug**: For password hashing and security.

## Prerequisites

- Python 3.x
- Flask and necessary libraries: Install dependencies using the following command:
  ```bash
  pip install Flask Flask-SocketIO Flask-Login Werkzeug
  ```

## Project Setup

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your_username/chat-app-flask.git
   cd chat-app-flask
   ```

2. **Install Dependencies**:
   Make sure Flask, SocketIO, and the necessary libraries are installed:
   ```bash
   pip install Flask Flask-SocketIO Flask-Login Werkzeug
   ```

3. **Initialize the Database**:
   The SQLite database will be created automatically when the application is run. If you'd like to reset the database, you can delete the `chat.db` file and rerun the app to reinitialize the database.

4. **Run the Application**:
   Start the Flask application with SocketIO:
   ```bash
   python app.py
   ```
   The app will be accessible at `http://localhost:5001/`.

## Database Structure

- **Users Table**:  
  - `id`: User ID (Primary Key)
  - `username`: Username of the user
  - `password`: Hashed password of the user
  
- **Messages Table**:  
  - `id`: Message ID (Primary Key)
  - `room`: Chat room where the message was sent
  - `username`: Username of the sender
  - `message`: The content of the message

## Usage

1. **Register**: Create a new user account by providing a unique username and password.
2. **Login**: Use your registered credentials to log in.
3. **Chat**: After logging in, you can access the chat room and start sending messages. All messages are broadcasted in real-time to all connected users.
4. **Logout**: You can log out using the logout option in the chat interface.

## SocketIO Events

- `send_message`: Triggered when a user sends a message. The message is broadcasted to all users in the room and stored in the database.
- `receive_message`: Broadcasts received messages to all connected users.
