# 🚀 SenseQuiet – A Multi-Modal Sensor Fusion Architecture for Adaptive Acoustic Environment Optimization

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Arduino-00979D?style=for-the-badge&logo=arduino&logoColor=white" alt="Arduino">
  <img src="https://img.shields.io/badge/Language-C%2FC%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" alt="C/C++">
  <img src="https://img.shields.io/badge/IoT-Embedded%20Systems-orange?style=for-the-badge" alt="Embedded Systems">
  <img src="https://img.shields.io/badge/Project-Engineering%20Proposal-purple?style=for-the-badge" alt="Engineering Project">
</p>

---

## 📌 Project Overview

**SenseQuiet** is an intelligent noise management system designed for environments such as libraries, hospitals, and study spaces.

Traditional noise monitoring systems often rely on fixed sound-level thresholds. However, the same sound level may have different meanings depending on the surrounding environment.

**SenseQuiet** aims to move beyond traditional fixed-threshold noise alarms by creating a **context-aware, adaptive system that understands its surroundings before responding.**

The proposed system combines **embedded systems, multi-sensor fusion, adaptive algorithms, and human-centered design** to create a smarter and less intrusive approach to noise management.

---

## 🎯 Project Objectives

The main objectives of SenseQuiet are to:

- Develop an adaptive noise-monitoring system.
- Automatically learn the ambient sound level of an environment.
- Combine multiple sensor inputs for better environmental understanding.
- Detect occupancy and environmental conditions.
- Reduce false alarms caused by temporary noise spikes.
- Provide context-sensitive feedback instead of intrusive alerts.
- Explore sensor-fusion techniques in embedded systems.
- Develop a practical and low-cost solution for real-world environments.

---

## 💡 Proposed System Highlights

### 🔊 Adaptive Noise Floor Calibration

SenseQuiet automatically learns the normal ambient sound level of its environment instead of relying on a fixed threshold.

The system can establish a baseline during an initial calibration period and adapt to gradual changes in background noise.

This allows the system to operate effectively in different environments.

### 🔬 Multi-Sensor Fusion

SenseQuiet combines information from a sound sensor, LDR, and PIR sensor to understand the surrounding context.

| Sensor | Purpose |
|--------|---------|
| 🔊 Sound Sensor | Detect surrounding acoustic activity |
| 💡 LDR | Detect ambient light conditions |
| 👤 PIR Sensor | Detect human presence / occupancy |

The system does not depend only on sound measurements. Multiple sensor inputs are considered before generating a response.

### 🚦 Tiered Feedback Mechanism

SenseQuiet uses different output devices to provide gradual and context-sensitive feedback.

| Output | Function |
|--------|----------|
| 🖥️ OLED Display | Display noise and system status |
| 🔴🟢🔵 RGB LED | Visual indication of current noise status |
| 🔔 Buzzer | Audible warning when required |

### ⏱️ Temporal Filtering Logic

Short-duration noise spikes should not immediately trigger an alert.

SenseQuiet considers the duration and persistence of noise before generating a warning.

**Short Noise Spike → Monitor → Noise Disappears → No Alert**

**Continuous Disturbance → Monitor Duration → Threshold Exceeded → Context-Aware Alert**

This helps reduce false alarms caused by:

- Dropped objects
- Short conversations
- Door closing
- Temporary movements
- Other brief sound events

---

## ⚙️ Proposed System Architecture

**Environment**

↓  

**Sound Sensor + LDR + PIR Sensor**

↓

**Sensor Fusion**

↓

**Environmental Context Analysis**

↓

**Adaptive Noise Floor Calibration**

↓

**Temporal Filtering & Decision Logic**

↓

**Context-Aware Response System**

↓

**OLED Display + RGB LED + Buzzer**

↓

**User Feedback**

---

## 🔄 System Workflow

### Step 1 — Environmental Sensing

The system collects data from:

- Sound sensor
- LDR
- PIR sensor

### Step 2 — Occupancy & Context Detection

The PIR sensor detects human presence, while the LDR provides information about the surrounding light conditions.

### Step 3 — Noise Floor Calibration

The system establishes an estimate of the normal ambient sound level.

### Step 4 — Continuous Monitoring

