# Design responsible AI security, governance, risk management, and compliance

## Identity and Access Design - Agent Identity

Every agent, tool, and pipeline has a first-class identity, clear ownership, and least privilege access.

### Key Design Principles

| Principle | Description |
|------------|-------------|
| **Unique Identity per Agent** | Assign a unique cloud identity per agent (prod, pre-prod, dev) with ownership, version, and lifecycle metadata. |
| **Clear Ownership** | Each agent identity should have designated ownership and accountability across environments. |
| **Environment Separation** | Maintain separate identities for Production, Pre-Production, and Development environments. |
| **Lifecycle Metadata** | Track ownership, version information, and lifecycle status for every agent identity. |
| **Managed Identities Preferred** | Prefer managed identities for agent-to-Azure authentication to remove secrets and simplify credential rotation. |
| **Least Privilege Access** | Grant only the permissions required for the agent to perform its intended functions. |

### Recommended Identity Strategy

| Environment | Identity Approach |
|------------|-------------------|
| **Development** | Dedicated managed identity with development-scoped permissions |
| **Pre-Production** | Separate managed identity with testing and validation permissions |
| **Production** | Dedicated managed identity with production-approved permissions only |

### Benefits of Managed Identities

| Benefit | Description |
|----------|-------------|
| **No Secrets Management** | Eliminates the need to store credentials or connection secrets |
| **Simplified Rotation** | Credential lifecycle managed automatically |
| **Improved Security** | Reduces risk of credential exposure |
| **Azure-Native Authentication** | Direct integration with Azure services |
| **Operational Simplicity** | Less administrative overhead for identity management |

## Data Governance and Protection - Data Boundaries

Agents use only the right data, in the right places, for the right duration.

### Key Data Boundary Principles

| Principle | Description |
|-----------|-------------|
| **Workload Separation** | Separate internal vs. public workloads; keep confidential sources out of public-facing agents. |
| **Data Access Control** | Ensure agents access only approved and authorized data sources. |
| **Confidential Data Protection** | Prevent confidential or sensitive organizational information from being exposed through public-facing AI solutions. |
| **Data Residency Compliance** | Honor data residency requirements by selecting compliant regions for knowledge, logs, and memory. |
| **Purpose-Based Data Usage** | Use data only for approved business scenarios and intended workloads. |
| **Data Lifecycle Management** | Retain and process data only for the required duration. |

### Recommended Governance Controls

| Control Area | Implementation Guidance |
|--------------|-------------------------|
| **Internal Agents** | Allow access to confidential organizational knowledge and approved internal systems. |
| **Public Agents** | Restrict access to public data sources and approved external content only. |
| **Knowledge Stores** | Store knowledge in approved geographic regions according to compliance requirements. |
| **Logging & Telemetry** | Ensure logs and monitoring data comply with regional residency requirements. |
| **Agent Memory** | Configure memory stores in compliant regions and according to retention policies. |

### Quick Exam Rule

| Requirement | Focus Area |
|-------------|-----------|
| Internal vs Public AI | Workload Separation |
| Sensitive Information Protection | Confidential Data Control |
| Regional Compliance | Data Residency |
| Data Usage Governance | Right Data |
| Location Governance | Right Place |
| Retention Governance | Right Duration |

## Data Governance and Protection - Retention and Transparency

### Retention and Minimization

| Principle | Description |
|-----------|-------------|
| **Retention Windows** | Define retention windows for logs, agent memories, and training data. |
| **Automated Purge** | Automate deletion of data when retention periods expire. |
| **Anonymization** | Apply anonymization processes to reduce exposure of sensitive information. |
| **Data Minimization** | Retain only the data required for business, operational, and compliance purposes. |

### Transparency

| Principle | Description |
|-----------|-------------|
| **AI Disclosure** | Disclose AI involvement to users and stakeholders. |
| **Data Usage Disclosure** | Communicate how data is collected, used, stored, and processed. |
| **Stakeholder Visibility** | Provide transparency into AI-assisted workflows and decision-making processes. |
| **Data Deletion Mechanisms** | Provide mechanisms for users to request or initiate data deletion. |

### Quick Exam Rule

| Requirement | Focus Area |
|-------------|-----------|
| How long should data be kept? | Retention |
| Remove expired data automatically | Purge |
| Protect personal information | Anonymization |
| Store only necessary information | Minimization |
| Inform users when AI is involved | Transparency |
| Explain how data is used | Data Usage Disclosure |
| Allow data removal requests | Data Deletion Mechanisms |

