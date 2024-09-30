# Retrieval-Augmented-Generation-RAG-System-Medical-Queries
This repository contains the code and documentation for a Retrieval Augmented Generation (RAG) system designed to answer medical queries. The system leverages vector stores to fetch relevant information chunks and advanced language models (LLMs) to provide accurate, relevant responses. In cases where the vector store doesn't provide enough relevant data, the system performs a web search to retrieve additional information.
![image](https://github.com/user-attachments/assets/8d8812da-9f88-40fc-b200-81ffcd27e705)

## Key Features
1. Vector Store Integration: Uses a vector store (ChromaDB) to retrieve relevant medical information chunks based on user queries.
2. Chunk Scoring & Filtering: Retrieved chunks are scored and filtered for relevance before being passed to the LLM.
3. Web Search Fallback: If no relevant chunks are found, the system performs a web search to ensure the user query is answered effectively.
4. Hallucination Check: The system verifies the accuracy and relevance of the LLM-generated responses to prevent hallucination.
5. Non-Medical Query Handling: For non-health-related queries, the system falls back to a different chain to provide responses from the LLM's general knowledge base.
## Stack
1. ChromaDB: For vector store retrieval and storage of medical document embeddings.
2. Tavily AI: To handle web search when the vector store doesn't contain relevant documents.
3. Hugging Face Embeddings: sentence-transformers/all-mpnet-base-v2 model used for document embedding generation.
4. Llama 3 70B: Utilized from Groq for generating accurate and detailed responses to user queries.
5. Langchain: For chaining the retrieval and generation processes.
6. LangGraph: For structuring the flow of retrieval and LLM response generation.
7. Gradio: For building a user-friendly interface for interacting with the system.
## System Workflow
1. User Query: The system takes the user's medical query through the Gradio interface.
2. Vector Store Retrieval: Relevant document chunks are retrieved from the vector store.
3. Chunk Filtering: Retrieved chunks are scored based on relevance and only the most relevant chunks are passed to the LLM.
4. Web Search: If no relevant chunks are found, or if all chunks are irrelevant, a web search is performed to fetch new information.
5. Hallucination Check: The generated answer is checked to ensure it is factually correct and relevant.
6. Response Delivery: The final answer is delivered to the user, ensuring accuracy and relevance.

## Usage
1. Open the Gradio interface in your browser.
2. Enter a medical query in the input field.
3. The system will fetch relevant chunks from the vector store, filter them, and pass them to the LLM.
4. If no relevant information is found, the system will search the web and provide the most accurate response possible.
5. The final response is checked for hallucination and displayed.

