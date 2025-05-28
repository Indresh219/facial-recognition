 # This project is a part of a hackathon run by https://katomaran.com 

# 🧠 Real-time Face Recognition + RAG Chatbot

This project blends **facial recognition** with a **real-time chatbot** powered by **RAG (Retrieval-Augmented Generation)**. You can register faces, log timestamps, and then ask the bot things like:

> “Who was the last person registered?”  
> “When was Alice registered?”  
> “How many people are in the system?”

💡 Built with React, Node.js, Python (FastAPI), and LangChain + FAISS.

---

## 🚀 Features

- 🔍 Real-time face recognition with face-api.js
- 💬 Chatbot using WebSocket + Python FastAPI
- 🧠 LangChain + FAISS for vector search
- 🕒 Auto-index update when new face is added (watchdog)
- 📂 JSON DB to store names + timestamps

---

## 📦 Tech Stack

| Frontend  | Backend (Node) | Backend (Python) |
|-----------|----------------|------------------|
| React     | Node.js + WS   | FastAPI + LangChain |
| face-api.js | WebSocket bridge | FAISS, watchdog, sentence-transformers |


---

## ⚙️ Getting Started

### 1. Clone the repo

git clone https://github.com/your-username/face-rag-chatbot.git
cd face-rag-chatbot

2. Install dependencies
Backend:

cd backend
npm install
pip install -r requirements.txt

Frontend:


cd ../frontend
npm install
3. Run it all
In root directory, run:


# Start backend services
npm run start:node-files

# In another terminal/tab:
npm run start:python-files

# (Optional) Start frontend separately:
npm run dev
🧪 Try it out
Register a face → saved to db.json with timestamp ✅

Ask the chatbot:

"Who was the last person registered?"

"When was John registered?"

"How many people registered?"

🧠 How it Works
face-api.js captures and encodes face

Saved to db.json with timestamp

faiss_update.py listens for db changes → rebuilds vector index

Chat UI sends question → Python FastAPI answers using vector search or custom logic



