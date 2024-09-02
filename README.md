# RAG with LLama 2 - Lecture Transcripts
## Objective
This project's aim is to curate specific responses for prompts based on transcripts from AI related courses.

Lecture transcripts are provided for retrieval, and the LLM is expected to draw upon the given text when responding to select prompts.
In addition, the project uses Langchain for document retrieval and chatbot functionality and ChromaDB to create the vector database.

## Project Overview

The main components of this project include:

1. **Data Loading and Preparation**: Loading text data, splitting it into manageable chunks, and creating embeddings for efficient retrieval.
2. **Model Initialization**: Setting up the models and tokenizers using the Hugging Face Transformers library.
3. **Embedding and Vector Store**: Using a pre-trained sentence transformer model to generate embeddings and store them in a FAISS vector store.
4. **RetrievalQA Chain**: Combining the retrieval capabilities with the generative model to form a RetrievalQA chain for answering queries based on the provided documents.
5. **Evaluation and Testing**: Running queries through the RAG system and evaluating the results.

## Key Features

- **Retrieval-Augmented Generation (RAG)**: Combines retrieval of relevant text chunks from the lecture transcripts with the generative capabilities of the LLaMA 2 model.
- **Chain of Thought (CoT) Prompting**: Enhances response quality by prompting the model to break down its reasoning into intermediate steps.
- **Faithfulness Evaluation**: Measures the faithfulness of the responses to the source documents using cosine similarity, providing a score to assess accuracy

## Key outcomes and areas for further exploration
- Grid search testing of different chunk size values generally yields either 124 or 256 as the optimal sizes for this data
  - Time and resource required to test chunks size via grid search and averaging results across ~20 sample prompts is signifcant (>30 mins); could be improved with more robust pretrained model or adjusted corpus
  - Average for all tested chunk sizes varies between 0.45 and 0.55. This generally underperforms expectations, but can be improved with some prompt engineering. 
- Baselines without Retrieval: Comparing RAG with a baseline model that generates responses without retrieval to highlight the benefits of incorporating a retrieval mechanism.
  - CoT prompts generally performed 5% to 10% better than unadjusted prompts
- Data Augmentation: Enhancing the training data with additional context or related documents to improve the model's understanding and generation capabilities.
- Improved Prompt Engineering: Experimenting with different prompt formats and instructions, like adding few shot along with existing CoT, to guide the model more effectively in generating accurate and relevant responses.
