# AI Brainstormer - Output File Templates

## Session Summary Template

```markdown
# Brainstorming Session - {TIMESTAMP}

## Original Idea
{idea_content}

## Brainstorming Summary
**Rounds**: 3
**Agents**: Best Practices, Cost-Effective, Simplicity
**Total Ideas Generated**: {count}
**Top 3 Selected**: {list_with_titles}

### Selection Rationale
{explanation_of_why_these_3_were_chosen}

## Debate Summary
**Rounds**: 3
**Analysis Focus**: Pros, Cons, Risks, Mitigation
**Total Debate Points**: {count}

### Key Insights
{major_learnings_from_debate}

## Final Ratings

| Idea | Best Practices | Cost-Effective | Simplicity | Balance | Overall |
|------|----------------|----------------|------------|---------|---------|
| {1}  | {score}/10     | {score}/10     | {score}/10 | {score} | {score} |
| {2}  | {score}/10     | {score}/10     | {score}/10 | {score} | {score} |
| {3}  | {score}/10     | {score}/10     | {score}/10 | {score} | {score} |

## Top Recommendation

**{top_rated_idea_name}**

**Overall Rating**: {score}/10

**Strengths**:
- {strength_1}
- {strength_2}
- {strength_3}

**Considerations**:
- {consideration_1}
- {consideration_2}

**Next Steps**: See implementation guide for detailed plan.
```

---

## Architecture Diagram Template

```markdown
# {Idea Name} - Architecture Diagram
**Timestamp**: {TIMESTAMP}
**Rating**: {overall_score}/10

## Overview
{brief_description_of_architecture}

## Architecture Diagram

\`\`\`mermaid
{diagram_content}
\`\`\`

## Key Components
- **{component_1}**: {description}
- **{component_2}**: {description}
- **{component_3}**: {description}

## Data Flow
{explanation_of_data_flow_through_system}

## Scalability Considerations
{how_this_architecture_scales}
```

---

## Brainstorm Round Template

```markdown
# Brainstorm Round {round_number} - {TIMESTAMP}

## Round Context
**Round**: {1, 2, or 3}
**Previous Ideas Count**: {count_from_earlier_rounds}
**Focus**: {what_this_round_emphasizes}

---

## Best Practices Agent Proposals

### Proposal 1: {title}
**Rationale**: {why_this_fits_best_practices}

**Key Features**:
- {feature_1}
- {feature_2}
- {feature_3}

**Architecture Diagram**:
\`\`\`mermaid
{diagram}
\`\`\`

### Proposal 2: {title}
{same_structure_as_above}

---

## Cost-Effective Agent Proposals

### Proposal 1: {title}
**Rationale**: {why_this_is_cost_effective}

**Cost Analysis**:
- Initial: {estimate}
- Operational: {estimate}
- ROI Potential: {estimate}

**Architecture Diagram**:
\`\`\`mermaid
{diagram}
\`\`\`

### Proposal 2: {title}
{same_structure_as_above}

---

## Simplicity Agent Proposals

### Proposal 1: {title}
**Rationale**: {why_this_is_simple}

**Simplicity Metrics**:
- Components: {count}
- Dependencies: {count}
- Learning Curve: {low/medium/high}

**Architecture Diagram**:
\`\`\`mermaid
{diagram}
\`\`\`

### Proposal 2: {title}
{same_structure_as_above}

---

## Round Summary
**Total Ideas This Round**: {count}
**Cumulative Ideas**: {total_across_all_rounds}
```

---

## Debate Round Template

```markdown
# Debate Round {round_number} - {TIMESTAMP}

## Round Context
**Round**: {1, 2, or 3}
**Ideas Under Analysis**: {top_3_idea_names}
**Previous Debate Points**: {count_from_earlier_rounds}

---

## Idea 1: {title}

### Best Practices Agent Analysis

**Pros**:
- {pro_1}
- {pro_2}
- {pro_3}

**Cons**:
- {con_1}
- {con_2}

**Risk Assessment**: {description_of_risks}

**Mitigation Strategies**:
- {strategy_1}
- {strategy_2}

### Cost-Effective Agent Analysis

**Pros**:
- {pro_1}
- {pro_2}

**Cons**:
- {con_1}
- {con_2}

**Risk Assessment**: {description_of_risks}

**Mitigation Strategies**:
- {strategy_1}
- {strategy_2}

### Simplicity Agent Analysis

**Pros**:
- {pro_1}
- {pro_2}

**Cons**:
- {con_1}
- {con_2}

**Risk Assessment**: {description_of_risks}

**Mitigation Strategies**:
- {strategy_1}
- {strategy_2}

---

## Idea 2: {title}
{same_structure_as_idea_1}

---

## Idea 3: {title}
{same_structure_as_idea_1}

---

## Round Insights
**Emerging Patterns**: {cross_cutting_themes}
**Critical Issues**: {major_concerns_across_ideas}
**Mitigation Progress**: {how_rounds_refined_understanding}
```

---

## Ideas Comparison Template

