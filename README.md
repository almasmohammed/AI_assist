# 📘 Pruju AI – Teaching Assistant App

Pruju AI is a customizable AI teaching assistant that answers student questions using only the provided course materials (such as slides, syllabus, and lecture notes). This ensures accurate and controlled responses aligned with learning objectives.

---

## 🚀 Features

* Answers strictly from course materials
* Supports OpenAI, Azure OpenAI, and Ollama
* Easy customization (no heavy coding required)
* Vector database support using FAISS / Qdrant
* Moodle integration for importing course data

---

## ⚙️ Setup Instructions

### 1. Install Dependencies

```bash
pip install -r requirements.txt
```

Fix dependency issues:

```bash
pip install --upgrade pip==24.0
pip install --upgrade six
```

---

### 2. Configure Environment Variables

Create a `.env` file:

```env
LLM_PROVIDER="openai"
MODEL_NAME="gpt-4"
OPENAI_API_KEY="your-api-key"

CHAT_DATA_FOLDER="prujuai_resources"

TOTAL_MODEL_QUOTA=5
MAX_PROMPT_TOKENS=2000
MAX_CONCURRENCY=2
MAX_QUEUE=10
```

---

### 3. Run the Application

```bash
gradio app.py
```

The app will provide a local URL to access the chatbot interface.

---

## 📂 Adding Your Own Course Materials

1. Copy the folder:

```
prujuai_resources → mycourse_resources
```

2. Update `.env`:

```env
CHAT_DATA_FOLDER="mycourse_resources"
```

3. Customize files:

* `prompt_template.txt` → chatbot behavior
* `examples_ui.txt` → sample questions
* `chat_header.md` / `chat_footer.md` → UI content

---

## 📊 Create Vector Database

Run:

```bash
python3 read_to_vectorstore.py
```

Move generated files:

```
index.faiss  
index.pkl
```

To:

```
CHAT_DATA_FOLDER/faiss_index
```

---

## 🔌 Optional Integrations

### Moodle Integration

```bash
python3 moodle.py
```

### Qdrant Vector Database

```env
VECTOR_STORE="qdrant"
VECTOR_STORE_COLLECTION="my_collection"
VECTOR_STORE_ENDPOINT="localhost"
VECTOR_STORE_API_KEY="your-key"
```

### Ollama (Local Models)

```env
LLM_PROVIDER="ollama"
MODEL_NAME="mistral"
```

Run:

```bash
ollama serve mistral
```

---

## 🚧 Project Status

* Demo-level project
* Not optimized for production use
* Can be extended with more features and UI improvements

---

## 📜 Disclaimer

This project is a modified version used strictly for educational and learning purposes.
All rights and credits belong to the original author(s).

If you are the owner and want this content removed or updated, please contact me.