Sound levels are continuously monitored and compared with the adaptive noise baseline.

### Step 5 — Temporal Filtering

The system evaluates whether the detected noise is:

- Temporary
- Repeated
- Continuous
- Significant enough to require intervention

### Step 6 — Decision Making

The sensor information is combined to determine the appropriate response.

### Step 7 — Feedback

The system provides feedback through:

- OLED display
- RGB LED
- Buzzer

---

## 🧠 Decision-Making Concept

The proposed decision-making process follows this concept:

**Sound Level**

↓

**Compare with Adaptive Noise Floor**

↓

**Normal Noise → No Warning**

**High Noise → Check Duration**

↓

**Short Spike → Continue Monitoring**

**Continuous Disturbance → Check Environmental Context**

↓

**Generate Appropriate Alert**

This approach allows SenseQuiet to distinguish between temporary sound events and persistent disturbances.

---

## 🛠️ Proposed Tech Stack

### 🔧 Hardware

- Arduino-based microcontroller
- Sound sensor
- LDR (Light Dependent Resistor)
- PIR motion sensor
- OLED display
- RGB LED
- Buzzer
- Supporting electronic components

### 💻 Software

- C/C++ firmware
- Arduino development environment
- Adaptive calibration algorithms
- Sensor-fusion logic
- Temporal filtering
- Embedded decision-making algorithms

---

## 📊 Sensor Fusion Concept

The key idea behind SenseQuiet is that **sound should not be interpreted independently**.

For example:

**Sound Level ↑ + Person Detected + Environmental Context → Higher Confidence of Actual Disturbance**

Whereas:

**Sound Level ↑ + No Person Detected + Very Short Duration → Possible Temporary Noise → Avoid Immediate Alert**

This multi-modal approach can make the system more intelligent than a conventional single-sensor noise alarm.

---

## 🚦 Tiered Alert System

SenseQuiet proposes a gradual response mechanism.

| Level | Condition | Response |
|------|-----------|----------|
| 🟢 Normal | Noise within expected range | Normal status |
| 🟡 Attention | Noise slightly above baseline | Visual indication |
| 🟠 Warning | Noise persistently above baseline | Stronger visual feedback |
| 🔴 Alert | Significant continuous disturbance | Buzzer + display warning |

The exact thresholds and response durations can be tuned during prototype development.

---

## 🖥️ OLED Display Concept

The OLED display can provide simple and understandable information such as:

**SENSEQUIET**

**Noise: NORMAL**

**Level: 42**

**Status: QUIET**

During an alert:

**SENSEQUIET**

**⚠️ NOISE DETECTED**

**Please Keep Quiet**

---

## 🌍 Potential Applications

### 📚 Libraries

Maintain a suitable acoustic environment for reading and studying.

### 🏥 Hospitals

Monitor noise levels in areas where excessive sound may be undesirable.

### 🧑‍💻 Study Areas

Provide non-intrusive feedback when persistent noise occurs.

### 🏫 Educational Institutions

Monitor noise levels in classrooms, laboratories, and study areas.

### 🏢 Offices

Support quieter working environments.

### 🏠 Smart Buildings

Integrate environmental sensing into intelligent building-management systems.

---

## 🌟 What Makes SenseQuiet Different?

Traditional noise alarms often follow a simple approach:

**IF sound > fixed threshold → ALERT**

SenseQuiet proposes a more adaptive approach:

**Sound + Occupancy + Environmental Conditions + Adaptive Noise Floor + Noise Duration**

↓

**Context Analysis**

↓

**Intelligent Decision**

↓

**Appropriate Feedback**

This approach focuses on **understanding the environment before responding**.

---

## 🌱 Human-Centered Design

A key focus of SenseQuiet is to avoid making noise monitoring systems unnecessarily intrusive.

Instead of immediately activating a loud buzzer whenever the sound level increases, the system proposes a **tiered response**.

The system can first provide subtle visual feedback and escalate the response only when the disturbance is persistent and significant.

This makes the proposed solution more suitable for environments such as libraries, hospitals, and study spaces.

---

## 🔬 Engineering Concepts Explored

The project brings together several engineering concepts:

