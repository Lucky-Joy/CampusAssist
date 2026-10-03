
# `governance.md`

```markdown
# CampusAssist Governance

## Overview

CampusAssist is designed around the principle that Generative AI should assist institutional workflows without replacing authorised human decision-makers.

The system therefore separates:

- Information assistance
- Evidence assessment
- Automated support actions
- Official institutional decisions

## Human Oversight

CampusAssist can provide information based on approved documents, but authorised staff remain responsible for official decisions.

Human review is required when a request involves:

- Official eligibility decisions
- Exceptions to documented policies
- Academic record changes
- Disciplinary decisions
- High-impact student situations
- Information not adequately covered by the knowledge base
- Actions requiring institutional authority

## Escalation

When the system determines that a request requires human review, it does not attempt to complete the restricted action.

Instead, it creates a support-ticket representation containing:

- Student details
- Original request
- Reason for escalation
- Priority
- Status

The prototype also generates a simulated email notification for the relevant support team.

## Governance Boundaries

CampusAssist is not intended to:

- Replace authorised institutional staff
- Make final institutional decisions
- Approve undocumented exceptions
- Modify academic records
- Invent institutional requirements
- Provide unsupported official information

The assistant should remain within the authority defined by the application.

## Evidence-Based Responses

The system uses an approved knowledge base as its primary source of institutional information.

Responses should be grounded in retrieved evidence rather than assumptions.

When evidence is insufficient, the assistant should communicate that limitation instead of inventing an answer.

Relevant source filenames are also returned with responses to improve traceability.

## Data Minimisation

The system should use only the information necessary to answer the student's request or create an escalation.

Users should not provide unnecessary sensitive information.

The prototype uses synthetic institutional documents and does not require real student records.

## Tool Governance

Automated tools should have narrowly defined purposes.

CampusAssist currently provides a support-ticket capability rather than unrestricted access to institutional systems.

A production system should additionally define:

- Which users can invoke each tool
- Which actions require human approval
- What information each tool can access
- What actions must be logged
- What actions are prohibited

## Accountability

Important institutional decisions should remain attributable to authorised human personnel.

CampusAssist should therefore be treated as an assistance layer rather than the final authority.

For high-impact workflows, the system should provide sufficient context for a human reviewer to understand:

- What the student asked
- What evidence was available
- Why the request was escalated
- What automated action was taken

## Governance and Safety

The system is designed to reduce several common risks associated with institutional AI assistants:

- Hallucinated policies
- Unsupported decisions
- Unauthorised actions
- Excessive automation
- Prompt injection
- Unnecessary exposure of sensitive information

These controls are implemented as a prototype demonstration and would require further validation before any real institutional deployment.

## Production Governance Requirements

A real deployment would require additional governance measures, including:

- Formal data-protection requirements
- Authentication and role-based access
- Access reviews
- Audit logging
- Incident-response procedures
- Human approval workflows
- Security assessments
- Model and prompt change management
- Continuous evaluation
- Clear ownership and accountability
- Retention and deletion policies

## Governance Principle

The central governance principle is:

> CampusAssist can assist with institutional information, but authority remains with the people and processes responsible for the institution.