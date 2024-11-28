# OSI Network Stack Implementation

This is my own implementation of the OSI Network Stack. The whole process of developing the OSI model will be documented, and the link will be provided here: [Documentation](https://github.com/bok1c4)

---

## OSI Layer Breakdown

The OSI model has 7 layers, and when you create a simple network stack, you will simulate or implement features corresponding to these layers.

### Layer 1: Physical Layer (Data Transmission)

**Features:**

- Although the physical layer typically deals with hardware and signal transmission, we will simulate this layer by dealing with basic transmission and reception of raw bits.
- For simplicity, this might involve sending and receiving data as a byte stream or byte array.

### Layer 2: Data Link Layer (Framing and Error Control)

**Features:**

- Frame creation: Encapsulates data into frames.
- Error detection: Implement basic error detection like checksums (e.g., CRC or parity).
- Addressing: Add MAC addresses to the frames, simulating Ethernet frames.
- Flow control: Implement basic mechanisms for controlling data flow (optional, depending on complexity).

### Layer 3: Network Layer (Routing and Logical Addressing)

**Features:**

- Packet creation: Encapsulates data into packets, including source and destination IP addresses.
- Routing: Implement a basic routing mechanism (e.g., direct routing or simulated routing tables).
- Fragmentation: Implements fragmentation of packets into smaller units (if needed).
- Addressing: Use IP addresses for identifying source and destination devices in the network.
- Optional: Implement basic ICMP for sending error messages and diagnostic tools (e.g., "ping").

### Layer 4: Transport Layer (End-to-End Communication)

**Features:**

- Segmentation: Breaking down data into smaller segments for transmission.
- Flow control: Implementing basic flow control like sliding window or stop-and-wait.
- Error correction: Implementing error detection and retransmission (e.g., checksum validation and retries).
- Protocols: Implement either a basic version of TCP (connection-oriented) or UDP (connectionless).
- Sequence numbering: Sequence packets for proper data reconstruction on the receiving side.

### Layer 5: Session Layer (Session Management and Communication Control)

**Features:**

- Session establishment and termination: Simulate the process of setting up and tearing down a session between two devices.
- Session management: Handle multiple communication sessions.
- Keep track of connection state between source and destination (e.g., opening/closing a "conversation").

### Layer 6: Presentation Layer (Data Translation)

**Features:**

- Data encoding/decoding: Implement basic encoding/decoding for the data you are transmitting (e.g., ASCII to binary).
- Data compression (optional): Implement simple compression algorithms to reduce packet size.
- Encryption/Decryption (optional): Apply basic encryption or decryption for data security.

### Layer 7: Application Layer (User Interface)

**Features:**

- Create a simple application protocol (e.g., a text-based application like HTTP, FTP, or a custom protocol).
- Send/receive data using a custom application layer protocol.
- Display network communications in a human-readable format (like a log or console output).

---

## Additional Key Features for the Simple Network Stack

### Packet Creation and Parsing

- Implement packet creation and parsing for each layer. Each layer should encapsulate data from the layer above it (e.g., the transport layer encapsulates data into network packets).
- The data from each layer should be correctly handled and passed down to the next lower layer for further processing.

### Socket-like Interface

- Simulate a socket interface for sending and receiving data through the stack. You can create functions like `send(data)` and `receive()` that invoke the appropriate network stack layer to process data.

### Basic Error Handling and Debugging

- Implement simple error handling, such as retries, checksum validation, and packet loss detection. Log errors and packet information for debugging purposes.

### Basic Routing Mechanism (if applicable)

- If you're implementing the network layer, create a simple routing table and implement a direct routing algorithm for forwarding packets to the correct destination. This can be done using static routes or a simplified routing algorithm (e.g., distance-vector routing).

### Multithreading/Concurrency (optional)

- For more advanced projects, implement concurrency to allow simultaneous sending and receiving of data on different layers or connections. Use multithreading to handle multiple client/server communications.

### Simulation of Network Devices

- For educational purposes, simulate multiple network devices (e.g., computers or routers) and show how data travels through the network stack from one device to another.
- You can also simulate simple LANs or larger network topologies and demonstrate how data moves across the stack.

---

## Optional Advanced Features (for deeper complexity)

### Implement a Routing Protocol

- If you're interested in diving deeper, implement a simple routing protocol like RIP or OSPF for automatic route discovery and updating.

### Connection Management (TCP-like)

- If implementing TCP, simulate a three-way handshake and manage connection states (SYN, ACK, FIN, etc.).
- Add a sliding window for flow control and retransmissions for lost packets.

### IP Fragmentation

- Implement fragmentation in the network layer to handle large packets and split them into smaller fragments that can be reassembled at the destination.

### Advanced Error Handling

- Implement more sophisticated error handling strategies, such as timeout-based retransmissions, ARQ (Automatic Repeat reQuest), or selective acknowledgments.

---

## Final Project Breakdown (for Clarity)

### Layer 1 - Physical Layer

- Simulate raw bit transmission between devices.

### Layer 2 - Data Link Layer

- Implement frame creation with error detection (CRC, parity).
- Add MAC addressing and simulate a local network.

### Layer 3 - Network Layer

- Create packets with IP headers and routing capabilities.
- Implement packet forwarding based on destination IP.

### Layer 4 - Transport Layer

- Implement segmentation and sequencing of data for reliable communication (e.g., a basic TCP-like protocol).
- Handle flow control and error recovery.

### Layer 5 - Session Layer

- Establish and manage communication sessions between two devices.
- Simulate opening and closing of connections.

### Layer 6 - Presentation Layer

- Implement basic encoding/decoding for data transmission (e.g., converting data to a different format).
- Optionally, handle encryption/decryption of transmitted data.

### Layer 7 - Application Layer

- Design a simple application protocol, such as a basic HTTP-like request/response system.
- Send and receive data using this protocol, displaying messages to the user.

---

## Summary of Features to Build

- Basic packet creation, parsing, and routing.
- Framing and error detection (Data Link Layer).
- Segmentation and flow control (Transport Layer).
- Session management and basic application protocols.
- Optional features like encryption or routing protocols for complexity.
