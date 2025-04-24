Casataa
Casataa is a real-time chat and file-sharing application built using Python, designed to operate over a Local Area Network (LAN). It features secure communication with AES encryption, a user-friendly GUI, and support for multiple clients. The project leverages network programming concepts like socket programming and multithreading, making it a practical demonstration of client-server architecture, transport layer protocols, and application security.
Features

Real-time text-based chat between multiple clients connected to a central server.
Secure file transfer with progress tracking.
AES encryption for all messages and files using Python's cryptography library.
User-friendly GUI built with Tkinter for an interactive chat experience.
Multi-client support through multithreading to handle concurrent connections.
Admin monitoring panel to view online users and activity logs.
Offline message queuing to store messages for users who are not currently online.

Tech Stack

Language: Python 3.8+
Networking: socket for TCP-based communication, threading for concurrency
Encryption: cryptography (Fernet for AES encryption)
GUI: tkinter for the client-side interface
File Handling: Python's built-in os module for file transfers
Optional Web Version: Flask and socket.io (for web-based deployment)

Prerequisites
Ensure you have the following installed before running the project:

Python 3.8 or higher
Required Python packages (listed in requirements.txt)

Install the dependencies by running:
pip install -r requirements.txt

Project Structure
chatra-suraksha/
│
├── server.py              # Server-side logic for handling clients, chat, and file transfers
├── client.py              # Client-side logic with GUI for chat and file sharing
├── encryptor.py           # AES encryption and decryption functions
├── requirements.txt       # List of Python dependencies
└── assets/                # Directory for GUI assets (e.g., icons, images)

Setup and Installation



Install Dependencies:
pip install -r requirements.txt


Run the Server:

Start the server on your machine (it will listen for incoming connections).

python server.py


The server defaults to localhost on port 5000. Modify the host/port in server.py if needed.


Run the Client:

On the same or a different machine within the same LAN, run the client.

python client.py


The client GUI will open. Enter the server's IP address (e.g., 192.168.1.x) and port (5000) to connect.


Usage:

Use the GUI to send messages and share files with other connected clients.
Messages and files are automatically encrypted before transmission and decrypted upon receipt.
The admin panel (accessible via the server console) shows connected users and activity logs.



How It Works

Server: Listens for client connections using TCP sockets on a specified port. Each client connection is handled in a separate thread to ensure concurrency.
Client: Connects to the server, displays a Tkinter-based GUI for chatting and file sharing, and communicates via encrypted messages.
Encryption: The encryptor.py module uses AES encryption (Fernet) to secure all messages and file transfers.
File Transfer: Files are sent as binary data over sockets, with a progress bar displayed in the GUI.
Admin Monitoring: The server logs all activity, including user connections and message/file transfers, for admin oversight.
Offline Messages: Messages for offline users are queued on the server and delivered when the user reconnects.

Example Usage

Start the server:
python server.py

The server will display: "Server started on 127.0.0.1:5000".

Launch the client on two different machines (or terminals):
python client.py


Enter the server IP (e.g., 127.0.0.1 for localhost) and port (5000).
Type a message in the text box and click "Send" to chat.
Use the "Upload File" button to select and send a file to other clients.


Observe the admin panel in the server terminal to see connected users and activity logs.


Network Configuration

LAN Usage: Ensure all devices are on the same local network (e.g., same Wi-Fi router). Use the server's local IP address (e.g., 192.168.1.x) in the client configuration.
Cross-Network (Optional): To enable usage across different networks:
Set up port forwarding on your router for the server's port (e.g., 5000).
Alternatively, use a tool like ngrok to create a public tunnel:ngrok tcp 5000

Then use the public address provided by ngrok in the client.



Limitations

Currently designed for LAN usage; internet usage requires additional configuration (e.g., port forwarding or a public server).
Offline message queuing is stored in-memory; a database integration would make it persistent.
The GUI is basic; it can be enhanced with advanced styling or a web-based interface using Flask.

Future Improvements

Add SSL/TLS for enhanced security using ssl.wrap_socket.
Implement a database (e.g., SQLite) for persistent storage of messages and user data.
Introduce Quality of Service (QoS) to prioritize message types.
Extend to a web version using Flask and WebSockets for broader accessibility.

Contributing
Contributions are welcome! To contribute:

Fork the repository.
Create a new branch for your feature or bug fix.
Submit a pull request with a description of your changes.

License
This project is licensed under the MIT License. See the LICENSE file for details.
Acknowledgments

Built as a networking project to demonstrate socket programming, encryption, and GUI development.
Inspired by real-world chat applications like Slack and Microsoft Teams.
Thanks to the Python community for providing excellent libraries like cryptography and tkinter.

Contact
For questions or feedback, reach out to sahilchaudhary975832@example.com or open an issue on GitHub.
