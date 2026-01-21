# AI Brainstormer - Agent Routing Patterns

## Overview

This document defines routing patterns for coordinating 3 specialized agents through brainstorming and debate phases using a manager-worker pattern.

---

## Specialized Agents

### 1. Best Practices Agent
**Path**: `@subagents/ai-brainstormer/best-practices-agent`

**Perspective**: Industry standards, proven patterns, scalability, maintainability

**Evaluation Criteria**:
- Adherence to architectural best practices
- Scalability and performance considerations
- Long-term maintainability
- Security and reliability
- Code quality and documentation

**Expected Outputs**:
- Proposals following established patterns
- Diagrams showing scalable architecture
- Rationale grounded in industry standards

---

### 2. Cost-Effective Agent
**Path**: `@subagents/ai-brainstormer/cost-effective-agent`

**Perspective**: Budget optimization, resource efficiency, ROI maximization

**Evaluation Criteria**:
- Initial implementation cost
- Operational/maintenance costs
- Infrastructure requirements
- License and tooling costs
- Time-to-market efficiency
- ROI potential

**Expected Outputs**:
- Proposals optimized for budget constraints
- Cost analysis and projections
- Rationale focused on economic viability

---

### 3. Simplicity Agent
**Path**: `@subagents/ai-brainstormer/simplicity-agent`

**Perspective**: Minimal complexity, ease of understanding, low maintenance burden

**Evaluation Criteria**:
- Conceptual simplicity
- Implementation complexity
- Learning curve for team
- Maintenance burden
- Dependency management
- Debugging ease

**Expected Outputs**:
- Proposals emphasizing simplicity
- Clear, minimal diagrams
- Rationale highlighting ease of use

---

## Brainstorming Phase Routing

### Agent Invocation Pattern

**Execution**: Parallel (all 3 agents concurrently)

**Context Level**: Level 2 (Filtered Context)

**Why Level 2**: Agents need full idea context + iterative history from previous rounds to build on earlier proposals and avoid duplication

### Data Passed to Each Agent

```javascript
{
  idea_content: "Full text of user's original idea",
  problem_summary: "Distilled 2-3 sentence problem statement",
  round_number: 1 | 2 | 3,
  previous_ideas: [
    {
      round: 1,
      agent: "best-practices",
      proposals: [...],
      diagrams: [...]
    },
    // ... other agents and rounds
  ],
  constraints: {
    minimum_proposals: 2,
    diagram_format: "Mermaid",
    include_timestamp: true
  }
}
```

### Expected Returns from Each Agent

```javascript
{
  proposals: [
    {
      title: "Proposal name",
      description: "Detailed explanation",
      key_features: ["feature1", "feature2", ...],
      implementation_notes: "How to build this",
      trade_offs: "Pros and cons"
    },
    // Minimum 2 proposals per agent
  ],
  diagrams: [
    {
      type: "mermaid",
      content: "```mermaid\n...\n```",
      timestamp: "2026-01-21T10:30:00Z",
      description: "What this diagram shows"
    },
    // One diagram per proposal
  ],
  rationale: "Why these proposals fit [agent's perspective]"
}
```

### Round Coordination

**Round 1**: Fresh ideas based on original problem
- No previous_ideas context
- Focus on diverse approaches
- Encourage bold, innovative thinking

**Round 2**: Build on Round 1 ideas
- Include previous_ideas from Round 1
- Refine promising concepts
- Explore variations and alternatives

**Round 3**: Final refinement
- Include previous_ideas from Rounds 1 & 2
- Polish best concepts
- Address gaps identified in earlier rounds

**Synchronization**: Wait for ALL 3 agents to complete before proceeding to next round

---

## Debate Phase Routing

### Agent Invocation Pattern

**Execution**: Parallel (all 3 agents analyze each idea concurrently)

**Context Level**: Level 2 (Filtered Context)

**Why Level 2**: Agents need full idea details + debate history to provide informed, non-repetitive analysis

