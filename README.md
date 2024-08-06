# RAG Testing with Llama 3.1
## Objective
This project's aim is to curate specific responses for prompts based on transcripts from AI related courses.

Lecture transcripts are provided for retrieval, and each pre trained LLM is expected to draw upon the given text when responding to select prompts.
In addition, the project uses Langchain and ChromaDB, and neither LLM receives fine tuning. This project can serve as a springboard for other tasks, including the optimization of chunk size in the corpus of retrieval documents.

## Project Overview

The main components of this project include:

1. **Data Loading and Preparation**: Loading text data, splitting it into manageable chunks, and creating embeddings for efficient retrieval.
2. **Model Initialization**: Setting up the models and tokenizers using the Hugging Face Transformers library.
3. **Embedding and Vector Store**: Using a pre-trained sentence transformer model to generate embeddings and store them in a FAISS vector store.
4. **RetrievalQA Chain**: Combining the retrieval capabilities with the generative model to form a RetrievalQA chain for answering queries based on the provided documents.
5. **Evaluation and Testing**: Running queries through the RAG system and evaluating the results.


## Areas for further exploration
- Alternative Retrieval Techniques: Testing different retrieval methods, such as Dense Passage Retrieval (DPR) or BM25, to see how they affect the quality of the final generated responses.
- Baselines without Retrieval: Comparing RAG with a baseline model that generates responses without retrieval to highlight the benefits of incorporating a retrieval mechanism.
- Data Augmentation: Enhancing the training data with additional context or related documents to improve the model's understanding and generation capabilities.
- Prompt Engineering: Experimenting with different prompt formats and instructions, such as few shot and chain of thought learning, to guide the model more effectively in generating accurate and relevant responses.
