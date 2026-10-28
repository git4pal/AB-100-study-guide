# Design overall AI strategy for business solutions


![Microsoft Cloud Adoption Framework](/images/microsoft-caf.png)

## Unified Model Overview

### Why Unify?

- CAF (Cloud Adoption Framework) provides an end-to-end adoption backbone for AI solutions on Azure.
- Agent adoption guidance layers into the **operating model** for planning, governing, building, and operating AI agents.
- Aligning CAF and agent lifecycle frameworks reduces risk, prevents agent sprawl, and accelerates value realization.

### Key Alignment Principles

- CAF AI adoption defines **foundations and operational guardrails**.
- Agent lifecycle management defines **how teams plan, govern, build, and operate agents**.

> **Outcome:** A unified approach combines Azure Cloud Adoption Framework guidance with agent lifecycle practices to ensure scalable, governed, and business-aligned AI adoption.

### Cloud Adoption Framework (CAF) for AI - Phase-by-Phase Guidance

| Phase | Goals | Key Activities | Outputs / Deliverables | Architect Checklist |
|---------|---------|---------|---------|---------|
| **Strategy** | Define AI vision, business outcomes, and success criteria. Align AI investments with organizational objectives. | • Identify business problems and opportunities<br>• Define AI use cases<br>• Evaluate value potential and ROI<br>• Establish executive sponsorship<br>• Define Responsible AI objectives | • AI Strategy Document<br>• Business Case<br>• Success Metrics/KPIs<br>• Prioritized Use Case Backlog<br>• Executive Sponsorship Model | ☐ Business goals identified<br>☐ AI use cases documented<br>☐ KPIs defined<br>☐ ROI hypothesis created<br>☐ Executive sponsorship secured |
| **Plan** | Translate strategy into an actionable adoption roadmap. | • Prioritize AI use cases<br>• Assess skill gaps and readiness<br>• Identify required resources<br>• Define implementation waves<br>• Create adoption roadmap | • AI Adoption Roadmap<br>• Skills Assessment<br>• Resource Plan<br>• Prioritized Portfolio<br>• Risk Assessment | ☐ Use cases prioritized<br>☐ Skills gaps assessed<br>☐ Budget estimated<br>☐ Roadmap approved<br>☐ Risks documented |
| **Ready** | Establish the technical, security, governance, and data foundations required for AI workloads. | • Create landing zones<br>• Establish identity and access controls<br>• Configure networking and security<br>• Define governance policies<br>• Prepare data architecture | • AI Landing Zone<br>• Security Architecture<br>• Governance Framework<br>• Data Platform Design<br>• Compliance Controls | ☐ Landing zone deployed<br>☐ Security controls configured<br>☐ RBAC implemented<br>☒ Data sources identified<br>☐ Governance policies defined |
| **Adopt** | Build, validate, and deploy AI solutions. | • Develop proof of concepts (POCs)<br>• Build pilots and MVPs<br>• Implement models, agents, and copilots<br>• Test business workflows<br>• Validate outcomes with users | • Proof of Concept (POC)<br>• Pilot Solution<br>• Production-Ready AI Application<br>• Evaluation Results<br>• Deployment Runbooks | ☐ POC completed<br>☐ User validation completed<br>☐ Security testing passed<br>☐ Production deployment approved<br>☐ Monitoring enabled |
| **Govern** | Ensure AI solutions remain secure, compliant, and responsible throughout their lifecycle. | • Define AI policies<br>• Monitor Responsible AI compliance<br>• Manage access controls<br>• Implement audit processes<br>• Review regulatory requirements | • Governance Policies<br>• Responsible AI Controls<br>• Audit Reports<br>• Compliance Documentation<br>• Risk Register | ☐ Responsible AI controls implemented<br>☐ Audit trail available<br>☐ Compliance requirements met<br>☐ Data access governed<br>☐ Policy reviews scheduled |
| **Manage** | Operate, monitor, optimize, and continuously improve AI solutions. | • Monitor performance and quality<br>• Track adoption and business metrics<br>• Manage incidents<br>• Optimize costs and models<br>• Continuously retrain and improve solutions | • Operational Dashboards<br>• Telemetry & Alerts<br>• Performance Reports<br>• Backlog of Improvements<br>• Optimization Recommendations | ☐ Monitoring configured<br>☐ KPIs tracked<br>☐ Usage analytics reviewed<br>☐ Cost optimization completed<br>☐ Continuous improvement process established |

### RACI Snapshot

