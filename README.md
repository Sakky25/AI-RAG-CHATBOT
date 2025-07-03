README.md – Legal RAG Chatbot

🧠 Project Overview

This project is a RAG-based (Retrieval Augmented Generation) chatbot trained on the eBay User Agreement. It uses semantic search with FAISS and Mistral-7B for generation. Users can ask legal queries and receive context-aware responses in real-time.

📂 Folder Structure

AI-RAG-Chatbot/
├── app.py
├── chunks/                      # Chunked eBay document in JSON format
├── data/                        # Original eBay agreement file
├── notebooks/                   # (Optional) Testing notebooks
├── src/                         # Core logic modules
│   ├── embedding.py             # Chunk & embed text
│   ├── retriever.py             # FAISS-based semantic search
│   ├── generator.py             # LLM generation using Mistral-7B
│   └── rag_pipeline.py         # End-to-end RAG flow
├── vectordb/                    # FAISS vector DB
├── requirements.txt             # Dependency list
└── README.md

⚙️ Setup Instructions

1. Clone the Repository

git clone https://github.com/your-repo/AI-RAG-Chatbot.git
cd AI-RAG-Chatbot

2. Install Dependencies

pip install -r requirements.txt

3. Prepare the Data

Place your document in: data/ebay_user_agreement.txt

Run:

python src/embedding.py  # Generates chunks and FAISS index

4. Launch the App

streamlit run app.py

💡 How It Works

Chunking: Splits the eBay agreement into overlapping segments.

Embedding: Uses all-MiniLM-L6-v2 to encode chunks.

Storage: Stores them in FAISS index.

RAG: Retrieves relevant chunks and prompts Mistral-7B with them.

Streaming: Answers are streamed to the user using Streamlit.

🧪 Sample Queries

Q: What happens if I don’t follow eBay’s rules?
Q: Is arbitration mandatory in eBay disputes?
Q: Can eBay suspend my account?
Q: How does eBay handle copyright claims?

🤖 Model

Embedding Model: all-MiniLM-L6-v2 (SentenceTransformers)

Generator Model: mistralai/Mistral-7B-Instruct-v0.1

Vector Store: FAISS

📌 Notes

Make sure faiss_index.index is generated before running app.py

Use GPU for Mistral-7B

Customize your prompts in generator.py

📧 Contact

Made by Sakshat Vyas – Indore, India
Reach out via LinkedIn or email.
