# 🚀 RAG-Pipeline for Intelligent Recommendations on Reddit

This project consists of three main components for extracting, embedding, and analyzing Reddit data.

## 📌 Components

### 1️⃣ `extractor.py` - Reddit Data Extractor 📝

**Purpose:** Scrapes data from Reddit using PRAW (Reddit API wrapper)

#### ✨ Key Features:

- 📤 Extracts posts, comments, and user information from specified subreddits
- ⏳ Handles rate limiting with exponential backoff
- 🧹 Cleans and normalizes text content
- 🔄 Processes comments recursively while maintaining thread structure
- ⚡ Uses threading for parallel processing
- 💾 Saves data in JSON format

### 2️⃣ `embeddings.py` - Data Embedding & Storage 📊

**Purpose:** Processes the extracted Reddit data and stores it in a vector database (ChromaDB)

#### ✨ Key Features:

- 🧠 Uses HuggingFace embeddings model (`sentence-transformers`)
- ⚙️ Handles documents asynchronously for better performance
- 🔄 Processes posts, comments, and user data in batches
- 🔑 Generates unique IDs for each document
- 📂 Maintains metadata for all content types
- 🚀 Uses `ThreadPoolExecutor` for parallel processing

### 3️⃣ `app.py` - Streamlit Web Interface 🎨

**Purpose:** Provides a user interface to analyze the processed Reddit data

#### ✨ Key Features:

- 🏷️ Three main modes:
  1. **User Details:** 🧐 Analyze specific Reddit users
  2. **Topic Exploration:** 🔍 Find users discussing specific topics
  3. **Content Synthesis:** 🤖 AI-powered analysis of content
- 🔎 Uses ChromaDB for similarity search
- 🤝 Integrates with Ollama for content synthesis
- ⚡ Caches embeddings for better performance
- 🎛️ Rich UI with expandable sections, metrics, and tabs

## 🛠️ Installation

### 📋 Prerequisites

- 🐍 Python 3.8+
- 🔗 PRAW
- 🏛️ ChromaDB
- 🧠 HuggingFace `sentence-transformers`
- 🌍 Streamlit
- 🤖 Ollama

### ⚙️ Setup

```bash
# Clone the repository
git clone https://github.com/your-repo/reddit-data-pipeline.git
cd reddit-data-pipeline

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`

# Install dependencies
pip install -r requirements.txt

# Configure Reddit API Credentials
export REDDIT_CLIENT_ID="your_client_id"
export REDDIT_CLIENT_SECRET="your_client_secret"
export REDDIT_USER_AGENT="your_user_agent"
```

## 🚀 Usage

### 📝 Extract Reddit Data

```bash
python extractor.py --subreddit example_subreddit --limit 1000
```

### 🔄 Process & Embed Data

```bash
python embeddings.py --input data.json
```

### 🎨 Run Web Interface

```bash
streamlit run app.py
```

## 📜 License

This project is licensed under the MIT License.

---

**👨‍💻 Author:** Kunal Chakane\
**📧 Contact:** [kunalchakane07@gmail.com](mailto\:kunalchakane07@gmail.com)

