# 🫀 Real-Time ECG Signal Processing Pipeline

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![Status](https://img.shields.io/badge/Status-Completed-success)
![DSP](https://img.shields.io/badge/Digital%20Signal%20Processing-ECG-blueviolet)
![Real-Time](https://img.shields.io/badge/Mode-Real--Time-red)
![FPGA](https://img.shields.io/badge/FPGA-Deployment%20Ready-yellow)
![License](https://img.shields.io/badge/License-MIT-green)

> A modular real-time ECG signal processing framework for continuous cardiac monitoring featuring adaptive preprocessing, Pan-Tompkins based PQRST delineation, physiological validation, and a streaming architecture designed for future FPGA deployment.

---

## Overview

This project was developed during my Summer Research Internship at **IISER Bhopal** under **Dr. Mitradeep Bhattacharjee**.

The objective was to design a complete ECG processing pipeline capable of continuously acquiring ECG signals, removing physiological and environmental noise, detecting cardiac fiducial points, validating extracted parameters, and supporting future deployment on FPGA-based embedded systems.

Unlike conventional offline ECG analysis, this project implements a **real-time sliding window architecture** for continuous monitoring while maintaining constant memory usage through a circular ring buffer.

---

## Architecture

```text
                 ECG Sensor
                      │
                      ▼
            Signal Acquisition
                      │
                      ▼
        Baseline Wander Removal
                      │
                      ▼
            50 Hz IIR Notch Filter
                      │
                      ▼
      Butterworth Bandpass Filter
                      │
                      ▼
          Pan–Tompkins Algorithm
                      │
                      ▼
          P • Q • R • S • T Detection
                      │
                      ▼
      RR Interval • HR • HRV Metrics
                      │
                      ▼
       Sliding Window Real-Time Engine
                      │
                      ▼
         Continuous ECG Visualization
```

---

## Features

- Dual-median baseline wander removal
- 50 Hz IIR notch filtering
- 4th-order Butterworth bandpass filtering (0.5–40 Hz)
- Pan-Tompkins based R-peak detection
- Complete PQRST delineation
- RR interval, Heart Rate and HRV computation
- Physiological validation against clinical reference ranges
- Ring buffer for continuous ECG acquisition
- 10-second sliding window with 90% overlap
- Duplicate peak suppression for streaming analysis
- Modular architecture suitable for FPGA deployment

---
## Processing Pipeline

```text
📈 ECG Acquisition
        │
        ▼
🧹 Adaptive Signal Preprocessing
(Baseline Wander Removal • 50 Hz Notch • Butterworth Bandpass)
        │
        ▼
⚡ Feature Enhancement
(Pan–Tompkins QRS Detection)
        │
        ▼
❤️ P-Q-R-S-T Wave Delineation
        │
        ▼
📊 Cardiac Parameter Extraction
(RR Interval • Heart Rate • HRV)
        │
        ▼
✅ Physiological Validation
        │
        ▼
🔄 Sliding Window Real-Time Monitoring
```
----
## Repository Structure

```text
├── notebooks/
├── figures/
├── report/
├── README.md
├── requirements.txt
└── LICENSE
```

---

## Results

✔ Improved ECG signal quality after preprocessing

✔ Robust PQRST delineation

✔ Accurate RR interval and Heart Rate estimation

✔ Physiological parameters within accepted clinical ranges

✔ Continuous monitoring using a ring-buffer based streaming architecture

---

## Future Scope

- FPGA implementation
- ASIC realization
- Wearable ECG monitoring
- Low-power embedded deployment

---

## Technologies

Python • NumPy • SciPy • WFDB • NeuroKit2 • Matplotlib • Jupyter Notebook

---

## Author

**Vanshika Gupta**

B.Tech Electronics & Communication Engineering

IIIT Guwahati

Summer Project Intern, IISER Bhopal
