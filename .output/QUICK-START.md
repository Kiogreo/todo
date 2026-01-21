# AI Brainstormer Framework - Quick Start Guide

## 🚀 Get Started in 5 Minutes

### Step 1: Set Up Directories

```bash
# Create input and output directories (if they don't exist)
mkdir -p ./input ./output
```

### Step 2: Create Your Idea File

```bash
# Copy and customize the template
cat > ./input/my-idea.sab-idea.md << 'EOF'
# Real-Time Collaboration Tool

## Problem Statement
Our team needs a better way to collaborate on documents in real-time, similar to Google Docs but with better privacy controls and offline support.

## Context
- Industry: Productivity software
- Target users: Remote teams (5-50 people)
- Current situation: Using email + version control, lots of merge conflicts

## Requirements
- Real-time collaborative editing
- Offline-first architecture
- End-to-end encryption
- Version history
- Commenting and suggestions
- Mobile support (iOS, Android)

## Constraints
- Budget: $10,000/month operational cost
- Timeline: 6 months to MVP
- Team: 4 developers (2 backend, 2 frontend)
- Technology: Prefer TypeScript/Node.js stack

## Goals
- Primary: Enable seamless real-time collaboration
- Secondary: Beat competitors on privacy and offline experience
- Success criteria: 10 teams actively using within 3 months of launch
EOF
```

### Step 3: Deploy the Agents

```bash
# Move generated agents to Claude Code directory
mkdir -p ./.Claude/agent/subagents/ai-brainstormer

cp .output/ai-brainstormer-orchestrator.md ./.Claude/agent/
cp .output/subagents/*.md ./.Claude/agent/subagents/ai-brainstormer/
```

### Step 4: Run Your First Session

```bash
# Invoke the orchestrator
claude --agent ai-brainstormer-orchestrator

# Or if already in Claude Code CLI:
# @.Claude/agent/ai-brainstormer-orchestrator
```

### Step 5: Review Your Results

```bash
# Check output files
ls -lh ./output/

# View session summary
cat ./output/session-*.sab.md

# View final recommendation
cat ./output/final-recommendation-*.sab.md

# View architecture diagrams
cat ./output/*.sab.mermaid
```

---

## 📊 What to Expect

### During Execution

**Stage 1: LoadIdea** (~5 seconds)
```
🔍 Scanning ./input/ for idea files...
✅ Found: my-idea.sab-idea.md
📖 Loading idea...
✅ Idea loaded: Real-Time Collaboration Tool
```

**Stage 2: BrainstormPhase** (~90 seconds)
```
🧠 Starting Brainstorming Phase (3 rounds)...

Round 1/3:
  → Best Practices Agent: Generating 2+ proposals...
  → Cost-Effective Agent: Generating 2+ proposals...
  → Simplicity Agent: Generating 2+ proposals...
  ✅ Round 1 complete: 8 ideas generated
  💾 Saved: brainstorm-round-1-20260121-143022.sab.md

Round 2/3:
  → Refining ideas based on Round 1...
  ✅ Round 2 complete: 7 ideas generated
  💾 Saved: brainstorm-round-2-20260121-143045.sab.md

Round 3/3:
  → Synthesizing best approaches...
  ✅ Round 3 complete: 9 ideas generated
  💾 Saved: brainstorm-round-3-20260121-143108.sab.md

🎯 Selecting top 3 ideas...
  1. CRDT-Based Collaborative Editor (Score: 8.7/10)
  2. WebSocket + Operational Transform Architecture (Score: 8.3/10)
  3. Hybrid P2P + Server Architecture (Score: 7.9/10)

💾 Saved: brainstorm-results-20260121-143115.sab.md
```

