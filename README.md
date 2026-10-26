# codesys-sorting-station-plc
Automated sorting station developed in CODESYS using Ladder Diagram (LD) and integrated HMI.

## Overview
This repository contains the automation logic and HMI implementation for an **Automated Sorting Station**, developed entirely within the **CODESYS V3.5** environment using **Ladder Diagram (LD)** 

The project focuses on a standalone PLC and HMI architecture, managing a conveyor belt system, sensor-based material detection, pneumatic actuators for sorting, and real-time production tracking.

---

## Control Logic & Key Features
The PLC program implemented within `PLC_PRG` and global variable lists (`GVL`) handles the following core functionalities:
- **System Management & Safety:** Start, Stop, Emergency Stop, and Reset routines, alongside system status flags (`GVL_System_Run`, `GVL_System_Alarm`, `GVL_Green_Light`).
- **Conveyor & Trigger Control:** Management of the conveyor motor and rising edge detection (`R_TRIG`) linked to the presence sensor (`Trig_Presence`).
- **Material Classification:** Evaluation of piece characteristics using inductive and height sensors (`GVL_Sensor_Inductive`, `GVL_Sensor_Height`) to assign a specific type code (`Piece_Type`).
- **Pneumatic Sorting Actuation:** Precise timing configurations (`TON` blocks) to control sorting mechanisms via dedicated pistons (`GVL_Piston_Metal`, `GVL_Piston_Plastic_Large`, `GVL_Piston_Plastic_Small`).
- **Production Counting:** Up-counters (`CTU`) tracking processed parts per category and total volume (`Counter_Metal`, `Counter_Plastic_Large`, `Counter_Plastic_Small`, `Counter_Total`).

---

## System Architecture
- **PLC Environment:** CODESYS V3.5
- **Programming Language:** Ladder Diagram (LD) - IEC 61131-3
- **HMI:** Integrated CODESYS Visualization for local operator control and monitoring.
