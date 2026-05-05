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

### Find docker image [here](https://hub.docker.com/r/omegabridge/omega-intellect).
#### Image Name: omegabridge/omega-intellect

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
# =========================
# Database
# =========================
DATABASE_URL=postgresql://user:password@host:5432/db

# =========================
# GitLab Integration
# =========================
GITLAB_URL=https://gitlab.com
GITLAB_TOKEN=your_gitlab_token

# =========================
# Security
# =========================
MASTER_ENCRYPTION_KEY=your_44_char_fernet_key

# =========================
# Sync Configuration
# =========================
SYNC_INTERVAL_HOURS=1

# =========================
# Embedding / Processing
# =========================
EMBEDDING_BATCH_SIZE=64

# =========================
# Chat / Context
# =========================
CHAT_HISTORY_LIMIT=50

# =========================
# AI Providers (Optional)
# =========================
OPENAI_API_KEY=
ANTHROPIC_API_KEY=
GEMINI_API_KEY=

# =========================
# Model Configuration (Optional)
# Format:
# model_name:Display Name:type
# =========================

OPENAI_MODELS=gpt-5-20250812:GPT-5:flagship

ANTHROPIC_MODELS=claude-sonnet-4-20250514:Claude Sonnet 4:flagship,claude-3-5-haiku-20241022:Claude 3.5 Haiku:fast

GEMINI_MODELS=gemini-1.5-pro-latest:Gemini 1.5 Pro:flagship,gemini-1.5-flash:Gemini 1.5 Flash:fast
```

## 🔐 Notes

### MASTER_ENCRYPTION_KEY
 - Used to encrypt API tokens securely in the database
 - Must be a Fernet key

**Requirements:**
 - 44-character URL-safe base64 string
 - Ends with =
 - Allowed characters: A-Z a-z 0-9 - _ =
### 🤖 Model Configuration

Each model entry follows this format:

```text
model_id[:Display Name][:tier][:token_limit]
```

---

### 📌 Field Definitions

| Field          | Required | Description                                                     |
| -------------- | -------- | --------------------------------------------------------------- |
| `model_id`     | ✅        | API model name (e.g., `gpt-4o`)                                 |
| `Display Name` | Optional | UI label (defaults to `model_id`)                               |
| `tier`         | Optional | `flagship` 🚀, `fast` ⚡, or `reasoning` 🧠 (defaults to `fast`) |
| `token_limit`  | Optional | Context window size (defaults to `128000`)                      |

---

### 🧩 Examples

```env
# Full format
OPENAI_MODELS=gpt-4o:GPT-4o:flagship:128000,gpt-4o-mini:GPT-4o Mini:fast:128000

# Shorthand (Display Name = model_id)
OPENAI_MODELS=gpt-4o:flagship,gpt-4o-mini:fast

# Minimal (tier = fast, token_limit = 128000)
OPENAI_MODELS=gpt-4o,gpt-4o-mini

# Mixed providers
GEMINI_MODELS=gemini-2.5-pro:Gemini 2.5 Pro:flagship:1000000,gemini-2.5-flash:fast
```

---

### 💡 Notes

* Fields are **optional from left to right** (you can skip trailing values)
* Multiple models must be **comma-separated**
* If `Display Name` is not provided → `model_id` is used
* If `tier` is not provided → defaults to `fast`
* If `token_limit` is not provided → defaults to `128000`

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