### Data Passed to Each Agent

```javascript
{
  idea_details: {
    title: "Idea name",
    full_proposal: "Complete proposal text",
    diagrams: [...],
    original_rationale: "Why this was proposed",
    selection_reason: "Why this made top 3"
  },
  round_number: 1 | 2 | 3,
  previous_debate_points: [
    {
      round: 1,
      agent: "best-practices",
      pros: [...],
      cons: [...],
      risks: [...]
    },
    // ... other agents and rounds
  ],
  task: "Analyze pros AND cons from your perspective"
}
```

### Expected Returns from Each Agent

```javascript
{
  pros: [
    {
      point: "Advantage description",
      impact: "high" | "medium" | "low",
      evidence: "Why this is a pro"
    },
    // Multiple pros expected
  ],
  cons: [
    {
      point: "Disadvantage description",
      severity: "high" | "medium" | "low",
      evidence: "Why this is a con"
    },
    // Multiple cons expected
  ],
  risk_assessment: {
    technical_risks: ["risk1", "risk2", ...],
    operational_risks: ["risk1", "risk2", ...],
    strategic_risks: ["risk1", "risk2", ...],
    overall_risk_level: "high" | "medium" | "low"
  },
  mitigation_strategies: [
    {
      risk: "Risk being addressed",
      strategy: "How to mitigate",
      feasibility: "high" | "medium" | "low"
    },
    // One strategy per major risk
  ]
}
```

### Debate Round Coordination

**Round 1**: Initial analysis
- Fresh perspective on each idea
- Identify obvious pros/cons
- Surface major risks

**Round 2**: Deeper analysis
- Include Round 1 debate points
- Address nuances and edge cases
- Explore mitigation effectiveness

**Round 3**: Final assessment
- Include Rounds 1 & 2 debate points
- Synthesize comprehensive view
- Finalize risk/mitigation understanding

**Iteration Pattern**:
```
FOR round IN [1, 2, 3]:
  FOR idea IN top_3_ideas:
    PARALLEL:
      - best-practices-agent(idea, round, previous_debates)
      - cost-effective-agent(idea, round, previous_debates)
      - simplicity-agent(idea, round, previous_debates)
    END PARALLEL
    
    COLLECT all debate points for current idea
  END FOR
  
  SAVE round results to file
END FOR
```

---

## Rating Calculation System

### Individual Criteria Scores (1-10 scale)

**Best Practices Score**:
- **8-10**: Excellent adherence to standards, highly scalable
- **5-7**: Good practices with minor compromises
- **1-4**: Significant technical debt or anti-patterns

**Cost-Effectiveness Score**:
- **8-10**: Highly cost-efficient, excellent ROI
- **5-7**: Reasonable costs with acceptable ROI
- **1-4**: Expensive or poor ROI

**Simplicity/Maintenance Score**:
- **8-10**: Very simple, minimal maintenance
- **5-7**: Moderate complexity, manageable maintenance
- **1-4**: High complexity, significant maintenance burden

### Composite Scores

**Balance Score**:
```
Balance = 10 - (StdDev(BestPractices, CostEffective, Simplicity) * 2)

High Balance (8-10): Scores are similar across criteria
Medium Balance (5-7): Some variation in scores
Low Balance (1-4): Highly specialized in one area
```

**Overall Rating** (Weighted Average):
```
Overall = (BestPractices × 0.35) + 
          (CostEffective × 0.30) + 
          (Simplicity × 0.25) + 
          (Balance × 0.10)

Weights can be adjusted based on project priorities
```

### Ranking Logic

1. Calculate all scores for all ideas
2. Sort by Overall Rating (descending)
3. In case of tie: Prefer higher Balance Score
4. Document rationale for final ranking

---

## Error Handling

### Agent Timeout
**Issue**: Agent takes too long to respond  
**Action**: Wait up to 2 minutes, then skip that agent's contribution for current round  
**Recovery**: Note missing data in round results, continue with available agents

