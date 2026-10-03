# CampusAssist

CampusAssist is an AI-powered student support and placement assistant designed to provide fast, evidence-based answers to institutional queries while maintaining human oversight for unsupported or high-impact requests.

The project demonstrates a practical Generative AI workflow combining hybrid retrieval, grounded generation, evidence assessment, controlled tool use, escalation, and security checks.

> **Note:** CampusAssist uses a completely synthetic institutional knowledge base based on a fictional institution called Hogwarts Institute. It does not represent any real institution or its policies.

## Features

- Hybrid retrieval using lexical and semantic search
- Sentence-transformer embeddings for semantic retrieval
- Grounded response generation using Gemini
- Source-aware responses using approved institutional documents
- Evidence sufficiency assessment
- Human escalation for unsupported or high-impact requests
- Controlled support-ticket creation
- Simulated staff email notification
- Prompt-injection detection
- Protection against unauthorised institutional actions
- Evaluation dataset and red-team testing
- Gradio-based interactive interface

## Architecture

```text
Student
   |
   v
Gradio Interface
   |
   v
Security Check
   |
   v
Hybrid Retrieval
(Lexical + Semantic)
   |
   v
Evidence Assessment
   |
   +-----------------------+
   |                       |
   v                       v
SUPPORTED              INSUFFICIENT /
   |                    ESCALATE
   v                       |
Grounded Gemini            v
Response              Support Ticket
   |                   + Simulated Email
   v
Sources
