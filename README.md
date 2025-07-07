# Advanced RAG Patterns with LangGraph
### Agentic RAG, Corrective RAG, Adaptive RAG

This repository contains Jupyter notebooks demonstrating sophisticated Retrieval-Augmented Generation (RAG) patterns implemented using **LangGraph**. These examples showcase how to build more intelligent and robust RAG systems by incorporating advanced decision-making, self-correction, and dynamic retrieval strategies.

## Table of Contents

1.  [Introduction](#introduction)
2.  [Notebooks Overview](#notebooks-overview)
    * [Adaptive RAG](#adaptive-rag)
    * [Agentic RAG](#agentic-rag)
    * [Corrective RAG](#corrective-rag)
3.  [Setup and Installation](#setup-and-installation)
4.  [Usage](#usage)
5.  [Contributing](#contributing)
6.  [License](#license)

---

## 1. Introduction

Traditional RAG systems retrieve documents and pass them to an LLM for answer generation. These notebooks explore advanced RAG architectures that enhance performance by:

* **Dynamically choosing retrieval sources:** Deciding between internal knowledge bases and external web search.
* **Self-correction and grading:** Evaluating retrieved content and generated answers for relevance and factual grounding.
* **Query optimization:** Rewriting queries for better retrieval results.
* **Agentic behavior:** Allowing the LLM to make decisions and take actions in a loop.

Each notebook provides a practical, code-driven example of these patterns.

---

## 2. Notebooks Overview

### Adaptive RAG

* **File:** `Adative_RAG.ipynb`
* **Concept:** Implements a RAG system that can **adaptively choose between a vector store and web search** based on the user's question. It includes components for routing questions and grading the relevance of retrieved documents.
* **Key Features:** LLM-powered query routing, document relevance grading, web search integration (Tavily).
* **Use Case:** Building RAG systems that can handle both domain-specific and general knowledge queries effectively.

### Agentic RAG

* **File:** `Agentic_RAG.ipynb`
* **Concept:** Demonstrates an **agent-driven RAG workflow** where the LLM acts as an agent, deciding when to retrieve information, how to rephrase queries, and ultimately generating an answer. It showcases a more dynamic and interactive RAG loop.
* **Key Features:** LLM as an agent, tool-calling for retrieval, conversational history management.
* **Use Case:** Creating more autonomous and flexible RAG applications that can engage in multi-turn interactions and make informed decisions.

### Corrective RAG (CRAG)

* **File:** `Corrective_RAG.ipynb`
* **Concept:** Implements a version of **Corrective RAG**, a strategy that incorporates **self-reflection and self-grading** on retrieved documents and generated answers. If initial retrieval is insufficient, it can re-evaluate and seek additional information via web search.
* **Key Features:** Document relevance grading, query re-writing for web search, hallucination grading, answer grading.
* **Use Case:** Enhancing RAG robustness by filtering irrelevant information and ensuring generated answers are grounded and address the question.

---

## 3. Setup and Installation

To run these notebooks, you'll need to set up your Python environment and install the necessary libraries.

1.  **Clone the repository (if applicable):**
    ```bash
    git clone https://github.com/Abubakar0011/RAG-with-LangGraph.git
    cd <repository_name>
    ```

2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate # On Windows: .\venv\Scripts\activate
    ```

3.  **Install dependencies:**
    These notebooks rely on `langchain`, `langgraph`, `pydantic`, `python-dotenv`, `langchain-openai`, and `langchain-community` (for `WebBaseLoader`, `Chroma`, `TavilySearchResults`).

    ```bash
    pip install langchain langgraph pydantic python-dotenv langchain-openai langchain-community jupyter ipykernel
    ```

4.  **Set up API Keys:**
    These notebooks require API keys for Large Language Models (LLMs) and web search.
    * Create a `.env` file in the root directory of your project.
    * Add your API keys to this file. For example:
        ```
        OPENAI_API_KEY="your_openai_api_key_here"
        TAVILY_API_KEY="your_tavily_api_key_here"
        GROQ_API_KEY="your_groq_api_key_here" # If using Groq models
        ```
    * Ensure `load_dotenv()` is called in your notebooks.

---

## 4. Usage

1.  **Start Jupyter Notebook:**
    ```bash
    jupyter notebook
    ```
2.  **Navigate:** Open the desired `.ipynb` file in your browser.
3.  **Run Cells:** Execute the cells sequentially to understand the workflow and observe the RAG patterns in action.

---

## 5. Contributing

Contributions are welcome! If you have new RAG patterns to demonstrate or improvements to existing ones, feel free to open an issue or submit a pull request.

---