## Governance Principles for AI Agents

### Accountability & Ownership

| Principle | Description |
|-----------|-------------|
| **Agent Owner** | Assign an agent owner responsible for lifecycle, security posture, and approvals. |
| **Agent Registry** | Maintain an agent registry documenting purpose, environment, risk level, and data access. |
| **Publishing Approvals** | Require publishing approvals for agents handling sensitive or regulated data. |

### Agent Ownership Model

| Agent | Owner | Environment | Risk Classification | Approval Required |
|---------|---------|------------|--------------------|------------------|
| Agent A | Assigned Owner | Production | Low | No |
| Agent B | Assigned Owner | Development | Medium | Manager |
| Agent C | Assigned Owner | Test | High | Executive |
| Agent D | Assigned Owner | Production | Medium | Manager |
| Agent E | Assigned Owner | Production | High | Executive |

> Note: The image contains placeholder/sample text in the ownership matrix. The key takeaway is the governance pattern: owner assignment, environment tracking, risk classification, and approval requirements.

### Governance Controls

| Governance Area | Requirement |
|-----------------|-------------|
| **Ownership** | Every agent must have a designated owner. |
| **Lifecycle Management** | Owners are accountable for updates, approvals, retirement, and operational governance. |
| **Registry Management** | Maintain centralized records of agent purpose, environment, risk level, and data access permissions. |
| **Risk Classification** | Categorize agents according to business and data sensitivity risk. |
| **Approval Workflow** | Require managerial or executive approval for medium- and high-risk agents. |
| **Regulated Data Handling** | Apply additional governance controls before publishing agents that process sensitive or regulated information. |

### Quick Exam Rule

| Requirement | Governance Focus |
|-------------|------------------|
| Who owns the agent? | Agent Owner |
| Where is the agent documented? | Agent Registry |
| How risky is the agent? | Risk Classification |
| Can the agent be published? | Approval Process |
| Handles regulated data? | Publishing Approval Required |
| Who approves high-risk agents? | Executive Sponsor / Executive Approval |

## Designing Model Security

### 1. Secure Identities and Authentication

#### Use Managed Identities

| Control | Guidance |
|----------|----------|
| **Managed Identities** | Use managed identities for each model endpoint and Foundry workload. |
| **Secret Elimination** | Remove all secrets, static keys, or embedded credentials from pipelines. |
| **Identity Lifecycle Management** | Enforce identity lifecycle management including rotation, disablement, and periodic review. |

#### Role-Based Access Control (RBAC)

| Control | Guidance |
|----------|----------|
| **Least Privilege Access** | Apply role-based access control (RBAC) using the least privilege principle. |
| **Function-Based Access** | Grant access based on model function, not developer convenience. |
| **Resource-Scoped Roles** | Use resource-scoped roles for training, deployment, and inferencing. |

## 2. Authorization and Access Boundaries

Solution architects help define the boundaries around what models can access, process, and output.

### Segregate Development and Production

| Control | Guidance |
|----------|----------|
| **Environment Separation** | Separate inference endpoints for Development, Test, and Production environments. |
| **Production Controls** | Apply tighter RBAC and approval workflows in production environments. |
| **Environment Isolation** | Prevent direct promotion or unrestricted access between environments. |

### Limit Privileged Access

| Control | Guidance |
|----------|----------|
| **Restricted Model Administration** | Restrict model modification, retraining, and redeployment rights. |
| **Approval Requirements** | Require multi-step approvals for sensitive model updates. |
| **Least Privilege** | Grant operational permissions only to authorized roles. |

### Authorization Architecture

| Layer | Components | Purpose |
|--------|------------|---------|
| **Identity Control Layer** | Managed Identity, RBAC Scopes | Controls authentication and authorization boundaries |
| **Model Execution Layer** | Inference Endpoint, Foundry Runtime | Executes model workloads within approved controls |
| **Data Boundary Layer** | Approved Data Sources, Redacted Output Filters | Restricts data access and protects sensitive information |

## 3. Protect Data Used by Models

Models interact with sensitive information through training data, memory stores, logs, and output responses.

### Data Minimization

