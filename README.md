 NCERT Doubt Solver (Multilingual RAG System)

A Multilingual NCERT Doubt Solver built using FastAPI + React (Vite) that allows students to ask questions from NCERT textbooks and get accurate answers using a Retrieval-Augmented Generation (RAG) pipeline.
Supports English, Hindi, Marathi, Tamil, Telugu, Bengali, Urdu.

 Features

📚 NCERT textbook-based answers
🌍 Multilingual question support
🔍 RAG-based semantic search
🔊 Optional text-to-speech output
🧠 Simple / Exam mode answers
🖼 OCR & voice input (frontend)
📂 Dataset & Embeddings

Download the NCERT dataset from Google Drive:

👉 NCERT PDFs & Data
🔗 https://drive.google.com/drive/folders/17rZP8FWp19gD7TX76c2V7dAaO-85IDU5?usp=sharing

Where to place it
After downloading, place the files like this:
backend/
 ├── data/
 │    ├── Class6/
 │    ├── Class7/
 │    ├── Class8/
 │    ├── Class9/
 │    └── Class10/


⚠️ Do not rename folders. The RAG pipeline depends on this structure.

🛠 Backend Setup (FastAPI)
1️⃣ Create Virtual Environment
cd backend
python -m venv venv
venv\Scripts\activate

2️⃣ Install Dependencies
pip install -r requirements.txt

3️⃣ Build Vector Index (One-time)
python
>>> from backend.rag import build_index
>>> build_index()
>>> exit()

4️⃣ Run Backend Server
python -m uvicorn backend.main:app --reload


Backend will run at:

http://127.0.0.1:8000


Swagger UI:

http://127.0.0.1:8000/docs

🧪 Backend Test (Swagger)

Use /ask endpoint:

{
  "question": "Henry's law",
  "language": "English",
  "mode": "simple"
}


If answers array is not empty, backend is working ✅

🎨 Frontend Setup (React + Vite)
1️⃣ Install Dependencies
cd frontend
npm install

2️⃣ Start Frontend
npm run dev


Frontend runs at:

http://localhost:5173


Chat page:

http://localhost:5173/chat

🔗 Frontend ↔ Backend Connection

Ensure frontend/src/services/api.ts contains:

const BASE_URL = "http://127.0.0.1:8000";

📁 Project Structure (Simplified)
ncertdoubtsolver-main/
│
├── backend/
│   ├── backend/
│   │   ├── main.py
│   │   ├── rag.py
│   │   ├── utils.py
│   │   ├── translate.py
│   │   └── cache.py
│   ├── data/
│   ├── embeddings/
│   └── requirements.txt
│
├── frontend/
│   ├── src/
│   │   ├── pages/
│   │   │   └── Chat.tsx
│   │   ├── services/
│   │   │   └── api.ts
│   │   └── App.tsx
│   └── package.json
│
└── README.md



## 🎥 Project Demo Video

▶️ Watch Demo:  
🔗 https://drive.google.com/drive/folders/17rZP8FWp19gD7TX76c2V7dAaO-85IDU5?usp=sharing


📌 What the Video Should Show (2–4 min)
Backend running (/docs)
Asking question in Swagger
Frontend chat interaction
Multilingual question (Hindi/Marathi)
Answer appearing correctly

🧠 Tech Stack
Backend: FastAPI, LangChain, FAISS
Frontend: React, Vite, TypeScript, Tailwind
Embeddings: Sentence Transformers
Translation: Transformers / MarianMT
RAG: NCERT PDF vector search

✅ Status
✔ Backend working
✔ Frontend connected
✔ Multilingual answers
✔ RAG retrieval fixed
✔ Production-ready structure

📌 Future Improvements
Chapter-wise filtering
Answer citations with page numbers
User authentication
Mobile UI optimization
