# Etesian Anemometer LoRaWAN Bridge

**A BLE-to-LoRaWAN bridge solution enabling remote wind monitoring on the Senet Network.**

> **Project Context:** This project serves as a reference implementation for bridging disparate wireless protocols (BLE & LoRaWAN). It features a complete **[Application Note (PDF)](docs/Etesian%20anemometer%20with%20Senet.pdf)**, authored to demonstrate comprehensive technical documentation standards for end-users.

## Project Overview

This project utilizes the **Laird RM1xx module** (SmartBASIC) as the end-device and the **Laird RG1xx** as the LoRaWAN gateway to bridge wind data from BLE to LoRaWAN. The system scans for environmental data (wind speed and temperature) from a battery-powered **Etesian Anemometer** via Bluetooth Low Energy (BLE) and transmits it to the Senet LoRaWAN network for visualization on the **Cayenne IoT Dashboard**.

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
