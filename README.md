<div align="center">

# 🛡️ DefenceX

**AI-powered scam call detection — transcribe, analyse, and flag suspicious calls in 33 languages.**

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-API-000000?style=flat-square&logo=flask)](https://flask.palletsprojects.com/)
[![Google Cloud](https://img.shields.io/badge/GoogleCloud-STT-4285F4?style=flat-square&logo=googlecloud&logoColor=white)](https://cloud.google.com/speech-to-text)
[![Gemini](https://img.shields.io/badge/Gemini-API-8E75B2?style=flat-square&logo=google&logoColor=white)](https://ai.google.dev/)

</div>

---

## Overview

DefenceX is a web app that helps users decide whether a phone call is a scam. Upload an audio recording, pick a language, and the service transcribes it via Google Cloud Speech-to-Text and runs the transcript through Gemini for scam-pattern analysis. Results are rendered back to a simple UI.

## Features

- 🎙️ **Audio upload** — drag-and-drop interface for call recordings
- 🌐 **Multilingual transcription** — 33 languages via Google Cloud Speech-to-Text
- 🔁 **Format normalisation** — incoming audio is converted to WAV before transcription
- 🧠 **Gemini-powered analysis** — transcript is scored for scam indicators
- 🖥️ **Web UI** — Flask backend renders findings in the browser

## Tech Stack

| Layer | Tools |
|---|---|
| Backend | Flask (`server.py`) |
| Speech | Google Cloud Speech-to-Text |
| LLM analysis | Gemini API |
| Frontend | HTML template (`templates/index.html`) |

## Getting Started

```bash
# 1. Clone
git clone https://github.com/bhavya-x/DefenceX.git
cd DefenceX

# 2. Virtualenv
python -m venv venv
source venv/bin/activate          # Windows: venv\Scripts\activate

# 3. Install
pip install -r requirements.txt

# 4. Configure credentials
export GOOGLE_APPLICATION_CREDENTIALS=path/to/service-account.json
export GEMINI_API_KEY=your_key_here

# 5. Run
python server.py
# Open http://localhost:5000
```

## Project Structure

```
DefenceX/
├── server.py            # Flask app + transcription/analysis pipeline
├── requirements.txt     # Python dependencies
└── templates/
    └── index.html       # Upload UI + result view
```

## Roadmap

- [ ] Live-call streaming mode
- [ ] Confidence scoring & reasons in the UI
- [ ] Caller-pattern history per user
- [ ] Self-hosted Whisper fallback for offline mode
