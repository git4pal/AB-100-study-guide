# Manage testing AI-powered business solutions

## Recommend process metrics

### 1. Testing Framework for AI Agents
- Create a testing framework for all AI agents.
- Establish the testing objective before testing begins.
- Validate agent’s ability to meet intended business outcomes.
- Ensure accuracy and consistency across scenarios.
- Verify guardrails, data boundaries, and compliance policies operate correctly.
- Detect issues early and establish baseline for future tuning.

### 2. Recommended Testing Process
- Testing can be manual or automated.
- Multiple types of testing apply to AI agents.

### 3. Testing Types
- Scenario testing
- Performance testing
- Safety testing
- Usability testing

#### 3.1 Core Quantitative Metrics
- **Accuracy and Relevance:** percentage of responses correctly answering user intent and aligned with business process.
- **Response Time:** speed and variability of agent's answers.
- **Success Rate:** percentage of tasks completed without human intervention.
- **Failure Rate:** incorrect, incomplete, or unusable answers; frequency of errors or guardrail triggers.
- **Token Efficiency (for generative agents):** content generated relative to cost; signs of verbosity or inefficiency.

#### 3.2 Behavioral and Quality Metrics
- **User Satisfaction:** survey or rating signals, number of escalations or repeated attempts.
- **Conversation Quality:** coherence, step-by-step reasoning, ability to interpret follow-up questions.
- **Knowledge Coverage:** depth and breadth of domain knowledge, completeness of grounding sources, gaps in information retrieval.

#### 3.3 Observability and Operational Metrics
- **Stability:** sessions completed without interruption, error spikes or instability patterns.
- **Load Handling:** agent behavior under heavy usage, throughput capacity.
- **Guardrail Compliance:** count of prevented actions, instances approaching restricted content.

## Foundations of Model Validation
- Model validation ensures custom AI models perform as expected and maintain quality in production.
- Core questions include correctness, stability, trustworthiness, and alignment with business intent.
- Key validation dimensions:
  - Performance metrics
  - Quality and accuracy checks
  - Safety and compliance
  - Cost and efficiency
  - User-centric metrics

### Define Quantitative Validation Criteria
Quantitative criteria ensure measurable and repeatable evaluation during tuning or deployment.
- **Accuracy Rate:** frequency of correct or acceptable outputs.
- **Latency and Response Time:** speed for mission critical workflows.
- **Throughput:** number of requests processed under peak loads.
- **Error Rates:** frequency of invalid or incomplete responses.
- **Token Efficiency:** model usage cost relative to output quality.
- **Drift Indicators:** changes in output quality due to evolving data.

### Define Qualitative Validation Criteria
Qualitative evaluation identifies nuanced issues beyond numeric metrics.
- **Relevance and Completeness:** right level of detail without hallucinations.
- **Consistency of Reasoning:** logical steps aligned with workflows.
- **Grounding Integrity:** use of approved organizational knowledge.
- **User Experience Quality:** clarity, coherence, readability, instructional usefulness.

### Example Validation Matrix for Custom Models

| Validation Area | Metric / Criteria | Success Threshold |
|-----------------|------------------|------------------|
| **Performance** | Latency | < 2 seconds |
| **Performance** | Throughput | 95th percentile stable |
| **Quality** | Accuracy | ≥ 90% correctness |
| **Quality** | Hallucination Rate | ≤ 3% |
| **Safety** | Guardrail Violations | 0 |
| **Safety** | Sensitive Output Detection | 100% blocked |
| **Cost Efficiency** | Token Utilization | On par with baseline |
| **User Experience** | Satisfaction Score | ≥ 4.5 / 5 |


## Metrics for Evaluating Prompt Effectiveness

### Prompt Quality Metrics
- **Accuracy** – output correctness and alignment with user intent
- **Consistency** – reliable quality across repeated runs
- **Relevance** – information focused on intended task
- **Format Compliance** – output follows required structure
- **Tone Alignment** – matches organizational or audience standards

## Foundations of End-to-End (E2E) Testing for AI Solutions

### AI + Dynamics 365 Multi App Context
- AI solutions interact with cross-app business processes such as:
  - Order to Cash (D365 Sales → D365 Finance → D365 Customer Service)
  - Case to Resolution (D365 Customer Service → D365 Field Service)
- Testing must validate the entire business process, not just individual modules.
- AI decisions depend on data across multiple apps.
- Workflow orchestration can break when one app changes.
- Data may be duplicated, synchronized, or transformed across systems.
- AI output quality relies on consistent, trusted, and well-timed input data.

### Identify Integration Points Across Apps
- **Data sync across entities** (Accounts, Orders, Cases, Journals)
- **AI predictions or insights** dependent on multi-app data
- **Automations** (Power Automate, custom plugins, event-based triggers)
- **Connectors to external systems** (ERP, CRM, data lakes)
- **Security roles, privileges, and data boundary enforcement**

### Best Practices for E2E Test Design
- Test realistic, high value business processes.
- Validate AI using multiple phrasing variations.
- Include both structured and unstructured data scenarios.
- Test with normal load and stress conditions.
- Incorporate exception paths and regulatory constraints.
- Document all test cases in repeatable templates.
- Design for consistent, repeatability.

## Understanding Copilot's Role in Test Case Design
- Copilot accelerates test case creation by translating requirements or code into structured, testable scenarios.
- Identifies edge cases that may be overlooked.
- Proposes test data variations.
- Helps maintain consistency as systems evolve.

### Important Consideration
Strategy design must include defining:
- Prompts
- Validation criteria
- Governance
- Quality thresholds

### Establish a Test Case Blueprint
Foundations of a Copilot Driven Test Case Strategy
- Use consistent patterns for best Copilot performance.
- Recommended blueprint includes:
  - Test ID
  - Purpose/Description
  - Preconditions
  - Inputs/Parameters
  - Steps
  - Expected Results
  - Edge Case Variations
  - Dependencies/External Systems
- Providing this template in prompts ensures predictable, high quality test cases.


![copilot-test-maturity-ladder](/images/copilot-test-maturity-ladder.png)

