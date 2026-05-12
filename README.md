# 🤖 PLC Refrigerator Control System + Robot Integration

<div align="center">

[![Live Demo](https://img.shields.io/badge/▶_Live_Demo-00C7B7?style=for-the-badge)](https://sazzadmahfuz.github.io/plc-control-system)
[![TwinCAT 3](https://img.shields.io/badge/TwinCAT_3-00599C?style=for-the-badge)](.)
[![Beckhoff](https://img.shields.io/badge/Beckhoff-EtherCAT-orange?style=for-the-badge)](.)
[![Structured Text](https://img.shields.io/badge/IEC61131--3-Structured_Text-blue?style=for-the-badge)](.)
[![MG400](https://img.shields.io/badge/Dobot-MG400-red?style=for-the-badge)](.)
[![Course](https://img.shields.io/badge/HAMK-Control_Systems-003087?style=for-the-badge)](.)

> **Project for Industrial Automation & Control Systems — HAMK University of Applied Sciences**  
> Real hardware industrial automation project using Beckhoff EtherCAT PLC modules, TwinCAT 3, Structured Text, LM35 analog temperature sensing, and Dobot MG400 robotic arm integration with PLC state machine control.

</div>

---

## 📸 Demo

```text
┌──────────────────────────────────────────────────────────────────────┐
│  PLC CONTROL SYSTEM                     ● TwinCAT Runtime Active    │
├──────────────────────────────────────────────────────────────────────┤
│  Temperature: 7.8°C                                            🟢  │
│  Setpoint:    8.0°C                                            🟢  │
│  Compressor:  ON                                               🟢  │
│  Alarm:       OFF                                              ⚪  │
├──────────────────────────────────────────────────────────────────────┤
│  Robot Integration                                               │
│                                                                  │
│  PLC Command  ───────────────►  MG400 DI8                        │
│  Robot Ack   ◄───────────────  MG400 DO8                         │
│                                                                  │
│  Position 1 → Cooling Tank → Position 3                          │
├──────────────────────────────────────────────────────────────────────┤
│  State Machine                                                    │
│                                                                  │
│  Idle → MoveToP2 → Cooling → MoveToP3 → Done                     │
│                                                                  │
│  Fault timeout handling enabled                                  │
├──────────────────────────────────────────────────────────────────────┤
│  EtherCAT Devices                                                 │
│                                                                  │
│  EL1008  Digital Inputs                                          │
│  EL2008  Digital Outputs                                         │
│  EL3074  Analog Input (LM35 Sensor)                              │
└──────────────────────────────────────────────────────────────────────┘
```

---

## ✨ Features

| Feature | Description |
|---|---|
| **TwinCAT PLC Control** | Industrial PLC programming using Structured Text (IEC 61131-3) |
| **Real Hardware Integration** | Beckhoff EtherCAT terminals connected to physical I/O |
| **LM35 Temperature Monitoring** | Analog temperature sensor with real-time acquisition |
| **Compressor Automation** | Automatic cooling logic based on setpoint control |
| **Alarm System** | Door-open alarm with reset functionality |
| **Robot–PLC Handshake** | Digital communication between PLC and Dobot MG400 |
| **Industrial State Machine** | Sequential process automation architecture |
| **Fault Handling** | Timeout monitoring and fault reset logic |
| **TwinCAT VISU** | Human–Machine Interface for monitoring and debugging |
| **Real-Time Monitoring** | Sensor values, outputs, and process states updated live |

---

## 🧠 Industrial Automation Concepts Demonstrated

### What This Project Simulates

This project simulates a real industrial cooling and handling process commonly used in:
- manufacturing automation
- metal quenching systems
- refrigeration processes
- robotic handling stations
- industrial production lines

The system combines:
- PLC supervision
- robot movement
- temperature monitoring
- sequential process control
- industrial networking

---

## 👤 Author

**Sazzad Ibna Mahfuz** — BEng ICT & Robotics, HAMK  
Industrial Automation · PLC Programming · Robotics

[Portfolio](https://sazzadmahfuz.github.io) · [LinkedIn](https://www.linkedin.com/in/sazzad-mahfuz) · [GitHub](https://github.com/sazzadmahfuz)
