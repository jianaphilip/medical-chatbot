# 🏥 MedAssist – AI-Powered Symptom Analysis Chatbot

**MedAssist** is a web-based AI medical assistant that helps users analyze their health symptoms using text or voice input and recommends the appropriate medical department. It combines **FastAPI**, **Next.js**, **SpeechRecognition**, and **jsPDF** to deliver an interactive and user-friendly healthcare assistant.

---

## 🚀 Features
- 🎤 Voice input with live transcription (SpeechRecognition + ffmpeg + pydub)
- 🤖 AI-generated medical advice & severity detection
- 🏥 Department classification & emergency alerts
- 💬 Chat history stored in browser localStorage
- 📄 Export conversation to PDF (jsPDF)
- ⚡ FastAPI backend with modular architecture

---

## 🧠 System Architecture
1. **Frontend (Next.js / React)** – Handles chat UI, recording, and PDF export.
2. **Backend (FastAPI)** – Processes text/audio, runs severity logic, calls LLM helper.
3. **SpeechRecognition + ffmpeg** – Converts voice input to text.
4. **LocalStorage** – Stores chat history in browser.

---

## 🧩 API Endpoints

### `POST /api/predict`
**Request:**
```json
{ "question": "I have chest pain and shortness of breath." }
```
**Response:**
```json
{
  "answer": "You may need to consult a cardiologist.",
  "severity": "CRITICAL",
  "severity_color": "red",
  "severity_message": "Possible emergency – seek medical attention immediately."
}
```

### `POST /api/transcribe`
Accepts audio (WebM/ogg), converts to WAV, and transcribes to text.
**Response:**
```json
{ "transcription": "I have chest pain..." }
```

---

## ⚙️ Tech Stack
**Frontend:** Next.js, React, Tailwind CSS, TypeScript, jsPDF, lucide-react  
**Backend:** FastAPI, Python, pydub, SpeechRecognition, ffmpeg, Uvicorn  
**Storage:** Browser localStorage (no persistent DB)

---

## 🖥️ System Requirements
- **OS:** Windows / macOS / Linux  
- **Node.js:** v16+  
- **Python:** 3.10–3.13  
- **RAM:** 4GB+  
- **Additional:** ffmpeg in PATH, pip, npm

---

## 🛠️ Setup & Run

### Backend
```bash
cd Backend
python -m venv .venv
.venv\Scripts\activate   # or source .venv/bin/activate
pip install -r requirements.txt
python -m uvicorn Backend.main:app --reload
```

### Frontend
```bash
cd Frontend
npm install
npm run dev
```
Visit **http://localhost:3000**
