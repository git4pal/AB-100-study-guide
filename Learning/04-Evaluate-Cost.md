# Evaluate costs and benefits of AI solutions

### Why ROI Criteria Matter for AI Solutions

- AI adoption often fails when organizations overestimate productivity gains.
- Underestimate operational and maintenance costs.
- Lack clear measurement frameworks.
- Cannot articulate business value to leadership.

### Core ROI Categories for AI-Powered Solutions

| ROI Category | Description | Example Benefits |
|-------------|-------------|------------------|
| **Productivity Gains** | Improve employee efficiency and automate repetitive work. | • Time saved per task<br>• Reduction in manual data entry<br>• Faster case resolution<br>• Automated summarization or classification |
| **Cost Savings** | Reduce operational expenses and optimize resource utilization. | • Operational efficiency<br>• Lower expenses<br>• Reduced support costs<br>• Resource optimization |
| **Revenue Impact** | Increase business growth and market opportunities. | • Sales growth<br>• New market share<br>• Higher margins<br>• Improved customer engagement |
| **Risk Reduction** | Lower compliance, security, and operational risks. | • Compliance support<br>• Security enhancement<br>• Reduced human error<br>• Futureproofing operations |
| **Strategic Value** | Create long-term competitive advantages and innovation opportunities. | • Long-term advantage<br>• Brand reputation<br>• Innovation enablement<br>• Organizational transformation |

### Map AI Value to Measurable Levers

- Time saved per transaction or step (cycle time compression).
- Quality lift (error reduction, first contact resolution, fewer escalations).
- Capacity/throughput (more work per FTE without adding headcount).
- Support each lever with measurable observations (e.g., automated step, accelerated decision, draft preparation).

## Quantify Savings with the Savings Calculator

### Inputs Needed

- Time saved per run (minutes)
- Successful runs in period
- Fully loaded labor rate (currency/hour)
- Optional tool-specific time/cost deltas

### Savings Model (Example)

| Parameter | Value |
|-----------|-------|
| Minutes saved per run | 6 |
| Successful runs / month | 20,000 |
| Labor rate ($/hour) | 60 |
| Monthly savings ($) | $120,000 |

### Sample Formula

```text
Monthly Savings =
(Minutes Saved per Run ÷ 60)
× Successful Runs
× Labor Rate
+ Error Cost
+ Backlog/Working Capital Effect
```

### Example Calculation

```text
(6 ÷ 60) × 20,000 × $60
= 0.1 × 20,000 × $60
= $120,000 per month
```

## Build the ROI, Payback, and Sensitivity View

- Net Benefit = Annual Benefit – Annual TCO.
- ROI % = (Net Benefit / Annual TCO) × 100.
- Payback (months) = Initial One-Time Cost / Net Monthly Benefit.

### Sensitivity Analysis

Sensitivity bands show upside and risk, anchored by research and telemetry.

- Create optimistic, expected, and conservative cases by varying:
  - Adoption rate
  - Minutes saved per run
  - Labor rates
  - Quality/rework effects

## Package the Executive One Slide Summary

Use a concise summary that decisionmakers can act on:

- **Problem & scope:** where the waste is today.
- **AI intervention:** what the agent automates or augments.
- **Measured impact:** minutes saved, resolved runs, quality lift (from Analytics).
- **Financials:** annual benefit, TCO, ROI %, payback.
- **Confidence & risks:** sensitivity band and key assumptions.
- **Decision:** "pilot for 8 weeks with success criteria X; scale to Y units on pass."

## Strategic Decision Context

- **Build:** Create AI components internally for deep customization and control.
- **Buy:** Acquire prebuilt AI capabilities for speed and standardized processes.
- **Extend:** Customize existing platforms like Microsoft Copilot for hybrid needs.

## Cost Structure Considerations

Evaluate costs across five domains: Infrastructure, Development, Data Preparation, Expertise, and Operations.

- **Infrastructure** includes compute, storage, networking, and scaling overhead.
- **Development** covers agent design, orchestration, API integration, and governance.
- **Data Preparation** involves cleansing, labeling, validation, and monitoring.
- **Expertise** includes AI engineers, architects, MLOps, and training.
- **Operations** cover monitoring, optimization, licensing, and security updates.

