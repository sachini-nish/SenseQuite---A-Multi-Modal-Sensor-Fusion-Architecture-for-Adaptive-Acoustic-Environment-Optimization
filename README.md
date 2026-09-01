# 🚀 SenseQuiet – Multi-Modal Sensor Fusion for Adaptive Acoustic Environment Optimization

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Arduino-00979D?style=for-the-badge&logo=arduino&logoColor=white" alt="Arduino">
  <img src="https://img.shields.io/badge/Language-C%2FC%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" alt="C/C++">
  <img src="https://img.shields.io/badge/Project-Engineering%20Prototype-orange?style=for-the-badge" alt="Engineering Project">
</p>

---

## 📌 Project Overview

**SenseQuiet** is an intelligent noise management system designed for environments where maintaining an appropriate acoustic environment is important, such as:

- 📚 Libraries
- 🏥 Hospitals
- 🧑‍💻 Study spaces
- 🏫 Educational environments
- 🏢 Quiet working areas

Traditional noise monitoring systems often rely on fixed sound-level thresholds. However, the same sound level may have different meanings depending on the surrounding environment.

**SenseQuiet** aims to move beyond fixed-threshold noise alarms by introducing a **context-aware and adaptive sensing architecture**.

The system combines multiple sensors and adaptive decision-making to understand the surrounding environment before generating a response.

---

## 🎯 Project Objectives

The main objectives of SenseQuiet are:

- Develop an adaptive noise-monitoring system.
- Automatically learn the ambient sound level of an environment.
- Combine multiple sensor inputs for better environmental understanding.
- Reduce false alarms caused by temporary noise spikes.
- Provide context-sensitive feedback instead of intrusive alerts.
- Explore sensor-fusion techniques in embedded systems.
- Develop a practical and low-cost solution for real-world environments.

---

## 💡 Proposed System Highlights

### 🔊 1. Adaptive Noise Floor Calibration

Instead of using a single fixed sound threshold, SenseQuiet is designed to **learn the normal ambient sound level** of its environment.

The system can establish a baseline during an initial calibration period and continuously adapt to gradual changes in the background noise.

This allows the system to operate more effectively in different environments.

---

### 🔬 2. Multi-Sensor Fusion

SenseQuiet combines information from multiple sensors to understand the surrounding context.

The proposed sensors include:

| Sensor | Purpose |
|--------|---------|
| 🔊 Sound Sensor | Detect surrounding acoustic activity |
| 💡 LDR | Estimate ambient light conditions |
| 👤 PIR Sensor | Detect human presence / occupancy |

Rather than relying only on sound measurements, the system considers multiple environmental parameters before deciding whether an alert is necessary.

---

### 🚦 3. Tiered Feedback Mechanism

SenseQuiet uses multiple output devices to provide different levels of feedback.

| Output | Function |
|--------|----------|
| 🖥️ OLED Display | Display noise/environment status |
| 🔴🟢🔵 RGB LED | Visual indication of the current status |
| 🔔 Buzzer | Provide an audible warning when required |

The feedback mechanism is designed to be **gradual and context-sensitive**, avoiding unnecessary or aggressive alerts.


---

### ⏱️ 4. Temporal Filtering Logic

Short-duration noise spikes should not necessarily trigger an alert.

SenseQuiet therefore proposes a temporal filtering mechanism that considers the **duration and persistence of noise**.

For example:

```text
Short Noise Spike
       │
       ▼
   Monitor
       │
       ▼
Noise disappears
       │
       ▼
 No Alert

Continuous Disturbance
       │
       ▼
   Monitor Duration
       │
       ▼
Threshold exceeded
       │
       ▼
 Context-aware Alert
