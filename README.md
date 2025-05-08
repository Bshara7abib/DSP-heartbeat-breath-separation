# 💓 Heartbeat and Breath Sound Separation Using DSP 🎧

This repository presents a real-time Digital Signal Processing (DSP) solution for analyzing and separating heartbeat and breath sounds from a mixed physiological signal. The project was developed using **Texas Instruments’ C674x DSP**, **TI-RTOS**, and **Code Composer Studio (CCSv11)**, in conjunction with **MATLAB-based filter design**.

> The system demonstrates precise filtering, envelope extraction, and frequency analysis under real-time constraints — leveraging ISR/SWI multitasking and TI's SYS/BIOS.

---

## 📌 Objectives

- Separate heartbeat and breath components using real-time filters.
- Implement energy-based envelope detection and FFT visualization.
- Track heartbeat and breath events in time-domain samples.
- Maintain real-time performance using ISR, SWI, semaphores, and task management.

---

## ⚙️ System Specifications

| Parameter           | Value/Description                     |
|---------------------|----------------------------------------|
| Sampling Frequency  | 2000 Hz                                |
| Buffer Size         | 4405 samples                           |
| DSP Processor       | TI C674x (OMAP-L138)                   |
| RTOS                | TI-RTOS (SYS/BIOS)                     |
| Development Tools   | Code Composer Studio (v11)            |
| Filter Design       | MATLAB (IIR Elliptic Filters)         |

---

## 🧠 Filter Architecture

- 🛑 **Notch Filter:** Removes 250 Hz noise
- 🌬 **Breath Detection Filter:** IIR Elliptic Lowpass (below 135 Hz)
- ❤️ **Heartbeat Detection Filter:** IIR Elliptic Highpass (above 135 Hz)

---

## 🔄 Real-Time Workflow

1. **Timer ISR:** Periodically samples data from physiological input.
2. **Software Interrupt:** Fetches sample buffer & synchronizes processing.
3. **DSP Tasks:**
   - Apply notch + band filters
   - Calculate smoothed signal envelopes
   - Count heartbeat and breath peaks
   - Perform FFT & energy calculations

---

## 📊 Visual Results

- ✅ Filtered signals (Notch, Breath, Heartbeat)
- ✅ Envelope tracking and peak detection
- ✅ FFT magnitude response
- ✅ Task performance and real-time scheduling

---

## 📎 Documentation

- [`DSP-Heartbeat-VS-Breath-Sound-Analysis.pdf`](docs/DSP-Heartbeat-VS-Breath-Sound-Analysis.pdf):  
  Full technical report including system design, filter specs, architecture diagrams, performance results, and signal screenshots.

---

## 🗂️ Repository Structure

```plaintext
dsp-heartbeat-breath-separation/
├── docs/
│   └── DSP-Heartbeat-VS-Breath-Sound-Analysis.pdf
├── src/
│   └── Heartbeat_VS_BreathSound_FinalProject.zip
├── LICENSE
└── README.md
