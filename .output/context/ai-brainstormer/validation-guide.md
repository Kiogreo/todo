# AI Brainstormer - Validation Guide

## Pre-Flight Validation

**When**: Before starting brainstorming session  
**Purpose**: Ensure environment and inputs are ready

### Directory Structure

```bash
# Required directories
./input/          # Must exist with at least one *.sab-idea.md file
./output/         # Must exist or be creatable

# Validation checks
✓ ./input/ directory exists
✓ ./input/ contains at least one *.sab-idea.md file
✓ ./output/ directory exists or can be created
✓ Write permissions to ./output/ directory
```

### Input File Validation

```bash
# File naming pattern
*.sab-idea.md     # Must follow this pattern

# Content requirements
✓ File is readable and valid Markdown
✓ Contains problem statement or idea description
✓ Has sufficient detail for brainstorming (>50 words recommended)
```

### Error Handling

**No input files found**:
```
⚠️ No brainstorming idea file found!

Please create: ./input/[your-idea-name].sab-idea.md

Would you like me to create a template? (yes/no)
```

**Multiple input files found**:
```
📁 Multiple idea files found:

1. ./input/mobile-sync.sab-idea.md (modified: 2026-01-20)
2. ./input/api-gateway.sab-idea.md (modified: 2026-01-18)
3. ./input/notification-system.sab-idea.md (modified: 2026-01-15)

Which idea would you like to brainstorm? (1-3)
```

**Permission errors**:
```
❌ Cannot write to ./output/ directory

Please check permissions or create directory manually:
mkdir -p ./output
chmod 755 ./output
```

---

## Mid-Flight Validation

**When**: During brainstorming and debate phases  
**Purpose**: Ensure quality and completeness of agent outputs

### Brainstorming Round Validation

**Per-Round Checks** (repeat for rounds 1, 2, 3):

```yaml
Round Validation:
  minimum_ideas_per_agent: 2
  minimum_total_ideas: 6  # 3 agents × 2 ideas
  required_fields_per_idea:
    - title
    - description
    - rationale
  required_diagram_per_idea: true
  diagram_requirements:
    - format: "mermaid"
    - has_timestamp: true
    - is_valid_syntax: true
```

**Validation Actions**:

✓ **Each agent returned ≥2 proposals**
```
✓ best-practices-agent: 3 proposals
✓ cost-effective-agent: 2 proposals
✓ simplicity-agent: 2 proposals
Total: 7 ideas ✓
```

❌ **Agent returned insufficient proposals**
```
⚠️ Warning: simplicity-agent returned only 1 proposal
Expected: 2 minimum
Action: Accepting available proposal, flagging for review
```

✓ **All proposals include diagrams with timestamps**
```
✓ All 7 proposals have Mermaid diagrams
✓ All diagrams include timestamps
✓ Diagram syntax validated
```

❌ **Missing diagrams**
```
❌ CRITICAL: cost-effective-agent proposal "Serverless Architecture" missing diagram
Rule Violation: @critical_rules.diagram_requirement
Action: Requesting re-generation with explicit diagram requirement
```

### Top 3 Selection Validation

**Selection Criteria Checks**:

```yaml
Top 3 Validation:
  coverage_across_criteria: true  # Must include best-practices, cost, simplicity perspectives
  feasibility_assessed: true      # Each idea rated for technical feasibility
  innovation_scored: true          # Novel approaches identified
  clarity_verified: true           # Ideas are well-articulated with diagrams
```

**Validation Output**:
```
Top 3 Selection ✓

Idea 1: "Microservices with Event Sourcing"
  ✓ Coverage: Best Practices (primary), Cost (secondary)
  ✓ Feasibility: High
  ✓ Innovation: Moderate (proven pattern, novel application)
  ✓ Clarity: Excellent (detailed diagram, clear rationale)

Idea 2: "Monolith with Feature Flags"
  ✓ Coverage: Simplicity (primary), Cost (secondary)
  ✓ Feasibility: Very High
  ✓ Innovation: Low (conservative, safe approach)
  ✓ Clarity: Excellent (simple diagram, clear trade-offs)

Idea 3: "Hybrid: Modular Monolith"
  ✓ Coverage: Balanced (all three criteria)
  ✓ Feasibility: High
  ✓ Innovation: High (creative compromise)
  ✓ Clarity: Good (diagram shows modularity)

Selection Rationale: Diverse approaches covering different trade-off priorities
```

