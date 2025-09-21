# RAG Chatbot for PDF Documents using LangChain and Pinecone 🤖

This project is a complete, end-to-end Retrieval-Augmented Generation (RAG) application. It allows you to chat with your PDF documents by leveraging the power of Large Language Models (LLMs) and a vector database. The system ingests a PDF, processes its content, and uses an open-source model from the Hugging Face Hub to answer questions based on the document's context.

This project was built to demonstrate a practical RAG pipeline for the 2025 South African Budget Speech, but it can be adapted for any PDF document.

## ✨ Features

* **PDF Document Ingestion:** Loads and processes text from PDF files.
* **Text Chunking & Embedding:** Splits documents into manageable chunks and converts them into vector embeddings.
* **Vector Storage:** Uses **Pinecone's** serverless vector database for efficient storage and retrieval.
* **Contextual Retrieval:** Finds the most relevant document chunks related to a user's query.
* **Generative Q&A:** Uses a powerful open-source LLM from **Hugging Face** to generate accurate answers based on the retrieved context.

---

## 🛠️ Tech Stack

* **Python 3.10+**
* **LangChain & LangChain Hugging Face:** The core framework for orchestrating the RAG pipeline.
* **Pinecone:** Serverless vector database for storing embeddings.
* **Hugging Face Hub:** For accessing free, open-source LLMs and embedding models.
* **Jupyter Notebooks:** For a step-by-step, interactive workflow.

---

## ⚙️ Setup and Installation

Follow these steps to set up and run the project locally.

### 1. Clone the Repository
```bash
git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
cd your-repo-name
```

### 2. Create a Virtual Environment
It's highly recommended to use a virtual environment to manage dependencies.

**On Windows:**
```bash
python -m venv venv
venv\Scripts\activate
```

**On macOS/Linux:**
```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies
This project uses a `requirements.txt` file to manage all necessary Python packages.

```bash
pip install -r requirements.txt
```
*(Note: If you don't have a `requirements.txt` file yet, you can create one by running `pip freeze > requirements.txt` after installing your packages.)*

### 4. Set Up Environment Variables
You need to provide your secret API keys for Pinecone and Hugging Face.

1.  In the root directory of the project, create a file named `.env`.
2.  Copy the following content into the `.env` file and replace the placeholder values with your actual keys.

    ```
    # Pinecone API Key
    PINECONE_API_KEY="your_pinecone_api_key_here"
    PINECONE_ENVIRONMENT="your_pinecone_environment_here" # e.g., "us-east-1"
    
    # Hugging Face API Token
    HUGGINGFACEHUB_API_TOKEN="hf_your_hugging_face_token_here"
    ```

* **To get your Pinecone API Key:** Visit [app.pinecone.io](https://app.pinecone.io/).
* **To get your Hugging Face API Token:** Visit [huggingface.co/settings/tokens](https://huggingface.co/settings/tokens).

---

## 🚀 How to Run the Project

The project is divided into two main steps, handled by two separate notebooks.

### Step 1: Ingestion (`setup.ipynb`)

This notebook is responsible for reading your PDF, chunking it, creating embeddings, and storing them in your Pinecone index.

1.  Place the PDF file you want to process inside the `documents/` folder.
2.  Open and run all the cells in the `setup.ipynb` notebook from top to bottom.
3.  This step only needs to be performed **once** for each new document you want to add to the knowledge base.

### Step 2: Querying (`query.ipynb`)

This notebook is where you ask questions and get answers from your document.

1.  Open and run all the cells in the `query.ipynb` notebook.
2.  The last cell contains the `question` variable. You can change the question in this cell and re-run it as many times as you like to chat with your document.

---

## 📂 Project Structure
```
.
├── documents/
│   └── speech.pdf        # Place your source PDF here
├── .env                  # Your secret API keys (created by you)
├── .gitignore            # Files for Git to ignore
├── query.ipynb           # Notebook for asking questions
├── requirements.txt      # Project dependencies
└── setup.ipynb           # Notebook for data ingestion
```
