# Internship_Python
# EEG Signal Processing and Analysis 🧠⚡

> Advanced EEG Signal Processing, Noise Reduction, Artifact Removal, and Dimensionality Reduction using Python and Machine Learning techniques.

<p align="left">
  <img src="https://img.shields.io/badge/Python-3.x-blue?logo=python" />
  <img src="https://img.shields.io/badge/MNE-Python-orange" />
  <img src="https://img.shields.io/badge/Scikit--Learn-ML-yellow" />
  <img src="https://img.shields.io/badge/EEG-Signal%20Processing-green" />
  <img src="https://img.shields.io/badge/License-MIT-red" />
</p>

---

# 📌 Project Overview

This project focuses on Electroencephalography (EEG) Signal Processing and Analysis using EDF files.

The system demonstrates:

- EEG signal loading
- Signal preprocessing
- Noise reduction
- ICA artifact removal
- PSD analysis
- PCA dimensionality reduction
- EEG visualization
- EEG to CSV conversion

---

# ✨ Features

✅ EDF file loading  
✅ Band-pass filtering  
✅ Notch filtering  
✅ ICA artifact removal  
✅ PSD analysis  
✅ SNR computation  
✅ PCA dimensionality reduction  
✅ EEG visualization  
✅ CSV conversion  

---

# 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core Programming |
| MNE-Python | EEG Processing |
| NumPy | Numerical Computation |
| Pandas | Data Handling |
| Matplotlib | Visualization |
| Scikit-Learn | PCA & ML |

---

# 📂 Project Structure

```bash
EEG-Signal-Processing/
│
├── data/
├── notebooks/
├── outputs/
├── screenshots/
├── requirements.txt
├── README.md
└── LICENSE
```

# ⚙️ Installation

## Clone Repository

```bash
git clone https://github.com/your-username/eeg-signal-processing.git
cd eeg-signal-processing
```

## Install Dependencies

```bash
pip install mne pyedflib numpy pandas scikit-learn matplotlib seaborn plotly scipy
```

---

# 🚀 Usage

## Load EEG Data

```python
import mne

file_path = "chb01_01.edf"
raw_data = mne.io.read_raw_edf(file_path, preload=True)

print(raw_data.info)
```

---

# 📊 Signal Preprocessing

## Band-pass Filtering

```python
raw_filtered_bandpass = raw_data.copy().filter(l_freq=1, h_freq=45)
```

## Notch Filtering

```python
raw_filtered_notch = raw_filtered_bandpass.copy().notch_filter(freqs=50)
```

---

# 🧠 ICA Artifact Removal

```python
ica = mne.preprocessing.ICA(
    n_components=20,
    random_state=97,
    max_iter=800
)

ica.fit(raw_filtered_notch)
```

---

# 📈 PCA Dimensionality Reduction

```python
from sklearn.decomposition import PCA
```

---

# 🔮 Future Enhancements

- Deep Learning based EEG classification
- Real-time EEG monitoring
- Seizure prediction system
- CNN/LSTM integration

---

# 👨‍💻 Author

## Dinesh Raj Upadhya

📫 LinkedIn:
www.linkedin.com/in/dinesh-raj-upadhya-920075206

📧 Email:
dineshrajupadhya86@gmail.com
