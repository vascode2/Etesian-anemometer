# Etesian Anemometer LoRaWAN Bridge

**A BLE-to-LoRaWAN bridge solution enabling remote wind monitoring on the Senet Network.**

> **Project Context:** This project serves as a reference implementation for bridging disparate wireless protocols (BLE & LoRaWAN). It features a complete **[Application Note (PDF)](docs/Etesian%20anemometer%20with%20Senet.pdf)**, authored to demonstrate comprehensive technical documentation standards for end-users.

## Project Overview

This project utilizes the **Laird RM1xx module** (SmartBASIC) to act as a central gateway. It scans for environmental data from a battery-powered **Etesian Anemometer** via Bluetooth Low Energy (BLE) and bridges that data to a LoRaWAN network (Senet) for visualization on the **Cayenne IoT Dashboard**.

### Key Features
* **Protocol Bridging:** Seamlessly converts BLE advertising packets into LoRaWAN payloads.
* **Power Optimization:** Uses the Cayenne Low Power Payload (LPP) format to minimize airtime.
* **Visualization:** Integration with Senet and Cayenne for real-time dashboards of Wind Speed, Direction, and Temperature.

## System Architecture

```mermaid
graph TD
    A[Etesian Anemometer] -- BLE Advertising --> B[Laird RM1xx Bridge]
    B -- LoRaWAN Uplink --> C[LoRa Gateway RG1xx]
    C -- Internet/IP --> D[Senet Network]
    D -- Integration --> E[Cayenne Dashboard]
