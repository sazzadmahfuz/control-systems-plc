# 🤖 PLC Refrigerator Control System + Robot Integration

<div align="center">

[![Live Demo](https://img.shields.io/badge/▶_Live_Demo-00C7B7?style=for-the-badge)](https://sazzadmahfuz.github.io/control-systems-plc)
[![TwinCAT 3](https://img.shields.io/badge/TwinCAT_3-00599C?style=for-the-badge)](.)
[![Beckhoff](https://img.shields.io/badge/Beckhoff-EtherCAT-orange?style=for-the-badge)](.)
[![Structured Text](https://img.shields.io/badge/IEC61131--3-Structured_Text-blue?style=for-the-badge)](.)
[![MG400](https://img.shields.io/badge/Dobot-MG400-red?style=for-the-badge)](.)
[![Course](https://img.shields.io/badge/HAMK-Control_Systems-003087?style=for-the-badge)](.)

> **Project for Industrial Automation & Control Systems — HAMK University of Applied Sciences**  
> Real industrial automation project using Beckhoff EtherCAT PLC modules, TwinCAT 3, Structured Text programming, LM35 analog temperature sensing, and Dobot MG400 robot integration.

</div>

---

# 📸 Project Gallery

<div align="center">

| Hardware Setup | TwinCAT Configuration |
|---|---|
| <img src="https://raw.githubusercontent.com/sazzadmahfuz/control-systems-plc/main/Pictures/1%20(1).jpeg" width="420"> | <img src="https://raw.githubusercontent.com/sazzadmahfuz/control-systems-plc/main/Pictures/1%20(1).png" width="420"> |

| PLC Program | Robot Integration |
|---|---|
| <img src="https://raw.githubusercontent.com/sazzadmahfuz/control-systems-plc/main/Pictures/1%20(2).jpeg" width="420"> | <img src="https://raw.githubusercontent.com/sazzadmahfuz/control-systems-plc/main/Pictures/1%20(2).png" width="420"> |

| Temperature Monitoring | System Overview |
|---|---|
| <img src="https://raw.githubusercontent.com/sazzadmahfuz/control-systems-plc/main/Pictures/1%20(3).jpeg" width="420"> | <img src="https://raw.githubusercontent.com/sazzadmahfuz/control-systems-plc/main/Pictures/1%20(4).jpeg" width="420"> |

</div>

---

# ✨ Features

| Feature | Description |
|---|---|
| **TwinCAT PLC Control** | Industrial PLC programming using Structured Text (IEC 61131-3) |
| **Real Hardware Integration** | Beckhoff EtherCAT terminals connected to physical I/O |
| **LM35 Temperature Monitoring** | Analog temperature sensor with real-time acquisition |
| **Compressor Automation** | Automatic cooling logic based on temperature setpoint |
| **Alarm System** | Door-open alarm with reset functionality |
| **Robot–PLC Handshake** | Digital communication between PLC and Dobot MG400 |
| **Industrial State Machine** | Sequential process automation architecture |
| **Fault Handling** | Timeout monitoring and fault reset logic |
| **TwinCAT VISU** | Human–Machine Interface for monitoring and debugging |
| **Real-Time Monitoring** | Sensor values and outputs updated live |

---

# 🧠 System Architecture

```text
[Industrial IPC]
        │
   EtherCAT Bus
        │
 ┌───────────────┐
 │ Beckhoff I/O  │
 └───────────────┘
        │
 ├── EL1008  → Digital Inputs
 ├── EL2008  → Digital Outputs
 ├── EL3074  → Analog Inputs
 │
 ├── LM35 Temperature Sensor
 ├── LEDs & Push Buttons
 │
 └── Dobot MG400 Robot
```

---

# 🔄 PLC ↔ Robot Communication

```text
PLC DO4  ─────→  MG400 DI8
MG400 DO8 ────→  PLC DI8
```

### Process Sequence

```text
1. PLC sends RobotCmd = TRUE
2. Robot moves part to cooling tank
3. Robot sends RobotAck = TRUE
4. PLC waits until cooling complete
5. PLC commands move to final position
6. Robot sends completion acknowledgement
```

---

# 🌡️ Temperature Monitoring

The project uses an **LM35 analog temperature sensor** connected through Beckhoff analog input terminals.

| Temperature | Voltage |
|---|---|
| 20°C | 0.20V |
| 25°C | 0.25V |
| 30°C | 0.30V |

The PLC continuously compares:
- actual temperature
- configured setpoint

to determine compressor operation.

---

# ⚙️ PLC State Machine

```iecst
TYPE E_ProcessState :
(
    stIdle,
    stRequestMoveToP2,
    stWaitRobotAtP2,
    stCooling,
    stRequestMoveToP3,
    stWaitRobotAtP3,
    stDone,
    stFault
);
END_TYPE
```

---

# 🛠️ Technologies Used

```text
TwinCAT 3
Structured Text (IEC 61131-3)
Beckhoff EtherCAT
PLC Programming
Industrial Automation
Robot Integration
LM35 Sensor
State Machines
Industrial Networking
Industrial HMI
```

---

# 🎓 Academic Context

**Programme:** BEng ICT & Robotics  
**University:** HAMK University of Applied Sciences  

### Topics Covered
- PLC programming
- TwinCAT 3
- EtherCAT communication
- Industrial I/O mapping
- Analog sensor integration
- Robot communication
- State machine control
- Industrial automation systems

---

# 🚀 Future Improvements

- OPC UA integration
- MQTT cloud monitoring
- SCADA dashboard
- SQL data logging
- PID temperature control
- Multi-robot synchronization

---

# 👤 Author

**Sazzad Ibna Mahfuz**  
BEng ICT & Robotics — HAMK University of Applied Sciences

[🌐 Portfolio](https://sazzadmahfuz.github.io)  
[💼 LinkedIn](https://www.linkedin.com/in/sazzad-mahfuz)  
[💻 GitHub](https://github.com/sazzadmahfuz)
