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

## Understanding the Role of AI Agents in Business Solutions

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

## Multi Agent Solution

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

### Platform Selection Summary

| Scenario | Recommended Platform |
|-----------|---------------------|
| Enhance individual productivity and collaboration | Microsoft 365 Copilot |
| Automate business processes with low-code development | Copilot Studio |
| Build enterprise-grade AI systems with complex workflows and integrations | Microsoft Foundry |

### Orchestration Alignment

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

### Identifying High Value Use Cases

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

### Comparison: Generative Orchestration vs Classic Orchestration

| Behavior | Generative Orchestration | Classic Orchestration |
|----------|--------------------------|-----------------------|
| **Topics** | Selected based on the description of their purpose. | Selected based on matching a user query with trigger phrases. |
| **Child and Connected Agents** | Selected based on their description. | Not applicable. |
| **Tools** | Agent can choose to call tools based on their name and description. | Tools can only be called explicitly from within a topic. |
| **Knowledge** | Agent can proactively search knowledge to answer a user's query. | Knowledge used as fallback when no topics match or called explicitly. |
| **Use of Multiple Topics, Tools, Knowledge Sources** | Agent can use a combination of topics, tools, and knowledge. | Agent tries to select a single topic, falling back to knowledge if configured. |
| **Asking Users for Input** | Agent automatically generates questions to prompt users for missing information. | Must use question nodes in topics to prompt users. |
| **Responding to a User** | Agent automatically generates a response using available information. | Must use message nodes in topics or call a tool. |

## Copilot Studio
Copilot Studio provides a **low-code environment** for building task and retrieval agents, enabling rapid design cycles and controlled extensibility. It imposes constraints through managed connectors, responsible AI boundaries, and simplified orchestration.

### Knowledge Sources in Copilot Studio

| Knowledge Source | Description | Typical Use Cases |
|------------------|-------------|-------------------|
| **Public Website Knowledge** | Search public websites for FAQs, product information, policies, and publicly available content. | Customer support, product information, public documentation, FAQs |
| **Uploaded Documents** | Use stored documents such as PDFs, Word files, PowerPoint presentations, and other internal content. | Internal knowledge bases, policy documents, training materials, manuals |
| **SharePoint Knowledge** | Search indexed SharePoint URLs and content across the organization. | Enterprise search, document retrieval, organizational knowledge management |
| **Dataverse Knowledge** | Answer specific queries using structured relational data stored in Dataverse. | Business applications, CRM data, case management, operational data |
| **Enterprise Connectors** | Access content from connected systems such as OneDrive, Salesforce, ServiceNow, and other enterprise platforms. | Cross-system knowledge retrieval, business process automation, enterprise integrations |
| **Azure OpenAI Connected Data** | Combine vector search and model reasoning to provide deeper contextual understanding and grounded responses. | RAG (Retrieval-Augmented Generation), semantic search, advanced AI assistants, knowledge discovery |

## Define solution rules and constraints for AI components

### Architectural Foundations and Platform Roles