**Stage 3: PresentResults** (user interaction)
```
## 🧠 Brainstorming Complete!

**Rounds Completed**: 3
**Total Ideas Generated**: 24
**Top 3 Selected Ideas**:

### Idea 1: CRDT-Based Collaborative Editor
**Criteria Balance**: Best Practices (9/10), Cost (8/10), Simplicity (9/10)
**Key Innovation**: Conflict-free replicated data types enable true offline-first with automatic merge
**Diagram**: [Mermaid diagram showing CRDT architecture]

[... Ideas 2 & 3 ...]

---

Would you like to proceed to the debate phase? (yes/no)
```

**Stage 4: DebatePhase** (~270 seconds)
```
⚖️ Starting Debate Phase (3 rounds)...

Round 1/3 - Analyzing Idea 1: CRDT-Based Collaborative Editor
  → Best Practices Agent: Analyzing pros & cons...
  → Cost-Effective Agent: Analyzing pros & cons...
  → Simplicity Agent: Analyzing pros & cons...
  ✅ Round 1 complete

[... Rounds 2 & 3 ...]

💾 Saved: debate-round-1-20260121-143445.sab.md
💾 Saved: debate-round-2-20260121-143512.sab.md
💾 Saved: debate-round-3-20260121-143539.sab.md

📊 Calculating final ratings...
```

**Stage 5: GenerateOutputs** (~10 seconds)
```
📁 Generating output files...
  ✅ session-20260121-143022.sab.md
  ✅ crdt-collaborative-editor.sab.mermaid
  ✅ websocket-ot-architecture.sab.mermaid
  ✅ hybrid-p2p-server.sab.mermaid
  ✅ ideas-comparison-20260121-143555.sab.md
  ✅ final-recommendation-20260121-143555.sab.md
  ✅ implementation-guide-20260121-143555.sab.md

✅ All outputs generated successfully!
```

**Stage 6: PresentFinalResults**
```
## ✅ Brainstorming Session Complete!

**Session Duration**: 6 minutes 33 seconds
**Timestamp**: 2026-01-21 14:30:22

### 📊 Final Ratings

| Idea | Best Practices | Cost-Effective | Simplicity | Overall |
|------|----------------|----------------|------------|---------|
| CRDT-Based Collaborative Editor | 9/10 | 8/10 | 9/10 | 8.7/10 |
| WebSocket + OT Architecture | 8/10 | 9/10 | 7/10 | 8.3/10 |
| Hybrid P2P + Server | 7/10 | 7/10 | 8/10 | 7.9/10 |

### 🏆 Top Recommendation
**CRDT-Based Collaborative Editor**
- Overall Rating: 8.7/10
- Strength: True offline-first with automatic conflict resolution
- Next Steps: Prototype with Yjs or Automerge library

### 📁 Deliverables Created

[... Full file list ...]

Would you like to:
- Start a new brainstorming session?
- Dive deeper into one specific idea?
- Refine the top recommendation?
```

---

## 📁 Understanding Your Output Files

### Session Documentation
**`session-<TIMESTAMP>.sab.md`**
- Complete record of the brainstorming session
- Includes: original idea, all rounds, top 3 selection, ratings
- Use for: Future reference, sharing with team, learning from past sessions

### Brainstorming Records
**`brainstorm-round-{1,2,3}-<TIMESTAMP>.sab.md`**
- Raw output from each brainstorming round
- Includes: All proposals from all agents with diagrams
- Use for: Seeing evolution of ideas across rounds

**`brainstorm-results-<TIMESTAMP>.sab.md`**
- Summary of brainstorming phase
- Includes: Top 3 selected ideas with rationale
- Use for: Quick overview of finalist ideas

### Debate Records
**`debate-round-{1,2,3}-<TIMESTAMP>.sab.md`**
- Pros/cons analysis for each idea
- Includes: Detailed analysis from all 3 perspectives
- Use for: Understanding trade-offs and risks

### Architecture Diagrams
**`{idea-name}.sab.mermaid`**
- Visual representation of architecture
- Includes: Timestamp of when idea was discussed
- Use for: Copy/paste into documentation, presentations, or Mermaid Live Editor

