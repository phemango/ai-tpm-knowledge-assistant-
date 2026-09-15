# AI-Powered Enterprise Knowledge Assistant

## AI TPM Portfolio Project

Imagine an employee asking:

> "How many vacation days can I carry over?"

Instead of searching through multiple company documents, the employee asks the AI assistant and receives an answer grounded in approved company information — with the system checking whether the information is current and whether the employee is authorized to access it.

This project demonstrates how an **AI Technical Program Manager (AI TPM)** can take an AI product from an initial idea through product definition, architecture, prototyping, evaluation, security considerations, and production readiness.

> **Portfolio note:** This project uses fictional, non-confidential enterprise documents created specifically for demonstration purposes.

---

## 🎯 What Problem Are We Solving?

Enterprise employees often need information from many internal policies, procedures, and documents.

A general-purpose LLM alone can create problems because it may:

- Give an answer that is not supported by company documentation
- Use outdated information
- Retrieve information the employee is not authorized to see
- Answer confidently when there is not enough evidence
- Fail to clearly identify where an answer came from

The goal of this project is to explore how a **Retrieval-Augmented Generation (RAG)** system can address these challenges.

---

## 💡 The Product

The Knowledge Assistant allows an employee to ask questions in natural language.

The system:

1. Receives the employee's question
2. Converts the question into a semantic representation
3. Searches the enterprise knowledge base for relevant information
4. Checks authorization and document status
5. Removes information the employee should not access
6. Provides the approved evidence to the LLM
7. Generates an answer grounded in that evidence
8. Provides the source of the information

If sufficient authorized evidence is not available, the system should **not invent an answer**.

### Example questions

- How many vacation days can I carry over?
- Who is eligible for parental leave?
- What should I do if I suspect a security incident?
- What is the company's executive compensation policy?

---

## 🧠 What I Demonstrated as an AI TPM

This project goes beyond building a simple chatbot.

It demonstrates the AI TPM lifecycle:

**Product Definition → Requirements → Architecture → Prototype → Evaluation → Security → Production Readiness → Operations**

### Product

- Defined the problem and target users
- Identified use cases
- Defined MVP scope
- Defined success criteria
- Identified stakeholders and dependencies

### Technical

- Designed the RAG architecture
- Defined document ingestion and chunking approach
- Selected an embedding model
- Selected vector search technology
- Evaluated LLM behavior
- Defined retrieval and grounding requirements

### Security & Responsible AI

- Designed authorization-aware retrieval
- Considered document freshness and source authority
- Tested unauthorized information scenarios
- Tested retired/outdated information
- Defined safe no-answer behavior

### Program Execution

- Created an evaluation and test strategy
- Maintained a RAID log
- Defined production-readiness criteria
- Created launch and rollout planning
- Defined monitoring, incident response, hypercare, and BAU ownership

---

## 🏗️ High-Level Architecture

```text
                    Enterprise Documents
                            │
                            ▼
                       Ingestion
                            │
                            ▼
                         Chunking
                            │
                            ▼
                  Metadata + Access
                            │
                            ▼
                    Embedding Model
                            │
                            ▼
                      Vector Index
                         (FAISS)
                            │
                            │
Employee Question ──────────┘
        │
        ▼
Question Embedding
        │
        ▼
  Semantic Search
        │
        ▼
Authorization + Freshness
+ Authority Filtering
        │
        ▼
   Relevant Evidence
        │
        ▼
        LLM
        │
        ▼
Grounded Answer + Source