### Total Cost of Ownership (TCO) Table

| Cost Domain | Build | Buy | Extend |
|------------|-------|-----|--------|
| Infrastructure | High | Low | Medium |
| Development | High | Low | Medium |
| Data Preparation | High | Low | High |
| Expertise | High | Low | Medium |
| Operations | High | Medium | Medium |

## Decision Framework for Build vs. Buy vs. Extend

### Build vs Buy vs Extend Decision Matrix

| Approach | Best When | Key Benefits | Typical Scenarios |
|-----------|-----------|-------------|-------------------|
| **Build** | • Deep customization is required<br>• Control over data, IP, and model behavior is critical<br>• Business processes are unique and not supported by commercial tools<br>• Proprietary system integration is required | • Maximum flexibility<br>• Full control over architecture and AI behavior<br>• Supports unique business requirements<br>• Enables proprietary competitive advantages | • Custom AI agents<br>• Industry-specific AI solutions<br>• Proprietary business workflows<br>• Specialized predictive models |
| **Buy** | • Time-to-value is the highest priority<br>• Internal engineering capacity is limited<br>• Business processes are standardized<br>• Reliability, vendor support, and continuous updates are required | • Fastest deployment<br>• Lower implementation risk<br>• Vendor-managed updates and maintenance<br>• Reduced development effort | • Microsoft 365 Copilot<br>• Dynamics 365 Copilot<br>• SaaS AI applications<br>• Prebuilt AI assistants |
| **Extend** | • Both speed and customization are needed<br>• Existing AI platforms already provide most required capabilities<br>• Domain-specific knowledge must be added<br>• Agent or Copilot behavior requires tailoring | • Faster than building from scratch<br>• Leverages existing platform investments<br>• Reduces development complexity<br>• Supports business-specific customization | • Copilot Studio agents<br>• Microsoft 365 Copilot extensions<br>• Azure AI Foundry agents<br>• Plugins, skills, and grounding-based solutions |

### Quick Comparison

| Decision Factor | Build | Buy | Extend |
|----------------|-------|-----|--------|
| Time to Value | Slow | Fast | Medium |
| Customization | Very High | Low | Medium-High |
| Development Effort | High | Low | Medium |
| Control over IP & Data | High | Low | Medium-High |
| Operational Complexity | High | Low | Medium |
| Integration Flexibility | High | Limited | High |
| Cost to Implement | High | Low-Medium | Medium |
| Best For | Unique business capabilities | Standardized business needs | Hybrid scenarios |

### Exam Shortcut

| Requirement | Recommended Option |
|-------------|-------------------|
| Need complete control | **Build** |
| Need fastest deployment | **Buy** |
| Need speed + customization | **Extend** |
| Proprietary processes | **Build** |
| Standard business functions | **Buy** |
| Copilot customization | **Extend** |
| Unique competitive advantage | **Build** |
| Limited engineering resources | **Buy** |
| Existing Microsoft ecosystem investment | **Extend** |

### Step-by-Step Architectural Flow

1. Define business requirements and processes.
2. Determine strategic importance (differentiation vs. commodity).
3. Assess vendor solutions and implementation effort.
4. Evaluate feasibility of extending existing tools or creating custom solutions.
5. Estimate TCO across five cost domains.
6. Forecast ROI including time saved, cost avoided, error reduction, throughput increases.
7. Score each option on a weighted model.
8. Select approach with optimal value-to-cost ratio.

## Why Model Routing Matters

- **Optimize Cost:** use SLMs for simple tasks, LLMs only when needed, reduce token consumption.
- **Improve Performance:** route low latency tasks to faster models, use specialized models for domain-specific tasks.
- **Increase Reliability:** failover to backup models, automatically switch to newer model versions.
- **Support Hybrid AI Strategies:** combine foundation, fine tuned, and custom models; align with build, buy, or both AI strategies.


### Designing Routing Rules

- **Static Rules:**
  - Example: "If task = classification → use SLM"
  - Example: "If domain = finance → use fine-tuned model"

- **Weighted Routing:**
  - Distribute traffic across models for A/B testing and gradual rollout.

- **Fallback Routing:**
  - Automatically route to a backup model if the primary model fails.

- **Version-Based Routing:**
  - Route to the latest stable version or experimental versions.

