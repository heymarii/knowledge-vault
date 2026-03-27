# Retrieval Augmented Generation (RAG)

**Category:** AI / Machine Learning  
**Complexity:** Intermediate  
**Last updated:** 2026-03-27

---

## What It Is

RAG is a technique that gives an LLM access to external information at inference time by retrieving relevant documents and adding them to the prompt. 

Without RAG, an LLM only knows what it was trained on. With RAG, it can answer questions about your specific documents, databases, or up-to-date information.

## How It Works

```
User Query
    ↓
1. Convert query to embedding (vector)
    ↓
2. Search vector DB for similar chunks
    ↓
3. Retrieve top-K relevant chunks
    ↓
4. Inject chunks into prompt context
    ↓
5. LLM generates answer grounded in retrieved content
    ↓
Response (with citations)
```

## The Key Components

**Chunking:** Breaking documents into appropriately-sized pieces. Too small = no context. Too large = noise and cost.

**Embedding model:** Converts text to vectors. Popular options: OpenAI `text-embedding-3-small`, Cohere, open-source Sentence Transformers.

**Vector database:** Stores and retrieves embeddings by similarity. Options: Pinecone, Weaviate, Chroma (local), pgvector (Postgres).

**Retrieval strategy:** Simple cosine similarity works well. Hybrid (keyword + vector) works better for exact terms.

## When to Use RAG

✅ Use RAG when:
- You have proprietary documents an LLM wasn't trained on
- You need up-to-date information (post training cutoff)
- You need citations/sources in responses
- Context window size is a constraint

❌ Don't use RAG when:
- The question is answerable from training data
- You have fewer than ~20 documents (just put them all in context)
- Latency is critical (RAG adds a retrieval step)

## Common Pitfalls

1. **Bad chunking:** Splitting in the middle of a sentence or concept loses context
2. **No reranking:** Top-K cosine similarity isn't perfect — use a reranker
3. **Missing metadata:** Store source, date, author with each chunk
4. **Hallucination on retrieved content:** LLMs still confabulate — validate outputs

---

## Resources

- [LlamaIndex RAG Tutorial](https://docs.llamaindex.ai/en/stable/getting_started/concepts/)
- [Anthropic RAG with Claude](https://github.com/anthropics/anthropic-cookbook/tree/main/skills/retrieval_augmented_generation)
