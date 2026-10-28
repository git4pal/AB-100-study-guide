# Design Application Lifecycle Management (ALM) process for AI-powered business solutions

## ALM Foundations for AI Data

### 1.1 Scope the "Data" in AI ALM
Treat the following as versioned, promotable ALM artifacts:
- **Training & fine tuning datasets** (raw, curated, feature/embedding sets).
- **Evaluation/Testing datasets** and "golden" sets for regression testing.
- **Grounding knowledge** (SharePoint/OneDrive corpora, Dataverse tables, wikis, KBs).
- **Prompt assets** (system prompts, prompt actions, templates).
- **Policies & guardrails** (DLP, sensitivity labels, allowed connectors, action limits).
- **Run telemetry** (latency, token/cost, success/failure, safety events) and feedback.

### 1.2 Environment Strategy
Create separate data planes per environment - **Dev → Test → Pre Prod → Prod** - with:
- **Least privilege access:** no cross env shared identity.
- **Red gold datasets pattern:** red (mutable, experimental) vs. gold (frozen, promoted).
- **Promotion gates** that require evidence:
  - Quality reports
  - Bias checks
  - Lineage
  - Security sign off

### AI Data ALM Process (End-to-End)

| Phase | Objective | Key Activities | Exit Gate / Deliverables |
|--------|------------|----------------|--------------------------|
| **Phase A – Plan & Catalog** | Define data governance, ownership, and business context. | • Identify business scenarios and data contracts (purpose, fields, retention, owners)<br>• Classify sensitivity levels<br>• Apply sensitivity labels<br>• Register assets in catalog<br>• Define KPIs and risk posture (PII handling, export boundaries, audit scope) | **Gate A → B:**<br>• Data contract approved<br>• Assets discoverable with owners and tags |
| **Phase B – Ingest & Prepare** | Prepare trusted, reproducible datasets for AI workloads. | • Profile and remediate quality issues (missingness, outliers, imbalance)<br>• Generate lineage information<br>• Stamp schema versions and hashes for each snapshot<br>• Produce curated datasets<br>• Create feature and embedding sets using deterministic pipelines | **Gate B → C:**<br>• Quality reports completed<br>• Lineage reports completed<br>• Reproducibility log signed |
| **Phase C – Develop & Evaluate** | Train, test, and validate models and AI solutions. | • Train and iterate using Dev/Test data only<br>• Never train on production knowledge<br>• Execute evaluation suites (accuracy, safety, robustness, cost)<br>• Validate using golden datasets<br>• Store model cards and data cards with dataset references and context limits | **Gate C → D:**<br>• Evaluation thresholds achieved<br>• Risk findings addressed<br>• Safety findings addressed |
| **Phase D – Stage & Approve** | Verify readiness for production deployment. | • Perform privacy, security, and compliance reviews (DLP, RAI, export controls)<br>• Execute canary runs using masked or representative production-like data<br>• Freeze gold datasets<br>• Sign immutability attestations | **Gate D → E:**<br>• CAB approval obtained<br>• Deployment runbooks ready<br>• Rollback plans documented |
| **Phase E – Deploy & Serve** | Release AI workloads and governed knowledge assets into production. | • Promote gold corpora and indexes<br>• Refresh semantic indexes and retrieval stores<br>• Enforce region and residency settings<br>• Configure connector allow/deny lists<br>• Register release in data catalog<br>• Publish consumer contracts | **Deliverables:**<br>• Production deployment<br>• Updated catalog entries<br>• Published consumer contracts |
| **Phase F – Operate & Monitor** | Maintain operational health, performance, and compliance. | • Monitor latency, token cost, success rate, safety violations, and access denials<br>• Detect data drift against baselines<br>• Trigger safeguard actions (circuit breakers, HITL)<br>• Schedule re-evaluations using golden datasets<br>• Create backlog items with trace IDs | **Deliverables:**<br>• Operational metrics dashboards<br>• Drift reports<br>• Re-evaluation reports<br>• Improvement backlog |
| **Phase G – Evolve & Retire** | Continuously improve or retire AI assets responsibly. | • Retrain or rotate models using updated gold datasets<br>• Retest before promotion<br>• Apply retention and deletion policies<br>• Preserve audit trails and lineage for compliance | **Deliverables:**<br>• Updated models and datasets<br>• Retention records<br>• Audit evidence<br>• Compliance-ready lineage documentation |