| Activity | Solution Architect | Platform Team | Security & Compliance | Data/Knowledge Owner |
|----------|-------------------|---------------|----------------------|----------------------|
| Strategy & use case selection | A/R | C | C | C |
| Agent tech plan (SaaS vs. custom) | A/R | C | C | C |
| Landing zone & policies | C | A/R | C/R (controls) | C |
| Agent governance & SDLC | R | A | A/R (policy) | C |
| Build agents (Foundry/Studio) | A/R | R (platform services) | C | C/R (grounding data) |
| Operate agents & telemetry | A/R | R | C | C |

**Legend:**

- **A** = Accountable
- **R** = Responsible
- **C** = Consulted

### Microsoft Azure Security Hierarchy
![Microsoft Azure Security Hierarchy](/images/microsoft-azure-iam.png)

### Azure Governance
![Azure Governance](/images/microsoft-governance.png)

### Understanding the Role of AI Agents in Business Solutions

- **AI agents** automate tasks, synthesize information, trigger workflows, and execute complex multi-step logic.

- **Microsoft's Cloud Adoption Framework (CAF)** guides architects on adopting ready-to-use SaaS agents or building custom agents using:
  - Azure AI Foundry
  - Microsoft Copilot Studio
  - Containerized AI models

- **Dynamics 365 Copilots** provide:
  - Guided actions
  - Summarization
  - Automated updates
  - Customer service support

These capabilities can serve as benchmarks when designing and deploying AI-powered business solutions.

### Learn More

- Microsoft Cloud Adoption Framework for AI Agents:  
  https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ai-agents/

 ### Technology Decision Framework for Agent Design

| Platform | Best For | Provides / Characteristics |
|----------|----------|----------------------------|
| **Copilot Studio (Low-Code / SaaS)** | • Fast deployment<br>• Direct integration with Dynamics 365 apps<br>• Business analyst-driven customization<br>• Retrieval and task agents | • Prebuilt connectors<br>• Azure AI Search integration<br>• Built-in Responsible AI features<br>• Minimal coding required<br>• Rapid business solution delivery |
| **Microsoft Foundry (Pro-Code / PaaS)** | • Complex orchestrations and multi-agent workflows<br>• Custom logic and advanced generative AI behavior<br>• Enterprise-scale system integration | • Declarative and code-first agent models<br>• Hosted execution environment<br>• Access to OpenAI, Anthropic, Meta, and Mistral models<br>• Support for Activity Protocol and agent-to-agent interactions<br>• Advanced customization and orchestration capabilities |
| **GPUs & Containers (Pro-Code / IaaS)** | • Full control over model execution<br>• Private and isolated compute environments<br>• Strict compliance and BYO model hosting requirements | • Maximum infrastructure control<br>• Self-hosted and open-source model support<br>• Custom networking and runtime configuration<br>• Enhanced security and performance tuning<br>• Complete operational responsibility for scaling, monitoring, and maintenance |

### Agent Architecture Comparison Chart

| Criteria | SaaS Agents | Copilot Studio | Microsoft Foundry | GPUs & Containers |
|-----------|------------|---------------|-------------------|------------------|
| **Customization Depth** | Minimal | Moderate | Deep | Full Control |
| **Security** | Standard SaaS security | Built-in Responsible AI features | Enterprise-grade security | Strict isolation and compliance |
| **Use Case Complexity** | Personal productivity | Process transformation | Strategic transformation | Compliance-sensitive or highly customized solutions |
| **Development Velocity** | Immediate value | Rapid deployment | Flexible development | Custom model configurations |
| **Integration Patterns** | Prebuilt connectors | Direct Dynamics 365 integration | Enterprise system integration | Private networking and isolated compute |
| **Best For** | Ready-to-use productivity assistants | Low-code business applications and workflow automation | Complex orchestrations, multi-agent workflows, and advanced AI applications | Private hosting, regulatory compliance, and full infrastructure control |
| **Target Users** | End users and business teams | Business analysts, citizen developers, Power Platform makers | AI engineers, software developers, solution architects | Platform engineers, ML engineers, infrastructure teams |
| **Infrastructure Management** | Microsoft Managed | Microsoft Managed | Microsoft Managed (PaaS) | Customer Managed (IaaS) |
| **Key Capabilities** | Out-of-the-box AI functionality | Azure AI Search integration, prebuilt connectors, Responsible AI controls | Code-first/declarative agents, hosted execution, multi-model catalog, agent-to-agent communication | Self-hosted models, custom networking, GPU acceleration, isolated environments |
| **Time to Value** | Fastest | Fast | Medium | Slowest |
| **Typical Examples** | Microsoft 365 Copilot, Dynamics 365 Copilots | Custom Copilot Studio agents | Azure AI Foundry agents, multi-agent systems, custom RAG applications | Containerized LLMs, open-source models on AKS, Azure Container Apps, VM-based deployments |
| **When to Choose** | Need immediate business productivity with minimal customization | Need rapid business process automation with low-code development | Need enterprise-grade custom AI solutions and sophisticated orchestration | Need complete control over models, infrastructure, networking, or compliance boundaries |

