# Architecture Implementation: Libraries & Frameworks Reference
# Recommended stack optimized for Python-based high-performance AI deployment
# All listed packages are real, installable dependencies (e.g., via uv or `pip`).

## 1. Query Interpretation & Analysis Module (Blue)
spacy                 # Core NLP pre-processing (Tokenization, Stopword Removal).
transformers          # Hugging Face library for zero-shot classification and intent detection.
scikit-learn          # Fallback framework for lightweight classification generators.

## 2. Agent Orchestrator & Source Selection (Green)
langchain             # Core framework for LLM agent routing and tool binding.
langgraph             # Extension for managing complex, stateful multi-agent orchestration.
n8n                   # Automated workflow engine ideal for orchestrating the Data Ingestion Pipeline.

## 3. Data Retrieval Layer & Generation (Yellow)
# RAG / Unstructured Data Pathway
llama-index           # Framework explicitly designed for data chunking, parsing, and RAG architectures.
sentence-transformers # Local generation of dense vector embeddings for chunked data.
faiss-gpu             # High-performance, CUDA-accelerated vector database for Semantic/Cosine similarity search.
chromadb              # Alternative lightweight, persistent vector database.

# Structured Data Pathway (SQL)
sqlalchemy            # Database toolkit and Object Relational Mapper for handling Simple SQL Queries.
psycopg2-binary       # High-performance PostgreSQL database adapter.

# LLM Generation / Inference Engine
vllm                  # High-throughput, memory-efficient serving engine for self-hosted LLMs.
openai                # Client library if utilizing proprietary, cloud-based LLM APIs.

## 4. Evidence Validation & Response Generation Module (Red & Light Blue)
# Validation (LLM-as-a-Judge / Consistency Checks)
ragas                 # Evaluation framework specifically for checking RAG Correctness and Relevance.
trulens-eval          # Tool for validating if retrieved context provides "Sufficient Data".

# Final Response Guardrails (Safety, Policy, Tone)
nemoguardrails        # NVIDIA framework for enforcing IT Policy Compliance and Data Sovereignty rules.
guardrails-ai         # Library for strict output formatting, tone checking, and verifying citations.

## 5. API Interface (System to User)
fastapi               # High-speed web framework for compiling the system into an accessible API endpoint.
uvicorn               # Lightning-fast ASGI server implementation to run the FastAPI application.
