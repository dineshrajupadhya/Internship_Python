# Internship_Python
EEG Signal Processing and Analysis 🧠⚡

Advanced EEG Signal Processing, Noise Reduction, Artifact Removal, and Dimensionality Reduction using Python and Machine Learning techniques.

<p align="left"> <img src="https://img.shields.io/badge/Python-3.x-blue?logo=python" /> <img src="https://img.shields.io/badge/MNE-Python-orange" /> <img src="https://img.shields.io/badge/Scikit--Learn-ML-yellow" /> <img src="https://img.shields.io/badge/EEG-Signal%20Processing-green" /> <img src="https://img.shields.io/badge/License-MIT-red" /> </p>
📌 Project Overview

This project focuses on Electroencephalography (EEG) Signal Processing and Analysis using EDF (European Data Format) files. The system demonstrates a complete EEG preprocessing pipeline including:

EEG signal loading
Signal cleaning and preprocessing
Noise reduction
Artifact removal using ICA
Power Spectral Density (PSD) analysis
Signal-to-Noise Ratio (SNR) analysis
Dimensionality reduction using PCA
EEG data visualization
EEG to CSV conversion

The project was developed as part of an internship/research work focused on biomedical signal processing and machine learning applications in healthcare.

✨ Features

✅ Load EEG data from .edf files
✅ Band-pass and notch filtering
✅ EEG artifact removal using ICA
✅ Power Spectral Density (PSD) analysis
✅ Signal-to-Noise Ratio (SNR) computation
✅ Principal Component Analysis (PCA)
✅ EEG signal visualization
✅ EEG to CSV conversion
✅ Multi-channel EEG processing
✅ Data preprocessing for ML applications

🧠 Technologies Used
Technology	Purpose
Python	Core Programming
MNE-Python	EEG Processing
PyEDFlib	EDF File Handling
NumPy	Numerical Computation
Pandas	Data Manipulation
Matplotlib	Visualization
Seaborn	Statistical Visualization
Plotly	Interactive Graphs
Scikit-Learn	PCA & ML Utilities
📂 Project Structure
EEG-Signal-Processing/
│
├── data/
│   └── .edf EEG files
│
├── notebooks/
│   └── eeg_processing.ipynb
│
├── outputs/
│   ├── plots/
│   ├── cleaned_signals/
│   └── csv_files/
│
├── screenshots/
│
├── requirements.txt
├── README.md
└── LICENSE
⚙️ Installation & Setup
1️⃣ Clone Repository
git clone https://github.com/your-username/eeg-signal-processing.git
cd eeg-signal-processing
2️⃣ Install Dependencies
pip install mne pyedflib numpy pandas scikit-learn matplotlib seaborn plotly scipy
📊 Dataset

This project uses EEG datasets stored in .edf format.

Example Dataset:

CHB-MIT Scalp EEG Database

Example Google Drive Path:

from google.colab import drive
drive.mount('/content/drive')

folder_path = "/content/drive/My Drive/archive/chb-mit-scalp-eeg-database-1.0.0"
🚀 Workflow
1️⃣ EEG Data Loading

Load EEG signals from EDF files using MNE.

import mne

file_path = "chb01_01.edf"
raw_data = mne.io.read_raw_edf(file_path, preload=True)

print(raw_data.info)
2️⃣ Signal Preprocessing
✔️ Band-pass Filtering

Removes unwanted low/high frequency components.

✔️ Notch Filtering

Removes power-line interference (50Hz/60Hz).

raw_filtered_bandpass = raw_data.copy().filter(l_freq=1, h_freq=45)
raw_filtered_notch = raw_filtered_bandpass.copy().notch_filter(freqs=50)
3️⃣ Artifact Removal using ICA

Independent Component Analysis (ICA) is used to remove:

Eye blink artifacts (EOG)
Muscle noise (EMG)
ECG artifacts
ica = mne.preprocessing.ICA(
    n_components=20,
    random_state=97,
    max_iter=800
)

ica.fit(raw_filtered_notch)

ica.exclude = [0, 1]

raw_cleaned = raw_filtered_notch.copy()
ica.apply(raw_cleaned)
📈 Noise Analysis
Power Spectral Density (PSD)

PSD helps analyze signal frequency components.

from scipy.signal import welch

def compute_psd(signal, fs):
    freqs, psd = welch(signal, fs=fs, nperseg=1024)
    return freqs, psd
PSD Visualization
Frequency domain analysis
Brainwave distribution analysis
Noise identification
🔊 Signal-to-Noise Ratio (SNR)

SNR analysis evaluates EEG signal quality.

def add_noise(signal, snr_db):
    return noisy_signal

Used for:

Noise simulation
Signal quality testing
Model robustness analysis
📉 Dimensionality Reduction using PCA

Principal Component Analysis reduces EEG dimensionality while preserving important features.

from sklearn.decomposition import PCA

def apply_pca(eeg_data, n_components=5):
    return reduced_data, explained_variance
Benefits

✅ Reduced computational complexity
✅ Better visualization
✅ Improved ML preprocessing

📊 Data Visualization

The project includes visualization of:

Raw EEG Signals
Filtered EEG Signals
PSD Graphs
ICA Components
PCA Components
Noise Analysis Graphs

Libraries Used:

Matplotlib
Seaborn
Plotly
🔄 EEG to CSV Conversion

Convert EDF EEG data into CSV format for:

Machine Learning
Data Analysis
Model Training
df = raw.to_data_frame()
df.to_csv(output_file, index=False)
📌 Applications

🧠 Seizure Detection
🧠 Brain-Computer Interface (BCI)
🧠 Neurological Disorder Analysis
🧠 EEG-based Machine Learning
🧠 Biomedical Signal Processing

📷 Sample Outputs
EEG Signal Visualization
Raw EEG waveforms
Filtered signals
Noise-reduced signals
Frequency Analysis
PSD graphs
Brainwave analysis
PCA Visualization
Reduced EEG dimensions
Variance plots

Add screenshots inside the /screenshots folder and update image links here.

🔮 Future Enhancements
Deep Learning based EEG classification
Real-time EEG monitoring
Seizure prediction system
CNN/LSTM integration
Cloud deployment
Web dashboard for EEG visualization
🤝 Contributing

Contributions are welcome!

If you'd like to improve this project:

Fork the repository
Create a new branch
Commit your changes
Submit a Pull Request
📜 License

This project is licensed under the MIT License.

👨‍💻 Author
Dinesh Raj Upadhya

🎓 MCA Student | Full Stack Developer | ML Enthusiast

📫 Connect with me:

LinkedIn: www.linkedin.com/in/dinesh-raj-upadhya-920075206
Email: dineshrajupadhya86@gmail.com