### Debate Round Validation

**Per-Round Checks** (repeat for rounds 1, 2, 3):

```yaml
Debate Validation:
  ideas_analyzed: 3  # All top 3 ideas
  agents_per_idea: 3  # All 3 agents analyze each idea
  required_fields_per_analysis:
    - pros: [minimum 2 points]
    - cons: [minimum 2 points]
    - risk_assessment: [must exist]
    - mitigation_strategies: [must exist]
```

**Validation Actions**:

✓ **Balanced pros/cons analysis**
```
Idea 1: "Microservices with Event Sourcing"
  ✓ best-practices-agent: 4 pros, 3 cons ✓
  ✓ cost-effective-agent: 3 pros, 4 cons ✓
  ✓ simplicity-agent: 2 pros, 5 cons ✓
  
Analysis Balance: Good (all agents provided both perspectives)
```

❌ **Imbalanced analysis**
```
⚠️ Warning: best-practices-agent provided 5 pros, 0 cons
Expected: Both pros AND cons required
Action: Flagging analysis as biased, continuing with available data
```

✓ **Risk assessments complete**
```
✓ All 3 ideas have comprehensive risk assessments
✓ All risks have mitigation strategies
✓ Risk severity levels documented
```

### User Approval Validation

**Approval Gate Check**:

```yaml
Approval Validation:
  presentation_shown: true
  user_response_received: true
  valid_responses: ["yes", "proceed", "modify", "no", "stop"]
```

**Validation Output**:
```
User Approval Gate ✓

Presentation: Shown ✓
User Response: "yes" ✓
Action: Proceeding to debate phase

Rule Compliance: @critical_rules.user_approval_gate ✓
```

---

## Post-Flight Validation

**When**: After all outputs generated  
**Purpose**: Ensure deliverables are complete and properly formatted

### File Existence Validation

**Required Files**:

```yaml
Session Files:
  - ./output/session-<TIMESTAMP>.sab.md

Brainstorming Files:
  - ./output/brainstorm-round-1-<TIMESTAMP>.sab.md
  - ./output/brainstorm-round-2-<TIMESTAMP>.sab.md
  - ./output/brainstorm-round-3-<TIMESTAMP>.sab.md
  - ./output/brainstorm-results-<TIMESTAMP>.sab.md

Debate Files:
  - ./output/debate-round-1-<TIMESTAMP>.sab.md
  - ./output/debate-round-2-<TIMESTAMP>.sab.md
  - ./output/debate-round-3-<TIMESTAMP>.sab.md

Architecture Diagrams (3 per top idea):
  - ./output/{idea-1-name}.sab.mermaid
  - ./output/{idea-1-name}.sab.md
  - ./output/{idea-2-name}.sab.mermaid
  - ./output/{idea-2-name}.sab.md
  - ./output/{idea-3-name}.sab.mermaid
  - ./output/{idea-3-name}.sab.md

Analysis Files:
  - ./output/ideas-comparison-<TIMESTAMP>.sab.md
  - ./output/final-recommendation-<TIMESTAMP>.sab.md
  - ./output/implementation-guide-<TIMESTAMP>.sab.md

Total Expected: 19-20 files
```

**Validation Checklist**:
```
✓ All session files created
✓ All brainstorming round files created (4 files)
✓ All debate round files created (3 files)
✓ All architecture diagrams created (6 files: 3 .mermaid + 3 .md)
✓ All analysis files created (3 files)
✓ Total files: 19 ✓
```

### File Naming Validation

**Naming Convention**: `[descriptive-name].<TIMESTAMP>.sab.[extension]`

**Rules**:
1. Must contain `.sab.` prefix
2. Must have descriptive name (not generic like "file1")
3. Timestamp format: ISO 8601 or UNIX timestamp
4. File extension matches content (.md or .mermaid)

**Validation Output**:
```
File Naming Validation ✓

✓ All files use .sab. prefix
✓ All files have descriptive names
✓ All files have valid timestamps
✓ File extensions match content types

Rule Compliance: @critical_rules.output_naming ✓
```

