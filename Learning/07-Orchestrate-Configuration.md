# Orchestrate configuration of prebuilt agents and apps

## Overview of AI Capabilities in Dynamics 365 Finance and Supply Chain Apps

- Automate decision-making, accelerate workflows, and improve productivity.

- Copilot provides conversational assistance, AI-driven insights, and embedded intelligent actions.

- Works across:
  - Finance
  - Procurement
  - Warehousing
  - Planning
  - Supply Chain Operations

- Solution architects design AI orchestration patterns ensuring:
  - Data governance
  - Responsible AI
  - Workflow consistency

- Guidance on orchestrating Copilot-driven features:
  - Sidecar chat
  - Embedded insights
  - External AI agents


## Extending Copilot for Finance and Supply Chain
- Extend Copilot using custom scripts and extensions via developer framework.
- Prompt-defined behaviors within sidecar experiences.
- Custom data sources such as external knowledge or structured business content.
- Business event triggers connected to Power Automate or Azure Functions.
- Custom actions callable by Copilot as part of guided workflows.

# Agent Design Framework: Five Steps
- **Frame the job to be done:** describe recurring business outcomes, not tool steps.
- **Map inputs, knowledge, and actions:** enumerate sources, tools, and write operations.
- **Define guardrails:** specify who can invoke, data scope, approval triggers, logging, and reversal.
- **Prototype the critical path:** start with a narrow end-to-end slice, test, and iterate.
- **Operationalize:** add telemetry, quality checks, and cost controls; move from pilot to production.

## Understanding Power Platform AI Capabilities

### Key AI Components

- AI experiences provide intelligence across apps, flows, pages, and copilots.

- Core components include:

  - **AI Hub:** The central experience for managing, discovering, and orchestrating AI within Power Platform, connecting models, copilots, and automation.

  - **Copilot in Power Platform:** Natural language-driven creation of apps, flows, tables, controls, and logic.

  - **AI Builder:** A collection of prebuilt and customizable AI models for classification, prediction, extraction, detection, translation, and document understanding.

  - **Copilot Studio:** Low-code conversational agent creation with extensibility into Microsoft 365 and external systems.

## The AI Hub: Orchestration for Enterprise AI

### Purpose of the AI Hub

- Centralize AI features across Power Apps, Power Automate, and Copilot Studio.

- Manage AI models, connectors, and copilots in a governed environment.

- Promote consistent, secure, monitored use of AI at scale.

- Provide guided paths for building AI-driven apps and flows.

### AI Hub Architecture

| Layer | Components |
|---------|-----------|
| **Data Sources** | Dataverse, SharePoint, Files, Connectors |
| **Power Platform AI Hub** | AI Builder, Copilot, Copilot Studio |
| **Governance** | DLP Policies, Security Roles, Environments |

### Data Flow

```text
Data Sources
├─ Dataverse
├─ SharePoint
├─ Files
└─ Connectors
        │
        ▼
Power Platform AI Hub
├─ AI Builder
├─ Copilot
└─ Copilot Studio
        │
        ▼
Governance
├─ DLP Policies
├─ Security Roles
└─ Environments
```

## Designing Copilot Client Plugins for Interoperability

- Plugins enable the agent to retrieve data, perform actions, trigger workflows, and integrate with external systems.

- Plugin capabilities include:
  - Defining custom actions
  - Providing structured responses
  - Enforcing business logic
  - Supporting multi-step workflows

- Design considerations involve identifying:
  - Missing data or actions from F&O
  - External systems to access
  - Business logic enforcement requirements
  - Constraints or validations required
