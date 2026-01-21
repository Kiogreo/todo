# AI Brainstormer - Detailed Stage Processes

## Stage 1: LoadIdea - Detailed Process

### File Discovery
1. Scan `./input/` directory for files matching `*.sab-idea.md`
2. If multiple files found, list with timestamps and request user selection
3. If no files found, prompt user to create one with template
4. Read selected idea file content

### Idea Extraction
5. Extract key problem statement (2-3 sentence summary)
6. Identify explicit constraints and requirements
7. Parse context information (domain, users, scope)
8. Generate timestamp for session tracking

### Preparation
9. Prepare idea summary package for subagents
10. Validate idea content is sufficient for brainstorming
11. Initialize session tracking

---

## Stage 2: BrainstormPhase - Detailed Process

### Round Execution (Repeat for rounds 1, 2, 3)

**Agent Routing:**
1. Route to each specialized agent concurrently:
   - @subagents/ai-brainstormer/best-practices-agent
   - @subagents/ai-brainstormer/cost-effective-agent
   - @subagents/ai-brainstormer/simplicity-agent

**Data Passed to Each Agent:**
- `idea_content` - User's original idea (full text)
- `problem_summary` - Distilled problem statement (2-3 sentences)
- `round_number` - Current round (1, 2, or 3)
- `previous_ideas` - Ideas from earlier rounds (if any)
- `constraint` - Generate minimum 2 distinct proposals

**Expected Returns from Each Agent:**
- `proposals[]` - At least 2 architecture ideas
- `diagrams[]` - Mermaid format diagrams with timestamps
- `rationale` - Why this approach fits their criteria

**Round Consolidation:**
4. Collect all proposals from all agents (6+ ideas per round)
5. Save round results to `./output/brainstorm-round-{round}-<TIMESTAMP>.sab.md`

### Synthesis Phase (After all 3 rounds)

6. Synthesize all rounds (total 6-18+ ideas from 3 agents × 3 rounds × 2+ ideas)
7. Identify top 3 ideas based on:
   - Coverage across criteria (best practices, cost, simplicity)
   - Feasibility assessment (technical viability, resource requirements)
   - Innovative approach (novel solutions, creative thinking)
   - Clear articulation with diagrams (understandability, completeness)

8. Prepare presentation document with:
   - Summary of brainstorming process
   - Top 3 selected ideas with diagrams
   - Rationale for selection (why these 3 stand out)
   - Next steps (debate phase overview)

---

## Stage 3: PresentResults - User Approval Process

### Presentation Display
1. Show brainstorming summary with metrics
2. Display top 3 ideas with diagrams and criteria scores
3. List all files created during brainstorming
4. Explain debate phase process

### User Interaction
2. Wait for user response
3. If user says "yes" or "proceed": Continue to Stage 4
4. If user requests changes: Return to Stage 2 with modifications
5. If user says "no": End session, save context to `./output/session-<TIMESTAMP>.sab.md`

---

## Stage 4: DebatePhase - Detailed Process

### Round Execution (Repeat for rounds 1, 2, 3)

**For Each Idea in Top 3:**

1. Route to all 3 agents with focus on current idea:
   - @subagents/ai-brainstormer/best-practices-agent
   - @subagents/ai-brainstormer/cost-effective-agent
   - @subagents/ai-brainstormer/simplicity-agent

**Data Passed to Each Agent:**
- `idea_details` - Full proposal with diagrams
- `round_number` - Current round (1, 2, or 3)
- `previous_debate_points` - Arguments from earlier rounds
- `task` - Analyze pros AND cons from their perspective

**Expected Returns from Each Agent:**
- `pros[]` - Advantages from their criteria
- `cons[]` - Disadvantages from their criteria
- `risk_assessment` - Potential issues and concerns
- `mitigation_strategies` - How to address cons

4. Collect all debate points for all ideas

**Round Consolidation:**
5. Save round results to `./output/debate-round-{round}-<TIMESTAMP>.sab.md`

### Rating Calculation (After all 3 rounds)

6. Synthesize all debate rounds (3 rounds × 3 ideas × 3 agents)

7. Calculate ratings for each idea:
   - **Best Practices Score (1-10)**: Adherence to industry standards, scalability, maintainability
   - **Cost-Effectiveness Score (1-10)**: Initial cost, operational cost, ROI potential
   - **Simplicity/Maintenance Score (1-10)**: Complexity, ease of understanding, maintenance burden
   - **Balance Score**: How well it balances all three criteria
   - **Overall Rating**: Weighted average (configurable weights)

8. Rank ideas by overall rating (highest to lowest)
9. Prepare final recommendation document with detailed rationale

---

## Stage 5: GenerateOutputs - File Creation Process

### Session Summary Document
1. Create `./output/session-<TIMESTAMP>.sab.md`:
   - Original idea (user's input)
   - Brainstorming summary (rounds, agents, total ideas)
   - Debate summary (rounds, analysis focus)
   - Final ratings (table format)
   - Top recommendation (selected idea with rationale)

### Architecture Diagrams (Per Idea)
2. For each top idea, create:
   - `./output/{idea-name}.sab.mermaid` - Standalone diagram file
   - `./output/{idea-name}.sab.md` - Detailed proposal document
   - Include timestamp in each diagram

### Comparison Document
3. Create `./output/ideas-comparison-<TIMESTAMP>.sab.md`:
   - Side-by-side comparison table
   - Ratings across all criteria
   - Pros/cons summary for each idea
   - Use case fit analysis

### Implementation Guide
4. Create `./output/implementation-guide-<TIMESTAMP>.sab.md`:
   - Step-by-step implementation plan for top-rated idea
   - Prerequisites (tools, skills, resources)
   - Milestones with timelines
   - Risk identification and mitigation strategies
   - Success criteria and validation approach

### Validation
5. Validate all outputs:
   - All files in `./output/` directory
   - All files have `.sab.` prefix
   - All diagrams have timestamps
   - Naming is descriptive and purposeful
   - No missing or corrupted files

---

## Stage 6: PresentFinalResults - Delivery Process

### Final Summary Display
1. Show session metrics (duration, timestamp)
2. Display final ratings table for all 3 ideas
3. Highlight top recommendation with key strengths
4. List all deliverables created (organized by category)
5. Provide next steps for implementation

### User Interaction
2. Await user response for next action:
   - Start new brainstorming session
   - Dive deeper into specific idea
   - Refine top recommendation
   - End session