❌ **Naming violations**:
```
❌ File: ./output/results.md
Issue: Missing .sab. prefix
Expected: ./output/results-<TIMESTAMP>.sab.md

❌ File: ./output/diagram.sab.txt
Issue: Wrong extension (should be .mermaid)
Expected: ./output/[idea-name].sab.mermaid
```

### Content Validation

**Diagram Validation**:

```yaml
Mermaid Diagram Checks:
  syntax_valid: true
  has_timestamp: true
  timestamp_format: "Timestamp: YYYY-MM-DDTHH:MM:SSZ"
  diagram_type_valid: ["graph", "flowchart", "sequenceDiagram", "classDiagram"]
```

**Validation Actions**:
```
✓ ./output/microservices-event-sourcing.sab.mermaid
  ✓ Valid Mermaid syntax
  ✓ Contains timestamp: "2026-01-21T10:45:30Z"
  ✓ Diagram type: flowchart

❌ ./output/monolith-with-flags.sab.mermaid
  ✓ Valid Mermaid syntax
  ❌ Missing timestamp
  Action: Adding timestamp to diagram
```

**Rating Validation**:

```yaml
Rating Checks:
  all_ideas_have_scores: true
  score_range: [1, 10]
  required_criteria:
    - best_practices_score
    - cost_effective_score
    - simplicity_score
    - balance_score
    - overall_rating
```

**Validation Output**:
```
Rating Validation ✓

Idea 1: Microservices with Event Sourcing
  ✓ Best Practices: 9/10
  ✓ Cost-Effective: 6/10
  ✓ Simplicity: 5/10
  ✓ Balance: 6/10
  ✓ Overall: 7.2/10

Idea 2: Monolith with Feature Flags
  ✓ Best Practices: 7/10
  ✓ Cost-Effective: 9/10
  ✓ Simplicity: 9/10
  ✓ Balance: 9/10
  ✓ Overall: 8.3/10

Idea 3: Hybrid: Modular Monolith
  ✓ Best Practices: 8/10
  ✓ Cost-Effective: 8/10
  ✓ Simplicity: 7/10
  ✓ Balance: 9/10
  ✓ Overall: 7.9/10

All ratings within valid range [1-10] ✓
All required criteria scored ✓
```

### Implementation Guide Validation

**Required Sections**:

```yaml
Implementation Guide Structure:
  - executive_summary
  - prerequisites
  - implementation_phases
  - risk_management
  - validation_approach
  - timeline
  - next_steps
```

**Validation Checklist**:
```
✓ Executive Summary: Present and concise (2-3 paragraphs)
✓ Prerequisites: Technical requirements, skills, resources listed
✓ Implementation Phases: At least 3 phases defined
✓ Risk Management: Risks identified with mitigation strategies
✓ Validation Approach: Testing strategy and success metrics defined
✓ Timeline: Milestones with target dates
✓ Next Steps: Immediate, short-term, long-term actions listed

Implementation Guide Completeness: ✓
```

---

## Comprehensive Session Validation Report

**Generated at**: End of session  
**Format**: Markdown summary

```markdown
# Session Validation Report - <TIMESTAMP>

## ✅ Pre-Flight Validation
- [x] Input directory exists
- [x] Input file found: ./input/mobile-sync.sab-idea.md
- [x] Output directory ready

## ✅ Brainstorming Phase Validation
- [x] Round 1: 7 ideas collected, all with diagrams
- [x] Round 2: 8 ideas collected, all with diagrams
- [x] Round 3: 6 ideas collected, all with diagrams
- [x] Top 3 selected with coverage across all criteria

## ✅ User Approval Validation
- [x] Presentation shown
- [x] User approved: "yes"

## ✅ Debate Phase Validation
- [x] Round 1: All 3 ideas analyzed by all 3 agents
- [x] Round 2: All 3 ideas analyzed by all 3 agents
- [x] Round 3: All 3 ideas analyzed by all 3 agents
- [x] Ratings calculated for all ideas

## ✅ Output Generation Validation
- [x] 19 files created
- [x] All files use .sab. prefix
- [x] All diagrams have timestamps
- [x] All ratings within valid range
- [x] Implementation guide complete

## 🎯 Overall Status: PASS

All critical rules enforced ✓
All validation gates passed ✓
Session completed successfully ✓
```

---

## Error Recovery Strategies

