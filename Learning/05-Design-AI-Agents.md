# Design AI agents for business solutions

## Introduction to Task Agents

- Task agents are specialized AI agents designed to complete specific actions or tasks on behalf of users.

- In Microsoft Copilot Studio, task agents extend Copilot’s intelligence into structured workflows integrating business logic, APIs, and enterprise data.

- Task agents improve efficiency by automating repetitive or multi-step workflows, executing actions, using context to make decisions, accessing organizational data safely, and supporting consistent processes across teams.

- Designing effective task agents requires understanding the architecture that drives how agents reason, take action, and collaborate with users.

### Components of a Task Agent

Task agents in Microsoft Copilot Studio use a modular architecture.

Each component contributes to the agent’s ability to act, reason, and integrate into business processes.

| Component | Purpose |
|------------|---------|
| **Goals** | Define what the agent is expected to accomplish. |
| **Skills** | Capabilities used to achieve goals (extraction, reasoning, planning). |
| **Actions** | Executable operations via connectors, APIs, or workflows. |
| **Knowledge** | Structured/unstructured information the agent can reference. |
| **Context** | Enterprise data and signals influencing decisions. |
| **Safety & Rules** | Guardrails that determine what the agent can and cannot do. |

![Task Agent Architecture Flow](/images/task-agent-flow.png)


## Introduction: What Are Autonomous Agents?
- Autonomous agents are **AI-powered systems that perform tasks independently** using business goals, contextual knowledge, and integrated instructions.
- They transform manual or repetitive business processes into automated, intelligent workflows.

### In Copilot Studio, Autonomous Agents:
- Understand intent using built-in reasoning.
- Access organizational knowledge to make informed decisions.
- Execute tasks using connectors, actions, and triggers.
- Operate inside Microsoft Teams or integrated enterprise applications.

### Core Components of an Autonomous Agent
- **Goals:** Define what the agent is expected to accomplish (e.g., "Create an onboarding request," "Summarize weekly reports").
- **Triggers:** Events that cause the agent to start, such as user input, system changes, or scheduled prompts.
- **Instructions:** Detailed business rules that guide agent behavior (e.g., "If the customer is VIP, escalate the ticket immediately").
- **Knowledge Sources:** Documents, SharePoint libraries, Dataverse tables, and enterprise content used to ground responses.
- **Actions:** Executable operations such as calling APIs, creating records, sending emails, or updating CRM fields.

## Overview of Prompt and Response Agents

Prompt and response agents in **Microsoft Copilot Studio** combine **natural language understanding (NLU)**, **topic-based logic**, and **event-driven behavior** to generate accurate answers and perform actions.

### Agents Process

- **User prompts** → Identify intent

- **Knowledge sources / topics** → Retrieve content

- **Conditions** → Shape the dialog flow

- **Triggers** → Start actions from events instead of user queries

> This modular architecture ensures flexibility and predictable results.

## Introduction to Azure AI Foundry Tools

- Azure AI Foundry provides a catalog of tools for agents to perform tasks like retrieving data, calling APIs, grounding responses, orchestrating workflows, and triggering actions.

- Selecting the correct tool is essential to meet requirements with minimal complexity.

### The Goal Is to Choose Tools That

- Meet the requirement with minimal complexity
- Ensure security and compliance
- Leverage existing enterprise systems
- Reduce integration overhead
- Support accurate, grounded outputs

### Mapping Requirements to Foundry Tools

| Requirement Type | Recommended Tool Category | Examples |
|------------------|---------------------------|----------|
| **Document retrieval** | Retrieval & Grounding | Vector search, semantic search |
| **App integration** | App & Data Connectors | REST APIs, Dynamics connector |
| **Workflow automation** | Workflow & Action | Power Automate, custom actions |
| **Data processing** | Compute Tools | Azure Functions, ML Tools |
| **Decision and planning** | Reasoning Tools | Planner, rule evaluators |

## Introduction to Topics in Copilot Studio
- Topics are building blocks of conversational logic in Microsoft Copilot Studio.
- Each topic defines a **specific user intent**, response flow, and connected actions.
- Copilot Studio selects topics based on **trigger phrases, natural language matching, and generative understanding**.
- Topics combine structured scenarios with generative responses where appropriate.

### Key Components of Topics
- **Trigger Phrases:** Signal the start of a topic (e.g., "Track my order").
- **Message Nodes:** Deliver concise, conversational information to users.
- **Question Nodes:** Gather structured responses like choices, text, dates, or numbers.
- **Conditions and Branching:** Route dialogs based on input, business rules, and context.
- **Actions:** Connect to business apps, databases, and workflows (e.g., update Dataverse, trigger Power Automate).

