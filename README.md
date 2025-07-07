# Modbus Protocol Overview

## 📘 What is Modbus?

**Modbus** is an open, serial communication protocol developed by Modicon (now Schneider Electric) in 1979. It is widely used in industrial automation systems to enable communication between **electronic devices** such as PLCs, HMIs, sensors, and drives.

---

## 🧭 Key Features

- **Master/Slave (Client/Server)** architecture
- Simple, lightweight, and widely supported
- Can operate over serial (RS-232, RS-485) or TCP/IP (Ethernet)
- Ideal for real-time communication in automation and control

---

## 🧱 Protocol Types

| Type        | Transport Layer | Description                            |
|-------------|------------------|----------------------------------------|
| Modbus RTU  | Serial (RS-485)   | Binary format, compact, CRC error check |
| Modbus ASCII| Serial (RS-232)   | ASCII encoded, easy to debug, slower   |
| Modbus TCP  | Ethernet          | Encapsulated in TCP/IP, fast and modern|

---

## 🕹️ Master-Slave (Client-Server) Model

- The **Master (Client)** initiates queries
- The **Slave (Server)** devices respond with data or actions

> Only the Master can initiate communication. Slaves never talk unless spoken to.

---

## 📦 Modbus Data Model

Modbus works with different **data types**, identified by function codes:

| Data Type           | Function Code | Access     | Description                      |
|---------------------|---------------|------------|----------------------------------|
| Coils               | 0x01, 0x05    | Read/Write | Single-bit outputs               |
| Discrete Inputs     | 0x02          | Read-only  | Single-bit inputs (sensors)      |
| Holding Registers   | 0x03, 0x06    | Read/Write | 16-bit general-purpose registers |
| Input Registers     | 0x04          | Read-only  | 16-bit sensor or input data      |

---

## 🧾 Example Modbus RTU Request

To read 2 holding registers starting at address 40001:

Request (hex):
01 03 00 00 00 02 CRC1 CRC2

Explanation:
01 → Slave ID
03 → Function code (Read Holding Registers)
00 00 → Start address
00 02 → Number of registers
CRC1 CRC2 → Error check (Cyclic Redundancy Check)



---

## 💡 Use Cases

- Reading temperature from a sensor
- Setting a motor speed on a drive
- Monitoring power meters or relays
- PLC to PLC communication

---

## 📚 Libraries & Tools

- **Python**: `pymodbus`, `minimalmodbus`
- **C/C++**: libmodbus
- **Node.js**: jsmodbus
- **Testing Tools**: ModScan, ModSim, QModMaster

---

## 🔒 Security Notice

Modbus does **not** include built-in encryption or authentication. Use with caution over unsecured networks or consider using Modbus over a secure VPN or with industrial firewalls.

---

## 📎 Resources

- [Official Modbus Specification](https://modbus.org/specs.php)
- [Modbus TCP Guide (PDF)](https://www.modbus.org/docs/Modbus_Messaging_Implementation_Guide_V1_0b.pdf)

---

## 🤝 License

This project uses Modbus concepts and is intended for educational or industrial integration purposes. Respect manufacturer protocols and licenses.



