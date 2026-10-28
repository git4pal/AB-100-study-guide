# Monitor, analyze, and tune AI agents

## Understanding Monitoring Requirements for AI Agents

### Operational Health

- Uptime
- Availability
- Error frequency
- Throttling
- Processing delays

### Performance Metrics

- Response times
- Success rates
- Tool reliability
- Workflow completion

### Quality and Output Accuracy

- Appropriateness
- Business rule alignment
- Deviation detection

### Usage Insights

- Volume trends
- User adoption
- Feature utilization
- Behavioral patterns

### Risk, Compliance, and Security

- Guardrail violations
- Sensitive data handling
- Suspicious activity
- Policy adherence

## Recommended Tools for Monitoring AI Agents

### Azure Monitor (Core Telemetry + Alerts)

- Provides application and agent telemetry.
- Dashboards for real-time metrics.
- Alert rules for anomalies.
- Integration with Log Analytics Workspaces.

#### Use Cases

- Monitor Power Platform or custom service workflows.
- Track errors.
- Track latency.
- Monitor throughput.
- Detect connector failures.
- Build KQL-based queries for deep diagnostics.

## Framework for Backlog Analysis: Categorize the Backlog by Domain

| Category | Example Backlog Items |
|----------|----------------------|
| **Accuracy** | Misinterpreted queries; missing context |
| **Knowledge** | Outdated docs; missing domain articles |
| **Performance** | High latency; connector throttling |
| **UX** | Confusing flows; unclear instructions |
| **Integration** | API failures; broken actions |
| **Governance** | Data access blocked; DLP alerts |

### Using Conversation Transcripts to Identify Patterns
- Identify where the agent misunderstood intent or users abandoned a flow.
- Detect incorrect reasoning steps and missing knowledge content.
- Recognize workflows requiring human intervention.
- Extract common failure paths and map transcript patterns to root causes.
- Recommend training, knowledge updates, guardrail adjustments, or action limits.

## AI Diagnostic Workflow

### Common Root Cause Categories
- **Model or Prompt Issues** – Misinterpretation or insufficient context.
- **Knowledge Gaps** – Missing organizational content or outdated files.
- **Integration Failures** – Connector constraints, API limits, data access rules.
- **Configuration Issues** – Incorrect environment variables, feature toggles, or role settings.
- **Governance Interference** – DLP blocking, sensitivity labels, restricted actions.

## Core Metrics for AI Agent Performance

### Operational Metrics
- **Latency** – Time taken to process agent requests.
- **Throughput** – Volume of completed runs over a period.
- **Error Rate** – Proportion of failed or incomplete tasks.
- **Resource Utilization** – Compute, memory, and token consumption.

### Quality and Reasoning Metrics
- **Response Accuracy** – Alignment with expected or validated outputs.
- **Knowledge Coverage** – Ability to surface correct domain content.
- **Action Effectiveness** – Completion of multi-step tasks as intended.

## User-Centered Metrics
- **Satisfaction Indicators** – User feedback trends and sentiment.
- **Abandonment Rate** – Drop off during agent workflows.
- **Task Completion Rate** – Whether users achieve intended outcomes.

## Tools and Processes Used to Monitor AI Agents

There are several Microsoft tools to achieve these monitoring objectives, including:
- Azure Monitor
- Microsoft 365 Admin Analytics
- Copilot & Agent Dashboards
- Power Platform Admin Center
- Third-party and Foundry-like solutions

## Diagnosing Issues and Applying Tuning

### Common Issue Categories

| Issue Type | Possible Causes | Tuning Strategy |
|------------|----------------|-----------------|
| **Incorrect responses** | Missing or outdated knowledge | Update grounding content |
| **Slow responses** | Heavy workflows, dependency latency | Streamline logic; adjust orchestration |
| **Action failures** | Connector/API constraints | Fix connector issues; update permissions |
| **High abandonment** | Confusing steps or unclear guidance | Improve UX flow and prompt clarity |
| **Guardrail violations** | Policy mismatch or missing rules | Adjust DLP, sensitivity labels, allowed actions |