| Solution / Platform | Key Constraints | Solution Rules |
|---------------------|----------------|----------------|
| **Microsoft 365 Copilot** | • Limited to Microsoft 365 security boundaries and permissions<br>• Uses organizational data through Microsoft Graph<br>• Primarily focused on productivity scenarios<br>• Customization is more constrained than custom-built agents | • Respect existing Microsoft 365 permissions<br>• Ground responses using approved organizational content<br>• Follow Responsible AI principles<br>• Restrict access to sensitive data based on user entitlements |
| **Copilot Studio** | • Low-code platform capabilities<br>• Dependent on available connectors and supported integrations<br>• Bound by Dataverse, environment, and governance policies<br>• Best suited for business workflow automation and guided experiences | • Define topics, triggers, instructions, and orchestration logic<br>• Establish escalation paths and approval workflows<br>• Control which actions can be executed automatically<br>• Define allowed knowledge sources and business processes |
| **Microsoft Foundry (Azure AI Foundry)** | • Requires AI engineering and governance practices<br>• Subject to model quotas, deployment limits, and service availability<br>• Requires implementation of security, monitoring, and lifecycle management<br>• Higher complexity than low-code solutions | • Define system prompts, agent behavior, and orchestration patterns<br>• Specify approved models and grounding sources<br>• Establish evaluation, monitoring, and safety controls<br>• Define human-in-the-loop requirements for critical decisions |
| **GPUs & Containers (Custom AI Infrastructure)** | • Customer responsible for infrastructure, scaling, security, patching, and monitoring<br>• Requires MLOps/GenAIOps capabilities<br>• Higher operational complexity and cost<br>• Compliance and availability are customer-managed | • Define model hosting and deployment standards<br>• Enforce networking, security, and compliance requirements<br>• Specify model lifecycle and version management processes<br>• Establish operational guardrails and monitoring requirements |
| **Azure AI Search / RAG Solutions** | • Quality depends on data freshness, chunking, indexing, and retrieval strategy<br>• Retrieval performance depends on index design and embeddings<br>• Access controlled by identity and authorization settings | • Define authoritative knowledge sources<br>• Specify chunking, indexing, and refresh policies<br>• Control citation and grounding requirements<br>• Ensure responses are generated only from approved knowledge sources |
| **Custom Models / Fine-Tuned Models** | • Require training datasets, evaluation frameworks, and monitoring<br>• Potential model drift over time<br>• Higher governance and maintenance requirements | • Define acceptable training data sources<br>• Establish evaluation metrics and success criteria<br>• Define retraining schedules and approval processes<br>• Apply Responsible AI and compliance reviews before deployment |
| **Power Platform AI Solutions** | • Governed by Power Platform environments and DLP policies<br>• Connector limitations and licensing may apply<br>• Dataverse often acts as the underlying data platform | • Apply environment governance controls<br>• Define approved connectors and data flows<br>• Enforce DLP and compliance policies<br>• Define automation boundaries and user permissions |

### Quick Exam Rule

| Platform | Primary Rule Focus | Primary Constraint Focus |
|-----------|-------------------|--------------------------|
| **Microsoft 365 Copilot** | User permissions, data access, and productivity workflows | Microsoft 365 security boundaries and Microsoft Graph permissions |
| **Copilot Studio** | Topics, actions, workflows, instructions, and business logic | Low-code platform capabilities, connector limitations, and environment policies |
| **Microsoft Foundry** | Agent behavior, orchestration, prompts, evaluations, and model governance | Model quotas, service limits, security requirements, and operational complexity |
| **GPUs & Containers** | Infrastructure standards, model lifecycle, security, and operational controls | Compute capacity, networking, compliance, infrastructure management, and cost |
| **Azure AI Search / RAG** | Grounding policies, retrieval quality, citations, and knowledge source governance | Index design, chunking strategy, embedding quality, and data freshness |
| **Custom Models** | Training governance, evaluations, monitoring, and retraining processes | Training data quality, model drift, lifecycle management, and compliance controls |
| **Power Platform AI** | DLP policies, automation rules, approved connectors, and user permissions | Environment governance, licensing, connector availability, and Dataverse dependencies |

## Extend Microsoft 365 Copilot vs Build a Custom Agent vs Create a Custom AI Model

