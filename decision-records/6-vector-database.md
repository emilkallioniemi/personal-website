# Decision Record: Use Vector Database with OpenAI Embeddings for Knowledge Base

## Status

Accepted

## Context

The AI chat feature needs access to information about me—my background, projects, experience, interests, etc. We need to provide this information to the LLM in a way that delivers high-quality, contextually relevant responses. Tools/function calling would work and is simpler, but we prioritize quality in this case. A vector database with semantic search provides better results for natural language queries and exploratory questions.

## Decision

We will use OpenAI's embeddings API to generate vector embeddings from knowledge chunks, and store them in a vector database that supports semantic search. Tools/function calling would also work for this use case, but we prioritize quality of responses over simplicity.

## Rationale

- **Quality**: Vector database with semantic search provides better results for natural language queries and exploratory questions
- **Best tool for the job**: Semantic search finds relevant information even when queries don't match exact keywords
- **Flexibility**: Can find connections across different parts of my background without requiring specific function calls
- **User experience**: Visitors can ask natural questions without needing to know the data structure
- **Priority**: We prioritize quality of responses over implementation simplicity

## Consequences

- **Positive**:
  - Accurate semantic search for relevant information
  - Better user experience with contextually relevant responses
  - Can find connections across different pieces of information
  - More natural for exploratory questions
  - Scalable approach—easy to add more knowledge chunks
- **Negative/Trade-offs**:
  - Requires vector database setup and maintenance
  - Embedding generation has API costs
  - Need to manage chunking strategy and embedding updates
  - More complex than tools/function calling (but we prioritize quality)
- **Risks and Mitigations**:
  - Risk: Chunking strategy affects search quality
    - Mitigation: Experiment with different chunk sizes and overlap strategies

## Notes

- **Alternative approach**: Tools/function calling (e.g., `getBackground()`, `getProjects()`, `getExperience()`) would also work and is simpler, but we prioritize quality of responses
- Specific vector database choice is still to be determined (Pinecone, Weaviate, Qdrant, Supabase Vector, etc.)
- Need to define chunking strategy (size, overlap, metadata)
- Embeddings will be generated using OpenAI's `text-embedding-3-small` or similar model
- The vector search pattern: user query → generate query embedding → vector search → retrieve relevant chunks → return to caller (which will pass to LLM)
