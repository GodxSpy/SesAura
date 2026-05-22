# SesAura 🔊  
### Detects Sounds. Delivers Alerts. Empowers Silent Spaces.

SesAura is an AI-powered smart acoustic alert system designed to assist hearing-impaired individuals by detecting important environmental sounds in real time and delivering instant alerts through mobile notifications, vibration, LED indicators, and speech-to-text conversion.

---

# 🚀 Features

- 🎤 Real-time environmental sound detection
- 🧠 AI-based sound classification using TensorFlow Lite + YAMNet
- 📱 Instant mobile alerts via Firebase
- 💡 LED-based visual alerts
- 🔔 Vibration notifications
- 🗣️ Speech-to-text conversion
- ⚡ Raspberry Pi edge deployment
- ☁️ Firebase Realtime Database integration

---

# 🔍 Sounds Detected

SesAura can currently detect:

- Baby Crying 👶
- Fire Alarm 🚨
- Dog Bark 🐶
- Glass Break 🪟
- Door Knock 🚪
- Scream 😨

It also filters silence and background noise.

---

# 🛠️ Tech Stack

## Hardware
- Raspberry Pi
- USB Microphone
- LED Indicators

## Software & AI
- Python
- TensorFlow Lite
- TensorFlow Hub (YAMNet)
- Firebase Realtime Database
- SpeechRecognition
- NumPy
- SoundDevice

---

# 🧠 How It Works

1. Audio is captured using a microphone.
2. YAMNet extracts audio embeddings.
3. A custom TensorFlow Lite model classifies the sound.
4. Firebase updates alerts in real time.
5. The mobile app receives:
   - Notifications
   - Vibration alerts
   - Speech transcription
6. LED indicators activate locally.

---

# 📂 Project Structure

```plaintext
SesAura/
│
├── app.py
├── yamnet_sound_classifier.tflite
├── requirements.txt
├── README.md
├── config.txt
└── serviceAccountKey.json   # NOT included in repo
```

---

# ⚙️ Installation

## 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/SesAura.git
cd SesAura
```

---

## 2️⃣ Create Virtual Environment

### Windows
```bash
python -m venv venv
venv\Scripts\activate
```

### macOS/Linux
```bash
python3 -m venv venv
source venv/bin/activate
```

---

## 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

# 🔑 Firebase Setup

Create a Firebase project and download your service account key.

Place the JSON file inside the project root:

```plaintext
serviceAccountKey.json
```

⚠️ IMPORTANT: Never upload this file to GitHub.

Add this to `.gitignore`:

```gitignore
serviceAccountKey.json
venv/
__pycache__/
```

---

# ▶️ Run the Project

```bash
python app.py
```

If everything works correctly:

```plaintext
✅ SesAura AI System Running
```

---

# 📡 Firebase Database Structure

```json
{
  "sound": {
    "baby": false,
    "dog": false,
    "fire": false,
    "glass": false,
    "knock": false,
    "scream": false
  },
  "speech": "",
  "mode": 0,
  "vibrate": false
}
```

---

# 🎙️ Speech Recognition Mode

SesAura supports live speech transcription using Google Speech Recognition.

When `mode = 1`:
- Microphone starts listening
- Speech converts into text
- Text is stored in Firebase

---

# 📊 AI Model

The project uses:

- **YAMNet** for audio feature extraction
- **Custom TensorFlow Lite classifier** for sound prediction

Pipeline:
- Audio Recording
- Embedding Extraction
- Classification
- Firebase Alert Update

---

# 🌟 Future Improvements

- Smartwatch integration
- Offline speech recognition
- Smart home automation
- Emergency SOS alerts
- More sound classes
- Multilingual speech transcription

---

# 📜 License

This project is developed for academic and educational purposes.

---

# ⭐ Acknowledgements

- TensorFlow
- TensorFlow Hub
- Firebase
- Raspberry Pi Foundation
- Google Speech Recognition API

---

# 📌 Important Note

This repository does NOT include:
- Firebase secret keys
- Service account credentials
- Training datasets

Please configure your own Firebase credentials before running the project.
