# Real-Time Chat Application

This is a real-time chat application built with Spring Boot and WebSockets. It allows users to communicate with each other in a public chat room.

## Features

*   **Public Chat Room:** A single chat room where all users can communicate.
*   **User Join and Leave Notifications:** Other users are notified when a user joins or leaves the chat.
*   **Real-Time Messaging:** Messages are sent and received in real-time using WebSockets.

## Technologies Used

*   **Backend:**
    *   Java 24
    *   Spring Boot 3.5.5
    *   Spring WebSocket
    *   Maven
    *   Lombok
*   **Frontend:**
    *   (Not included in this project) - A frontend needs to be created to interact with the WebSocket endpoints.

## Getting Started

### Prerequisites

*   Java 24 or higher
*   Maven

### Installation

1.  Clone the repository:
    ```sh
    git clone https://github.com/Exodus2004/chat_app-springboot.git
    ```
2.  Navigate to the project directory:
    ```sh
    cd chat_app-springboot/realtimechatapplication
    ```
3.  Build the project using Maven:
    ```sh
    mvn clean install
    ```
4.  Run the application:
    ```sh
    java -jar target/realtimechatapplication-0.0.1-SNAPSHOT.jar
    ```

The application will be running on `http://localhost:8080`.

## Usage

To use the chat application, you need a WebSocket client (e.g., a JavaScript frontend or a tool like Postman) to connect to the following endpoints:

*   **WebSocket Endpoint:** `/websocket`
*   **Application Destination Prefix:** `/app`
*   **Public Topic:** `/topic/public`

### Message Types

The application uses the following message types:

*   `JOIN`: When a user joins the chat.
*   `CHAT`: For regular chat messages.
*   `LEAVE`: When a user leaves the chat.

### Sending Messages

To send a message, you need to send a `ChatMessage` object to the `/app/chat.send` destination. The `ChatMessage` object has the following structure:

```json
{
  "content": "Hello, world!",
  "sender": "sagar",
  "type": "CHAT"
}
```

### Registering a User

To register a user, send a `ChatMessage` object to the `/app/chat.register` destination with the user's name.

```json
{
  "sender": "sagar",
  "type": "JOIN"
}
```
