# HR Policy RAG Chatbot

A Retrieval-Augmented Generation (RAG) chatbot that answers employee questions using information from an HR Policy document.

The project retrieves the most relevant sections of the HR policy using semantic similarity and then uses the Llama 3.2 model through Ollama to generate an answer based only on the retrieved context.

## Project Overview

This project demonstrates a basic RAG pipeline:

**HR Policy PDF → Text Extraction → Chunking → Embeddings → FAISS Vector Search → Relevant Context → Llama 3.2 → Answer**

The chatbot is designed to avoid making assumptions and answers only from the information available in the HR policy.

## HR Policy Topics

The HR policy document contains information about:

1. Casual Leave
2. Sick Leave
3. Work From Home
4. Working Hours
5. Annual Leave
6. Leave Approval
7. Public Holidays
8. Employee Benefits
9. Performance Review
10. Resignation Notice Period

## Technologies Used

* Python
* Jupyter Notebook
* Sentence Transformers
* FAISS
* NumPy
* Ollama
* Llama 3.2:3b

## How the RAG System Works

### 1. Load the HR Policy

The HR Policy PDF is used as the knowledge source.

### 2. Text Chunking

The extracted policy text is divided into smaller chunks so that relevant sections can be retrieved efficiently.

### 3. Generate Embeddings

Sentence Transformers converts the text chunks into numerical vector representations.

### 4. Store Embeddings

FAISS is used as the vector index for similarity search.

### 5. User Query

The user's HR-related question is converted into an embedding.

### 6. Retrieve Relevant Information

FAISS searches the vector index and retrieves the top 2 most relevant policy chunks.

### 7. Generate the Answer

The retrieved chunks are provided as context to Llama 3.2 through Ollama.

The chatbot is instructed to answer only using the provided context.

## Example Questions

You can ask questions such as:

* How many casual leaves are employees eligible for?
* How many sick leaves are available per year?
* How many days can employees work from home?
* What are the normal working hours?
* How many annual leaves do employees receive?
* How many public holidays does the company observe?
* How often are performance reviews conducted?
* What is the resignation notice period?

## Important RAG Rule

The chatbot follows this rule:

> Answer the user's question using only the provided HR policy context.

If the retrieved context does not directly answer the question, the chatbot responds:

**"I don't know based on the provided HR policy."**

## Project Structure

```text
Hr-policy-rag-chatbot/
│
├── HR_Policy_RAG_Chatbot.ipynb
├── HR_Policy.pdf
├── README.md
└── requirements.txt
```

## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/Hr-policy-rag-chatbot.git
```

Move into the project directory:

```bash
cd Hr-policy-rag-chatbot
```

Install the Python dependencies:

```bash
pip install -r requirements.txt
```

## Ollama Setup

This project uses Ollama to run the Llama 3.2 model locally.

Install Ollama and then download the required model:

```bash
ollama pull llama3.2:3b
```

Make sure Ollama is running before executing the RAG chatbot code.

## Running the Project

Open the Jupyter Notebook:

```bash
jupyter notebook
```

Then open:

```text
HR_Policy_RAG_Chatbot.ipynb
```

Run the notebook cells in order.

## Future Improvements

Possible improvements include:

* Adding a web-based chatbot interface
* Adding conversation history
* Improving document chunking
* Adding metadata filtering
* Supporting multiple HR policy documents
* Adding source citations to answers
* Deploying the chatbot as a web application
* Adding evaluation metrics for retrieval and answer quality

## Disclaimer

This project is created for learning and demonstration purposes. The HR policy content is a sample policy document and should not be treated as official employment advice.
