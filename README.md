# 🧠 EEG Emotion Predictor

**An AI-powered web application that detects human emotions from raw EEG data using signal processing and machine learning.**

This project leverages brainwave signal data from EEG devices to classify emotions like **Happy**, **Sad**, and **Neutral**. It combines Python-based signal processing and ML with a modern React-based UI for easy, real-time analysis.

> Emotion detection from EEG data can be instrumental in **mental health monitoring**, **neurofeedback applications**, **HCI**, and **affective computing**.

---

## 🎯 Features

### Backend (Python + Flask)
- 🧮 **EEG Signal Processing**: Handles filtering, epoch segmentation, and band power feature extraction.
- 🔍 **Machine Learning Prediction**: Uses a **Random Forest classifier** trained on labeled EEG features.
- 🧠 **Auto Training**: If no model is found, it auto-trains using the provided `eeg_features_emotions.csv`.
- ⚙️ **Sampling Rate Detection**: Parses sampling rate from metadata in CSV files for accurate frequency calculations.

### Frontend (React + Tailwind)
- 🖱️ Upload EEG `.csv` files through an intuitive UI.
- 📊 See instant emotion predictions for each EEG epoch.
- ⚡ Real-time status updates and feedback.
- 📱 Fully responsive UI built with **Tailwind CSS** and **Vite**.

---

## 🏗️ Tech Stack

| Layer      | Technologies                                      |
|------------|---------------------------------------------------|
| Frontend   | React, Tailwind CSS, Vite, Axios                  |
| Backend    | Python, Flask, Flask-CORS, NumPy, Pandas, SciPy   |
| ML Model   | Scikit-learn (Random Forest), Joblib              |
| Data Format| CSV EEG files with metadata and sampling rate     |

---

## 🚀 Getting Started

### 🔧 Prerequisites

- Python 3.9+
- Node.js 18+
- pip & npm or yarn

---

### 📦 Backend Setup

```bash
git clone <your-repository-url>
cd backend

# Create and activate virtual environment
python -m venv venv
source venv/bin/activate  # or .\venv\Scripts\activate on Windows

# Install dependencies
pip install -r requirements.txt

# Ensure CSV data or model is present
# eeg_features_emotions.csv for training OR emotion_model.joblib for prediction

# Run the server
python app.py
# Default: http://localhost:5000
```

---

### 💻 Frontend Setup

```bash
cd frontend

# Install dependencies
npm install
# or
yarn install

# Start frontend server
npm run dev
# or
yarn dev

# Default: http://localhost:5173
```

Make sure your backend is running at `http://localhost:5000`.

---

## 📡 API Usage

### `/predict` – Emotion Prediction Endpoint

- **Method**: `POST`
- **Request**: EEG `.csv` file in `multipart/form-data`
- **Response**:
  ```json
  {
    "predictions": ["HAPPY", "NEUTRAL", "SAD", ...]
  }
  ```

---

## 📄 CSV File Format for EEG

> The accuracy of prediction relies heavily on correctly formatted EEG data.

### ✅ Required:
- UTF-8 `.csv` file
- Metadata line indicating sampling rate (e.g., `Sampling Rate:EEG_128Hz`)
- EEG channel column (default: `EEG.AF3`)
- Sufficient samples to cover at least one 2-second epoch (e.g., 256 values for 128 Hz)

Example:
```csv
# Sampling Rate:EEG_128Hz
Timestamp,EEG.AF3,EEG.F7,...
1634822400.000,4200.51,4250.12,...
1634822400.004,4201.70,4251.30,...
```

---

## 📁 Project Structure

```
📦 EEG-Emotion-Predictor
 ┣ 📁 backend
 ┃ ┣ 📄 app.py
 ┃ ┣ 📄 eeg_features_emotions.csv
 ┃ ┣ 📄 emotion_model.joblib
 ┃ ┣ 📄 requirements.txt
 ┃ ┗ 📁 venv/
 ┣ 📁 frontend
 ┃ ┣ 📁 src/components/EEGProcessor.jsx
 ┃ ┣ 📄 App.jsx
 ┃ ┣ 📄 index.css
 ┃ ┣ 📄 vite.config.js
 ┃ ┣ 📄 tailwind.config.js
 ┗ 📄 README.md
```

---

## 🔭 Future Enhancements

### ✅ Short-term Goals
- 📊 **EEG Frequency Plotting**
- 🧠 **More Emotion Labels**
- 🛡️ **User Authentication**
- 🌐 **Deploy on Render/Netlify**

### 🚀 Long-term Vision
- 🧬 **Deep Learning Integration**
- 📉 **Real-Time EEG Streaming**
- 📈 **User Emotion Trends**
- 🌍 **Multilingual Support**
- 📁 **Dataset Uploader**

---

## 🤝 Contribution

We welcome contributions! Feel free to:
- Open issues
- Suggest new features
- Submit pull requests

---

## 🧑‍💻 Authors

- **Project Lead & Developer**: Likhitha
- **Contributors**: Open to collaborators and volunteers

---

## 📜 License

This project is licensed under the **MIT License**.

---

If you're excited about the intersection of neuroscience, AI, and web development—**⭐ star this repository** and help us build smarter emotion-aware systems! 😊
