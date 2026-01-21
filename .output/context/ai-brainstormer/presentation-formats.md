# AI Brainstormer - Presentation Formats

## Stage 3: Brainstorming Results Presentation

```markdown
## 🧠 Brainstorming Complete!

**Rounds Completed**: 3
**Total Ideas Generated**: {count}
**Agents Consulted**: Best Practices, Cost-Effective, Simplicity

---

### 📋 Top 3 Selected Ideas

#### Idea 1: {title}

**Criteria Balance**:
- Best Practices: {score}/10
- Cost-Effective: {score}/10
- Simplicity: {score}/10

**Key Innovation**: {1-2_sentence_summary}

**Why Selected**: {rationale_for_selection}

**Architecture Diagram**:
\`\`\`mermaid
{mermaid_diagram}
\`\`\`

---

#### Idea 2: {title}

**Criteria Balance**:
- Best Practices: {score}/10
- Cost-Effective: {score}/10
- Simplicity: {score}/10

**Key Innovation**: {1-2_sentence_summary}

**Why Selected**: {rationale_for_selection}

**Architecture Diagram**:
\`\`\`mermaid
{mermaid_diagram}
\`\`\`

---

#### Idea 3: {title}

**Criteria Balance**:
- Best Practices: {score}/10
- Cost-Effective: {score}/10
- Simplicity: {score}/10

**Key Innovation**: {1-2_sentence_summary}

**Why Selected**: {rationale_for_selection}

**Architecture Diagram**:
\`\`\`mermaid
{mermaid_diagram}
\`\`\`

---

### 📁 Files Created

**Brainstorming Records**:
- `./output/brainstorm-round-1-<TIMESTAMP>.sab.md`
- `./output/brainstorm-round-2-<TIMESTAMP>.sab.md`
- `./output/brainstorm-round-3-<TIMESTAMP>.sab.md`
- `./output/brainstorm-results-<TIMESTAMP>.sab.md`

**Total Size**: {file_size_summary}

---

### 🎯 Next Phase: Debate

In the debate phase, all 3 agents will:
- Analyze pros AND cons for each idea
- Assess risks from their perspective
- Propose mitigation strategies
- Rate ideas across multiple criteria

**Duration**: 3 rounds of collaborative analysis

---

### ❓ Ready to Proceed?

Would you like to proceed to the debate phase? **(yes/no)**

**Options**:
- **yes** - Start debate phase
- **modify** - Request changes to top 3
- **no** - End session and save context
```

---

## Stage 6: Final Results Presentation

```markdown
## ✅ Brainstorming Session Complete!

**Session Duration**: {duration}
**Timestamp**: {TIMESTAMP}
**Total Files Created**: {count}

---

### 📊 Final Ratings

| Idea | Best Practices | Cost-Effective | Simplicity | Overall |
|------|----------------|----------------|------------|---------|
| {idea_1_name} | {score}/10 | {score}/10 | {score}/10 | **{score}/10** |
| {idea_2_name} | {score}/10 | {score}/10 | {score}/10 | **{score}/10** |
| {idea_3_name} | {score}/10 | {score}/10 | {score}/10 | **{score}/10** |

---

### 🏆 Top Recommendation

**{top_idea_name}**

**Overall Rating**: {score}/10

**Key Strengths**:
- {strength_1}
- {strength_2}
- {strength_3}

**Why This Idea Won**:
{2-3_sentence_explanation}

**Next Steps**: {implementation_summary}

---

### 📁 Deliverables Created

#### Session Documentation
- `./output/session-<TIMESTAMP>.sab.md` - Complete session context

#### Brainstorming Records (3 rounds)
- `./output/brainstorm-round-1-<TIMESTAMP>.sab.md`
- `./output/brainstorm-round-2-<TIMESTAMP>.sab.md`
- `./output/brainstorm-round-3-<TIMESTAMP>.sab.md`
- `./output/brainstorm-results-<TIMESTAMP>.sab.md`

#### Debate Records (3 rounds)
- `./output/debate-round-1-<TIMESTAMP>.sab.md`
- `./output/debate-round-2-<TIMESTAMP>.sab.md`
- `./output/debate-round-3-<TIMESTAMP>.sab.md`

#### Architecture Diagrams
- `./output/{idea-1-name}.sab.mermaid`
- `./output/{idea-2-name}.sab.mermaid`
- `./output/{idea-3-name}.sab.mermaid`

#### Detailed Proposals
- `./output/{idea-1-name}.sab.md`
- `./output/{idea-2-name}.sab.md`
- `./output/{idea-3-name}.sab.md`

#### Analysis Documents
- `./output/ideas-comparison-<TIMESTAMP>.sab.md`
- `./output/final-recommendation-<TIMESTAMP>.sab.md`
- `./output/implementation-guide-<TIMESTAMP>.sab.md`

**Total Files**: {count}
**Total Size**: {size_summary}

---

### 🚀 Next Steps

#### Immediate Actions
1. **Review** the implementation guide for the top-rated idea
2. **Assess** resource requirements and timeline
3. **Validate** assumptions with stakeholders

#### Short-Term (Week 1-2)
4. **Begin** POC development using architecture diagrams as reference
5. **Set up** development environment and dependencies
6. **Prototype** critical components

#### Long-Term (Month 1+)
7. **Iterate** based on real-world testing
8. **Refine** architecture based on learnings
9. **Scale** implementation to production

---

### 💡 Additional Options

Would you like to:
- **New session** - Start a new brainstorming session?
- **Deep dive** - Dive deeper into one specific idea?
- **Refine** - Refine the top recommendation further?
- **Compare** - Generate additional comparison analysis?
- **Export** - Export session data in different format?

**Your choice**: {awaiting_user_input}
```