```markdown
# Ideas Comparison - {TIMESTAMP}

## Rating Summary

| Criteria | Idea 1: {name} | Idea 2: {name} | Idea 3: {name} |
|----------|----------------|----------------|----------------|
| Best Practices | {score}/10 | {score}/10 | {score}/10 |
| Cost-Effective | {score}/10 | {score}/10 | {score}/10 |
| Simplicity | {score}/10 | {score}/10 | {score}/10 |
| Balance Score | {score} | {score} | {score} |
| **Overall** | **{score}** | **{score}** | **{score}** |

---

## Side-by-Side Analysis

### Strengths

| Idea 1 | Idea 2 | Idea 3 |
|--------|--------|--------|
| {strength_1} | {strength_1} | {strength_1} |
| {strength_2} | {strength_2} | {strength_2} |
| {strength_3} | {strength_3} | {strength_3} |

### Weaknesses

| Idea 1 | Idea 2 | Idea 3 |
|--------|--------|--------|
| {weakness_1} | {weakness_1} | {weakness_1} |
| {weakness_2} | {weakness_2} | {weakness_2} |

### Use Case Fit

| Use Case | Idea 1 | Idea 2 | Idea 3 |
|----------|--------|--------|--------|
| {use_case_1} | {fit_score} | {fit_score} | {fit_score} |
| {use_case_2} | {fit_score} | {fit_score} | {fit_score} |
| {use_case_3} | {fit_score} | {fit_score} | {fit_score} |

---

## Recommendation

**Winner**: {top_idea_name}

**Why This Idea Won**:
{detailed_explanation_of_selection}

**When to Consider Alternatives**:
- **Idea 2** if {scenario}
- **Idea 3** if {scenario}
```

---

## Implementation Guide Template

```markdown
# Implementation Guide - {top_idea_name}
**Timestamp**: {TIMESTAMP}
**Overall Rating**: {score}/10

## Executive Summary
{2-3_paragraph_overview_of_implementation_approach}

---

## Prerequisites

### Technical Requirements
- {requirement_1}
- {requirement_2}
- {requirement_3}

### Skills Required
- {skill_1}
- {skill_2}
- {skill_3}

### Resources Needed
- {resource_1}: {details}
- {resource_2}: {details}
- {resource_3}: {details}

---

## Implementation Phases

### Phase 1: {phase_name} ({duration})

**Goals**:
- {goal_1}
- {goal_2}

**Tasks**:
1. {task_1}
2. {task_2}
3. {task_3}

**Deliverables**:
- {deliverable_1}
- {deliverable_2}

**Success Criteria**:
- {criterion_1}
- {criterion_2}

### Phase 2: {phase_name} ({duration})
{same_structure_as_phase_1}

### Phase 3: {phase_name} ({duration})
{same_structure_as_phase_1}

---

## Risk Management

### High Priority Risks

| Risk | Impact | Probability | Mitigation Strategy |
|------|--------|-------------|---------------------|
| {risk_1} | {high/medium/low} | {high/medium/low} | {strategy} |
| {risk_2} | {high/medium/low} | {high/medium/low} | {strategy} |

### Medium Priority Risks

| Risk | Impact | Probability | Mitigation Strategy |
|------|--------|-------------|---------------------|
| {risk_1} | {high/medium/low} | {high/medium/low} | {strategy} |

---

## Validation Approach

### Testing Strategy
{description_of_testing_approach}

### Validation Checkpoints
1. **{checkpoint_1}**: {what_to_validate}
2. **{checkpoint_2}**: {what_to_validate}
3. **{checkpoint_3}**: {what_to_validate}

### Success Metrics
- {metric_1}: {target}
- {metric_2}: {target}
- {metric_3}: {target}

---

## Timeline

| Milestone | Target Date | Dependencies | Owner |
|-----------|-------------|--------------|-------|
| {milestone_1} | {date} | {dependencies} | {owner} |
| {milestone_2} | {date} | {dependencies} | {owner} |
| {milestone_3} | {date} | {dependencies} | {owner} |

**Total Estimated Duration**: {duration}

---

## Next Steps

1. **Immediate** ({timeframe}): {action}
2. **Short-term** ({timeframe}): {action}
3. **Long-term** ({timeframe}): {action}
```

---

## Final Recommendation Template

```markdown
# Final Recommendation - {TIMESTAMP}

## Top Rated Idea: {title}

**Overall Score**: {score}/10

---

## Rating Breakdown

| Criteria | Score | Justification |
|----------|-------|---------------|
| Best Practices | {score}/10 | {explanation} |
| Cost-Effective | {score}/10 | {explanation} |
| Simplicity | {score}/10 | {explanation} |
| Balance | {score} | {explanation} |

---

## Why This Idea Won

### Key Strengths
1. **{strength_1}**: {detailed_explanation}
2. **{strength_2}**: {detailed_explanation}
3. **{strength_3}**: {detailed_explanation}

### Competitive Advantages
- {advantage_1}
- {advantage_2}
- {advantage_3}

### Risk Mitigation
All identified risks have clear mitigation strategies:
- {risk_1}: {mitigation}
- {risk_2}: {mitigation}

---

## Runner-Up Ideas

### Idea 2: {title} ({score}/10)
**When to Choose This**: {scenario_description}

**Key Differentiator**: {what_makes_this_unique}

### Idea 3: {title} ({score}/10)
**When to Choose This**: {scenario_description}

**Key Differentiator**: {what_makes_this_unique}

---

## Implementation Readiness

**Status**: {ready/needs_planning/needs_prototyping}

**Critical Path**: {description_of_first_steps}

**Quick Wins**: {early_value_opportunities}

---

## References

- Session Summary: `./output/session-<TIMESTAMP>.sab.md`
- Architecture Diagrams: `./output/{idea-name}.sab.mermaid`
- Ideas Comparison: `./output/ideas-comparison-<TIMESTAMP>.sab.md`
- Implementation Guide: `./output/implementation-guide-<TIMESTAMP>.sab.md`
```
