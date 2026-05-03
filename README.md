# 🧠 OmegaIntellect

### *Your Codebase, Fully Understood.*

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Status](https://img.shields.io/badge/status-active-success.svg)
![AI Powered](https://img.shields.io/badge/AI-powered-purple.svg)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-required-blue)

> Built for teams who need to understand complex codebases—fast.

---

## 🚀 What is OmegaIntellect

**OmegaIntellect** is an AI-powered code intelligence platform that helps engineering teams **search, understand, and analyze codebases in real time**.

It goes beyond traditional code search by combining **structural parsing, semantic understanding, and contextual reasoning** to deliver **accurate, meaningful insights from your code**.

Find docker image [here](https://hub.docker.com/r/omegabridge/omega-intellect).

---

## ✨ Core Capabilities (Search • Understand • Generate)

### 🧠 Structural Code Understanding

* Parses code into:

  * Functions
  * Classes
  * Logical units
* Eliminates noisy, line-based chunking

👉 Ensures clean, meaningful context

---

### 🔎 Hybrid Search

* Combines:

  * Semantic understanding
  * Keyword & symbol matching
* Works even when queries are vague

👉 Ask naturally → get precise results

---

### 🔗 Context-Aware Retrieval

* Automatically follows:

  * Imports
  * Dependencies
* Builds a connected execution flow

👉 No more isolated snippets

---

### 🤖 Intelligent Query Understanding

* Converts natural language into code-aware queries
* Improves retrieval accuracy automatically

---

### 📊 Smart Context Filtering

* Removes low-relevance results
* Prioritizes high-signal code

👉 Cleaner, more useful answers

---

## 🎯 Why OmegaIntellect

| Capability         | Traditional Tools | OmegaIntellect   |
| ------------------ | ----------------- | ---------------- |
| Code Understanding | Text-based        | AST-based        |
| Search             | Keyword only      | Hybrid           |
| Context            | Limited           | Dependency-aware |
| Signal Quality     | Noisy             | Filtered         |

---

## ⚡ How to Use

```text
1. Connect your repository (via GitLab token)
2. Let OmegaIntellect index your codebase
3. Ask questions in natural language
```

---

### 💬 Example

```text
Q: How is authentication implemented?

→ Returns:
- Relevant files
- Code snippets with line numbers
- Clear explanation of flow
```

---

## ⚡ Quick Start

### ✅ Requirements

* PostgreSQL with `pgvector` and `vectorscale` extensions
* GitLab access token


---

### ▶️ Run
#### 1. Create `.env` file
```env
# Database
DATABASE_URL=postgresql://user:password@host:5432/db

# GitLab Integration
GITLAB_URL=https://gitlab.com
GITLAB_TOKEN=your_gitlab_token

# Security
MASTER_ENCRYPTION_KEY=your_secure_key

# Sync Configuration
SYNC_INTERVAL_HOURS=1

# Embedding / Processing
EMBEDDING_BATCH_SIZE=64

# Chat / Context
CHAT_HISTORY_LIMIT=50

# Optional AI Providers (use any one or multiple)
OPENAI_API_KEY=
ANTHROPIC_API_KEY=
GEMINI_API_KEY=
```

#### 2. Run using Docker image
```bash
docker run -it --env-file .env -p 8501:8501 omegabridge/omega-intellect
```

---

#### 3. Access the application

👉 Open in browser:

```
http://localhost:8501
```
---

## 🧠 How It Works

```text
GitLab → AST Parsing → Embeddings → PostgreSQL (pgvector)
                                   ↓
                           Hybrid Retrieval
                                   ↓
                           OmegaIntellect AI
                                   ↓
                                Chat UI
```

OmegaIntellect:

* Understands code structure
* Finds relevant logic
* Expands context via dependencies
* Filters noise
* Generates clear answers

---

## 💼 Use Cases

* 🔍 Understand large codebases instantly
* 🐞 Debug production issues faster
* 🚀 Accelerate developer onboarding
* 🔗 Trace logic across services
* 📚 Prepare for automated documentation (coming soon)

---

## 🚧 Roadmap

Built with a long-term vision to become the intelligence layer for all codebases.

### 📝 AI-Powered Documentation (Coming Soon)

* Generate **project-level documentation**
* Auto-create **file summaries**
* Add **function & class-level explanations**
* Inject **inline comments into code**

```python
def authenticate_user(token):
    """
    Validates the token and returns the associated user.
    Raises an error if invalid or expired.
    """
```

👉 Designed to make even large, undocumented codebases instantly understandable

---

### 🧠 Deeper Intelligence

* Cross-repository reasoning
* Architecture-level insights

---

## 🧠 Final Thought

OmegaIntellect is not just a tool.

It’s your **codebase intelligence layer**—helping teams:

* Move faster
* Understand deeper
* Build with confidence

