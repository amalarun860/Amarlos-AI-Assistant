# Amarlos | AI Assistant

> **Work in Progress** — Amarlos is a personal AI assistant currently under development.

Amarlos is a conversational AI assistant built with Python, LangGraph, Google Gemini, and Streamlit.

## Current Features

- **AI-powered conversations:** Uses Google Gemini to generate responses.
- **LangGraph workflow:** Manages the chatbot's message state and execution flow.
- **Multiple conversations:** Start new chats and switch between conversation threads.
- **Conversation checkpointing:** Uses LangGraph's in-memory `MemorySaver` checkpointer.

## Tech Stack

- Python
- LangGraph
- LangChain Core
- Google Gemini
- Streamlit
- python-dotenv

## Project Structure

```text
Amarlos-AI-Assistant/
├── agentic_chatbot.py   # Chatbot workflow and Gemini integration
├── app_thread.py        # Streamlit interface and conversation threads
├── requirements.txt     # Python dependencies
├── .env.example         # Example API key configuration
├── .gitignore           # Files excluded from Git
└── README.md            # Project documentation
```

## Setup and Run

### 1. Clone the Repository

```bash
git clone YOUR_REPOSITORY_URL
cd Amarlos-AI-Assistant
```

Replace `YOUR_REPOSITORY_URL` with your GitHub repository URL.

### 2. Create a Virtual Environment

**Windows:**

```bash
python -m venv .venv
.venv\Scripts\activate
```

**macOS / Linux:**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure the API Key

Create a `.env` file in the project root and add your Google Gemini API key:

```env
GOOGLE_API_KEY=your_google_api_key
```

The `.env` file is excluded from Git. Never commit real API keys or other credentials.

### 5. Start the Application

```bash
streamlit run app_thread.py
```

Open the local URL shown in the terminal.

## How It Works

1. The user submits a message through the Streamlit interface.
2. The app sends the message to the LangGraph chatbot with the current conversation's thread ID.
3. LangGraph passes the conversation messages to the Gemini model.
4. The model's response is added to the conversation state and displayed in the interface.
5. The checkpointer keeps each thread's state available while the application process is running.

## Current Limitation

Conversation state is stored using the in-memory `MemorySaver` checkpointer. It is not permanently saved and will be lost when the application process stops. The conversation thread list is also held in Streamlit session state.

## Future Development

Amarlos is being developed as a personal AI assistant. More capabilities may be added as the project evolves.

---

**Amarlos | AI Assistant** — A personal project under active development.