- 🔊 Acoustic sensing
- 🔬 Multi-sensor fusion
- 🤖 Adaptive algorithms
- ⏱️ Temporal filtering
- ⚡ Embedded systems
- 💻 Microcontroller programming
- 📊 Signal and data processing
- 🧠 Decision-making logic
- 👥 Human-centered design

---

## 🌍 Real-World Problem

Many existing noise monitoring systems use fixed thresholds.

However, environmental noise naturally changes depending on:

- Location
- Time
- Occupancy
- Background activity
- Environmental conditions

A fixed threshold may therefore result in:

- ❌ False alarms
- ❌ Unnecessary warnings
- ❌ Poor adaptability
- ❌ Intrusive user experience

SenseQuiet addresses this challenge through **adaptive calibration and multi-modal sensing**.

---

## 💡 Proposed Solution

SenseQuiet proposes an intelligent architecture that combines:

**Sound Sensing + Occupancy Detection + Environmental Sensing + Adaptive Calibration + Temporal Filtering + Context-Aware Feedback**

This enables the system to make a more informed decision before generating an alert.

---

## 🔮 Future Improvements

Future versions of SenseQuiet could include:

- 📱 Dedicated mobile application
- 🌐 Web-based monitoring dashboard
- ☁️ Cloud-based data storage
- 📊 Real-time noise-level graphs
- 🤖 Machine-learning-based sound classification
- 🎙️ Advanced microphone-based sound analysis
- 🗺️ Multi-zone noise monitoring
- 📡 Wireless sensor networks
- 🔋 Low-power operation
- 📈 Long-term environmental data analysis
- 🔔 Customizable alert levels
- 🧠 More advanced context-aware decision-making
- 📶 IoT-based remote monitoring

---

## 📂 Project Structure

    SenseQuiet/
    │
    ├── README.md
    │
    ├── src/
    │   ├── main.ino
    │   ├── sensors.cpp
    │   ├── sensors.h
    │   ├── calibration.cpp
    │   └── calibration.h
    │
    ├── hardware/
    │   ├── circuit-diagram.png
    │   └── schematic.pdf
    │
    ├── docs/
    │   ├── project-proposal.pdf
    │   └── documentation.pdf
    │
    ├── images/
    │   ├── prototype.jpg
    │   ├── circuit.jpg
    │   └── system-architecture.png
    │
    └── LICENSE

---

## 🚧 Project Status

**Status:** 🚧 Project Proposal / Prototype Development

SenseQuiet is currently being developed as an engineering project proposal with the goal of transforming the proposed architecture into a functional prototype.

---

## 👥 Team

### Team Members

- **Minangi Jayasinghe**
- **Ridma Sajantha**

### 👨‍🏫 Project Guidance

Special thanks to **Logeeshan Velmanickam (Ph.D.)** for his valuable guidance and support throughout the project.

---

## 🙏 Acknowledgement

We would like to express our sincere gratitude to our team members for their ideas, collaboration, and contributions throughout this project.

Special thanks to **Logeeshan Velmanickam (Ph.D.)** for guiding us and helping us develop this engineering project proposal.

---

## 📜 Project Proposal

This project proposal focuses on combining:

**Embedded Systems + Sensor Fusion + Adaptive Algorithms + Human-Centered Design**

to create a smarter and less intrusive approach to acoustic environment management.

The goal is to transform this idea into a working prototype and explore intelligent sensing solutions for real-world environments.

---

## 💭 What We Aim to Learn

Through the development of SenseQuiet, we aim to gain practical experience in:

- Embedded system development
- Arduino programming
- Sensor interfacing
- Sensor fusion
- Adaptive threshold algorithms
- Signal processing
- Human-centered system design
- Hardware-software integration
- Real-world engineering problem solving

---

## 🌐 Project Vision

> **"Sense the environment. Understand the context. Respond intelligently."**

SenseQuiet aims to demonstrate how **multi-modal sensing, adaptive algorithms, and embedded systems** can be combined to create smarter and less intrusive solutions for real-world acoustic environments.

---

<p align="center">
  <b>🚀 SenseQuiet</b>
</p>

<p align="center">
  <i>A Multi-Modal Sensor Fusion Architecture for Adaptive Acoustic Environment Optimization</i>
</p>

<p align="center">
  Team SenseQuiet | Engineering Project Proposal
</p>
