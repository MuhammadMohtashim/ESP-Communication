# ESP32 Mesh Network with Dynamic Encryption

## Overview

This project demonstrates a decentralized Wi‑Fi mesh network using ESP32 boards and the [painlessMesh](https://github.com/gmag11/painlessMesh) library. In this system, multiple ESP32 nodes (e.g., "Alpha", "Bravo", "Charlie") communicate directly with each other without requiring a traditional router. Each message is dynamically encrypted using one of three algorithms (XOR, Caesar, or Vigenère) with a corresponding identifier so that the receiving node can correctly decrypt the content. Users can also send custom messages via the Serial terminal, making this a versatile platform for secure, ad hoc communication.

## Technical Details

- **Hardware:**
  - ESP32 development boards
  - USB cables and standard programming setup

- **Networking:**
  - **Mesh Networking:** Utilizes the painlessMesh library to form a router-less mesh network in AP/STA mode.
  - **Mesh Credentials:** All nodes share the same `MESH_PREFIX`, `MESH_PASSWORD`, and `MESH_PORT` to join the same network.

- **Encryption Algorithms:**
  1. **XOR Cipher:** A simple symmetric cipher using a shared key.
  2. **Caesar Cipher:** A basic substitution cipher with a fixed shift (e.g., 3).
  3. **Vigenère Cipher:** A polyalphabetic cipher that uses a repeating key (e.g., "VIGENERE").

- **Encryption Identifier:**  
  Each outgoing message is prepended with an identifier (`"1:"`, `"2:"`, or `"3:"`) corresponding to the encryption method used, enabling the receiver to apply the correct decryption.

- **Custom Message Support:**  
  Users can input custom messages via the Serial terminal, which are then encrypted using a randomly selected algorithm and broadcast to all mesh nodes.

- **Development Environment:**
  - Arduino IDE with ESP32 board support
  - [painlessMesh library](https://github.com/gmag11/painlessMesh)

## Features

- **Decentralized Mesh Networking:** Communicate directly between ESP32 nodes without a router.
- **Dynamic Encryption:** Random selection of encryption algorithms for each message to enhance security and demonstrate cryptographic techniques.
- **Unique Node Identification:** Each node has a unique identifier incorporated into every message.
- **Custom Messaging:** Real-time, interactive communication via the Serial terminal.
- **Scalable Design:** Easily expandable to more nodes with minimal changes to network credentials and configuration.

## Applications

- **IoT Communication:** Secure data exchange in IoT deployments without relying on centralized infrastructure.
- **Ad Hoc Networks:** Ideal for temporary networks in events, disaster recovery, or remote field operations.
- **Educational Tool:** Demonstrates concepts in mesh networking, encryption, and embedded systems.
- **Prototyping:** Serves as a foundation for developing more robust and secure communication systems for industrial or military applications (with further enhancements).

## Setup Instructions

1. **Prerequisites:**
   - ESP32 development boards.
   - Arduino IDE with the latest ESP32 board support.
   - Install the [painlessMesh library](https://github.com/gmag11/painlessMesh) via the Arduino Library Manager.

2. **Hardware Setup:**
   - Connect each ESP32 board to your computer using a USB cable.
   - Ensure that all devices are powered and within Wi‑Fi range for mesh networking.

3. **Software Configuration:**
   - Open the provided sketch in the Arduino IDE.
   - Change the `DEVICE_NAME` variable on each ESP32 to unique names (e.g., "Alpha", "Bravo", "Charlie").
   - Confirm that `MESH_PREFIX`, `MESH_PASSWORD`, and `MESH_PORT` are identical across all nodes.
   - Upload the sketch to each board.

4. **Operation:**
   - Open the Serial Monitor on each device (baud rate 115200) to view initialization and debug messages.
   - Type custom messages in the Serial Monitor and press enter to broadcast them across the mesh network.

## Future Upgrades

- **Enhanced Encryption:**  
  Integrate robust encryption algorithms (e.g., AES) for higher security in production environments.

- **Unicast Messaging:**  
  Implement targeted messaging for one-to-one communication instead of relying solely on broadcast.

- **Mobile or Web Interface:**  
  Develop an interface for monitoring and controlling the mesh network remotely.

- **Scalability Improvements:**  
  Optimize the mesh network to support more nodes and higher message throughput.

- **Advanced Routing Protocols:**  
  Enhance the network with intelligent routing and automated node discovery to improve reliability and performance.

- **Error Handling and Reliability:**  
  Add mechanisms such as acknowledgments and retries to ensure message delivery in challenging environments.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details

## Acknowledgments

- [painlessMesh](https://github.com/gmag11/painlessMesh) for the excellent mesh networking library.
- The ESP32 community for continuous innovation and support.

---
