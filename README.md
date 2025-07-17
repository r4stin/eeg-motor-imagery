# 🧠 EEG Motor Imagery Classification – Deep Learning Benchmark

This project benchmarks deep learning models on the [PhysioNet EEG Motor Movement/Imagery Dataset](https://physionet.org/content/eegmmidb/1.0.0/) to classify left vs. right motor imagery using ERP signals.

## 📊 Models Compared
- 🌲 **Random Forest (RF)** – Strong classical baseline using ERP epochs
- 🔷 **LSTM** – Sequence model trained on normalized EEG trials
- 🟪 **CNN** – 2D ConvNet for local spatiotemporal features
- 🧠 **EEGNet** – Compact and efficient deep model for EEG data (best performer)

## 📈 Results (Test Accuracy)
| Model   | Accuracy |
|---------|----------|
| EEGNet  | **74.34%** ✅ |
| LSTM    | 70.81% |
| CNN     | 62.08% |
| RF      | 67.20% |

All models trained on ERP segments of 15 motor-related channels, extracted from 109 subjects.

## 🧪 Preprocessing
- 64-channel EDF files
- Event classes: `T1` (Left Fist), `T2` (Right Fist)
- Preprocessing:
  - Bandpass filter: 1–40 Hz
  - Epoching: -0.2s to +0.8s around each event
  - Normalization: per-epoch z-score
  - Used 15 motor cortex channels (C3, Cz, C4, FCx, CPx)

## 🛠️ Tech Stack
- Python, PyTorch, scikit-learn, MNE
- Training loop with cross-validation & test evaluation
- Jupyter + Kaggle-compatible environment