---

## Progress Indicators

### Round Progress Format
```
Brainstorming Round {X}/3...
├─ Best Practices Agent ✓
├─ Cost-Effective Agent ✓
└─ Simplicity Agent ⏳

Ideas collected: {count}/6 minimum
```

### Debate Progress Format
```
Debate Round {X}/3...
├─ Analyzing Idea 1: {name}
│  ├─ Best Practices Agent ✓
│  ├─ Cost-Effective Agent ✓
│  └─ Simplicity Agent ✓
├─ Analyzing Idea 2: {name}
│  ├─ Best Practices Agent ✓
│  ├─ Cost-Effective Agent ⏳
│  └─ Simplicity Agent ⏸
└─ Analyzing Idea 3: {name}
   └─ Pending...

Debate points collected: {count}
```

### File Generation Progress
```
Generating Output Files...
├─ Session summary ✓
├─ Architecture diagrams (3/3) ✓
├─ Detailed proposals (2/3) ⏳
├─ Comparison document ⏸
└─ Implementation guide ⏸

Files created: {count}/{total}
```

---

## Error/Warning Messages

### No Input File Found
```
⚠️ No brainstorming idea file found!

Please create a file in `./input/` with the pattern `*.sab-idea.md`

**Example**: `./input/my-app-architecture.sab-idea.md`

**Template**:
\`\`\`markdown
# My Architecture Idea

## Problem Statement
{describe_the_problem}

## Context
{provide_context}

## Constraints
{list_constraints}

## Goals
{what_you_want_to_achieve}
\`\`\`

Would you like me to create a template file for you? (yes/no)
```

### User Declined Debate
```
📝 Session Saved

Brainstorming results have been saved to:
- `./output/brainstorm-results-<TIMESTAMP>.sab.md`
- `./output/session-<TIMESTAMP>.sab.md`

You can resume this session later or start a new one.

To resume: Provide the session file when starting a new brainstorming session.
```

### Insufficient Ideas Generated
```
⚠️ Warning: Low Idea Count

Expected: Minimum 6 ideas per round (3 agents × 2 ideas)
Received: {count} ideas

**Suggestion**: Re-run this round with clearer constraints or consider:
- Relaxing constraints
- Providing more context
- Focusing the problem scope

Continue anyway? (yes/no)
```

---

## Success Confirmations

### Brainstorm Round Complete
```
✅ Brainstorm Round {X}/3 Complete

**Ideas Generated**: {count}
**Diagrams Created**: {count}
**File Saved**: `./output/brainstorm-round-{X}-<TIMESTAMP>.sab.md`

Proceeding to Round {X+1}...
```

### Debate Round Complete
```
✅ Debate Round {X}/3 Complete

**Ideas Analyzed**: 3
**Debate Points**: {count}
**File Saved**: `./output/debate-round-{X}-<TIMESTAMP>.sab.md`

Proceeding to Round {X+1}...
```

### All Outputs Generated
```
✅ All Output Files Generated Successfully

**Total Files**: {count}
**Output Directory**: `./output/`
**Session ID**: {TIMESTAMP}

All files validated ✓
All diagrams include timestamps ✓
All files use `.sab.` prefix ✓

Ready to present final results...
```