### Insufficient Proposals
**Issue**: Agent returns fewer than 2 proposals  
**Action**: Accept what's available, flag warning in round results  
**Recovery**: Ensure minimum 6 total ideas across all agents before proceeding

### Missing Diagrams
**Issue**: Agent doesn't include diagrams  
**Action**: Flag as critical violation of @critical_rules.diagram_requirement  
**Recovery**: Request re-generation with explicit diagram requirement

### Invalid Debate Points
**Issue**: Agent returns only pros or only cons  
**Action**: Flag warning, use available analysis  
**Recovery**: Note imbalance in debate documentation

---

## Context Allocation Strategy

### Level 2 Rationale

**Why Not Level 1 (Complete Isolation)**:
- Agents need awareness of previous rounds to avoid duplication
- Iterative refinement requires seeing earlier proposals
- Debate analysis requires full idea context

**Why Not Level 3 (Windowed/Stateful)**:
- Brainstorming is stateless per round
- No ongoing conversation state needed
- Each round is self-contained with explicit context

**Optimal Approach**: Level 2 with filtered, explicit context
- Pass only relevant previous rounds
- Include full idea details for current analysis
- Minimize noise from unrelated session data

---

## Parallel Execution Benefits

### Performance Gains
- 3× faster per round (parallel vs sequential)
- Total session time: ~10-15 minutes (vs ~30-45 sequential)

### Consistency
- All agents work from same idea state
- No order-dependent biases
- Fair comparison across perspectives

### Implementation
```
PARALLEL_START
  agent1 = call(best-practices-agent, context)
  agent2 = call(cost-effective-agent, context)
  agent3 = call(simplicity-agent, context)
PARALLEL_WAIT_ALL

results = [agent1.response, agent2.response, agent3.response]
```

---

## Routing Decision Logic

### When to Use Standard 3-Agent Setup
- **General software architecture** problems
- **Balanced requirements** (quality, cost, simplicity all matter)
- **Typical team constraints** (budget, skill, time)

### When to Add Specialized Agents
- **Security-critical** systems → Add security-focused agent
- **Compliance-heavy** domains → Add compliance agent
- **Highly specialized** tech → Add domain-expert agent

### Dynamic Agent Selection
```
IF idea.mentions("security") OR idea.mentions("compliance"):
  agents.add(security-compliance-agent)

IF idea.mentions("real-time") OR idea.mentions("performance"):
  agents.add(performance-optimization-agent)

IF idea.mentions("data science") OR idea.mentions("ML"):
  agents.add(data-architecture-agent)
```

**Default**: Always include core 3 agents (best-practices, cost-effective, simplicity)

---

## Solo Brainstorming Optimizations

### Conversational Enhancements

**Thinking Partner Mode**: Frame agents as collaborative thought partners, not just evaluators

**Iterative Dialogue**: 
- Round 1: "Let's explore diverse approaches..."
- Round 2: "Building on what we discovered..."
- Round 3: "Refining our best thinking..."

**Encouragement**:
- "Great idea! Let's push this further..."
- "Interesting trade-off. Let's explore alternatives..."
- "This is coming together. Final refinements..."

### Autonomous Execution

**Self-Driven**: Orchestrator makes decisions without requiring constant user input

**Approval Gates**: Only at critical decision points (before debate phase)

**Progress Updates**: Keep user informed but don't interrupt flow
```
"Brainstorming Round 1/3... ⏳"
"Collected 8 ideas from 3 agents ✓"
"Selecting top 3... ⏳"
```

### Idea Capture

**Low-Friction Input**: Accept rough, unstructured ideas
```markdown
# Quick Idea Template
Just describe your problem or idea in natural language.
Don't worry about structure - we'll figure it out together.

Example:
"I need a way to sync data between mobile app and web app 
without conflicts when users work offline."
```

**Problem Extraction**: Orchestrator extracts structured problem from free-form text