### Topic Types in Copilot Studio

| Topic Type | Purpose | Example |
|------------|---------|---------|
| **Instructional Topic** | Guides the user through a task | Reset MFA method |
| **Action Topic** | Runs an automated step | Create support ticket |
| **Informational Topic** | Provides structured information | Business hours |
| **System Topic** | Handles system-level events | Greeting, escalation, fallback |
| **Reusable Topic** | Shared logic across topics | Authentication |

### How Copilot Selects Topics

```text
User Message
      │
      ▼
Intent Analysis Engine
      │
      ├───────────────┬─────────────────────┐
      ▼               ▼                     ▼
Trigger Phrases   Natural Language   Generative Orchestration
                  Understanding
      │               │                     │
      └───────────────┴─────────────────────┘
                      │
                      ▼
               Intent Matched?
                  /       \
                Yes        No
                 │          │
                 ▼          ▼
          Selected Topic  Fallback Topic
                 │          │
                 └────┬─────┘
                      ▼
                Fulfill Intent
```

### Topic Selection Flow

1. User submits a message.
2. The **Intent Analysis Engine** evaluates the request using:
   - Trigger Phrases
   - Natural Language Understanding (NLU)
   - Generative Orchestration
3. Copilot determines whether an intent match exists.
4. If a match is found, the appropriate topic is selected.
5. If no match is found, the fallback topic is invoked.
6. The selected topic fulfills the user's intent.

## Platform Choices for Grounding

- **Azure Well-Architected + Azure AI Search Architected + Azure AI Search:** Retrieval backbone managing ingestion, chunking, embedding, schema, and freshness with index maintenance patterns like side-by-side rebuilds.

- **Microsoft Foundry - RAG with your data:** Build searchable data and grounded agents/apps using Foundry portal and SDK.

- **Copilot Studio & AI Builder:** Low-code grounded prompts based on Dataverse data; reuse prompts in Power Apps, Power Automate, and Copilot Studio with licensing and environment prerequisites.

## Decision Framework for Choosing the Right Approach

| Requirement Type | Standard NLU | Azure CLU | Generative AI Orchestration |
|------------------|--------------|-----------|-----------------------------|
| Structured commands | ✓ Best choice | ✓ Good | — |
| Regulatory accuracy, predictable outcomes | ✓ Best | ✓ Good | — |
| Moderate linguistic variability | — | ✓ Best choice | ✓ Possible |
| Highly variable or ambiguous language | — | ✓ Good | ✓ Best choice |
| Requires enterprise grounding knowledge | — | — | ✓ Best |
| Needs reasoning, summarization, content creation | — | — | ✓ Best |
| Needs explicit intent routing | ✓ Good | ✓ Best | ✓ Can augment |
| Multi-step conversations | — | ✓ Good | ✓ Best |

## Coplit Studio Agent Flow Orchestration

![Coplit Studio Agent Flow Orchestration](/images/copilot-studio-agent-flow.png)

## What Are Prompt Actions?

Prompt actions allow your Copilot Agent to:
- Generate natural language responses.
- Perform reasoning tasks.
- Transform or summarize content.
- Follow structured instructions and constraints.
- Interact with user inputs and variables.
- Improve consistency across all agent responses.

> Prompt actions behave as reusable instruction blocks the agent can call when needed.

### Using the Prompt Coach Template

- Break prompts into structured sections.

- Maintain consistency and quality.

- Increase predictability and reduce hallucinations.

- Align output with organizational standards (tone, terminology, safety).

### Core Prompt Coach Structure

| Section | Purpose |
|----------|---------|
| **Goal** | What the agent must achieve |
| **Context** | Relevant information, data, or user scenario |
| **Instructions / Rules** | Tone, constraints, allowed content |
| **Examples (optional)** | Demonstrations of correct output |
| **Output Format** | The exact structure for the response |

### Prompt Action Types

| Prompt Type | Description | Example Scenario |
|-------------|-------------|------------------|
| **Transform** | Rewrites content | Create professional rewrite of customer message |
| **Summarize** | Produces short, clear summary | Summaries for cases, chats, notes |
| **Extract** | Pulls entities or fields | Extract order number and issue type |
| **Generate** | Produces new text | Draft email response to customer |
| **Classify** | Categorizes input | Identify request as billing, onboarding, or support |