### Missing Agent Response

**Issue**: Agent doesn't respond within timeout

**Detection**:
```
⏱️ Timeout: best-practices-agent (2 minutes exceeded)
```

**Recovery**:
1. Log timeout event
2. Continue with available agents (cost-effective, simplicity)
3. Note missing perspective in round results
4. Ensure minimum 6 ideas still collected from remaining agents
5. Flag affected ideas in final report

### Corrupted Output File

**Issue**: File write fails or produces corrupted data

**Detection**:
```
❌ File write error: ./output/brainstorm-round-1-<TIMESTAMP>.sab.md
Error: Disk full / Permission denied
```

**Recovery**:
1. Retry write operation (up to 3 attempts)
2. Try alternate location: ./output/backup/
3. If all fails: Store in memory, warn user
4. Provide data dump for manual recovery

### Invalid Diagram Syntax

**Issue**: Mermaid diagram has syntax errors

**Detection**:
```
⚠️ Invalid Mermaid syntax in diagram for "Microservices Idea"
Error: Unexpected token on line 5
```

**Recovery**:
1. Attempt automatic syntax fix (common issues)
2. If auto-fix fails: Flag diagram as invalid
3. Include text description as fallback
4. Continue session, note issue in validation report
5. Recommend manual diagram review

### Insufficient Ideas Generated

**Issue**: Fewer than 6 ideas collected in a round

**Detection**:
```
⚠️ Round 1: Only 4 ideas collected
Expected: Minimum 6 (3 agents × 2 ideas)
```

**Recovery Options**:

**Option A: Re-run round**
```
Re-running Round 1 with clearer constraints...
- Emphasizing minimum 2 proposals per agent
- Providing additional context/examples
```

**Option B: Continue with warning**
```
Continuing with 4 ideas (warning flagged)
Will ensure total 6+ ideas across all 3 rounds
```

**Option C: User consultation**
```
⚠️ Low idea count detected

Options:
1. Re-run this round with adjusted constraints
2. Continue and compensate in next rounds
3. Modify problem statement for clarity

Your choice: (1/2/3)
```

---

## Validation Metrics

### Success Criteria

**Full Session Success**:
- All pre-flight checks pass
- All 3 brainstorming rounds complete with 6+ ideas each
- User approval obtained
- All 3 debate rounds complete with balanced analysis
- All output files created with proper naming
- All diagrams include timestamps
- All ratings calculated and documented

**Partial Success** (acceptable):
- Minor warnings (e.g., 1 agent returned 1 instead of 2 ideas)
- Non-critical file naming issues
- Missing non-essential sections

**Failure** (unacceptable):
- Critical rule violations (@critical_rules)
- No user approval obtained before debate
- Missing diagrams completely
- Fewer than 3 ideas in top selection
- Output files missing .sab. prefix
- No ratings calculated

### Quality Metrics

```yaml
Idea Quality:
  minimum_ideas_per_round: 6
  minimum_total_ideas: 18
  diagram_coverage: 100%
  timestamp_coverage: 100%

Debate Quality:
  ideas_analyzed: 3
  analysis_balance: "Both pros AND cons for each idea"
  risk_mitigation: "All risks have strategies"

Output Quality:
  file_naming_compliance: 100%
  required_files_created: 100%
  template_adherence: >=90%
```

---

## Validation Automation

### Automated Checks (Run After Each Stage)

```bash
# Pre-flight validation script
validate_pre_flight() {
  check_directory "./input"
  check_files "./input/*.sab-idea.md"
  check_writable "./output"
}

# Round validation script
validate_round(round_number, results) {
  check_idea_count(results, minimum: 6)
  check_diagrams(results, required: true)
  check_timestamps(results.diagrams)
}

# Output validation script
validate_outputs() {
  check_file_count(expected: 19)
  check_naming_convention("*.sab.*")
  check_content_validity()
}
```

### Manual Review Checklist

**Human verification recommended for**:
- Idea quality and originality
- Diagram clarity and accuracy
- Rating reasonableness
- Implementation guide practicality

**Review Template**:
```
[ ] Ideas are distinct and non-duplicative
[ ] Diagrams accurately represent proposals
[ ] Ratings reflect actual pros/cons
[ ] Implementation guide is actionable
[ ] Recommendations make sense for problem
```
