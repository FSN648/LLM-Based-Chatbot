## Agentic LLM Chatbot with LangGraph and RAG
This project implements an agentic chatbot built around an open-weight large language model as its core reasoning engine. Rather than fine-tuning the model, the focus is on treating it as a powerful black box and orchestrating it with tools and routing logic to handle diverse user queries.
On receiving a user message, the chatbot dynamically routes it down one of three paths:

1-Web search: queries a search engine to retrieve up-to-date or external information<br>
2-Document retrieval (RAG): searches and retrieves relevant passages from a local reference knowledge base<br>
3-Direct response: answers general queries directly using the LLM's own knowledge<br>

Once the appropriate path is selected, the corresponding pipeline executes and produces the final response to the user.

## Tech Stack
-LangChain & LangGraph for orchestration and agent workflow<br>
-TavilySearch for web search retrieval<br>
-HuggingFaceEmbeddings + FAISS for vector-based document retrieval (RAG)<br>
-BM25Retriever for keyword-based retrieval<br>
-TogetherAI for LLM inference<br>

## Notes

The reference knowledge base for the RAG pipeline is built from publicly available materials from the Stanford NLP course. The internal document collection is primarily based on the textbook:

Jurafsky, D., & Martin, J. H. — *Speech and Language Processing*  
https://stanford.edu/~jurafsky/slp3/

The system architecture intentionally decomposes the problem into smaller, composable steps so that each component can be easily understood, tested, and extended.
