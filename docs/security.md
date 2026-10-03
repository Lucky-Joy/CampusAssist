# CampusAssist Security

## Overview

CampusAssist is designed with security boundaries that prevent the assistant from blindly following user instructions or performing restricted institutional actions.

The security approach combines:

- Prompt-injection detection
- Grounded generation
- Evidence assessment
- Authority-boundary checks
- Controlled tool access
- Human escalation
- Minimal information handling

## Security Goals

The system aims to:

1. Prevent attempts to expose internal instructions.
2. Prevent unsupported institutional claims.
3. Prevent the assistant from making official high-impact decisions.
4. Prevent unauthorised modification of institutional records.
5. Restrict automated actions to explicitly defined tools.
6. Route uncertain or high-impact requests to human support.

## Prompt-Injection Protection

CampusAssist performs a security check before entering the normal retrieval and generation workflow.

The prototype detects patterns associated with requests such as:

- Ignoring previous instructions
- Ignoring the system prompt
- Revealing hidden system prompts
- Revealing internal instructions
- Bypassing assistant instructions

Detected requests are classified as:

```text
SECURITY_BLOCK