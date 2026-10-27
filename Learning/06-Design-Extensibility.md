# Design extensibility of AI solutions

## Custom Models
### When to Use Custom Models & Usage Scenarios

Evaluate business complexity, data requirements, regulatory needs, and performance targets to determine the need for custom AI models.

- **Domain-specific language and reasoning** required in industries like legal, healthcare, engineering, finance, and manufacturing.

- **High-impact decision processes** where accuracy affects compliance, financial outcomes, or operational safety.

- **Data sovereignty and governance mandates** requiring control over data processing, storage, evaluation, and monitoring.

- **Unique workflows or personalization** needs not supported by prebuilt copilots.

- **Cost optimization for high-volume inference** with small, specialized custom models.

### Operationalizing Custom Models in Foundry

- **Model Monitoring and Observability:** Track drift, performance degradation, user friction areas, latency, and unexpected model outputs.

- **Governance and Compliance Controls:** Ensure deployments meet enterprise privacy, security, and regulatory requirements.

- **Versioning and Lifecycle Management:** Maintain model version trails, update pipelines, and rollback strategies.

- **Deployment Automation (MLOps/GenAIOps):** Automate validations, approval workflows, and environment-specific deployments.

## Foundations of Microsoft 365 Copilot Agents

- Copilot agents are modular, instruction-driven AI components for specific business tasks and workflows.

- Agents follow structured instructions, leverage organizational data, and use tools and connectors to take action.

- Typical agent functions include:
  - Task automation
  - Information retrieval
  - Multi-step operations
  - Collaboration workflows

- Agents operate inside:
  - Microsoft Teams
  - Outlook
  - Loop
  - SharePoint
  - Custom line-of-business applications

## Overview of Agent Extensibility in Copilot Studio

- Provides expert guidance for designing extensible, enterprise-grade agents.

- Learn to structure agent capabilities, integrate external logic, apply custom instructions, and use pro-code extensibility.

- Ensures agents scale across business scenarios, product lines, and organizational boundaries.

- Focuses on:
  - Adding custom logic
  - Integrating enterprise systems
  - Modifying instructions
  - Extending with Visual Studio Code
  - Supporting governance

### Extensibility Layer Model

![Extensibility Layer Model](/images/extensibility-layers.png)

## Integration Patterns for MCP Enabled Agents

- **Pattern A – Context Driven Reasoning:** Agents retrieve real-time MCP context to ensure responses reflect authoritative business rules.
  - Ideal for compliance-sensitive tasks, finance workflows, procurement, and vendor management scenarios.

- **Pattern B – Workflow Integrated Agents:** Agents augment workflows by using MCP to drive approvals, escalate exceptions, and summarize status.

- **Pattern C – Multiagent Collaboration via MCP:** Standardizes data each agent can reference, improving cross-domain collaboration (e.g., HR + Finance + Supply Chain AI processes).

### Pattern Comparison

| Pattern | Description | Typical Use Cases |
|----------|-------------|-------------------|
| **Context Driven Reasoning** | Retrieves real-time MCP context to ground responses in authoritative business rules. | Compliance, finance, procurement, vendor management |
| **Workflow Integrated Agents** | Uses MCP to support workflow automation, approvals, escalations, and status tracking. | Business process automation, exception handling, operational workflows |
| **Multiagent Collaboration via MCP** | Provides a shared context layer across multiple agents to improve coordination and consistency. | Cross-functional AI solutions involving HR, Finance, Supply Chain, and other domains |

## Behavior Foundations

Agent behavior is shaped by four main components:
- **Instructions:** Define purpose, persona, goals, tone, and guardrails.
- **Knowledge:** Governs accessible content and information retrieval.
- **Actions / Tools:** Execute tasks, retrieve data, call downstream systems.
- **Policies and Constraints:** Ensure compliance, privacy, and responsible AI principles.

### Behavior Design Principles
- Provide clear role definition for the agent.
- Establish allowed and disallowed behavior.
- Define escalation patterns.
- Apply formatting rules for responses.
- Include business logic constraints and error handling expectations.