| Control | Guidance |
|----------|----------|
| **Minimum Required Data** | Use the minimum data required for the model's purpose. |
| **Sensitive Data Redaction** | Redact sensitive fields (PII, secrets, financial identifiers) during preprocessing. |
| **Purpose-Based Data Usage** | Limit data collection and processing to approved business objectives. |

### Encryption and Residency

| Control | Guidance |
|----------|----------|
| **Encryption at Rest** | Ensure all stored data and model artifacts are encrypted at rest. |
| **Encryption in Transit** | Ensure all input, output, and intermediate artifacts are encrypted in transit. |
| **Data Residency Compliance** | Deploy models in regions that meet data residency and compliance requirements. |

### DLP Enforcement

| Control | Guidance |
|----------|----------|
| **DLP Rules** | Apply DLP rules to prevent sensitive data from being returned in model responses. |
| **Output Protection** | Implement filters to block harmful or restricted outputs. |
| **Data Leakage Prevention** | Prevent unintended exposure of confidential information through prompts, logs, or responses. |

### Security Architecture Summary

| Security Layer | Key Controls |
|---------------|-------------|
| **Data Collection Layer** | Data minimization, PII redaction |
| **Storage Layer** | Encryption at rest, residency controls |
| **Processing Layer** | Encryption in transit, approved datasets |
| **Output Layer** | DLP policies, output filtering |
| **Governance Layer** | Compliance monitoring, auditing, retention controls |

## 4. Harden AI Workloads

Harden the environment where AI models operate to reduce attack surfaces.

### Model Infrastructure Hardening

| Control | Guidance |
|----------|----------|
| **Network Isolation** | Use isolated networks or private endpoints. |
| **Secure Build Pipelines** | Enforce secure build pipelines for training artifacts. |
| **Public Traffic Restrictions** | Block inbound public traffic unless explicitly required. |

### Model Drift and Poisoning Safeguards

| Control | Guidance |
|----------|----------|
| **Data Lineage Tracking** | Track data lineage for all training sources. |
| **Training Data Validation** | Validate newly introduced data before using it in retraining pipelines. |
| **Anomaly Detection** | Automate anomaly detection in model behavior and output patterns. |

### Model Hardening Blueprint

| Layer | Purpose |
|--------|---------|
| **Secure Compute** | Protect compute resources used for training and inferencing. |
| **Private Endpoints** | Restrict network access to approved private connections. |
| **Threat Protection** | Detect and mitigate attacks against AI infrastructure. |
| **Validation Pipeline** | Verify models, datasets, and deployments before promotion. |
| **Hardened Model Core** | Operate AI models within secured and validated environments. |
| **Monitoring & Drift Detection** | Continuously monitor behavior, performance, drift, and anomalies. |

## 5. Threat Detection and Response

Harden the environment where AI models operate to reduce attack surfaces.

### Threat Protection

| Control | Guidance |
|----------|----------|
| **AI-Specific Threat Detection** | Enable AI-specific threat detection for prompt injection, unauthorized access attempts, and unusual inference patterns. |
| **Automated Security Scanning** | Use automated scanning to identify insecure default settings and misconfigurations. |
| **Prompt Injection Protection** | Detect and mitigate attempts to manipulate model instructions or behavior. |
| **Access Anomaly Detection** | Monitor for abnormal authentication, authorization, and usage patterns. |

### Logging and Monitoring

| Control | Guidance |
|----------|----------|
| **Identity Access Logging** | Collect logs for identity access activities. |
| **Model Operations Logging** | Track model operations and lifecycle events. |
| **System Event Monitoring** | Monitor infrastructure and platform events. |
| **Output Anomaly Detection** | Identify unusual model outputs and response patterns. |
| **SOC Integration** | Route security alerts to SOC workflows for triage and escalation. |

### Incident Response for AI Models

| Control | Guidance |
|----------|----------|
| **Compromised Endpoint Procedures** | Predefine steps to disable a compromised model endpoint. |
| **Forensic Evidence Preservation** | Preserve inference logs and model artifacts for forensic analysis. |
| **Rollback Planning** | Establish rollback procedures for restoring prior model versions. |
| **Incident Recovery** | Ensure recovery processes exist for security and operational incidents. |

### Security Operations Framework

| Security Area | Key Controls |
|--------------|-------------|
| **Prevention** | Threat detection, automated scanning, prompt injection protection |
| **Detection** | Monitoring, anomaly detection, log collection |
| **Response** | SOC triage, endpoint disablement, incident management |
| **Recovery** | Rollback procedures, forensic analysis, service restoration |

