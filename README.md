#            PLC Refrigerator Control System + Robot Integration

<div align="center">

[![Live Demo](https://img.shields.io/badge/▶_Live_Demo-00C7B7?style=for-the-badge)](https://sazzadmahfuz.github.io/control-systems-plc)
[![TwinCAT 3](https://img.shields.io/badge/TwinCAT_3-00599C?style=for-the-badge)](.)
[![Beckhoff](https://img.shields.io/badge/Beckhoff-EtherCAT-orange?style=for-the-badge)](.)
[![Structured Text](https://img.shields.io/badge/IEC61131--3-Structured_Text-blue?style=for-the-badge)](.)
[![MG400](https://img.shields.io/badge/Dobot-MG400-red?style=for-the-badge)](.)
[![Course](https://img.shields.io/badge/HAMK-Control_Systems-003087?style=for-the-badge)](.)

### Advanced Industrial Automation & PLC–Robot Integration System

Real industrial automation project developed using:

**TwinCAT 3 · Beckhoff EtherCAT · Structured Text · LM35 Sensors · Dobot MG400 Robot**

---

### 👨‍💻 Developed by

# Sazzad Ibna Mahfuz

Bachelor of Engineering — ICT Robotics  
Häme University of Applied Sciences (HAMK), Finland

</div>

---

#  Project Overview

This project demonstrates a complete **Industrial Control Systems and PLC Automation workflow** using real industrial hardware and robot integration technologies.

The system combines:

- Beckhoff EtherCAT I/O terminals
- TwinCAT 3 PLC programming
- Structured Text (IEC 61131-3)
- Analog temperature acquisition
- Refrigerator compressor automation
- Alarm and safety systems
- Industrial robot communication
- Dobot MG400 robot integration
- State-machine-based automation logic
- Human–Machine Interface (HMI)

The project was developed as part of the **Control Systems and Industrial Automation coursework** at:

### Häme University of Applied Sciences (HAMK)

The objective was to simulate a real industrial refrigeration and material-handling process where a robot communicates directly with a PLC system using industrial digital I/O.

---

#  Project Objectives

The main objectives of this project were:

- Understand industrial PLC programming concepts
- Learn TwinCAT 3 industrial automation development
- Configure Beckhoff EtherCAT terminals
- Integrate analog and digital industrial sensors
- Implement real-time compressor control
- Develop industrial alarm systems
- Build PLC–robot communication interfaces
- Implement sequential industrial state machines
- Understand industrial automation architecture
- Simulate real manufacturing workflows
- Develop industrial HMI monitoring systems
- Perform industrial troubleshooting and debugging

---

#  Industrial System Architecture

```text
┌────────────────────────────┐
│        Industrial PC       │
│        TwinCAT Runtime     │
└─────────────┬──────────────┘
              │
         EtherCAT Bus
              │
┌────────────────────────────┐
│      Beckhoff I/O Rack     │
├────────────────────────────┤
│ EL1008 → Digital Inputs    │
│ EL2008 → Digital Outputs   │
│ EL3074 → Analog Inputs     │
└─────────────┬──────────────┘
              │
      ┌───────┴────────┐
      │                │
┌────────────┐   ┌──────────────┐
│ LM35 Temp  │   │ Dobot MG400 │
│ Sensor     │   │ Robot Arm   │
└────────────┘   └──────────────┘
              │
      Refrigerator System
              │
      Compressor + Alarm
```

---

#  Industrial Hardware Used

| Hardware | Purpose |
|---|---|
| Beckhoff IPC | PLC Runtime Environment |
| EtherCAT Bus | Real-time industrial communication |
| EL1008 | Digital input terminal |
| EL2008 | Digital output terminal |
| EL3074 | Analog input terminal |
| LM35 Sensor | Temperature acquisition |
| LEDs & Push Buttons | Industrial input/output simulation |
| Dobot MG400 | Robot arm integration |
| TwinCAT 3 | PLC programming platform |

---

# 🔌 EtherCAT I/O Configuration

The system uses industrial Beckhoff EtherCAT terminals for real-time deterministic control.

## Digital Inputs — EL1008

Used for:

- Start button
- Stop button
- Reset button
- Door switch
- Robot acknowledgment
- Safety logic

---

## Digital Outputs — EL2008

Used for:

- Compressor control
- Alarm indicators
- Robot command signals
- Status LEDs
- Cooling process outputs

---

## Analog Inputs — EL3074

Used for:

- LM35 analog temperature sensing
- Real-time voltage acquisition
- Sensor scaling and calibration

---

#  Temperature Monitoring System

The project implements real-time refrigerator temperature monitoring using an:

# LM35 Analog Temperature Sensor

The LM35 provides a linear analog voltage proportional to temperature:

```text
10mV / °C
```

---

## Sensor Scaling

| Temperature | Output Voltage |
|---|---|
| 20°C | 0.20V |
| 25°C | 0.25V |
| 30°C | 0.30V |
| 40°C | 0.40V |

---

## PLC Temperature Conversion

The PLC continuously converts raw analog values into engineering units:

```iecst
Temperature := AnalogVoltage * 100;
```

This enables:

- Real-time monitoring
- Cooling control
- Alarm triggering
- Process supervision

---

#  Refrigerator Compressor Logic

The compressor control system uses threshold-based automation.

## Cooling Logic

```text
IF Temperature > Setpoint
    Compressor = ON
ELSE
    Compressor = OFF
```

---

## Process Behavior

| Condition | Compressor State |
|---|---|
| Temperature above setpoint | ON |
| Temperature below setpoint | OFF |
| Door open alarm active | Warning |
| Fault condition | System Halt |

---

# 🚨 Industrial Alarm System

The system includes fault detection and industrial alarm monitoring.

## Alarm Conditions

- Refrigerator door left open
- Sensor timeout
- Robot communication failure
- Cooling timeout
- Process interruption

---

## Alarm Features

✅ Alarm reset button  
✅ Visual alarm indicators  
✅ PLC fault states  
✅ Timeout supervision  
✅ Emergency stop handling

---

#  PLC ↔ Robot Integration

A major feature of the project is real industrial robot communication between:

# Beckhoff PLC ↔ Dobot MG400 Robot

The PLC communicates with the robot using industrial digital I/O signals.

---

#  Communication Architecture

```text
PLC DO4  ─────→  MG400 DI8
MG400 DO8 ────→  PLC DI8
```

---

#  Robot Handshake Logic

The PLC and robot exchange command and acknowledgment signals.

---

## Process Sequence

```text
1. PLC sends RobotCmd = TRUE
2. Robot receives move command
3. Robot moves object to cooling station
4. Robot sends RobotAck = TRUE
5. PLC activates cooling cycle
6. Cooling timer completes
7. PLC commands move to output station
8. Robot confirms completion
9. PLC returns to idle state
```

---

#  Industrial Automation Workflow

```text
System Start
     │
     ▼
Temperature Monitoring
     │
     ▼
Robot Receives Product
     │
     ▼
Move Product to Cooling Area
     │
     ▼
PLC Activates Compressor
     │
     ▼
Cooling Process
     │
     ▼
Robot Transfers Product
     │
     ▼
Process Complete
```

---

#  PLC State Machine Architecture

The automation logic was implemented using a professional industrial state machine.

---

## State Machine Definition

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

## State Descriptions

| State | Description |
|---|---|
| stIdle | Waiting for process start |
| stRequestMoveToP2 | PLC requests robot movement |
| stWaitRobotAtP2 | Wait for robot acknowledgment |
| stCooling | Refrigerator cooling active |
| stRequestMoveToP3 | Request final transfer |
| stWaitRobotAtP3 | Waiting for completion |
| stDone | Process completed |
| stFault | Fault or timeout condition |

---

#  Project Demonstration

The following screenshots demonstrate the real industrial hardware setup, TwinCAT PLC implementation, robot integration, and HMI monitoring environment.

---

<table align="center">
<tr>
<td align="center" width="50%">

<img src="https://raw.githubusercontent.com/sazzadmahfuz/control-systems-plc/main/Pictures/1%20(1).jpeg" width="95%">

### TwinCAT HMI Interface

TwinCAT 3 HMI visualization displaying refrigerator process monitoring, control states, and industrial automation interface.

</td>

<td align="center" width="50%">

<img src="https://raw.githubusercontent.com/sazzadmahfuz/control-systems-plc/main/Pictures/1%20(1).png" width="95%">

### Dobot MG400 Integration

Industrial robot integration setup demonstrating PLC-to-robot communication and automated pick-and-place workflow.

</td>
</tr>

<tr>
<td align="center" width="50%">

<img src="https://raw.githubusercontent.com/sazzadmahfuz/control-systems-plc/main/Pictures/1%20(2).jpeg" width="95%">

### Beckhoff PLC Hardware

Beckhoff EtherCAT PLC rack with industrial I/O terminals, wiring, push buttons, and control components.

</td>

<td align="center" width="50%">

<img src="https://raw.githubusercontent.com/sazzadmahfuz/control-systems-plc/main/Pictures/1%20(2).png" width="95%">

### Robot Automation Workflow

Dobot MG400 robotic handling process integrated with the industrial cooling and automation sequence.

</td>
</tr>

<tr>
<td align="center" width="50%">

<img src="https://raw.githubusercontent.com/sazzadmahfuz/control-systems-plc/main/Pictures/1%20(3).jpeg" width="95%">

### LM35 Temperature Monitoring

LM35 analog temperature sensor connected to Beckhoff analog input modules for real-time monitoring and compressor control.

</td>

<td align="center" width="50%">

<img src="https://raw.githubusercontent.com/sazzadmahfuz/control-systems-plc/main/Pictures/1%20(4).jpeg" width="95%">

### Industrial System Overview

Complete industrial automation environment combining PLC control, EtherCAT communication, sensor integration, and robotic material handling.

</td>
</tr>
</table>

---

#  Industrial HMI & Monitoring

The project includes visualization and real-time monitoring features using TwinCAT visualization tools.

---

## Monitoring Features

✅ Live temperature display  
✅ Compressor state visualization  
✅ Alarm indicators  
✅ Robot communication states  
✅ Cooling process monitoring  
✅ Digital I/O visualization  
✅ Fault condition alerts  
✅ Process status feedback

---

#  Industrial Safety & Fault Handling

Industrial automation systems require robust fault handling mechanisms.

The project implements:

- Timeout supervision
- Fault reset states
- Safe idle conditions
- Robot communication validation
- Cooling timeout protection
- Sensor validation logic

---

## Example Fault Logic

```text
IF RobotAck NOT received within timeout
    → Enter stFault
    → Stop compressor
    → Raise alarm
```

---

#  Real-Time Industrial Communication

The project uses:

# EtherCAT Industrial Communication

Benefits include:

- Deterministic real-time communication
- High-speed industrial networking
- Low latency control
- Reliable synchronization
- Industrial-grade stability

---

#  Technologies Used

| Technology | Purpose |
|---|---|
| TwinCAT 3 | PLC development |
| Structured Text | IEC 61131-3 PLC programming |
| Beckhoff EtherCAT | Industrial communication |
| LM35 Sensor | Analog temperature acquisition |
| Dobot MG400 | Industrial robot integration |
| EtherCAT Terminals | Industrial I/O |
| Industrial IPC | PLC runtime execution |
| HMI Systems | Monitoring & visualization |

---

#  Topics Covered

- PLC Programming
- TwinCAT 3
- EtherCAT Networking
- Industrial Automation
- State Machine Design
- Industrial Sensors
- Analog Signal Processing
- Robot Integration
- Digital I/O Mapping
- Industrial HMI Systems
- Sequential Automation
- Industrial Communication

---

#  Key Learning Outcomes

This project helped develop practical industrial automation skills in:

✅ PLC programming  
✅ Structured Text development  
✅ EtherCAT networking  
✅ TwinCAT engineering  
✅ Industrial robot communication  
✅ State-machine-based automation  
✅ Real-time control systems  
✅ Industrial fault handling  
✅ Analog signal processing  
✅ Industrial refrigeration automation  
✅ Human–Machine Interface systems

---

#  Future Improvements

Potential future developments include:

- OPC UA industrial networking
- MQTT cloud connectivity
- SCADA integration
- SQL database logging
- PID temperature control
- AI-based fault prediction
- Multi-robot coordination
- ROS2 integration
- Edge computing integration
- Industrial dashboard analytics
- Remote monitoring systems
- Predictive maintenance systems

---

#  Author

## Sazzad Ibna Mahfuz

Bachelor of Engineering — ICT Robotics  
Häme University of Applied Sciences (HAMK)  
Finland
[Portfolio](https://sazzadmahfuz.github.io) · [LinkedIn](https://www.linkedin.com/in/sazzad-mahfuz) · [GitHub](https://github.com/sazzadmahfuz)

---

<div align="center">

# ⭐ If you found this project interesting, consider starring the repository!

</div>
