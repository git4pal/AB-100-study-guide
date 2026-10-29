
## Requirement-to-Approach Mapping

| Requirement | Recommended Approach |
|-------------|----------------------|
| Predictable workflows, predefined questions, deterministic outputs | **Standard NLU** |
| Complex intent recognition, varied user phrasing | **Azure CLU** |
| Open-ended conversations, AI reasoning | **Generative AI Orchestration** |
| Knowledge-base Q&A with generated responses | **NLU Boost / Generative Answers** |

## Microsoft's Build vs. Extend vs. Buy Decision Framework

| Approach | When to Use |
|----------|-------------|
| **Buy** | Standard business productivity scenarios with minimal customization. |
| **Extend** | Existing Copilot capabilities can be customized using enterprise data and moderate business logic. |
| **Build** | Highly specialized requirements, strict compliance, proprietary data, unique workflows, and organizations capable of developing and operating custom AI solutions. |

## Security Priorities for Action-Oriented AI Agents

### When an Agent Can...

- Write data
- Update systems
- Execute transactions
- Approve requests
- Trigger workflows

### Focus First On

| Security Control | Why It Matters |
|------------------|----------------|
| **Identity and Access Management (IAM)** | Ensure every agent, user, and system interaction is authenticated and authorized. |
| **Least Privilege** | Grant only the minimum permissions required to perform the intended task. |
| **Human-in-the-Loop (HITL) Controls** | Require human review and approval for sensitive or high-impact actions. |
| **Approval Workflows** | Enforce governance and accountability before critical actions are executed. |
| **Audit Logging** | Maintain traceability for all agent actions, decisions, and system changes. |
| **Separation of Duties (SoD)** | Prevent one agent or user from having excessive control over an entire business process. |

### Key Principle

> When an AI agent can **take action** rather than simply **provide information**, prioritize **security, governance, and access controls** before focusing on knowledge sources, channels, prompts, or triggers.

## Governance, Security, Privacy, and Compliance First Rule

### When You See...

- Third-party vendor
- External connector
- Customer data
- Employee data
- Privacy concerns
- Missing legal approval
- Missing compliance review

### Always Prioritize

| Priority Area | What to Validate |
|---------------|------------------|
| **Governance** | Ownership, approval process, risk classification, auditability, usage policies |
| **Security** | IAM, RBAC, least privilege, managed identities, network isolation, secure connectors |
| **Privacy** | Data minimization, PII protection, consent requirements, retention policies, data residency |
| **Compliance** | Legal review, regulatory requirements, industry standards, DLP policies, Responsible AI controls |

### Decision Matrix

| Situation | First Question to Ask |
|------------|----------------------|
| Third-party vendor integration | Has governance and security review been completed? |
| External connector access | Is access restricted using least privilege and approved connectors? |
| Customer data processing | Are privacy and compliance requirements satisfied? |
| Employee data access | Are permissions, retention, and data protection controls defined? |
| Privacy concerns raised | Have privacy impact assessments been completed? |
| Missing legal approval | Stop deployment until legal review is completed. |
| Missing compliance review | Stop deployment until compliance validation is completed. |

## AI Experience Selection Framework

| User Behavior | Recommended Experience |
|---------------|------------------------|
| Users stay within one application/workspace | ✅ **Embedded AI** |
| Users need conversational assistance across tasks | ✅ **Sidecar Copilot** |
| Users need cross-system automation | ✅ **External Orchestration** |
| Users need contextual recommendations inside forms, dashboards, or records | ✅ **Embedded AI** |

### Exam Tips
| Requirement | Choose |
|-------------|--------|
| In-app assistance | Embedded AI |
| Context-aware recommendations | Embedded AI |
| Cross-application conversation | Sidecar Copilot |
| Productivity assistance across tasks | Sidecar Copilot |
| Multi-system workflows | External Orchestration |
| Business process automation | External Orchestration |

## AI Solution Design Decision Examples

| Requirement | Best Choice | Why |
|------------|------------|-----|
| HR agent requires consistent responses across departments | ✅ **Centralized prompt governance and templates** | Ensures standardized prompts, common business definitions, and consistent responses across all departments. |
| Claims agent needs HIPAA-compliant processing and auditing | ✅ **Custom platform supporting compliance pipelines** | HIPAA requires strict access controls, audit logging, security controls, and compliance validation workflows. |
| Routing agent must process multiple dependent steps | ✅ **Sequential orchestration for controlled execution** | Sequential orchestration ensures each step executes in the correct order with predictable outcomes and auditability. |
| Patient intake crosses regulated system boundaries | ✅ **Multi-agent architecture with boundary separation** | Separates responsibilities across systems and security domains while enforcing regulatory and data-access boundaries. |

## Managed Identity vs Service Principal - Quick Decision Guide

| Scenario | Preferred Choice |
|----------|------------------|
| Azure-hosted AI workload | ✅ Managed Identity |
| Azure-to-Azure authentication | ✅ Managed Identity |
| Need to avoid secrets entirely | ✅ Managed Identity |
| External/non-Azure system | ⚠️ Service Principal may be required |
| Service Principal stored in Key Vault | Valid fallback, not equivalent best practice |

### AI Exam Rule

| If the Question Says... | Answer |
|-------------------------|--------|
| Azure-hosted resource accessing another Azure resource | Managed Identity |
| Eliminate secrets/passwords | Managed Identity |
| Least operational overhead | Managed Identity |
| External application needs Azure access | Service Principal |
| Non-Azure workload | Service Principal |
| Client secret or certificate required | Service Principal |
| Azure-to-Azure authentication | Managed Identity |

## Responsible AI Principle Quick Reference

| Scenario Clue | Responsible AI Principle |
|---------------|--------------------------|
| No explanation of AI decisions | ✅ Transparency |
| No human oversight for high-impact decisions | ✅ Accountability |
| Biased outcomes between groups | ✅ Fairness |
| Sensitive data exposure | ✅ Privacy & Security |
| Users unable to access/use solution | ✅ Inclusiveness |
| Unreliable or unsafe outputs | ✅ Reliability & Safety |

