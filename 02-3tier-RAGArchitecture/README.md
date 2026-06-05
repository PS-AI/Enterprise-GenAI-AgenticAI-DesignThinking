# Multi-Tier Enterprise Translation Memory & Glossary RAG System

This framework introduces a decoupled 3-tier RAG architecture designed specifically to balance between latency and precision for a production-grade, high-performance Translation Memory. 

The core business case this system addresses is **Translation Glossary Injection** -dynamically retrieving and injecting client-specific glossary terms as strict context constraints into the Large Language Model (LLM) window right before translation begins.

---

## The Business Case: Core Enterprise Pain Points Solved

At enterprise scale, standard machine translation lacks the contextual boundaries required for specialized industries. This 3-tier RAG architecture natively addresses three critical operational challenges:

1. **Deterministic Control:** Ensures that client-specific glossaries are enforced strictly. This introduces "hard-constrained" generation, preventing the LLM from hallucinating or altering corporate-approved branding, product codes, or legal definitions.
2. **Domain Consistency:** Synthesizes and maintains precise terminology across highly specialized, multi-lingual, high-dimensional technical jargon.
3. **Explainability:** By citing the specific glossary source, the pipeline provides a verifiable "provenance trail" detailing exactly why a specific term was chosen. This transparency is vital for establishing enterprise trust and simplifying human-in-the-loop audits.

---

## Repository Structure

The project is structured into modular execution directories at the root levels:

```text
├── tier1-vertexai-managed-engine/                     # Cloud-Native Managed Ecosystem Route
├── tier2-hybrid-lexical-semantic-engine/              # Sovereign In-Memory Local Cache Route
└── tier3-decentralized-large-scale-hybrid-rag/        # Decentralized Massive-Scale Enterprise Cluster Route 
```

### Tier 1: Cloud-Native Managed Ecosystem Route
* **Target Audience:** Rapid-deployment environments requiring minimal infrastructure overhead.
* **Blueprint:** Relies on fully managed cloud infrastructure and out-of-the-box cloud RAG tooling (Google Vertex AI RAG Engine).
* **Key Focus:** Speed to market.

### Tier 2: Hybrid Local Lexical-Semantic Core Route
* **Target Audience:** Mid-tier organizations requiring localized data sovereignty, strict privacy bounds, or a compact infrastructure footprint.
* **Blueprint:** Runs a dual-stream search combining a local BM25 Engine for exact token anchors with an in-memory FAISS RAM Index for semantic conceptual meaning.  
* **Key Focus:** Low execution footprint / On-prem setups.  

### Tier 3: Decentralized Massive-Scale Enterprise Route
* **Target Audience:** Advanced enterprise accounts processing millions of multi-lingual rows for translation glossaries.  
* **Blueprint:** Completely decouples database state from the application layer. It utilizes a remote Qdrant Storage Cluster and a Dedicated GPU-Accelerated Validation Tier (`BGE-Reranker` Cross-Encoder).  
* **Key Focus:** Infinite horizontal scaling, asynchronous throughput optimization, and maximum precision context verification.  

---