### Agent Orchestration Patterns

| Orchestration Pattern | Description | Typical Flow / Behavior | Best Used For |
|----------------------|-------------|-------------------------|---------------|
| **Sequential Orchestration** | Deterministic pipeline where tasks execute in a predefined order. | Plan → Enrich → Verify → Act | Multi-step business processes, approvals, document processing, compliance workflows |
| **Concurrent Orchestration** | Multiple agents execute independent tasks in parallel and results are aggregated. | Parallel execution → Aggregate → Reconcile | Research, data gathering, analysis across multiple sources, large-scale processing |
| **Group Chat Orchestration** | Multiple specialized agents collaborate through a mediated discussion while a moderator agent coordinates decisions. | Agent proposals → Discussion → Moderator arbitration → Final response | Brainstorming, decision support, complex problem solving, expert-panel scenarios |
| **Handoff Orchestration** | Control and context are transferred to another specialized agent or a human when specific conditions are met. | Agent detects trigger → Transfer context → Specialist/Human handles request | Customer support escalation, incident management, human-in-the-loop workflows |
| **Magnetic Orchestration** | Dynamic routing model where the most appropriate expert agents are selected at runtime based on the task. | Request → Agent selection → Expert engagement → Consolidated response | Enterprise AI ecosystems, adaptive workflows, large agent networks |

#### Comparison of Orchestration Models

| Criteria | Sequential | Concurrent | Group Chat | Handoff | Magnetic |
|----------|------------|------------|------------|----------|----------|
| **Execution Style** | Linear | Parallel | Collaborative | Transfer-based | Dynamic |
| **Complexity** | Low | Medium | High | Medium | High |
| **Speed** | Slower | Faster | Moderate | Depends on escalation | Adaptive |
| **Agent Interaction** | Minimal | Limited | Extensive | Point-to-point | Dynamic |
| **Determinism** | High | Medium | Medium | High | Low |
| **Human Involvement** | Optional | Optional | Optional | Common | Optional |
| **Best For** | Predictable workflows | Independent subtasks | Multi-perspective reasoning | Escalation scenarios | Large-scale adaptive systems |

> **Selection Guidance**
>
> - Use **Sequential** when workflow order matters.
> - Use **Concurrent** when tasks can be parallelized.
> - Use **Group Chat** when multiple expert perspectives improve outcomes.
> - Use **Handoff** when specialized expertise or human intervention is required.
> - Use **Magnetic** when agent selection must be dynamic and context-driven.

### Platform Role Mapping

| Role | Best Fit Platform | Why | Typical Orchestration |
|------|------------------|-----|----------------------|
| **Domain Assistant (Productivity)** | **Microsoft 365 Copilot** | Immediate value within the flow of work and personal productivity scenarios | Handoff, Group Chat |
| **Business Workflow Agent** | **Copilot Studio** | Rapid iteration, prebuilt connectors, governance guardrails, and low-code customization | Sequential, Handoff |
| **Integration / Orchestration Agent** | **Microsoft Foundry** | Pro-code tools, complex workflows, custom evaluations, enterprise integrations, and advanced orchestration | Concurrent, Sequential, Magnetic |

## Platform Selection Summary

| Scenario | Recommended Platform |
|-----------|---------------------|
| Enhance individual productivity and collaboration | Microsoft 365 Copilot |
| Automate business processes with low-code development | Copilot Studio |
| Build enterprise-grade AI systems with complex workflows and integrations | Microsoft Foundry |

## Orchestration Alignment

| Orchestration Pattern | Most Common Platform |
|----------------------|----------------------|
| Sequential | Copilot Studio, Foundry |
| Concurrent | Foundry |
| Group Chat | Microsoft 365 Copilot, Foundry |
| Handoff | Microsoft 365 Copilot, Copilot Studio |
| Magnetic | Foundry |

## Understanding Prebuilt Agents

Prebuilt **Microsoft 365 Copilot agents** are ready-to-use intelligent assistants that help employees complete tasks, retrieve information, and accelerate workflows across Microsoft 365 applications.