## 6. Governance and Lifecycle Controls

Strong governance ensures models remain secure throughout their lifecycle.

### Policy-Driven Model Management

| Control | Guidance |
|----------|----------|
| **Approval Checkpoints** | Mandate approval checkpoints for model deployment, retraining, and version promotion. |
| **Model Documentation** | Require documentation for model purpose, training data, parameters, and risk profile. |
| **Version Governance** | Control promotions between model versions through formal review and approval processes. |
| **Risk Management** | Maintain documented risk assessments and mitigation plans for models throughout their lifecycle. |

### Lifecycle Governance

| Control | Guidance |
|----------|----------|
| **Retention Requirements** | Assign retention requirements for training data, logs, and memory stores. |
| **Model Review Process** | Periodically review models to ensure continued security, quality, and compliance. |
| **Model Retirement** | Retire outdated models that no longer meet security, performance, or quality standards. |
| **Lifecycle Tracking** | Maintain visibility into the status of models from creation through retirement. |

### Model Governance Lifecycle

| Lifecycle Stage | Key Controls |
|-----------------|-------------|
| **Create Model** | Validation, Documentation |
| **Review Model** | Peer Review, Testing |
| **Approve Model** | Sign-off, Compliance Check |
| **Deploy Model** | Staging, Rollout Plan |
| **Monitor Model** | Performance Tracking, Bias Detection |
| **Update / Retire Model** | Retraining, Archiving |

## AI Vulnerability Categories Summary

| Vulnerability Category | Common Risks / Attack Vectors | Potential Impact | Recommended Mitigations |
|------------------------|-------------------------------|------------------|-------------------------|
| **Prompt Manipulation Risks** | • Override system instructions ("ignore previous instructions")<br>• Deceptive context injection<br>• Multi-step coercion or prompt poisoning<br>• Hidden instructions in text, HTML, or uploaded files | • Sensitive data disclosure<br>• Unintended action execution<br>• Harmful or incorrect outputs<br>• Manipulation of downstream tools and automations | • Input validation<br>• Prompt filtering and guardrails<br>• Context isolation<br>• Output monitoring and review |
| **Model Behavior Vulnerabilities** | • Hallucinations and fabricated information<br>• Toxic or harmful content generation<br>• Weak safety-boundary enforcement<br>• Biased reasoning and unfair outcomes<br>• Overgeneralization creating compliance risks | • Loss of trust<br>• Regulatory issues<br>• Incorrect business decisions<br>• Reputational damage | • Evaluate output safety<br>• Validate output correctness<br>• Monitor consistency<br>• Measure response variability<br>• Detect model drift after retraining |
| **Data Exposure Vulnerabilities** | • Indirect disclosure through prompts<br>• Unprotected logs, memory stores, or transcripts<br>• Excessive permissions<br>• Malicious instructions embedded in input files | • Exposure of PII and confidential information<br>• Compliance violations<br>• Data leakage | • Data minimization<br>• RBAC enforcement<br>• Intent-based access<br>• Sensitive data redaction<br>• Secure storage and logging |
| **Identity, Access, and RBAC Gaps** | • Elevated privilege misuse<br>• Unauthorized access to downstream tools<br>• Privilege escalation through connectors or plugins | • Unauthorized actions<br>• Data access violations<br>• Security breaches | • Least-privilege access<br>• Managed identities<br>• Environment separation (Dev/Test/Prod)<br>• Access log reviews and anomaly detection |
| **Agent and Workflow-Level Vulnerabilities** | • Autonomous tool use without guardrails<br>• Misinterpreted instructions<br>• Lack of auditing and rollback capabilities<br>• Unsecured external workflow integrations | • Unintended business actions<br>• Workflow failures<br>• Compliance and operational risks | • Define tool capability boundaries<br>• Enable end-to-end auditing<br>• Implement monitoring<br>• Validate workflows through evaluation pipelines before production |


### Security Mapping

| Security Control | Protects Against |
|------------------|------------------|
| Guardrails & Prompt Filtering | Prompt Manipulation |
| Safety Evaluations | Model Behavior Risks |
| Data Minimization & RBAC | Data Exposure |
| Managed Identity & Least Privilege | Identity & Access Gaps |
| Auditing, Monitoring & Workflow Validation | Agent & Workflow Vulnerabilities |

