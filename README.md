# CampusAssist

CampusAssist is an AI-powered student support and placement assistant designed to provide fast, evidence-based answers to institutional queries while maintaining human oversight for unsupported or high-impact requests.

The project demonstrates a practical Generative AI workflow combining hybrid retrieval, grounded generation, evidence assessment, controlled tool use, escalation, and security-aware workflows.

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
```

A detailed architecture diagram and technical documentation are available in the `docs/` directory.

## How It Works

1. Institutional documents are loaded from the synthetic knowledge base.
2. Documents are extracted and divided into overlapping chunks.
3. Each chunk is converted into a semantic embedding.
4. User queries are processed using both lexical and semantic retrieval.
5. Retrieved evidence is assessed before generating an answer.
6. Supported questions are answered using only the approved evidence.
7. Unsupported questions are routed for human review.
8. Requests involving official decisions or restricted actions are escalated.
9. Prompt-injection attempts are blocked before entering the normal workflow.
10. Responses include the relevant source documents where applicable.

## Technology Stack

- Python
- Google Gemini API
- Sentence Transformers
- NumPy
- PyPDF
- Gradio
- Google Colab

## Evaluation

CampusAssist was tested against a set of 10 representative cases covering:

- Placement eligibility
- Registration procedures
- Internship procedures
- Student services
- Unsupported questions
- Exceptions requiring human judgement
- Academic record modification
- Prompt injection

The final decision-level evaluation achieved:

**10/10 test cases passed (100%)**

The system was also tested against additional red-team scenarios targeting prompt injection, authority boundaries, restricted actions, and unsupported information requests.

## Performance

In the Colab prototype, three representative supported queries were measured for response latency.

| Component | Average Latency |
|---|---:|
| Retrieval | 0.125 s |
| Evidence Assessment | 0.611 s |
| Response Generation | 0.861 s |
| End-to-End | **1.597 s** |

These measurements are indicative of the prototype environment and should not be treated as production performance benchmarks.

## Knowledge Base

The project includes a synthetic institutional knowledge base covering:

- Placement Policy
- Placement Eligibility Rules
- Placement Registration Guide
- Academic Procedures
- Student Services Guide
- Internship Guidelines
- Support & Escalation Policy
- AI Assistant Usage Policy

All institutional information in this repository is fictional and created for demonstration and educational purposes.

## Project Structure

```text
CampusAssist/
│
├── README.md
├── LICENSE
│
├── notebook/
│   └── CampusAssist.ipynb
│
├── knowledge_base/
│   ├── 01_Placement_Policy.pdf
│   ├── 02_Placement_Eligibility_Rules.pdf
│   ├── 03_Placement_Registration_Guide.pdf
│   ├── 04_Academic_Procedures.pdf
│   ├── 05_Student_Services_Guide.pdf
│   ├── 06_Internship_Guidelines.pdf
│   ├── 07_Support_and_Escalation_Policy.pdf
│   └── 08_AI_Assistant_Usage_Policy.pdf
│
├── docs/
│   ├── architecture.png
│   ├── evaluation.md
│   ├── governance.md
│   └── security.md
│
└── screenshots/
```

## Running the Project

The prototype was developed and tested in Google Colab.

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/CampusAssist.git
cd CampusAssist
```

### 2. Install dependencies

```bash
pip install -U pypdf sentence-transformers google-genai gradio
```

### 3. Configure the Gemini API key

Set your Gemini API key as an environment variable or configure it using the secret-management mechanism available in your execution environment.

Do not commit API keys or other credentials to the repository.

### 4. Run the notebook

Open:

```text
notebook/CampusAssist.ipynb
```

and execute the cells in order.

## Responsible Use

CampusAssist is designed as an educational prototype demonstrating responsible Generative AI application design.

The assistant is not intended to:

- Make official institutional decisions
- Approve exceptions
- Modify academic records
- Replace authorised staff
- Invent undocumented policies
- Process unnecessary sensitive information

Requests requiring official judgement or action are intended to be routed to human support.

## Limitations

This is a prototype rather than a production institutional system.

Current limitations include:

- Synthetic rather than real institutional data
- Prototype-scale knowledge base
- Simple lexical scoring combined with semantic similarity
- Rule-based prompt-injection detection
- Simulated support-ticket and email workflows
- Colab-based execution
- No real authentication or institutional system integration
- Latency measurements are environment-dependent

A production implementation would require stronger authentication, access controls, monitoring, privacy controls, robust security testing, institutional integrations, and operational infrastructure.

## Educational Purpose

This repository is intended to serve as a reference for learning how multiple Generative AI application concepts can be combined into a single practical system.

You are encouraged to study the architecture, understand the implementation choices, experiment with the components, and build your own systems.

Please do not present this project or its implementation as your own work without substantial independent development.

## License

This project is released under the terms specified in `LICENSE`.

The license permits use of the repository as a reference while placing restrictions on redistribution and direct copying of the project.

## Author

**Lucky Joy Tutika**

Built as a Generative AI capstone project.