### Roles and RACI – Data Used in AI Models and Agents

| Activity | Data Owner | AI Architect | Security / Compliance | Platform Admin | Product Owner |
|-----------|-----------|-------------|----------------------|---------------|--------------|
| **Define data contract** | R | A | C | C | C |
| **Classify & label** | A/R | C | C | C | I |
| **Quality profiling & lineage** | R | A | C | I | I |
| **Evaluation thresholds** | C | A/R | C | I | C |
| **Residency configuration** | C | A | R | R | I |
| **Deployment & rollback** | I | A | C | R | R |
| **Monitoring & drift response** | C | A | C | R | R |
| **Retention & deletion** | A/R | C | C | I | I |

#### RACI Legend

| Code | Meaning |
|--------|---------|
| **R** | Responsible |
| **A** | Accountable |
| **C** | Consulted |
| **I** | Informed |
|

## ALM Foundations for Copilot Studio

### Copilot Studio Solutions Typically Include

| Component Type | Examples |
|----------------|----------|
| **Agents** | Conversational agents, Autonomous agents |
| **Custom Connectors** | Connectors to external systems and services |
| **Actions, Skills, and Prompt Assets** | Prompt actions, reusable skills, templates, instructions |
| **Supporting Dataverse Components** | Dataverse tables, business data, supporting entities |
| **Environment Data and Application Settings** | Environment configurations, application settings, runtime parameters |

### A Mature ALM Process Ensures
| ALM Capability | Description |
|---------------|-------------|
| **Version Control** | Version control of all solution artifacts |
| **Environment Separation** | Clear separation between development, testing, and production |
| **Promotion Validation** | Monitoring and validation at each promotion stage |
| **Governance Compliance** | Compliance with governance, DLP, and data residency requirements |
| **Lifecycle Management** | Sustainable lifecycle for updates and deprecations |
|

## ALM Foundations for Microsoft Foundry Agents

### The ALM Strategy for Microsoft Foundry Agents

| ALM Area | Description |
|-----------|-------------|
| **Environment Separation** | Dev → Test → Production environments |
| **Version Management** | Versioned agent configurations |
| **Promotion Controls** | Controlled promotion gates between environments |
| **Governance** | Governance for connectors, secrets, and data access |
| **Deployment Automation** | Repeatable deployment pipelines |
| **Operations Management** | Monitoring and operations governance |
| **Lifecycle Management** | Lifecycle retirement processes |

### Foundry Control Plane Capabilities

| Capability | Purpose |
|------------|---------|
| **Centralized Agent Management** | Provides centralized oversight of agent definitions across environments |
| **Security Context Management** | Manages security settings and authorization boundaries |
| **Data Source Governance** | Controls access to data sources and grounding information |
| **Runtime Behavior Governance** | Oversees agent runtime behavior across multiple environments |
| **Multi-Environment Administration** | Enables consistent governance from development through production |

### Quick Exam Rule

| Requirement | Foundry ALM Focus |
|-------------|------------------|
| Environment Isolation | Dev → Test → Prod |
| Agent Changes | Versioned Configurations |
| Deployment Readiness | Promotion Gates |
| Security Management | Connectors, Secrets, Data Access |
| Operational Excellence | Monitoring & Governance |
| Long-Term Sustainability | Lifecycle Retirement |

## ALM Foundations for Custom AI Models

### A Strong ALM Process Ensures

| ALM Principle | Description |
|--------------|-------------|
| **Consistency** | Documented development, testing, validation, and deployment steps for every model. |
| **Compliance** | Protection and governance of sensitive data, PII, and industry-specific requirements across iterations. |
| **Repeatability** | Predictable retraining and redeployment with clear version histories and evaluation criteria. |
| **Operational Readiness** | Runtime monitoring, governance logs, and rollback plans to ensure business resilience. |

### Quick Exam Rule

| Principle | Remember |
|-----------|----------|
| **Consistency** | Standardized processes |
| **Compliance** | Secure and governed data |
| **Repeatability** | Versioned and reproducible deployments |
| **Operational Readiness** | Monitor, govern, and recover |

### Custom AI Model ALM Summary

```text
Consistency
    ↓
Compliance
    ↓
Repeatability
    ↓
Operational Readiness

Result:
Reliable, Governed, Reproducible, and Production-Ready AI Models
```

