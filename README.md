# Intelligent Clinical Knowledge Assistant

An enterprise-grade Retrieval-Augmented Generation (RAG) application designed to provide healthcare professionals with intelligent access to clinical knowledge. The platform enables physicians, nurses, and healthcare teams to retrieve, summarize, and contextualize information from clinical guidelines, medical literature, hospital protocols, treatment documentation, and healthcare knowledge repositories using natural language queries. Built with hybrid retrieval, advanced reranking, and citation enforcement, the system delivers accurate, context-aware, and source-backed clinical insights for informed healthcare decision-making.

## 🚀 Key Features

* **Clinical Knowledge Retrieval**: Enables intelligent search across clinical guidelines, treatment protocols, medical literature, hospital policies, and healthcare documentation using natural language.
* **Hybrid Retrieval**: Combines BM25 keyword search with vector-based semantic search to maximize retrieval accuracy and recall.
* **Cross-Encoder Reranking**: Improves response relevance by prioritizing the most contextually appropriate clinical documents before answer generation.
* **Citation Enforcement**: Every generated response is backed by trusted clinical sources, ensuring transparency, traceability, and confidence in healthcare recommendations.
* **Production-Ready Architecture**: Built with FastAPI, Dependency Injection, and a modular architecture for scalability, maintainability, and enterprise deployment.
* **Evaluation Pipeline**: Includes automated quality evaluation to validate retrieval accuracy and response quality before deployment.

## 🛠️ Tech Stack

* **Framework:** FastAPI (Python 3.11)
* **RAG Engine:** LlamaIndex
* **Vector Database:** Qdrant (Local/Remote)
* **LLM Providers:** Ollama, OpenAI, Azure, Gemini, SageMaker
* **User Interface:** Gradio

## 🚦 Getting Started

### Installation

```bash
# Install dependencies with production extras
poetry install --extras "ui llms-ollama embeddings-ollama vector-stores-qdrant"
```

### Running the Application

To launch the Intelligent Clinical Knowledge Assistant using the default production configuration:

```bash
# Set profiles and start
$env:PGPT_PROFILES="ollama"
poetry run python -m production_rag
```

## ⚙️ Configuration

Configuration is managed through YAML profiles located in the project root.

* `settings.yaml` – Global application configuration.
* `settings-ollama.yaml` – Configuration for Ollama-based local LLM execution.
* `settings-local.yaml` – Configuration for local LlamaCPP/HuggingFace execution.

The configuration supports flexible customization of language models, vector databases, retrieval settings, and runtime parameters for different deployment environments.

## 🧪 Evaluation

Run the evaluation pipeline to validate retrieval relevance, citation accuracy, and overall response quality before deployment.

```bash
python production_rag/rag/evaluation/evaluator.py --threshold 0.7
```

## 🛡️ License

This project is licensed under the Apache-2.0 License.