**To render diagrams**:
```bash
# Option 1: Use Mermaid Live Editor (https://mermaid.live/)
# Copy/paste content from .sab.mermaid file

# Option 2: Use Mermaid CLI
npm install -g @mermaid-js/mermaid-cli
mmdc -i ./output/crdt-collaborative-editor.sab.mermaid -o ./output/diagram.png
```

### Analysis Documents
**`ideas-comparison-<TIMESTAMP>.sab.md`**
- Side-by-side comparison of top 3 ideas
- Includes: Rating table, pros/cons summary, use case fit
- Use for: Decision-making with stakeholders

**`final-recommendation-<TIMESTAMP>.sab.md`**
- Detailed breakdown of top-rated idea
- Includes: Full analysis, debate summary, rating justification
- Use for: Presenting final recommendation to team

**`implementation-guide-<TIMESTAMP>.sab.md`**
- Step-by-step plan for implementing top idea
- Includes: Prerequisites, milestones, risks, mitigation strategies
- Use for: Starting development with clear roadmap

---

## 💡 Tips for Best Results

### Writing Great Idea Files

**DO**:
- ✅ Be specific about the problem you're solving
- ✅ Include concrete constraints (budget, timeline, team size)
- ✅ Define clear success criteria
- ✅ Mention relevant context (industry, users, current situation)

**DON'T**:
- ❌ Write vague or overly broad ideas ("make a website")
- ❌ Skip constraints (agents need boundaries for realistic proposals)
- ❌ Forget to mention what success looks like
- ❌ Leave out technical context (preferred tech stack, existing systems)

### Example: Poor vs. Good Idea Files

**Poor**:
```markdown
# Build an App

We want to build an app for our business.
```

**Good**:
```markdown
# Inventory Management App for Retail Store

## Problem Statement
Our small retail store (10 employees) tracks inventory manually in Excel spreadsheets, 
leading to stockouts and overordering. We need a simple mobile app for real-time inventory 
tracking.

## Context
- Industry: Small retail (clothing store)
- Target users: Store employees (cashiers, stock clerks)
- Current situation: Excel spreadsheets, updated once per day

## Requirements
- Barcode scanning for quick item lookup
- Real-time stock level updates
- Low stock alerts
- Simple reorder workflow
- Works offline (spotty store WiFi)

## Constraints
- Budget: $2000 one-time + $200/month
- Timeline: Need MVP in 2 months
- Team: Owner + 1 tech-savvy employee (no developers)
- Technology: Must work on Android tablets we already own

## Goals
- Primary: Reduce stockouts by 80%
- Secondary: Save 5+ hours/week on inventory management
- Success criteria: All employees using app within 1 month
```

### Interpreting Ratings

**Overall Rating**: Weighted average of all criteria
- **9-10**: Exceptional solution, minimal trade-offs
- **8-9**: Strong solution, good balance
- **7-8**: Solid solution, some trade-offs
- **6-7**: Acceptable solution, notable compromises
- **<6**: Weak solution, significant issues

**Criteria Scores**:
- **Best Practices**: Engineering excellence, maintainability, scalability
- **Cost-Effective**: Resource optimization, ROI, pragmatic choices
- **Simplicity**: Ease of understanding, low complexity, developer experience

**Example Interpretation**:
```
Idea: CRDT-Based Editor
Best Practices: 9/10  ← Excellent engineering (CRDT pattern, testability)
Cost-Effective: 8/10  ← Good ROI, but CRDT library learning curve costs time
Simplicity: 9/10      ← Simple mental model once CRDT understood
Overall: 8.7/10       ← Strong recommendation with minor cost concern
```

### When to Dive Deeper

**After first session**, consider diving deeper if:
- Ratings are close (e.g., 8.7 vs 8.3) → Run focused comparison
- Top idea has significant cons → Request mitigation strategies
- Team has specific expertise → Request refinement favoring that expertise
- Budget/timeline constraints are critical → Request cost-optimized variant

