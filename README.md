# Edge AI Indoor Anomaly Sound Detection

## Project Overview
This project focuses on detecting abnormal indoor sounds using edge AI and real-time microphone input from the XIAO ESP32S3 Sense. The system classifies indoor sound events into **normal** and **abnormal** categories using spectrogram-based feature extraction and a lightweight CNN model built in Edge Impulse.

The project was initially explored using laptop-based audio as a baseline, but the final implementation shifted to hardware-consistent, device-side data collection to better reflect real deployment conditions. The final model supports real-time anomaly detection on an embedded edge device with low latency and low memory usage.

## Final System
- **Device:** Seeed Studio XIAO ESP32S3 Sense
- **Input:** `mic_value` from onboard microphone
- **Sampling frequency:** 200 Hz
- **Window size:** 3 seconds
- **Feature extraction:** Spectrogram
- **Model:** Lightweight CNN classifier in Edge Impulse
- **Classes:** Normal / Abnormal

## Key Results
- **Validation accuracy:** 87.5%
- **Weighted precision:** 0.90
- **Weighted recall:** 0.88
- **Weighted F1-score:** 0.87
- **Inference time:** 3 ms
- **RAM usage:** 12.7 KB
- **Flash usage:** 45.9 KB

The model performed strongly on normal sounds and achieved useful abnormal-event detection, especially for sharp spike-based events such as taps and knocks.

## Repository Structure

`data/`  
Contains project data references, sample descriptions, and notes on normal vs abnormal sound categories.

`notebooks/`  
Contains exploratory notebooks from the earlier baseline phase, including audio preprocessing and feature analysis.

`src/`  
Contains Python scripts and utilities related to preprocessing, experimentation, or baseline workflow development.

`models/`  
Contains saved model artifacts, screenshots, or exported files related to training and evaluation.

`deployment/`  
Contains edge deployment notes, Edge Impulse setup details, and device-side workflow information for the XIAO ESP32S3 Sense.

`docs/`  
Contains project documentation, weekly reflections, planning notes, and implementation details.

`reports/`  
Contains poster, presentation materials, final write-up, and supporting visuals.

## Workflow

XIAO ESP32S3 Sense Microphone → `mic_value` Time-Series Input → Spectrogram Feature Extraction → CNN Classification → Normal / Abnormal Output

## Methodology
1. Collected indoor sound samples directly from the XIAO ESP32S3 Sense onboard microphone.
2. Labeled samples into two categories: **normal** and **abnormal**.
3. Used 3-second windows at 200 Hz for data acquisition.
4. Converted time-series audio signals into spectrogram features using Edge Impulse.
5. Trained a lightweight CNN classifier for binary sound classification.
6. Evaluated the model using validation accuracy, confusion matrix, and live classification tests.
7. Demonstrated real-time inference using the connected device.

## Example Sound Categories

### Normal
- Ambient room noise
- Typing
- Light movement
- Soft indoor activity

### Abnormal
- Sharp desk taps
- Knocks
- Sudden spike-based sound events
- Repeated hard taps

## Technologies
- Python
- Edge Impulse
- Spectrogram-based audio feature extraction
- Convolutional Neural Networks (CNN)
- TinyML / Edge AI
- Seeed Studio XIAO ESP32S3 Sense

## Notes
This repository reflects both the early baseline exploration and the final hardware-aligned implementation. The final project emphasis is on **real-time edge-based anomaly detection**, not only offline audio classification.

## Author
**Mihir Bhansali**  
University of Florida  
M.S. Applied Data Science

## Faculty Advisor
**Dr. Andrea Ramirez-Salgado**
