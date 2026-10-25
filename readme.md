# Synapse: Custom RAG Chatbot

## 📌 Overview
An end-to-end Retrieval-Augmented Generation (RAG) pipeline built entirely from scratch. This project ingests custom text documents, chunks and embeds them into a vector space, and uses the Gemini API to answer user queries based strictly on the provided context.

## 🚀 Key Features
- **Custom Chunking:** Splits text with overlap to preserve semantic context.
- **Semantic Search:** Uses `all-MiniLM-L6-v2` embeddings and normalized cosine similarity to retrieve the Top-K most relevant chunks.
- **Hallucination Guardrails:** Implements a strict similarity threshold. If the user asks a question outside the document's scope, the bot refuses to answer.
- **Source Citation:** Appends exact page/chunk references to every generated answer.
- **Resilience:** Implements exponential backoff for API rate limits.

## 📊 Evaluation Results
I validated the architecture using an 8-question test set (direct, split, and absent queries). 
*   **Plain LLM (No Context):** 0.0% Accuracy (hallucinated on every question).
*   **RAG Bot (With Context):** 87.5% Accuracy.

## 🛠️ Tech Stack
- **Python**
- **Google Colab** (Development)
- **Sentence-Transformers** (Embeddings)
- **Gemini API** (Generation)
- **Gradio** (UI)

## 📂 How to Run
1. Clone the repository.
2. Install dependencies: `pip install -r requirements.txt`
3. Set your Gemini API key: `export GEMINI_API_KEY="your_api_key"`
4. Run the notebook `Synapse_RAG_Pipeline.ipynb` to launch the Gradio interface.