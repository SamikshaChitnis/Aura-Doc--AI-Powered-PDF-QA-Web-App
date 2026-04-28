# AuraDoc 📄

> Upload a PDF. Ask questions. Get instant AI-powered answers.

AuraDoc is a Streamlit web app that lets you chat with your PDF documents. Powered by **Groq's LLaMA 3.1** model, it reads your document and answers questions based strictly on its content — no hallucinations, no guessing.

---

## What It Does

- 📎 Upload any PDF and start a conversation with it
- 💬 Ask questions in plain English and get precise answers
- 🔐 Secure user accounts with encrypted passwords
- 🗂️ All your chats are saved — pick up where you left off
- 🗑️ Manage and delete past chats from the sidebar
- 🐳 Runs fully containerized with Docker — one command setup

---

## Tech Stack

| Layer | Technology |
|---|---|
| UI | Streamlit |
| AI Model | Groq API — LLaMA 3.1 8B Instant |
| Database | MongoDB |
| PDF Parsing | pdfplumber |
| Authentication | bcrypt |
| Containerization | Docker + Docker Compose |

---

## Getting Started

### Prerequisites

- [Docker](https://docs.docker.com/get-docker/) installed on your machine
- A free Groq API key → [Get one here](https://console.groq.com/)

---

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/AuraDoc.git
cd AuraDoc
```

---

### 2. Set up your API key

```bash
cp .env.example .env
```

Open the `.env` file and paste your Groq API key:

```
GROQ_API_KEY=your_groq_api_key_here
```

> ⚠️ Never share or commit your `.env` file. It is already listed in `.gitignore`.

---

### 3. Run the app

```bash
docker-compose up --build
```

Then open your browser and go to → **http://localhost:8501**

---

## Running Without Docker

Make sure you have **Python 3.10+** and **MongoDB** running locally.

```bash
pip install -r requirements.txt
streamlit run app.py
```

> If running locally, update the MongoDB connection string in `app.py` from `mongodb://mongodb:27017/` to `mongodb://localhost:27017/`

---

## Project Structure

```
AuraDoc/
├── app.py                 # Main application
├── requirements.txt       # Python dependencies
├── Dockerfile             # Docker image config
├── docker-compose.yml     # Full stack setup (app + MongoDB)
├── .env.example           # API key template (safe to commit)
└── .gitignore             # Files excluded from Git
```

---

## Environment Variables

| Variable | Required | Description |
|---|---|---|
| `GROQ_API_KEY` | ✅ Yes | Your API key from [console.groq.com](https://console.groq.com/) |

---

## How It Works

1. **Register / Login** — Create an account securely
2. **Upload a PDF** — Use the sidebar to upload any PDF file
3. **Start chatting** — Type your question in the chat box
4. **Get answers** — The AI reads your document and responds based on its content
5. **Come back later** — All chats are saved and accessible from the sidebar

---

## Security

- Passwords are hashed using **bcrypt** before storage — never stored in plain text
- The Groq API key is loaded from environment variables — never hard-coded
- `.env` is excluded from version control via `.gitignore`

---

## License

MIT License — free to use, modify, and distribute.

---

## Author

Built by Samiksha Chitnis.
