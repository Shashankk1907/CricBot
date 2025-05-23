# CricBot - Chatbot by RAG

This project is a command-line chatbot that answers questions about the 2022 T20 World Cup cricket tournament using a Retrieval-Augmented Generation (RAG) approach. It leverages LangChain, HuggingFace embeddings, ChromaDB, and an LLM served via OpenRouter to provide detailed and specific answers based on tournament data.

## Features

- Ask questions about player stats, match results, and team information from the 2022 T20 World Cup.
- Uses a RAG model combining vector search with a large language model.
- Processes cricket data from CSV files into searchable documents.
- Interactive command-line chatbot interface.

## Setup Instructions

1. Clone or download the project files.

2. Install the required Python packages:

```bash
pip install langchain langchain-community chromadb tiktoken python-dotenv openai pandas
```

3. Obtain an OpenRouter API key by signing up at [OpenRouter](https://openrouter.ai/).

4. Set your OpenRouter API key in the notebook by replacing the placeholder:

```python
OPENROUTER_API_KEY = "your_openrouter_api_key_here"
```

5. Ensure the following CSV files are present in the same directory as the notebook:

- `player_info.csv`
- `batting_summary.csv`
- `bowling_summary.csv`
- `match_results.csv`

These files contain the tournament data used by the chatbot.

## Running the Chatbot

Run the notebook in a Jupyter or Colab environment. The chatbot function will start a command-line interface where you can type questions about the 2022 T20 World Cup.

Type your question and press Enter to get an answer. Type `quit` to exit the chatbot.

## How It Works

- The notebook loads and processes cricket data from CSV files into LangChain Document objects.
- Documents are split into chunks and embedded using HuggingFace sentence transformers.
- Embeddings are stored in ChromaDB for efficient similarity search.
- A retriever fetches relevant documents based on user queries.
- The retrieved context is passed to an LLM via OpenRouter with a custom prompt template.
- The LLM generates detailed answers based on the retrieved context.

## Data Description

- **player_info.csv**: Player details including name, team, playing role, batting and bowling styles.
- **batting_summary.csv**: Batting performance summaries per match.
- **bowling_summary.csv**: Bowling performance summaries per match.
- **match_results.csv**: Match outcomes including teams, winner, margin, date, and venue.

## Notes

- The first run may take some time to initialize embeddings and vector store.
- Ensure all required CSV files are available before running.
- The OpenRouter API key is required for the LLM to function.

---

Enjoy exploring the 2022 T20 World Cup with this intelligent chatbot!
