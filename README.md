# Smart Home Automation System (ESP32 + BLE Mesh)

An IoT-based smart home automation system developed using ESP32 and the ESP-IDF framework. It uses a Bluetooth Low Energy (BLE) Mesh network to connect three device nodes: a Light Sensor, a Switch, and a Gateway. The system monitors ambient light levels and automatically controls a connected lamp through a relay based on predefined light thresholds.

Integrates BLE Mesh networking, Wi-Fi connectivity, and a web-based interface to provide wireless communication and remote device control. Users can also provision and configure network devices using the nRF Mesh mobile application.

![framework](https://img.shields.io/badge/framework-ESP--IDF-red) ![platform](https://img.shields.io/badge/platform-ESP32-blue) ![network](https://img.shields.io/badge/network-BLE%20Mesh-0082FC) ![protocol](https://img.shields.io/badge/protocol-Bluetooth%20LE-660066) ![connectivity](https://img.shields.io/badge/connectivity-Wi--Fi-green) ![control](https://img.shields.io/badge/control-Web%20Interface-orange) ![hardware](https://img.shields.io/badge/hardware-TSL2561%20%7C%20Relay-brightgreen)

---

## Features

- BLE Mesh wireless communication between three ESP32 nodes.
- Ambient light monitoring using the TSL2561 light sensor.
- Automatic light detection based on a predefined threshold.
- Relay-based lamp switching.
- Manual ON/OFF control through a web interface.
- Wi-Fi connectivity through the Gateway node.
- LED indicators during BLE Mesh provisioning.
- Device provisioning and configuration using the nRF Mesh application.
- Generic OnOff server and client model implementation.

## Hardware Components

- ESP32 Development Boards (3 units)
- TSL2561 Light Sensor
- Relay Module
- LEDs (3 units)
- Breadboard and Jumper Wires
- Lamp (optional for relay demonstration)

## Device Nodes

| Node | Function |
|---|---|
| Light Sensor | Measures ambient light and broadcasts light status through BLE Mesh. |
| Switch | Receives BLE Mesh commands and controls the connected relay. |
| Gateway | Connects to Wi-Fi and provides a web interface for manual switch control. |

## Technologies Used

- ESP32 and ESP-IDF
- C Programming Language
- Visual Studio Code and PlatformIO
- Bluetooth Low Energy (BLE) Mesh
- Wi-Fi
- HTTP Web Server
- Generic OnOff Model
- nRF Mesh Mobile Application

## System Communication

```text
       Light Sensor Node
          (TSL2561)
              |
              | BLE Mesh
              |
              v
         Switch Node
           (Relay)
              ^
              |
              | BLE Mesh
              |
         Gateway Node
           (ESP32)
              |
              | Wi-Fi
              |
         Web Interface
```

## BLE Mesh Configuration

The system uses the following BLE Mesh models:

| Model | Purpose |
|---|---|
| Configuration Server | Handles device provisioning and network configuration. |
| Health Server | Provides device health reporting and LED attention indicators. |
| Generic OnOff Server | Publishes device state changes and receives ON/OFF commands. |
| Generic OnOff Client | Sends or receives state changes through the BLE Mesh network. |

## Installation and Setup

Clone the repository:

```bash
git clone YOUR_REPOSITORY_URL
cd YOUR_PROJECT_FOLDER
```

Open the project in Visual Studio Code with PlatformIO and ESP-IDF installed.

Configure the development environment and Wi-Fi credentials for the Gateway node. Ensure that the required BLE Mesh configurations and dependencies are included.

Build and upload the firmware for each ESP32 node:

```bash
pio run
pio run -t upload
```

Monitor the ESP32:

```bash
pio device monitor
```

Install the **nRF Mesh** mobile application to provision and configure the three ESP32 nodes. Bind the appropriate application keys to the Generic OnOff models and configure the Light Sensor publication settings.

Connect the Gateway to the local Wi-Fi network and access its web interface using its assigned IP address.

## Testing

The system can be tested through the following scenarios:

1. Send an ON command through the Gateway web interface and verify that the relay activates.
2. Send an OFF command and verify that the relay deactivates.
3. Reduce the ambient light level below the configured threshold and verify that the switch turns the lamp ON.
4. Increase the ambient light level above the threshold and verify that the switch turns the lamp OFF.

## Authors

**Kent Jesser Neri**

**Alwyn Jade Reuyan**

**JC Ree Redelosa**

**Project:** Smart Home Automation System

---

*Academic Laboratory Project — IoT and Embedded Systems*
