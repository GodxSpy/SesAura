SesAura 🔊
Detects Sounds. Delivers Alerts. Empowers Silent Spaces.

SesAura is an AI-powered smart acoustic alert system designed to assist hearing-impaired individuals by detecting important environmental sounds in real time and sending instant alerts through mobile notifications, vibration, LED indicators, and speech-to-text conversion.

🚀 Features
🎤 Real-time environmental sound detection
🧠 AI-based sound classification using TensorFlow Lite + YAMNet
📱 Instant mobile alerts through Firebase
💡 LED alert indicators
🔔 Vibration alerts
🗣️ Speech-to-text conversion
⚡ Edge deployment support using Raspberry Pi
☁️ Firebase Realtime Database integration
🔍 Sounds Detected

SesAura currently detects:

Baby Crying
Fire Alarm
Dog Bark
Glass Break
Door Knock
Scream

The model also filters silence and background noise.

🛠️ Tech Stack
Hardware
Raspberry Pi
USB Microphone
LED Indicators
Software & AI
Python
TensorFlow Lite
TensorFlow Hub (YAMNet)
Firebase Realtime Database
SpeechRecognition
NumPy
SoundDevice
🧠 How It Works
Audio is captured using a microphone.
YAMNet extracts embeddings from the audio stream.
A custom TensorFlow Lite classifier predicts the sound class.
Firebase updates alert states in real time.
Mobile app receives:
Notifications
Vibration alerts
Speech transcription
LED indicators activate locally.

Architecture and module flow are shown in the project presentation.

📂 Project Structure
SesAura/
│
├── app.py
├── yamnet_sound_classifier.tflite
├── serviceAccountKey.json   # NOT included in repo
├── requirements.txt
├── README.md
└── config.txt
⚙️ Installation
1️⃣ Clone the repository
git clone https://github.com/your-username/SesAura.git
cd SesAura
2️⃣ Create virtual environment
python -m venv venv

Activate it:

Windows
venv\Scripts\activate
macOS/Linux
source venv/bin/activate
3️⃣ Install dependencies
pip install -r requirements.txt
🔑 Firebase Setup

Create a Firebase project and download your service account JSON key.

Place it in the project root:

serviceAccountKey.json

⚠️ Never upload this file to GitHub.

Add this to .gitignore:

serviceAccountKey.json
venv/
__pycache__/
▶️ Run the Project
python app.py

If everything works correctly:

✅ SesAura AI System Running
📡 Firebase Realtime Database Structure
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
🎙️ Speech Recognition Mode

SesAura supports live speech transcription using Google Speech Recognition.

When mode = 1:

Microphone starts listening
Speech is converted into text
Text is stored in Firebase

Implementation available in speech_mode_loop() inside app.py.

📊 AI Model

The project uses:

YAMNet for audio embeddings
Custom TensorFlow Lite classifier for sound prediction

Inference pipeline:

Audio Recording
Embedding Extraction
Classification
Firebase Alert Update

Main implementation available in app.py.

📱 Future Improvements
Smartwatch integration
Offline speech recognition
More sound classes
Smart home automation
Emergency SOS alerts
Multilingual speech transcription
👨‍💻 Team
ANJALY JINS
ALEX JOSE
BILNA BENNY
ROHAN RAJESH

Guide:

Ms. MANJU M

From:
Department of Computer Science and Engineering
Vimal Jyothi Engineering College, Chemperi

📜 License

This project is developed for academic and educational purposes.

⭐ Acknowledgements
TensorFlow
TensorFlow Hub
Firebase
Raspberry Pi Foundation
Google Speech Recognition API
📌 Repository Note

This repository does NOT include:

Firebase secret keys
Service account credentials
Large training datasets

Please configure your own Firebase credentials before running the project.