| Parameter | Extend Microsoft 365 Copilot | Build a Custom Agent | Create a Custom AI Model |
|------------|-----------------------------|----------------------|--------------------------|
| **Primary Goal** | Enhance user productivity within Microsoft 365 experiences | Automate business processes and execute business-specific workflows | Solve domain-specific AI problems requiring specialized intelligence |
| **Typical Use Cases** | Summarization, drafting, Q&A, meeting insights, content creation | Workflow automation, approvals, case management, operational processes | Fraud detection, demand forecasting, predictive maintenance, medical diagnosis, custom classification |
| **Business Focus** | User productivity | Process automation | Business intelligence and specialized AI capabilities |
| **Autonomy** | Low | High | N/A (model provides predictions or reasoning, not workflows) |
| **Workflow Complexity** | Simple interactions | Complex multi-step workflows | Typically embedded inside workflows or applications |
| **Custom Logic** | Limited | Extensive | Learned from training data rather than explicit business rules |
| **Data Sources** | Microsoft Graph and Microsoft 365 content | Any enterprise data source | Specialized training datasets and enterprise data |
| **Knowledge Grounding** | Microsoft 365 organizational content | Enterprise-wide knowledge and systems | Training data, fine-tuning datasets, and domain-specific data |
| **Reasoning Scope** | Productivity-focused assistance | Business-process reasoning and orchestration | Specialized domain reasoning and prediction |
| **Actions** | Simple actions and integrations | Complex actions, approvals, transactions, and updates | Typically no direct actions; provides intelligence consumed by applications or agents |
| **Orchestration** | None or implicit | Full agent orchestration | Requires external orchestration by applications or agents |
| **Enterprise Integration** | Microsoft ecosystem | Cross-platform enterprise integrations | Integrated into applications, agents, or AI pipelines |
| **Development Approach** | Configuration and extension | Agent design and development | Data science, model training, evaluation, and deployment |
| **Required Skills** | Microsoft 365 administration and Copilot extensibility | Solution architecture, development, AI orchestration | Data science, machine learning, MLOps, model governance |
| **Time to Value** | Fastest | Medium | Slowest |
| **Data Requirements** | Existing Microsoft 365 content | Operational and enterprise data | Large quantities of high-quality training data |
| **Infrastructure Complexity** | Low | Medium | High |
| **Operational Overhead** | Low | Medium to High | High |
| **Governance Requirements** | Built-in Microsoft governance | Custom governance and monitoring | Full model governance, monitoring, retraining, and compliance controls |
| **Model Ownership** | Microsoft managed | Uses Microsoft or third-party foundation models | Organization owns or manages the model lifecycle |
| **Cost Profile** | Lowest | Medium | Highest |
| **Best Fit Scenario** | Improve how people work | Automate how work gets done | Create AI capabilities not available from existing models |
| **Example** | Summarize recent customer emails and prepare a draft response | Create a customer case, validate data, route for approval, and notify stakeholders | Train a model to predict equipment failures before they occur |

### Decision Guide

| If the Requirement Is... | Recommended Approach |
|--------------------------|---------------------|
| Summarize, draft, search, or answer questions | Extend Copilot |
| Improve employee productivity | Extend Copilot |
| Work inside Teams, Outlook, Word, Excel, or PowerPoint | Extend Copilot |
| Automate a multi-step workflow | Build a Custom Agent |
| Execute business actions across systems | Build a Custom Agent |
| Orchestrate multiple tools, APIs, or agents | Build a Custom Agent |
| Predict future outcomes | Create a Custom AI Model |
| Detect anomalies or fraud | Create a Custom AI Model |
| Classify content using domain-specific criteria | Create a Custom AI Model |
| Use proprietary business data to create unique intelligence | Create a Custom AI Model |
| Require highly specialized industry expertise | Create a Custom AI Model |

### Architecture Selection Shortcut

| Question | Choose |
|-----------|--------|
| Need to help users work better? | Extend Copilot |
| Need to automate a business process? | Build a Custom Agent |
| Need AI to predict, classify, detect, or forecast something unique? | Create a Custom AI Model |

### Exam Shortcut

```text
Extend Copilot
  → Productivity
  → Microsoft 365
  → Summarize / Draft / Search

Custom Agent
  → Automation
  → Orchestration
  → Actions
  → Multi-step Workflows

Custom AI Model
  → Predictions
  → Classification
  → Forecasting
  → Domain Expertise
  → Training Data
```

## SLM Use Cases

### When to Use a Customized SLM vs a General LLM

| Decision Factor | Use Customized SLM | Use General LLM |
|----------------|-------------------|-----------------|
| Domain specificity | High | Low |
| Latency sensitivity | High | Medium/Low |
| Cost constraints | High sensitivity | Moderate |
| Data sovereignty required | Yes | Maybe |
| Task complexity | Medium-High, specialized | High, general |
| Deployment environment | Edge/IoT/onprem | Cloud |
| Regulatory restrictions | High | Moderate |

