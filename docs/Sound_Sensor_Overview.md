# 🔊 Sound Sensor Overview

## 1. Introduction

The sound sensor was developed to detect and monitor ambient noise levels in environments that require a quiet atmosphere, such as libraries, hospitals, and study areas.

The system converts sound waves into an electrical signal, processes the signal through several conditioning stages, and generates an analog output proportional to the surrounding noise level.

This output is acquired using an **NI myDAQ** and analyzed in **LabVIEW** to detect abnormal increases in noise and trigger alerts.

---

## 2. Electret Microphone

The sensing element of the system is an **electret microphone**, which converts acoustic energy into a small electrical signal.

Since the microphone produces only a few millivolts, the signal is too weak for direct processing. Therefore, an **LM324 operational amplifier** is used to amplify the microphone output and improve signal quality.

---

## 3. LM324 Operational Amplifier

An **LM324 operational amplifier** is used as the main amplification component.

The LM324 was selected because:

- It can operate from a single 5 V supply.
- It is suitable for low-power embedded applications.
- It is widely available and cost-effective.
- It can be used for signal amplification and conditioning.

The amplifier increases the small microphone signal to a suitable level for further processing.

---

## 4. 2.5 V Reference Voltage / Virtual Ground

To enable proper amplification using a single power supply, a **2.5 V reference voltage (virtual ground)** is generated.

The reference circuit consists of:

- Two 4.7 kΩ resistors
- One 10 µF capacitor

The two resistors form a voltage divider:

**5 V → 4.7 kΩ → 2.5 V → 4.7 kΩ → GND**

The capacitor helps stabilize the reference voltage.

This 2.5 V reference shifts the microphone signal into the middle of the operating range. As a result, both positive and negative variations of the audio signal can be amplified without clipping.

---

## 5. Signal Amplification

The electret microphone generates a small AC signal.

The signal is biased around the 2.5 V reference and then amplified using the LM324.

The signal-processing concept is:

**Microphone Signal**

→ **2.5 V Biasing**

→ **LM324 Amplification**

→ **Amplified Audio Signal**

The amplified signal is then passed to the envelope detector.

---

## 6. Envelope Detector

The amplified audio signal is passed through an **envelope detector** consisting of:

- **1N4148 diode**
- Capacitor
- Resistor

The purpose of the envelope detector is to extract the amplitude information from the audio waveform.

Instead of processing the rapidly varying audio waveform directly, the envelope detector produces a voltage that represents the overall amplitude of the sound.

### 1N4148 Diode

The **1N4148** was selected because of its:

- Fast switching characteristics
- Low capacitance
- Suitable response for signal detection
- Common availability

The diode rectifies the amplified audio signal, allowing the capacitor and resistor to follow the signal envelope.

---

## 7. Envelope Detection Principle

The envelope detection process can be represented as:

**Audio Waveform**

→ **Rectification**

→ **Peak / Envelope Extraction**

→ **Sound-Level Voltage**

A louder sound produces a larger audio amplitude, resulting in a higher envelope voltage.

Therefore:

**Higher Sound Intensity → Higher Output Voltage**

**Lower Sound Intensity → Lower Output Voltage**

---

## 8. Low-Pass Filter

Following the envelope detector, a **low-pass filter** is used to smooth the signal and remove unwanted fluctuations and electrical noise.

The low-pass filter:

- Smooths the detected signal
- Removes rapid fluctuations
- Reduces electrical noise
- Produces a stable analog output
- Improves threshold detection
- Helps minimize false triggering

The resulting voltage represents the overall sound level rather than the instantaneous audio waveform.

---

## 9. Analog Output

The final output of the sensor is an **analog voltage** that changes according to the surrounding noise level.

The general relationship is:

**Sound Level ↑ → Output Voltage ↑**

**Sound Level ↓ → Output Voltage ↓**

This analog output is connected to the **NI myDAQ** for data acquisition.

---

## 10. NI myDAQ Data Acquisition

The conditioned analog signal is acquired using an **NI myDAQ**.

The NI myDAQ provides the interface between the physical sound-sensing circuit and the LabVIEW software.

The main functions include:

- Analog signal acquisition
- Signal conversion
- Real-time data transfer
- Interface with LabVIEW
- Real-time signal monitoring

---

## 11. LabVIEW Analysis

The acquired signal is processed and analyzed using **LabVIEW**.

LabVIEW is used to:

- Read the analog sound-level signal
- Display the acquired signal
- Perform calibration
- Determine the ambient noise baseline
- Calculate the detection threshold
- Continuously monitor sound levels
- Detect excessive noise
- Trigger warnings or alerts

---

## 12. Calibration Process

Before normal operation, the system performs a calibration process to determine the normal ambient noise level.

During calibration, the sound sensor measures the surrounding environment under normal conditions.

The measured value is used as the **baseline sound level**.

This allows the system to adapt to the environment rather than relying on a completely fixed threshold.

---

## 13. Threshold Calculation

After determining the baseline, the threshold is calculated using:

**Threshold = Baseline × 1.1**

This sets the detection threshold at **110% of the measured baseline**.

### Example

If:

**Baseline = 2.00 V**

Then:

**Threshold = 2.00 × 1.1**

**Threshold = 2.20 V**

Therefore, a measured sound-level voltage above **2.20 V** would be identified as excessive noise.

---

## 14. Excessive Noise Detection

During normal operation, the sound level is continuously monitored.

The basic decision logic is:

**Measured Sound Level ≤ Threshold**

→ Normal Noise Level

**Measured Sound Level > Threshold**

→ Excessive Noise Detected

→ Activate Warning / Alert

This allows the system to identify significant increases in ambient noise.

---

## 15. Complete Signal Processing Flow

**Sound Waves**

↓

**Electret Microphone**

↓

**LM324 Amplification**

↓

**2.5 V Virtual Ground / Biasing**

↓

**Envelope Detector**

↓

**Low-Pass Filter**

↓

**Analog Sound-Level Output**

↓

**NI myDAQ**

↓

**LabVIEW**

↓

**Calibration**

↓

**Baseline Calculation**

↓

**Threshold = Baseline × 1.1**

↓

**Noise-Level Comparison**

↓

**Warning / Alert**

---

## 16. System Block Diagram

```text
              SOUND WAVES
                   │
                   ▼
        ┌────────────────────┐
        │ Electret Microphone│
        └─────────┬──────────┘
                  │
                  ▼
        ┌────────────────────┐
        │  2.5 V Biasing /   │
        │   Virtual Ground   │
        └─────────┬──────────┘
                  │
                  ▼
        ┌────────────────────┐
        │   LM324 Amplifier  │
        └─────────┬──────────┘
                  │
                  ▼
        ┌────────────────────┐
        │  Envelope Detector │
        │  1N4148 + RC       │
        └─────────┬──────────┘
                  │
                  ▼
        ┌────────────────────┐
        │   Low-Pass Filter  │
        └─────────┬──────────┘
                  │
                  ▼
        ┌────────────────────┐
        │   Analog Output    │
        └─────────┬──────────┘
                  │
                  ▼
        ┌────────────────────┐
        │      NI myDAQ      │
        └─────────┬──────────┘
                  │
                  ▼
        ┌────────────────────┐
        │      LabVIEW       │
        └─────────┬──────────┘
                  │
                  ▼
        ┌────────────────────┐
        │ Calibration &      │
        │ Threshold Analysis │
        └─────────┬──────────┘
                  │
                  ▼
             🚨 ALERT
