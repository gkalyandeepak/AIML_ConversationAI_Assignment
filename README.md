# Multilingual FAQ Retrieval & RAG
 
This repository compares retrieval methods for a student-support chatbot that answers questions about semester assignments: instructions, deadlines, submissions, extensions, marks, feedback and workload.
 
The knowledge base is an **English-only FAQ**, while queries come in **English and code-mixed languages**: **Hinglish** (Hindi + English), **Tinglish** (Telugu + English) and **Finglish** (French + English).
 
## What's Inside
 
- **FAQ dataset:** 35 English FAQs (FAQ ID, intent, question, answer).
- **Test queries:** 140 conversational queries covering all 35 intents, one each in English, Hinglish, Tinglish and Finglish, each labelled with its expected FAQ ID.
- **Retrievers:**
  - BM25 (keyword-based)
  - English embeddings (`all-MiniLM-L6-v2`)
  - Multilingual embeddings (`multilingual-e5-small`)
  - Hybrid: BM25 + multilingual embeddings, combined with Reciprocal Rank Fusion (RRF)
- **Evaluation:** Recall@1 and Recall@3 for each language style, with an analysis of where each method succeeds or fails.
- **RAG demo:** the best retriever finds the relevant English FAQ, and an LLM uses it to write the final answer.