**How to dive deeper**:
```bash
# Create focused idea file
cat > ./input/deep-dive-crdt.sab-idea.md << EOF
# Deep Dive: CRDT-Based Collaborative Editor

Based on previous brainstorming session (2026-01-21), we selected the CRDT-Based 
Collaborative Editor architecture. Now we need deeper analysis on:

1. CRDT library comparison (Yjs vs Automerge vs custom)
2. Detailed cost breakdown (development + operational)
3. Risk mitigation strategies for identified cons
4. Phased implementation roadmap

Use previous session context: ./output/session-20260121-143022.sab.md
EOF

# Run new session focused on deep dive
claude --agent ai-brainstormer-orchestrator
```

---

## 🔧 Customization Options

### Adjust Agent Focus

**To emphasize security** (in addition to existing criteria):
1. Create `security-agent.md` based on existing agent template
2. Update orchestrator Stage 2 routing to include security agent
3. Re-run session

### Change Round Counts

**To reduce execution time** (use 2 rounds instead of 3):
1. Edit orchestrator `<critical_rules>`:
   ```xml
   <rule id="multi_round_limit">
     Brainstorming MUST NOT exceed 2 rounds; debate MUST NOT exceed 2 rounds
   </rule>
   ```
2. Update Stage 2 and Stage 4 FOR loops: `FOR round IN [1, 2]:`

### Custom Output Templates

**To add cost breakdown table** to final recommendation:
1. Edit orchestrator Stage 5 `<file_templates>`
2. Add cost table to `final-recommendation` template
3. Re-run session

---

## ❓ Troubleshooting

### "No idea files found"
```
Problem: ./input/ directory is empty or files don't have .sab-idea.md extension

Solution:
1. Create idea file with correct naming: ./input/{name}.sab-idea.md
2. Ensure file has content (not empty)
3. Re-run orchestrator
```

### "Agent not responding"
```
Problem: Subagent routing fails

Solution:
1. Verify subagent files are in correct location:
   ./.Claude/agent/subagents/ai-brainstormer/
2. Check file names match orchestrator routing:
   - best-practices-agent.md
   - cost-effective-agent.md
   - simplicity-agent.md
3. Ensure files have valid YAML front matter
```

### "Output files not created"
```
Problem: Stage 5 fails to generate files

Solution:
1. Verify ./output/ directory exists and is writable:
   mkdir -p ./output
   chmod 755 ./output
2. Check disk space
3. Review Stage 5 logs for specific error
```

### "Diagrams missing"
```
Problem: Proposals don't include Mermaid diagrams

Solution:
1. Verify critical rule enforcement in subagents:
   <rule id="diagram_requirement">Each proposal MUST include a Mermaid diagram</rule>
2. Check subagent output format includes diagram field
3. Validate diagram syntax with Mermaid Live Editor
```

---

## 📚 Next Steps

1. **Run your first session** with the example idea file
2. **Review all output files** to understand what gets generated
3. **Create a real idea file** for a problem you're actually facing
4. **Compare results** with your current brainstorming process
5. **Customize agents** to match your team's priorities
6. **Share results** with your team and iterate

---

## 🎯 Success Checklist

After your first session, you should have:

- [ ] 14 output files in `./output/` directory
- [ ] All files follow `.sab.*` naming convention
- [ ] 3 architecture diagrams (one per top idea)
- [ ] Final ratings table with quantified scores
- [ ] Implementation guide for top-rated idea
- [ ] Complete session context saved for future reference

If you have all of these, **congratulations!** 🎉 Your AI Brainstormer Framework is working correctly.

---

## 📖 Further Reading

- **OPTIMIZATION-ANALYSIS.md**: Deep dive into research patterns and system design
- **AGENTS.md**: OpenAgent Framework guide (if in Claude Code repository)
- Individual agent files: Understand evaluation criteria for each perspective

---

**Ready to brainstorm?** Create your idea file and run your first session! 🚀

*Last updated: 2026-01-21*