### Common Use Cases

These agents simplify everyday tasks such as:

- Summarizing long documents, chat conversations, and email threads
- Retrieving organizational knowledge and information quickly
- Drafting emails, reports, and other communications
- Providing guidance based on company policies and procedures
- Assisting with routine operational workflows and business processes

### Key Benefits

| Benefit | Description |
|----------|-------------|
| Increased Productivity | Reduces time spent on repetitive tasks |
| Faster Information Retrieval | Quickly finds relevant organizational knowledge |
| Improved Communication | Assists with drafting and summarizing content |
| Consistent Guidance | Delivers responses aligned with organizational policies |
| Workflow Acceleration | Streamlines routine business processes |

### Examples of Prebuilt Microsoft 365 Copilot Capabilities

| Microsoft 365 App | Example Agent Capability |
|-------------------|--------------------------|
| Word | Drafting, rewriting, and summarizing documents |
| Outlook | Email composition, summarization, and prioritization |
| Teams | Meeting recap generation and action item extraction |
| Excel | Data analysis, trend identification, and formula assistance |
| PowerPoint | Presentation creation and content summarization |

> **Key Takeaway:** Prebuilt Microsoft 365 Copilot agents provide immediate business value by helping users work more efficiently within familiar Microsoft 365 applications, without requiring custom development.

## Identifying High Value Use Cases

Solution architects determine candidate use cases by analyzing

- **Task repetitiveness:** How often the task occurs per user per week

- **Knowledge intensity:** Volume of data needed to effectively answer or complete tasks

- **Pain points:** Delays, errors, bottlenecks, or ingestion heavy workflows

- **ROI KPIs impacted:** Hours saved, reduction in ticket volume, faster cycle time

The Microsoft Scenario Library supports identifying functional areas. For more information, see:

https://adoption.microsoft.com/en-us/scenario-library/


### Common Use Case Categories

- **Knowledge Search & Q&A:** Quickly surface policies, procedures, and answers from scattered information

- **Summarization & Reporting:** Turn large content into clear summaries and actionable reports

- **Guided Assistance (e.g., Travel):** Provide consistent, structured guidance using predefined templates

- **Research & Analysis:** Gather insights, analyze data, and deliver KPIs within defined boundaries

- **Productivity Workflows:** Automate communication, meetings, and follow-ups to boost efficiency

## Comparison: Generative Orchestration vs Classic Orchestration

| Behavior | Generative Orchestration | Classic Orchestration |
|----------|--------------------------|-----------------------|
| **Topics** | Selected based on the description of their purpose. | Selected based on matching a user query with trigger phrases. |
| **Child and Connected Agents** | Selected based on their description. | Not applicable. |
| **Tools** | Agent can choose to call tools based on their name and description. | Tools can only be called explicitly from within a topic. |
| **Knowledge** | Agent can proactively search knowledge to answer a user's query. | Knowledge used as fallback when no topics match or called explicitly. |
| **Use of Multiple Topics, Tools, Knowledge Sources** | Agent can use a combination of topics, tools, and knowledge. | Agent tries to select a single topic, falling back to knowledge if configured. |
| **Asking Users for Input** | Agent automatically generates questions to prompt users for missing information. | Must use question nodes in topics to prompt users. |
| **Responding to a User** | Agent automatically generates a response using available information. | Must use message nodes in topics or call a tool. |


## Knowledge Sources in Copilot Studio

| Knowledge Source | Description | Typical Use Cases |
|------------------|-------------|-------------------|
| **Public Website Knowledge** | Search public websites for FAQs, product information, policies, and publicly available content. | Customer support, product information, public documentation, FAQs |
| **Uploaded Documents** | Use stored documents such as PDFs, Word files, PowerPoint presentations, and other internal content. | Internal knowledge bases, policy documents, training materials, manuals |
| **SharePoint Knowledge** | Search indexed SharePoint URLs and content across the organization. | Enterprise search, document retrieval, organizational knowledge management |
| **Dataverse Knowledge** | Answer specific queries using structured relational data stored in Dataverse. | Business applications, CRM data, case management, operational data |
| **Enterprise Connectors** | Access content from connected systems such as OneDrive, Salesforce, ServiceNow, and other enterprise platforms. | Cross-system knowledge retrieval, business process automation, enterprise integrations |
| **Azure OpenAI Connected Data** | Combine vector search and model reasoning to provide deeper contextual understanding and grounded responses. | RAG (Retrieval-Augmented Generation), semantic search, advanced AI assistants, knowledge discovery |