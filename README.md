📚 Book-Based Q&A System with Hybrid RAG & Advanced Prompt Engineering

This project lets you upload a PDF book 📂 and ask smart questions 🔍.
It uses Hybrid RAG (Retrieval-Augmented Generation) combining BM25 (keyword search) and FAISS (semantic search) to find the best parts of the book.
Then, it uses T5 (a transformer model) to generate detailed, intelligent answers. 🚀

✨ Features

Upload any PDF file (like books, notes, documents).
Hybrid Retrieval: Combines BM25 (sparse) and FAISS (dense) retrieval.
Smart Answer Generation using T5-base model.
Specially tuned to handle:
Definitions
Explanations
Summaries
Lists and Steps
Easy-to-use Gradio Web Interface.
📦 Technologies Used

Python
PyTorch (deep learning)
HuggingFace Transformers (T5 model)
Sentence Transformers (MiniLM-L6-v2 model)
BM25 (keyword-based search)
FAISS (semantic vector search)
Gradio (web app UI)
PyPDF (PDF reading)
🔥 Installation

# Clone this repository
git clone https://github.com/your-repo/book-qa-hybrid-rag.git
cd book-qa-hybrid-rag

# Install dependencies
pip install torch transformers gradio pypdf huggingface_hub faiss-cpu rank_bm25 sentence-transformers
✅ Also authenticate to HuggingFace Hub if needed:

python from huggingface_hub import notebook_login notebook_login()


⚙️ How It Works

1. **Upload a PDF** file.
2. The system **reads and splits** the text into smaller chunks (512 characters).
3. **Create BM25** (for keyword search) and **FAISS** (for meaning search) indexes.
4. When you ask a question:
   - It retrieves top matching chunks using FAISS.
   - It **re-ranks** them using BM25 for more accurate matching.
5. A **custom prompt** is created based on your question type ("what", "explain", "summarize", etc.).
6. The **T5 model** generates a natural, detailed answer.
7. All of this is available in a **Gradio web app**.

🚀 Running the App

```bash
python your_script_name.py
It will open a Gradio app link like:

Running on local URL:  http://127.0.0.1:7860/
✅ You can also share it publicly with others!

📈 Folder Structure

📁 project/
 ├── ai1.py                  # Main script (all code)
 ├── requirements.txt         # Python packages (optional)
 ├── README.md                # This file
 └── 📂 outputs/              # (optional) for saving results
🧠 Models Used

Model	Purpose
T5-Base	Text-to-Text Generation (answer generation)
all-MiniLM-L6-v2	Sentence Embedding (meaning-based search)
BM25	Keyword search
FAISS	Fast vector similarity search
📚 Example Usage

Task	How the system behaves
"What is photosynthesis?"	Gives a clear definition
"Explain black holes"	Writes a detailed explanation
"Summarize Chapter 2"	Summarizes the main ideas
"List types of ecosystems"	Lists different types with short descriptions
"Steps of water cycle"	Gives a step-by-step list
💬 Credits

HuggingFace (T5, Sentence Transformers)
Facebook AI (FAISS)
Gradio Team (UI library)
📌 Notes

Only supports PDFs** currently.
Depends on GPU** if available (else CPU will work but slower).
Works best** when the uploaded document is well-scanned and text-based.
✨ Feel free to fork, modify, and improve it!
Built with ❤️ for learning and exploration.
