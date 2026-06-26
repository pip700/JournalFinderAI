# 📚 JournalFinder AI Journal Recommender

JournalFinder AI is a Docker-based Streamlit application that recommends the most suitable scientific journals for research manuscripts using semantic similarity, AI-assisted manuscript analysis, and live publication data from OpenAlex.

---

## Features

- 📄 Recommend journals from manuscript title and abstract
- 🤖 Optional AI manuscript analysis using Ollama
- 🔍 Semantic similarity search with scientific embeddings
- 📚 Live publication retrieval from OpenAlex
- 📊 Interactive Streamlit dashboard
- ⚡ GPU acceleration (NVIDIA CUDA)
- 🐳 Docker-based deployment

---

## Prerequisites

- Docker
- NVIDIA Container Toolkit (optional, for GPU acceleration)
- Ollama (optional, for AI-assisted features)

---

# Quick Start

## 1. (Optional) Install Ollama

Download and install Ollama:

https://ollama.com/download

Pull a lightweight model:

```bash
ollama pull llama3.2:3b
```

Start the Ollama server:

```bash
ollama serve
```

Default server address:

```
http://localhost:11434
```

If Ollama is not running, JournalFinder AI automatically falls back to keyword-based retrieval.

---

## 2. (Optional) Configure OpenAlex

JournalFinder AI retrieves publication data from **OpenAlex**.

OpenAlex is **free to use** and **does not require an API key**.

For higher and more reliable request limits, simply provide your email address (for example, a Gmail account) to use the **OpenAlex Polite Pool**.

Example:

```text
dhairiyaa@gmail.com
```

You may also provide a Premium API Key if available.

More information:

https://docs.openalex.org/

---

## 3. Run JournalFinder AI

```bash
sudo docker run \
    --rm \
    -v $(pwd):/workspace \
    -p 8501:8501 \
    ghcr.io/pip700/journalfinderai:v1
```

> **Linux users:** If `host.docker.internal` is unavailable, replace it with your host machine's IP address (for example `http://192.168.1.100:11434`).

---

## 4. Open the Application

Open your browser and visit:

```
http://localhost:8501
```

---

# Usage

1. Enter the manuscript title.
2. Paste the manuscript abstract.
3. (Optional) Add keywords.
4. Click **Analyze Manuscript**.
5. Review the ranked journal recommendations.

If Ollama is enabled, the application can also:

- Generate manuscript summaries
- Expand search queries
- Suggest research keywords
- Identify research fields
- Estimate manuscript novelty

---

# Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `OLLAMA_URL` | Ollama server URL | Optional |
| `OLLAMA_MODEL` | Ollama model name | Optional |
| `OPENALEX_EMAIL` | Email for OpenAlex Polite Pool | Optional |
| `OPENALEX_API_KEY` | OpenAlex Premium API Key | Optional |

---

# Recommended Ollama Models

| Model | Size | Recommendation |
|------|------|----------------|
| `llama3.2:3b` | ~2 GB | ⭐ Recommended |
| `qwen2.5:3b` | ~2 GB | Fast multilingual |
| `llama3.1:8b` | ~5 GB | Higher quality |
| `mistral:7b` | ~4 GB | Strong reasoning |

---

# GPU Support

Verify NVIDIA GPU support:

```bash
nvidia-smi
```

Run the container with GPU acceleration:

```bash
--gpus all
```

---

# Technologies

- Streamlit
- Python
- Docker
- OpenAlex API
- Ollama
- Llama 3.2
- Sentence Transformers
- SPECTER2 Embeddings
- Cross-Encoder Reranking

---

# License

This project is intended for research and educational purposes only.