## AI Workload Role Matrix

| Role | Purpose | Key Responsibilities | Risk if Missing |
|------|---------|----------------------|-----------------|
| **Executive Sponsor / Business Leader** | Provides strategic direction, secures funding, and removes organizational barriers. | • Align AI initiatives with business strategy and KPIs<br>• Champion cultural and operational change<br>• Approve governance frameworks and risk posture | Stalled adoption, lack of funding, and reduced organizational visibility. |
| **AI Center of Excellence (AI CoE) Lead** | Coordinates AI strategy, ensures governance, and orchestrates organizational alignment. | • Facilitate collaboration across business, data, engineering, and compliance teams<br>• Prioritize AI use cases based on business value<br>• Develop enterprise AI maturity and workflow standards | Lack of technological oversight, inconsistent architecture, and breakdowns in Responsible AI principles such as transparency. |
| **Product Owner for AI Workloads** | Owns the business outcome of AI solutions. | • Define problem statements and acceptance criteria<br>• Manage roadmap, budget, and stakeholder expectations<br>• Guide the AI solution lifecycle from ideation to deployment | Unclear vision, poor alignment with business objectives, low user adoption, and increased technical debt. |
| **Business Domain Specialist** | Provides domain expertise required for model grounding, evaluation, and performance validation. | • Validate AI output accuracy within business context<br>• Provide labeled data and subject matter insights<br>• Identify operational pain points suitable for AI augmentation | Increased risk of inaccurate outputs and solutions that fail to meet business requirements. |
| **Data Owner / Data Steward** | Ensures the quality, accessibility, and governance of organizational data powering AI workloads. | • Approve data access and safeguarding measures<br>• Oversee data inventory, classification, and lineage<br>• Ensure compliance with regulatory and organizational data policies | Poor data quality, governance gaps, and compliance risks. |
| **Responsible AI / Compliance Officer** | Implements risk management, legal, and Responsible AI guardrails. | • Define ethical guidelines and governance frameworks<br>• Evaluate and mitigate model risk scenarios<br>• Monitor fairness, transparency, and safe operation of AI workloads | Increased bias, ethical concerns, regulatory risks, and non-compliance with Responsible AI principles. |
| **Change Management & Skilling Lead** | Drives adoption by preparing employees for AI-enabled workflows. | • Define skilling plans mapped to workforce personas<br>• Develop adoption playbooks and onboarding materials<br>• Ensure organizational readiness and operational integration | Low adoption, poor change management, and failure to realize AI business value. |

### AI Workload Technical Personas

| Persona | Primary Responsibility |
|----------|------------------------|
| **AI Engineer** | Builds, tests, and evaluates AI workloads. |
| **Data Scientist** | Develops and experiments with models and feature pipelines. |
| **Data Engineer** | Prepares and orchestrates data assets for AI consumption. |
| **Application Developer** | Integrates AI capabilities into applications and services. |
| **MLOps / AIOps Engineer** | Manages deployment, automation, monitoring, and performance optimization. |

### Quick Exam Rule

| Role | Focus Area |
|------|-----------|
| Executive Sponsor | Strategy, Funding, Executive Support |
| AI CoE Lead | Governance, Standards, Coordination |
| Product Owner | Business Outcomes, Roadmap, Requirements |
| Business Domain Specialist | Domain Expertise, Validation, Grounding |
| Data Owner / Steward | Data Quality, Security, Compliance |
| Responsible AI Officer | Ethics, Risk Management, Governance |
| Change & Skilling Lead | Adoption, Training, Readiness |
| AI Engineer | AI Solution Development |
| Data Scientist | Model Creation & Optimization |
| Data Engineer | Data Pipelines & Integration |
| Application Developer | Application Integration |
| MLOps / AIOps Engineer | Deployment, Monitoring, Operations |