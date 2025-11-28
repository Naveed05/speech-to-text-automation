🎤 Speech-to-Text Automation (Python Voice Assistant)

A simple and beginner-friendly Speech Recognition & Voice Command Automation project using:

SpeechRecognition

PyAudio

pyttsx3 (Text-to-Speech)

pywhatkit (YouTube Player)

This app listens to your voice, converts speech to text, and plays YouTube songs when you say “play <song name>”.

🚀 Features

✔ Converts speech to text
✔ Uses Google Speech API
✔ Plays YouTube songs
✔ Speaks responses
✔ Works offline for TTS
✔ Beginner-friendly & easy to modify

🛠️ Installation
1. Create Virtual Environment (Optional)
python -m venv venv
venv\Scripts\activate

2. Install Dependencies
pip install SpeechRecognition
pip install pipwin
pipwin install pyaudio
pip install pyttsx3
pip install pywhatkit

▶ How to Run
python speech_recognition.py

📌 Code Overview
import speech_recognition as sr
import pyttsx3 as pt
import pywhatkit as pk

listener = sr.Recognizer()
engine = pt.init()

def speak(text):
    engine.say(text)
    engine.runAndWait()

def hear():
    try:
        with sr.Microphone() as mic:
            print("Listening...")
            voice = listener.listen(mic)
            cmd = listener.recognize_google(voice)
            cmd = cmd.lower()
            print("You said:", cmd)
            return cmd
    except:
        return ""

def run():
    cmd = hear()
    if "play" in cmd:
        song = cmd.replace("play", "")
        speak("Playing " + song)
        pk.playonyt(song)

run()

🧠 Future Improvements

🔹 Add Whisper AI (Offline STT)
🔹 Add multiple commands (time, weather, search)
🔹 Add NLP intent classification
🔹 GUI version with Tkinter/Streamlit

👨‍💻 Author

Mirza Naveed Baig
Python | NLP | AI | Data Science
