# Homework Helper Agent with MCTS

A Flask-based homework helper that uses LangChain, FAISS, and Google's Generative AI to help students with their homework questions.

## Features

- 📄 **PDF Upload**: Upload your homework notes and documents
- 🤖 **AI-Powered**: Uses Google's Gemini API for intelligent responses
- 🔍 **Semantic Search**: FAISS vector database for finding relevant content
- 🌳 **MCTS**: Monte Carlo Tree Search for exploring multiple solution paths
- 💬 **Multi-mode**: Works with PDF context or general knowledge

## Setup

### 1. Get a Google API Key

1. Visit [Google AI Studio](https://aistudio.google.com/app/apikey)
2. Click "Create API Key"
3. Copy your API key

### 2. Set Up the API Key

**Option A: Using Environment Variable (Recommended)**
```bash
# Windows (PowerShell)
$env:GOOGLE_API_KEY = "your_api_key_here"

# Windows (Command Prompt)
set GOOGLE_API_KEY=your_api_key_here

# Mac/Linux
export GOOGLE_API_KEY=your_api_key_here
```

**Option B: Using .env File**
```bash
# Copy the example file
cp .env.example .env

# Edit .env and replace with your actual key
GOOGLE_API_KEY=your_api_key_here
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the App

```bash
python app.py
```

Then open your browser to: **http://127.0.0.1:5000**

## Usage

1. **Ask Without PDF**: Simply type your question and click "Ask" to get answers using general knowledge
2. **Upload & Ask**: 
   - Click "Choose File" and select a PDF
   - Type your question
   - Click "Ask" - the AI will search your PDF for relevant information

## Troubleshooting

### "Google API key is not set"
- Make sure you've set the `GOOGLE_API_KEY` environment variable
- Restart the app after setting the environment variable

### "Google API key is invalid or suspended"
- Your API key may have expired or been revoked
- Get a new key from https://aistudio.google.com/app/apikey
- Update your environment variable or .env file

### "Permission denied: CONSUMER_SUSPENDED"
- Your Google project has been suspended
- Create a new project in Google Cloud Console
- Generate a new API key

## Technologies Used

- **Flask**: Web framework
- **LangChain**: LLM framework and orchestration
- **Google Generative AI**: Gemini API for responses and embeddings
- **FAISS**: Vector similarity search
- **PyPDF**: PDF document loading
- **MCTS**: Monte Carlo Tree Search for exploration

## Architecture

- `app.py`: Main Flask application
- `static/style.css`: UI styling
- `templates/index.html`: Main interface
- `templates/mcts.html`: MCTS interface

## License

MIT
