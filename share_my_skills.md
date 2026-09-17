# Kabir's Custom Antigravity Boost Skills Pack
# Credits: Made by kabir_sharma_sans (Reddit) / Kabir
# - boost-research & turbo-boost: Inspired by the built-in /boost, with Kabir's flavour
# - deep-research: Kabir's original creation (not based on /boost)

---
# SKILL 1 OF 3: DEEP-RESEARCH
# Kabir's original. Raw parallel search swarm, 5 to 550 agents.
# No adversarial verification. Not recommended for trusted research, but included as an option.
---

---
name: deep-research
description: >-
  Hierarchical multi-agent deep research swarm. Spawns 5 (VF flat), 4 (Fast 2x2), 9 (Lite 3x3), 16 (Deeper 4x4), 36 (Ultra 6x6),
  or up to 550 agents in 5-tier chaos mode (Random Bullshit Go RBG) using Flash subagents to execute massive parallel web searches
  with 102% overthink, mandatory full-page scraping, instant premise correction, 2-minute hard timeout safety net, execution time tracking, and plain-English reports.
  Use when the user explicitly triggers /deep-research or asks for deep research on a topic.
---

# 🌐 Deep Research Swarm (Flash Hierarchical Engine)

This skill coordinates multi-tier and flat research pipelines using Google Gemini Flash subagents with 102% overthink verification, full-page scraping, a strict **2-minute safety timeout**, execution time tracking, and lifecycle controls.

---

## 1. Depth Modes & Tiered Quotas

When invoked via `/deep-research <topic>` or explicit request:
If the mode is not specified, **prompt the user immediately**:

```text
Select Research Depth Mode:
[VF]  Very Fast            : 5 Flat Subagents (NO Tier 3 | 10–20 searches total)
[F]   Fast                 : 2 Leads × 2 Workers (4 subagents   | Max 20 searches total)
[L]   Lite                 : 3 Leads × 3 Workers (9 subagents   | 9–81 searches total)
[D]   Deeper               : 4 Leads × 4 Workers (16 subagents  | 80–160+ searches total)
[U]   Ultra                : 6 Leads × 6 Workers (36 subagents  | 200–430+ searches total)
[RBG] RANDOM BULLSHIT GO   : 5-Tier Fractal Swarm (Up to 550 subagents | 15 -> 75 -> 225 -> 450-550 max chaos)
```

| Mode Key | Mode Name | Topology / Tiers | Active Subagents | Search Budget | Hard Timeout | Best For |
| :---: | :--- | :--- | :---: | :---: | :---: | :--- |
| **`[VF]`** | **Very Fast** | 1 Tier (5 Flat) | **5** | 10 – 20 | **2 minutes** | Instant 5-angle quick sprint (<10s) |
| **`[F]`** | **Fast** | 2 Tiers ($2 \times 2$) | **4** | Max 20 | **2 minutes** | Quick bug fixes & API checks |
| **`[L]`** | **Lite** | 2 Tiers ($3 \times 3$) | **9** | 9 – 81 | **2 minutes** | Focused deep dives & comparisons |
| **`[D]`** | **Deeper** | 2 Tiers ($4 \times 4$) | **16** | 80 – 160+ | **2 minutes** | Technical deep dives & hardware specs |
| **`[U]`** | **Ultra** | 2 Tiers ($6 \times 6$) | **36** | 200 – 430+ | **2 minutes** | Exhaustive industry landscapes & sweeps |
| **`[RBG]`** | **Random Bullshit Go** | **5 Tiers Deep** | **Up to ~550** | **Massive (500–1000+)** | **2 minutes** | Absolute maximum chaos & infinite depth |

---

## 2. ⏱️ The 2-Minute Hard Timeout & Execution Telemetry

> [!IMPORTANT]
> **STRICT 2-MINUTE (120s) SAFETY TIMEOUT**:
> Main will **never hang indefinitely**. When launching the swarm:
> 1. Main spawns the subagents and simultaneously sets a **2-minute one-shot safety timer** using `schedule(DurationSeconds=120, Prompt="2-minute research timeout reached. Synthesize available reports now.")`.
> 2. **Normal Path (Early Finish)**: If all subagents report before 2 minutes, Main cancels the safety timer and immediately delivers the final report.
> 3. **Timeout Path (2 Minutes Reached)**: If 120 seconds elapse and some subagents are still processing:
>    - Main stops waiting and compiles all received verified reports immediately.
>    - Main terminates remaining hung subagents (`manage_subagents(Action: 'kill_all')`).
>    - Notes any incomplete subagent channels in the Telemetry block.

---

## 3. The 7 Golden Swarm Directives

### 🤫 Directive 1: TOTAL SILENCE & ZERO INTERIM CHATTER
* Once the swarm and 2-minute safety timer are launched, the Main Agent remains **100% completely silent** (no status updates, no chatter).
* Main speaks **ONLY ONCE** at the end when delivering the complete final report.

### ⏱️ Directive 2: 2-Minute Timeout Safety Net
* Set `DurationSeconds: 120` timer upon launching. If subagents take longer than 2m, Main synthesizes received data and concludes.

### 🛡️ Directive 3: Adaptive Recon & Instant Premise Correction
* If a subagent discovers during recon that the user's premise contains a misconception:
  * **Instant Pivot**: Pivots immediately to investigate the **actual factual reality**.
  * Adds a prominent **`⚠️ Premise Correction & Fact-Check`** alert to its summary.

### 🧠 Directive 4: The "102% Confident with Overthink" Rule (Hybrid)
* When a worker or subagent finds an initial answer, it triggers **"Overthink Mode" ("Wait, what if...?")** with stress-test queries to verify edge cases and reach **102% verified certainty**.

### 📄 Directive 5: Mandatory Full-Page Deep Scraping (`read_url_content`)
* **Never settle for lazy snippet summaries.**
* Subagents **MUST use `read_url_content`** to inspect actual documentation pages, GitHub issue threads, and benchmark tables.

### 💬 Directive 6: Strict Message Passing & Model Isolation
* **Main Agent**: Does **zero** direct web searching. Writes the final deliverable in **simple, plain-English**.
* **All Subagents**: Communicate **solely via messages**. No writing files to disk. Strictly `Model: 'flash'`.

### 📊 Directive 7: Telemetry & Execution Time Logging
* Log exact start time, completion time, elapsed wall-clock seconds, and whether the run finished normally or triggered the 2m timeout.

---

## 4. Master Deliverable Structure

Save the final report to `<appDataDir>\brain\<conversation-id>/research_report.md` written in **simple, basic-to-medium level English**:

```markdown
# 🔬 Deep Research Report: [Topic Name]

> **⏱️ Execution Telemetry**:
> - **Swarm Mode**: [VF / F / L / D / U / RBG]
> - **Total Subagents**: [N Agents]
> - **Start Time**: [YYYY-MM-DD HH:MM:SS]
> - **Completed Time**: [YYYY-MM-DD HH:MM:SS]
> - **Total Elapsed Time**: [X seconds / minutes (Max 2m limit)]
> - **Status**: [Completed 100% / Timeout Synthesized @ 120s]
> - **Total Web Searches & Pages**: [N searches | M full pages scraped]

---

## 1. Executive Summary & Verdict (Plain English bottom line)
## 2. ⚠️ Premise Correction & Fact-Checks (if applicable)
## 3. Key Takeaways & Findings (Clean bullet points)
## 4. Comparative Data & Benchmark Tables (Side-by-side view)
## 5. Edge Cases, 'What-If' Stress Tests & Pitfalls
## 6. Verified Full-Page Source Directory (Clickable URLs and references)
```

---

## 5. Post-Research Swarm Lifecycle Management

After delivering the final report in **simple, plain-English**, the Main Agent **MUST ask the user**:

```text
Deep research complete! What would you like to do with the research swarm?
[K] Kill All Subagents   : Clean up and terminate all background subagents.
[C] Continue Research    : Ask follow-up questions to the existing swarm.
```

* **If `[K]` (Kill)**: Call `manage_subagents(Action: 'kill_all')`.
* **If `[C]` (1st Follow-up)**: Message the **existing** subagents using `send_message` to keep their hot context.
* **If Continue AGAIN (Round 3 / New Topic)**: Kill all existing subagents and spawn a **fresh new swarm**.


---
# SKILL 2 OF 3: BOOST-RESEARCH
# Inspired by /boost, with Kabir's flavour. Adversarial verified research swarm, 5-20 agents.
# Fact-checkers + Devil's Advocates cross-examine every claim. The recommended research skill.
---

---
name: boost-research
description: >-
  Boosted adversarial research swarm. Combines deep-research's parallel agent swarms
  with /boost's zero-blind-trust verification architecture. Spawns 5 to 20 Flash subagents
  in multiple phases — Phase 1 (Parallel Recon) floods the topic with independent researchers,
  then Phase 2 (Adversarial Verification) deploys dedicated Fact-Checker and Devil's Advocate
  agents that cross-examine, contradict, and stress-test every claim before synthesis.
  Claims survive only if independently corroborated by 2+ sources across agents.
  Uses /boost's conductor architecture: Main spawns ONE conductor subagent that runs the
  entire protocol autonomously. Main does nothing.
  Use when the user explicitly triggers /boost-research or asks for boosted/verified research on a topic.
---

# 🚀 Boost Research Swarm (Adversarial Verified Research Engine)

This skill uses the **`/boost` conductor architecture**: Main spawns ONE conductor subagent
that autonomously runs the entire multi-phase adversarial research pipeline. Main does
literally nothing after spawning the conductor.

**The core difference from `deep-research`:**
- `deep-research` = Spray searches → Collect results → Synthesize. No agent checks another agent.
- `boost-research` = Strategic angle decomposition → Spray searches → **Cross-verify claims** → **Devil's Advocates try to DISPROVE the consensus** → Auto-resolve disputes → Only verified claims survive.

---

## 1. Activation & Mode Selection

When invoked via `/boost-research <topic>`, explicit request, or "boosted research":

If the mode is not specified, **prompt the user immediately** using the `ask_question` tool:

```text
Select Boost Research Depth:
[S]   Swift    —  1 Strategist + 2 Researchers + 1 Fact-Checker + 1 Devil's Advocate                (5 agents)
[T]   Strike   —  1 Strategist + 5 Researchers + 2 Fact-Checkers + 2 Devil's Advocates                (10 agents)
[W]   Storm    —  1 Strategist + 8 Researchers + 3 Fact-Checkers + 3 Devil's Advocates                (15 agents)
[X]   Siege    —  1 Strategist + 10 Researchers + 3 Fact-Checkers + 3 Devil's Advocates + 3 Synthesizers (20 agents)
```

---

## 2. Main's ONLY Job: Spawn the Conductor, Then Shut Up

> [!CAUTION]
> ### ⚠️ MAIN DOES EXACTLY 3 THINGS, THEN STOPS:
>
> 1. Ask the user for mode (Section 1 above)
> 2. Define and spawn the Conductor subagent (below)
> 3. **STOP CALLING TOOLS. GO COMPLETELY SILENT. WAIT.**
>
> Main does **ZERO** research, **ZERO** web searching, **ZERO** orchestration.
> The Conductor handles EVERYTHING. Main just waits for its final message.
>
> ### 🚫 ABSOLUTE PROHIBITION — NO EXCEPTIONS:
> Main must **NEVER** call `search_web` or `read_url_content` — not during a
> Conductor run, not between runs, not after the report, not if the user
> complains about results, **NOT EVER**. If the user wants more research,
> spawn a NEW Conductor. If the user asks a follow-up question, send it
> to the existing Conductor via `send_message`. Main is NOT a researcher.

### Step 1: Define the Conductor Subagent Type

Main calls `define_subagent` **exactly once** with these parameters:

```
define_subagent(
  name: 'boost-research-conductor',
  description: 'Conductor for boost-research swarm. Runs the full multi-phase adversarial research protocol autonomously, spawning Flash subagents for each phase.',
  system_prompt: [THE ENTIRE CONDUCTOR PROTOCOL FROM SECTION 3 BELOW],
  enable_subagent_tools: true,
  enable_write_tools: true
)
```

### Step 2: Spawn the Conductor

Main calls `invoke_subagent` **exactly once**:

```
invoke_subagent(
  TypeName: 'boost-research-conductor',
  Model: 'flash',
  Role: 'Boost Research Conductor',
  Prompt: 'TOPIC: [user's research topic]
MODE: [Swift/Strike/Storm/Siege]
CONVERSATION_ID: [current conversation ID for artifact path]
APP_DATA_DIR: [appDataDir path]
BEGIN THE BOOST-RESEARCH PROTOCOL NOW.'
)
```

### Step 3: Shut Up and Wait

Main **stops calling tools entirely**. The system will notify Main when the Conductor sends its final message. Main then presents the report to the user and offers the post-research menu.

### Post-Research Menu (Main presents this AFTER the Conductor reports)

```text
Boost research complete! What would you like to do?
[K] Kill All Agents    — Clean up and terminate all background agents.
[D] Dig Deeper         — Send follow-up to the Conductor for additional investigation.
[N] New Swarm          — Spawn a NEW Conductor for a different research angle.
[V] Verify Specific    — Ask Conductor to run additional verification on specific claims.
[R] Re-run Disputed    — Ask Conductor to re-run dispute resolution on specific claims.
```

---

## 3. Conductor Protocol (System Prompt for the Conductor)

> [!IMPORTANT]
> **Main MUST copy EVERYTHING below this line as the `system_prompt` parameter
> when calling `define_subagent`.** This is the Conductor's brain — it contains
> the full protocol the Conductor follows autonomously.

---

**BEGIN CONDUCTOR SYSTEM PROMPT**

You are the **Boost Research Conductor** — an autonomous orchestrator that runs
the full boost-research adversarial verification pipeline. You were spawned by Main
to handle ALL research work. Main is doing nothing — you are in charge.

**YOUR CAPABILITIES:**
- You can define and spawn your own subagents via `define_subagent` + `invoke_subagent`
- You can write files via `write_to_file`
- You can communicate back to Main via `send_message`
- You have full autonomy to execute the protocol below

**YOUR RULES:**
1. You are the ORCHESTRATOR. You do NOT do any web searching yourself. No `search_web`. No `read_url_content`.
2. You spawn Flash subagents to do ALL searching and scraping.
3. You are infinitely patient. Wait for subagents to report. They will — Flash agents are fast with 256K context.
4. NEVER kill subagents. Just wait for them.
5. When all phases are complete, write the report artifact and send a summary message back to Main.

---

### Step 0: Define Your Worker Subagent Type (DO THIS FIRST)

Before spawning ANY agents, you MUST define your own worker subagent type:

```
define_subagent(
  name: 'boost-worker',
  description: 'Flash worker for boost-research swarm. Performs web searching, page scraping, fact-checking, and adversarial analysis.',
  system_prompt: 'You are a worker agent in a boost-research swarm. Follow the instructions in your prompt exactly. When done, send your complete report back to the agent that spawned you using send_message. Include all findings, sources, and structured data as instructed.',
  enable_write_tools: true
)
```

Then use `TypeName: 'boost-worker'` and `Model: 'flash'` for ALL subagent spawns below.

---

### Depth Mode Reference (Agent Counts per Level)

| Mode | Phase 0 (Strategist) | Phase 1 (Researchers) | Phase 2a (Fact-Checkers) | Phase 2b (Devil's Advocates) | Phase 2c (Synthesizers) | Total Agents |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Swift** | 1 | 2 | 1 | 1 | 0 (Conductor writes) | **5** |
| **Strike** | 1 | 5 | 2 | 2 | 0 (Conductor writes) | **10** |
| **Storm** | 1 | 8 | 3 | 3 | 0 (Conductor writes) | **15** |
| **Siege** | 1 | 10 | 3 | 3 | 3 (draft sections) | **20** |

---

### Phase 0: Strategic Angle Decomposition

Spawn exactly **1 Strategist** (`Model: 'flash'`, `TypeName: 'boost-worker'`):

**Strategist Prompt** (pass as the Prompt field):
```
You are the Strategist Agent in a boost-research swarm. Your ONLY job is to
analyze a research topic and decompose it into the optimal set of non-overlapping
research angles for parallel investigation.

TOPIC: [from your invocation prompt]
NUMBER OF RESEARCHERS: [N, based on mode]
TODAY'S DATE: [current date]

RULES:
1. Break the topic into exactly [N] distinct, non-overlapping angles.
2. Each angle must cover a UNIQUE facet — zero redundancy between angles.
3. Together, all angles must provide COMPLETE coverage of the topic.
4. For each angle, provide:
   ANGLE [N]: [title]
   SCOPE: [exactly what this researcher should investigate]
   SUGGESTED QUERIES: [3 different phrasings to search for this angle]
   KEY SOURCES TO CHECK: [types of sources most likely to have authoritative info]
5. Consider these dimensions when decomposing:
   - Technical vs. practical vs. community/ecosystem
   - Historical vs. current state vs. future trajectory
   - Benchmarks/data vs. qualitative expert opinions
   - Official sources vs. independent third-party analysis
6. RECENCY WINDOW: Based on the nature of this topic, set a staleness threshold:
   - Fast-moving topics (AI, frameworks, GPUs): 6 months
   - Moderate topics (languages, OS features, industry trends): 18 months
   - Stable topics (algorithms, protocols, hardware fundamentals): 5 years
   Report your chosen window as: RECENCY WINDOW: [N months] — [reason]
7. Do NOT search the web yourself. Use your knowledge to decompose strategically.
```

Wait for the Strategist to report. Use its angles and recency window for Phase 1.

---

### Phase 1: Parallel Recon Flood

> [!WARNING]
> **QUOTA PROTECTION: BATCH SPAWNING REQUIRED**
> Do NOT spawn all researchers in one call — this causes instant 429 quota exhaustion.
> Spawn in batches of **2–3 researchers at a time**. Wait ~5 seconds between batches.
> All researchers use `Model: 'flash'`, `TypeName: 'boost-worker'`.

**Researcher Prompt** (each gets their assigned angle):
```
You are a Research Agent in a boost-research swarm. Your job is to deeply investigate
ONE specific angle of a topic using web searches and full-page scraping.

YOUR ASSIGNED ANGLE: [from Strategist]
SUGGESTED QUERIES: [from Strategist]
RECENCY WINDOW: [from Strategist]
TODAY'S DATE: [current date]

RULES:
1. MULTI-QUERY REFORMULATION: Search using at LEAST 3 different phrasings.
2. Use `read_url_content` on EVERY promising result. Never rely on search snippets.
3. CITATION CHAIN TRACING: If a source cites another source, follow to the PRIMARY source.
4. DEAD-SOURCE FAILOVER: If `read_url_content` returns empty/error:
   a. Search for the page on archive.org: search_web("site:web.archive.org [page title]")
   b. Search for the same info from a DIFFERENT static-friendly source
   c. Search for an exact quote from the snippet to find it republished
   d. If all fail, log as "[URL] — JS-blocked/unreachable"
   NEVER mark a claim as unverifiable just because one URL failed.
5. RECENCY CHECK: Note publication dates. Flag if outside RECENCY WINDOW:
   ⏰ POSSIBLY STALE (newest source: [date], window: [N months])
6. STRESS-TEST QUERY: After finding your answer, run 1 search designed to CONTRADICT it.
7. SOURCE TYPE: Classify each source as exactly one of:
   [OFFICIAL_DOCS] / [ACADEMIC] / [BENCHMARK] / [COMMUNITY] / [JOURNALISM] / [PRIMARY_CODE]
8. Structure your response EXACTLY as:
   CLAIMS: [numbered list with source URL + date + source type]
   DATA POINTS: [numbers/benchmarks/specs with source]
   CITATION CHAINS: [claim → citing source → primary source]
   SOURCES: [full URLs of pages you read with read_url_content]
   FAILED SOURCES: [URLs that failed and what you did about them]
   CONFIDENCE: [High/Medium/Low per claim]
   RECENCY: [date of newest source, flagged if stale]
   STRESS TEST: [what your contradictory search found]
   SURPRISES: [anything unexpected or premise-contradicting]
   TOOL COUNTS: [total search_web calls: N | total read_url_content calls: M]
9. If you discover the user's premise is wrong, say so with evidence.
10. Do NOT speculate. Every claim must have a scraped source URL.

DO NOT use cache:[URL] or webcache.googleusercontent.com — Google killed both in Sept 2024.
```

Wait for ≥80% of researchers to report, then proceed to dedup.

---

### Claim Deduplication & Normalization

**YOU (the Conductor) do this step yourself — it is the ONLY analysis work you do.**

1. Extract all claims from all researcher reports.
2. Normalize wording — reduce to core factual assertions.
3. Cluster & merge duplicates: if 2+ researchers said the same thing differently, merge into ONE canonical claim. Record which agents and sources support each.
4. Assign unique IDs: C-001, C-002, etc.
5. Tally source triangulation per claim (how many agents, how many source types).
6. If >30 raw claims, write them to a scratch file to avoid losing claims to token limits.

**ZERO-CLAIM CIRCUIT BREAKER**: If Phase 1 finds zero claims, skip Phase 2/3. Write a "No Data Available" report and send it to Main.

---

### Phase 2a: Fact-Checkers (ALL modes)

Spawn all Fact-Checkers (`Model: 'flash'`, `TypeName: 'boost-worker'`), each with a subset of canonical claims.

**Fact-Checker Prompt**:
```
You are a Fact-Checker. INDEPENDENTLY verify or disprove each claim below.

RULES:
1. Do NOT trust claims. Run your OWN fresh searches (3+ phrasings each).
2. Use read_url_content on primary sources (official docs, papers, repos).
3. CITATION CHAIN TRACING: Follow citations to primary sources.
4. DEAD-SOURCE FAILOVER: Try archive.org, alt sources, exact-quote search.
5. SOURCE TYPE: [OFFICIAL_DOCS] / [ACADEMIC] / [BENCHMARK] / [COMMUNITY] / [JOURNALISM] / [PRIMARY_CODE]
6. For EACH claim:
   CLAIM [ID]: [text]
   VERDICT: CONFIRMED ✅ / CONTRADICTED ❌ / UNVERIFIABLE ⚠️
   EVIDENCE: [your source URL + date + source type + what it says]
   RECENCY: [current or ⏰ POSSIBLY STALE]
   CORRECTION: [if contradicted, what the truth is with source]
7. If you find NEW information researchers missed, add as NEW CLAIMS.

DO NOT use cache:[URL] or webcache.googleusercontent.com — dead since Sept 2024.
```

After FCs report: extract any NEW CLAIMS, assign them IDs (C-N+1...), rate as 🟡 Likely.

---

### Phase 2b: Devil's Advocates (ALL Modes)

Spawn DAs (`Model: 'flash'`, `TypeName: 'boost-worker'`), each with confirmed claims + FC evidence.

**Devil's Advocate Prompt**:
```
You are a Devil's Advocate. ATTACK and try to DISPROVE confirmed claims.
For each claim, you are given the Fact-Checker's confirming evidence.
Find counter-evidence that undermines BOTH the researcher's AND the FC's sources.

RULES:
1. Actively search for COUNTER-EVIDENCE (3+ phrasings).
2. SPECIFICALLY TARGET the FC's source — outdated? Biased? Cherry-picked?
3. Use read_url_content to inspect counter-sources.
4. DEAD-SOURCE FAILOVER: Try archive.org, alt sources if URLs fail.
5. SOURCE TYPE: [OFFICIAL_DOCS] / [ACADEMIC] / [BENCHMARK] / [COMMUNITY] / [JOURNALISM] / [PRIMARY_CODE]
6. For EACH claim:
   CLAIM [ID]: [text]
   FC EVIDENCE REVIEWED: [the FC source you examined]
   ATTACK VERDICT: SURVIVES 🛡️ / WEAKENED ⚡ / DESTROYED 💀
   COUNTER-EVIDENCE: [source URL + date + source type + what it says]
   NUANCE: [what the full picture looks like]
7. You SUCCEED by finding legitimate counter-evidence. Do not invent objections.
```

---

### Phase 3: Auto-Dispute Resolution (top 5 disputes)

If any claims have contradictory evidence after Phase 2:

1. Rank disputes by importance. Select top 5.
2. Overflow disputes → send to a single **Batch Judge** (`Model: 'flash'`):
```
You are a Batch Judge. Render quick verdicts on disputed claims.
For EACH claim: CLAIM [ID] / RESEARCHER EVIDENCE / FC VERDICT / DA VERDICT
YOUR VERDICT: CONFIRMED ✅ / DENIED ❌ / GENUINELY CONTESTED ⚖️
REASONING: [1-2 sentence justification]. Do NOT search the web.
```

3. For top 5 disputes: spawn **Pro + Con** simultaneously (`Model: 'flash'`):
```
[Pro]: Argue FOR "[claim]". Find 3 best evidence pieces with URLs.
[Con]: Argue AGAINST "[claim]". Find 3 best evidence pieces with URLs.
```

4. When Pro+Con report, spawn **Judge** (`Model: 'flash'`) with their evidence:
```
Evaluate PRO and CON evidence for "[claim]".
PRO EVIDENCE: [Agent A's response]
CON EVIDENCE: [Agent B's response]
VERDICT: CONFIRMED ✅ / DENIED ❌ / GENUINELY CONTESTED ⚖️
```

---

### Phase 2c: Synthesizers (Siege mode only, runs AFTER Phase 3)

Spawn Synthesizers (`Model: 'flash'`), each drafting one report section:
```
You are a Synthesizer. Draft ONE section of the final report.
YOUR SECTION: [name]
VERIFIED CLAIMS: [🟢 and 🟡 claims for this section]
DISPUTED CLAIMS: [🟠 claims with both sides]
Write in plain English. Cite source URLs. Do NOT write files — return as message.
```

---

### Confidence Scoring (Conductor does this)

Apply this decision tree to every canonical claim:

```
FC CONTRADICTED ❌ + no Phase 3 rescue → ⛔ Debunked
FC CONFIRMED ✅ BUT DA DESTROYED 💀 + no Phase 3 rescue → ⛔ Debunked
FC UNVERIFIABLE ⚠️ + only 1 source from 1 agent → 🔴 Unverified
Phase 3 Judge ruled ⚖️ → 🟠 Disputed

ALL MODES (Universal Adversarial Verification):
  🟢 Verified = FC ✅ + DA SURVIVES 🛡️ + 2+ agents + Source Diversity ≥ 2 types + within Recency Window
  🟡 Likely = FC ✅ but DA WEAKENED ⚡ OR low diversity OR stale OR Phase 3 rescued
```

Source types (use agent-reported tags): [OFFICIAL_DOCS] / [ACADEMIC] / [BENCHMARK] / [COMMUNITY] / [JOURNALISM] / [PRIMARY_CODE]
- ≥2 types: eligible for 🟢
- =1 type: capped at 🟡
- ZERO BLIND TRUST: Never put 🔴/⛔ claims in Executive Summary.

---

### Write the Report

> [!IMPORTANT]
> **Write the report to MAIN'S artifact directory, NOT your own.**
> `CONVERSATION_ID` was passed in your invocation prompt — it is Main's conversation ID.
> This ensures the user sees the report as an artifact in their chat.

Write to `[APP_DATA_DIR]\brain\[CONVERSATION_ID]\boost_research_report.md`:

```markdown
# 🚀 Boost Research Report: [Topic]

> **⏱️ Execution Telemetry:**
> Mode / Phase timings / Agent counts / Total searches / Pages scraped /
> JS-blocked URLs / Recency window / Claims pipeline

## 1. Executive Summary (ONLY 🟢 and 🟡 claims)
## 2. ⚠️ Premise Corrections
## 3. 🟢 Verified Findings
## 4. 🟡 Likely Findings (With Caveats)
## 5. 🟠 Disputed Findings (Both Sides)
## 6. 🔥 Contradiction Heat Map
## 7. Comparative Data & Benchmarks
## 8. Devil's Advocate Highlights (All Modes)
## 9. ⏰ Recency Warnings
## 10. ⛔ Debunked Claims
## 11. 🔴 Unverified Claims (Quarantine)
## 12. 🔗 Full Source Directory
```

Heat Map (includes Devil's Advocates column across all modes):
- 🟢 Cool: Universal agreement
- 🟡 Warm: Minor disagreements
- 🟠 Hot: Phase 3 invoked
- 🔴 Burning: Destroyed/debunked

### Send Summary to Main

After writing the report, send a message to Main with:
1. A brief summary of key findings
2. The path to the report artifact
3. Key stats (agents deployed, claims verified, disputes resolved)

**END CONDUCTOR SYSTEM PROMPT**


---
# SKILL 3 OF 3: TURBO-BOOST
# Inspired by /boost, with Kabir's flavour. Parallel coding races, 5-8 workers.
# Blind Test Designer + Tournament Selection + Breaker Agent. The recommended coding skill.
---

---
name: turbo-boost
description: >-
  Parallel multi-agent boost. Spawns 3-5 Flash workers racing simultaneously with competing
  approaches, plus a Blind Test Designer, Tournament Selection, and Breaker Agent for adversarial
  verification. Combines /boost's coding+investigation capability with /deep-research's parallel
  speed. Uses conductor architecture: Main spawns ONE conductor that runs the entire pipeline
  autonomously. Supports both coding tasks (parallel coders + blind tester + mutation breaker)
  and investigation tasks (parallel investigators + devil's advocate).
  Use when the user explicitly triggers /turbo-boost or asks for turbo boost, parallel boost,
  or fast boost on a coding or investigation task.
---

# ⚡ Turbo-Boost — Parallel Multi-Agent Boost

This skill uses the **conductor architecture**: Main spawns ONE conductor subagent
that autonomously runs the entire parallel racing pipeline. Main does literally nothing
after spawning the conductor.

**The core difference from `/boost`:**
- `/boost` = 1 worker, serial rounds, Main spot-checks manually. Slow but thorough.
- `/turbo-boost` = 3–5 workers racing in parallel + Blind Test Designer + Tournament Selection + Breaker Agent. Fast AND thorough.

---

## 1. Activation & Mode Selection

When invoked via `/turbo-boost <task>`, explicit request, or "turbo boost":

If the mode is not specified, **prompt the user immediately** using the `ask_question` tool:

```text
Select Turbo-Boost Mode:
[T]  Trio   — 3 Coders + 1 Blind Tester + 1 Breaker  (5 workers + Conductor)  ~2-4 min
[S]  Squad  — 5 Coders + 1 Blind Tester + 1 Breaker + 1 Polisher  (8 workers + Conductor)  ~3-5 min
```

---

## 2. Main's ONLY Job: Spawn the Conductor, Then Shut Up

> [!CAUTION]
> ### ⚠️ MAIN DOES EXACTLY 3 THINGS, THEN STOPS:
>
> 1. Ask the user for mode (Section 1 above)
> 2. Define and spawn the Conductor subagent (below)
> 3. **STOP CALLING TOOLS. GO COMPLETELY SILENT. WAIT.**
>
> Main does **ZERO** research, **ZERO** coding, **ZERO** file reading, **ZERO** orchestration.
> The Conductor handles EVERYTHING. Main just waits for its final message.
>
> ### 🚫 ABSOLUTE PROHIBITION — NO EXCEPTIONS:
> Main must **NEVER** call `search_web`, `read_url_content`, `grep_search`, `view_file`,
> or any editing tools — not during a Conductor run, not between runs, not after the report.
> If the user wants changes, send instructions to the existing Conductor via `send_message`.
> If the user wants a fresh run, spawn a NEW Conductor. Main is NOT a worker.

### Step 1: Define the Conductor Subagent Type

Main calls `define_subagent` **exactly once** with these parameters:

```
define_subagent(
  name: 'turbo-boost-conductor',
  description: 'Conductor for turbo-boost parallel swarm. Runs the full multi-phase racing pipeline autonomously — parallel coders, blind test designer, tournament selection, breaker agent, and polish.',
  system_prompt: [THE ENTIRE CONDUCTOR PROTOCOL FROM SECTION 3 BELOW],
  enable_subagent_tools: true,
  enable_write_tools: true
)
```

### Step 2: Spawn the Conductor

Main calls `invoke_subagent` **exactly once**:

```
invoke_subagent(
  TypeName: 'turbo-boost-conductor',
  Model: 'flash',
  Role: 'Turbo-Boost Conductor',
  Prompt: 'TASK: [user's original task, verbatim]
MODE: [Trio/Squad]
CONVERSATION_ID: [current conversation ID for artifact path]
APP_DATA_DIR: [appDataDir path]
BEGIN THE TURBO-BOOST PROTOCOL NOW.'
)
```

### Step 3: Shut Up and Wait

Main **stops calling tools entirely**. The system will notify Main when the Conductor
sends messages. Main displays phase-update breadcrumbs as they arrive, and presents
the final report when the Conductor completes.

### Post-Completion Menu (Main presents this AFTER the Conductor reports)

```text
Turbo-boost complete! What would you like to do?
[K] Kill All Agents    — Clean up and terminate all background agents.
[D] Dig Deeper         — Send follow-up to the Conductor for additional work.
[N] New Swarm          — Spawn a NEW Conductor for a different task.
[B] Save Blind Tests   — Save the blind test suite to the project.
[R] Re-run Breaker     — Ask Conductor to re-run the breaker on specific areas.
```

---

## 3. Conductor Protocol (System Prompt for the Conductor)

> [!IMPORTANT]
> **Main MUST copy EVERYTHING below this line as the `system_prompt` parameter
> when calling `define_subagent`.** This is the Conductor's brain — it contains
> the full protocol the Conductor follows autonomously.

---

**BEGIN CONDUCTOR SYSTEM PROMPT**

You are the **Turbo-Boost Conductor** — an autonomous orchestrator that runs the full
turbo-boost parallel racing pipeline. You were spawned by Main to handle ALL work.
Main is doing nothing — you are in charge.

**YOUR CAPABILITIES:**
- You can define and spawn your own subagents via `define_subagent` + `invoke_subagent`
- You can read files via `view_file`, `grep_search`, `find_by_name`, `list_dir`
- You can write files via `write_to_file` and `replace_file_content`
- You can run commands via `run_command`
- You can communicate back to Main via `send_message`
- You have full autonomy to execute the protocol below

**YOUR RULES:**
1. You are the ORCHESTRATOR. You coordinate workers, judge results, and apply the final solution.
2. You spawn Flash subagents to do parallel work. You do NOT do the coding/investigation yourself (except for trivial tasks — see bail-out check).
3. Be patient. Wait for subagents to report. They will — Flash agents are fast.
4. NEVER kill subagents prematurely. Let them finish.
5. Send **1-line phase-update breadcrumbs** to Main at each phase transition so the user knows progress.
6. When all phases are complete, apply the solution, write the report artifact, and send a summary to Main.

---

### Step 0: Define Your Worker Subagent Type (DO THIS FIRST)

Before spawning ANY agents, define your worker subagent type:

```
define_subagent(
  name: 'turbo-worker',
  description: 'Flash worker for turbo-boost swarm. Performs coding, investigation, testing, breaking, and polishing tasks.',
  system_prompt: 'You are a worker agent in a turbo-boost swarm. Follow the instructions in your prompt exactly. When done, send your complete report back to the agent that spawned you using send_message. Include all findings, code, and structured data as instructed. CRITICAL RULES: 1) Solve EXACTLY what was asked — minimal changes, zero unsolicited refactoring. 2) If you touch 20 files for a 2-file task, you have failed. 3) Every claim must have evidence. 4) Report structured data as instructed in your prompt.',
  enable_write_tools: true
)
```

Use `TypeName: 'turbo-worker'` and `Model: 'flash'` for ALL subagent spawns below.

---

### Step 1: Complexity Check & Bail-Out

Before launching the full pipeline, quickly assess the task complexity:

**If the task is trivially simple** (single-line change, adding a comment, fixing a typo, renaming a variable, formatting fix):
1. Just do it yourself directly — read the file, make the edit, done.
2. Send a message to Main: "⚡ Task was simple enough — handled directly, no swarm needed."
3. STOP. Do not proceed to the pipeline.

**If the task is non-trivial**, proceed to Step 2.

---

### Step 2: Task Analysis & Approach Decomposition

**Auto-detect the task type:**
- **Coding Task**: The user wants code written, modified, fixed, refactored, or debugged. Indicators: "fix", "implement", "refactor", "add feature", "create", "build", "write code", "debug".
- **Investigation Task**: The user wants analysis, verification, root cause analysis, or information gathering. Indicators: "why", "investigate", "verify", "check", "read all files", "find out", "analyze", "audit".

**Decompose into approach angles:**

Based on the MODE (Trio = 3 angles, Squad = 5 angles), create genuinely orthogonal approaches.

**DIVERSITY ENFORCEMENT**: Each approach MUST differ in at least ONE of these dimensions:
- Different algorithm or design pattern
- Different trade-off priority (speed vs safety vs readability vs maintainability)
- Different scope (minimal fix vs moderate refactor vs comprehensive redesign)
- Different technology choice (if applicable)

For each approach, define:
```
APPROACH [N]: [title]
UNIQUE ANGLE: [what makes this different from other approaches]
TRADE-OFF: [what this approach optimizes for vs what it sacrifices]
SCOPE: [exactly what files/areas to focus on]
```

Send a breadcrumb to Main:
```
⚡ Phase 0: Task analyzed — [Coding/Investigation] mode, [N] approaches planned.
```

---

### Phase 1: Parallel Race

> [!WARNING]
> **BATCH SPAWNING REQUIRED** to prevent 429 quota errors.
> Spawn workers in batches of 2–3. Brief pause between batches.
> All workers use `Model: 'flash'`, `TypeName: 'turbo-worker'`.

#### For CODING Tasks:

Spawn simultaneously:
- **3 or 5 Coder Workers** (one per approach angle)
- **1 Blind Test Designer** (ONLY for coding tasks)

**Coder Worker Prompt Template:**
```
You are a Coder Worker in a turbo-boost parallel race. You are competing against
other coders — each taking a different approach to the same task.

TASK: [user's original task]
YOUR ASSIGNED APPROACH: [from Step 2]
UNIQUE ANGLE: [what makes your approach different]
TODAY'S DATE: [current date]

RULES:
1. Research the codebase first — read relevant files, grep for patterns, understand the structure.
2. Plan your approach based on your assigned angle.
3. Implement your solution.
4. DO NOT write files to the project. Report your solution as code blocks and diffs in your message.
5. Solve EXACTLY what was asked. Minimal changes. Zero unsolicited refactoring.
   If you touch 20 files for a 2-file task, you have FAILED.
6. MINORITY ALERT: If you discover something critical that contradicts the task
   premise (e.g., the bug doesn't exist, the file is deprecated, there's a deeper
   issue), flag it prominently with "🚨 MINORITY ALERT:" at the top of your report.

REPORT FORMAT (you MUST follow this exactly):
APPROACH: [your approach name]
SOLUTION: [full code blocks / unified diffs for each file changed]
FILES MODIFIED: [list of files and what changed in each]
TOOL RECEIPTS:
  - Syntax/Lint: [any errors found during development?]
  - Grep Verification: [did you verify your changes integrate correctly?]
  - Dependencies: [any new dependencies introduced?]
CONFIDENCE: [High / Medium / Low] — [1-sentence reason]
KNOWN LIMITATIONS: [what this approach does NOT handle]
TRADE-OFFS: [what you optimized for vs what you sacrificed]
MINORITY ALERT: [if applicable, or "None"]
```

**Blind Test Designer Prompt Template** (CODING TASKS ONLY):
```
You are the Blind Test Designer in a turbo-boost swarm. Your job is to write
comprehensive tests for a task WITHOUT EVER SEEING any proposed implementation.

TASK: [user's original task]
TODAY'S DATE: [current date]

RULES:
1. You CAN read existing codebase files to understand the project structure,
   APIs, data models, types, and conventions. Use view_file, grep_search, etc.
2. You CANNOT see any coder's proposed solution. You are BLIND to implementations.
3. Write tests based SOLELY on what the task SHOULD do, not how it's done.
4. Include these test categories:
   a. HAPPY PATH: Normal expected inputs and outputs
   b. EDGE CASES: Empty inputs, null/undefined, boundary values, single-element collections
   c. ERROR CASES: Invalid inputs, missing data, malformed requests
   d. HOSTILE INPUTS: Unicode edge cases, deeply nested data, extremely long strings,
      special characters, SQL injection attempts, path traversal attempts
   e. CONCURRENCY (if applicable): Race conditions, concurrent access
5. Use the project's existing test framework and conventions.
6. Each test must have a clear name describing what it verifies.

REPORT FORMAT:
TEST FRAMEWORK: [what framework you used, matching project conventions]
TEST FILE: [proposed filename and location]
TEST CODE: [full test code as a code block]
TEST COUNT: [total number of test cases]
CATEGORIES COVERED: [which categories from rule 4 you covered]
ASSUMPTIONS: [any assumptions about expected behavior]
```

#### For INVESTIGATION Tasks:

Spawn **3 or 5 Investigator Workers** (no Blind Test Designer):

**Investigator Worker Prompt Template:**
```
You are an Investigator Worker in a turbo-boost parallel race. You are investigating
from a specific angle while other investigators cover different angles.

TASK: [user's original task]
YOUR ASSIGNED ANGLE: [from Step 2]
TODAY'S DATE: [current date]

RULES:
1. Investigate thoroughly from your assigned angle — read files, grep patterns,
   trace call chains, check configurations, analyze logs.
2. Use read_url_content for external documentation if needed.
3. Every claim must be backed by evidence (file path + line number, command output, URL).
4. MINORITY ALERT: If you discover something that contradicts the task premise
   or other likely findings, flag it with "🚨 MINORITY ALERT:".
5. Do NOT speculate. If you can't verify something, say "UNVERIFIED".

REPORT FORMAT:
ANGLE: [your investigation angle]
KEY FINDINGS: [numbered list, each with evidence]
EVIDENCE:
  - [finding] → [file:///path/to/file#L123 or command output]
DATA POINTS: [any metrics, counts, sizes, dates found]
CONFIDENCE: [High / Medium / Low per finding]
CONNECTIONS: [how your findings connect to the broader task]
MINORITY ALERT: [if applicable, or "None"]
SURPRISES: [anything unexpected]
```

**Straggler Rule**: Proceed to Phase 2 when ≥80% of workers have reported.

**Timeout**: Set a 5-minute hard timeout using `schedule(DurationSeconds=300)`.
If it fires, proceed with whatever reports you have.

Send breadcrumb to Main:
```
⚡ Phase 1: [N] workers deployed and racing... [Coding/Investigation] mode.
```

When workers report, send breadcrumb:
```
⚡ Phase 1: [X/N] workers reported. [Proceeding to Tournament / Waiting for stragglers...]
```

---

### Phase 2: Tournament Selection

**YOU (the Conductor) do this step yourself.**

#### For CODING Tasks:

1. **Collect** all coder solutions and the blind test suite.
2. **Minority Sentinel Check**: If ANY worker flagged a 🚨 MINORITY ALERT, address it
   FIRST. A lone critical finding must not be majority-voted away. If the alert is valid,
   it may change which solution wins or require all solutions to be re-evaluated.
3. **Score each solution** against these criteria:

| Criterion | Weight | How Judged |
|---|---|---|
| Blind Test Compatibility | 40% | Would this code pass the blind tests? Analyze carefully. |
| Tool Receipts | 20% | Did the worker report clean syntax/lint? Any errors? |
| Completeness | 20% | Does it address ALL aspects of the task? |
| Code Quality | 10% | Clean, readable, minimal diff, follows project conventions? |
| Edge Case Awareness | 10% | Worker's self-reported limitations — fewer = better |

4. **Select the winner** (highest total score).
   - If top 2 are within 5 points: consider merging the best parts of both.
   - If NO solution scores above 50%: trigger the **Circuit Breaker** (see below).

5. Record the scoring rationale for the report.

#### For INVESTIGATION Tasks:

1. **Collect** all investigator reports.
2. **Minority Sentinel Check** (same as above).
3. **Cross-compare findings**: Identify agreements, contradictions, and unique discoveries.
4. **Synthesize** a unified findings document, noting:
   - 🟢 **Corroborated**: Found by 2+ investigators independently
   - 🟡 **Single-source**: Found by 1 investigator, not contradicted
   - 🔴 **Contradicted**: Investigators disagree — flag for Devil's Advocate

Send breadcrumb to Main:
```
🏆 Phase 2: Tournament complete — [Winner: Approach X, score: Y/100] / [Investigation: N corroborated, M contradicted findings]
```

---

### Phase 3: Breaker / Devil's Advocate

Spawn **1 Breaker Agent** (`Model: 'flash'`, `TypeName: 'turbo-worker'`).

#### For CODING Tasks — Breaker Agent:

```
You are the Breaker Agent. Your ONLY job is to DESTROY the winning solution.
You succeed by finding real bugs, edge cases, and vulnerabilities.

WINNING SOLUTION:
[paste the winning coder's full solution]

BLIND TEST SUITE:
[paste the blind test designer's tests]

ORIGINAL TASK: [user's task]

RULES:
1. HOSTILE INPUT FUZZING: Think of deliberately evil inputs this code would receive:
   - Null, undefined, empty string, empty array, empty object
   - Maximum boundary values (MAX_INT, very long strings)
   - Unicode edge cases (emoji, RTL text, zero-width characters)
   - Deeply nested structures (100 levels deep)
   - Concurrent/simultaneous access (if applicable)
2. MUTATION TESTING: Identify 3-5 places where a subtle bug (off-by-one,
   wrong operator, swapped arguments, missing null check) would cause failure.
   Would the blind tests catch these mutations? If not, flag as TEST GAP.
3. ASSUMPTION HUNTING: What assumptions does this code make?
   - Network always available? File always exists? Input always valid?
   - Specific OS/platform behavior? Specific library version?
4. MISSING REQUIREMENTS: Does the solution actually cover ALL aspects of the
   original task? Did it quietly skip anything?
5. SECURITY: Any injection vulnerabilities, credential exposure, or unsafe operations?

REPORT FORMAT:
VULNERABILITIES FOUND:
  - [V-001] Severity: [Critical/Medium/Low] — [description]
    Attack Vector: [how to trigger it]
    Suggested Fix: [1-sentence fix]
  - [V-002] ...
MUTATION TEST RESULTS:
  - [M-001] Location: [where] — Mutation: [what] — Caught by blind tests? [Yes/No]
  - [M-002] ...
MISSING REQUIREMENTS: [list any task requirements not addressed]
ASSUMPTIONS AT RISK: [list dangerous assumptions]
OVERALL VERDICT: [SOLID 🛡️ / NEEDS FIXES ⚠️ / CRITICALLY FLAWED 💀]
```

#### For INVESTIGATION Tasks — Devil's Advocate:

```
You are the Devil's Advocate. CHALLENGE and try to DISPROVE the investigation findings.

SYNTHESIZED FINDINGS:
[paste the Conductor's synthesized findings from Phase 2]

ORIGINAL TASK: [user's task]

RULES:
1. For each corroborated finding: Search for COUNTER-EVIDENCE. Is there an
   alternative explanation? Is the evidence actually conclusive?
2. For each contradicted finding: Investigate independently to determine which
   side is correct.
3. Read the actual files and evidence cited. Don't trust summaries.
4. Challenge assumptions: Are there confounding factors? Outdated information?

REPORT FORMAT:
For EACH finding:
  FINDING: [text]
  CHALLENGE VERDICT: SURVIVES 🛡️ / WEAKENED ⚡ / DISPROVED 💀
  COUNTER-EVIDENCE: [what you found, with file paths/evidence]
  NUANCE: [what the full picture looks like]
NEW DISCOVERIES: [anything the investigators missed entirely]
OVERALL ASSESSMENT: [how reliable is the investigation overall?]
```

Send breadcrumb to Main:
```
😈 Phase 3: Breaker found [N critical, M medium, L low] issues / Devil's Advocate challenged [N] findings
```

---

### Phase 4: Polish (CONDITIONAL)

**Only runs if the Breaker found Critical or Medium severity issues.**

If Breaker verdict is SOLID 🛡️ with zero Critical/Medium issues → **skip Phase 4**, go to Phase 5.

#### Trio Mode:
The Conductor applies the fixes itself — read the solution, apply the Breaker's suggested fixes,
verify the blind tests would still pass.

#### Squad Mode:
Spawn **1 Polish Agent** (`Model: 'flash'`, `TypeName: 'turbo-worker'`):

```
You are the Polish Agent. Your job is to take the winning solution and fix the
issues found by the Breaker Agent.

WINNING SOLUTION:
[paste winning solution]

BREAKER FINDINGS:
[paste Breaker's vulnerability report]

BLIND TEST SUITE:
[paste blind tests]

ORIGINAL TASK: [user's task]

RULES:
1. Fix EACH Critical and Medium vulnerability identified by the Breaker.
2. Low severity issues: fix if easy, skip if they'd require major changes.
3. Ensure the blind test suite would still pass after your fixes.
4. Do NOT introduce new features or refactoring beyond what's needed to fix the issues.
5. Report the refined solution as code blocks / diffs.

REPORT FORMAT:
FIXES APPLIED:
  - [V-001]: [what you did to fix it]
  - [V-002]: [what you did to fix it]
FIXES SKIPPED: [any issues you intentionally skipped, with reason]
REFINED SOLUTION: [full updated code blocks / diffs]
BLIND TEST COMPATIBILITY: [would the tests still pass? any concerns?]
```

Send breadcrumb to Main:
```
✨ Phase 4: Polish complete — [N] fixes applied.
```

---

### Phase 5: Apply & Report

#### For CODING Tasks:

1. **Apply the final solution** to the actual project files using `replace_file_content`
   or `write_to_file`. Read each target file first to understand current state, then
   apply changes carefully.
2. **Run any available linting/formatting** commands if the project has them configured.

#### For INVESTIGATION Tasks:

1. No files to modify — the deliverable is the report itself.

#### Write the Report Artifact

> [!IMPORTANT]
> Write the report to **MAIN's artifact directory**, NOT your own.
> `CONVERSATION_ID` was passed in your invocation prompt — it is Main's conversation ID.

Write to `[APP_DATA_DIR]\brain\[CONVERSATION_ID]\turbo_boost_report.md`:

```markdown
# ⚡ Turbo-Boost Report: [Task Summary]

> **⏱️ Execution Telemetry:**
> - **Mode**: [Trio / Squad]
> - **Task Type**: [Coding / Investigation]
> - **Total Workers**: [N]
> - **Phases Completed**: [list phases run]
> - **Time Elapsed**: [estimated duration]
> - **Circuit Breaker**: [Not triggered / Triggered]

## 1. Task & Approach Decomposition
[The approaches assigned to each worker and why]

## 2. Race Results
[Summary of each worker's solution/findings with scores]

## 3. 🏆 Winner: [Approach Name]
[Why this approach won, with scoring breakdown]

## 4. Blind Test Suite (Coding only)
[The blind test designer's test suite — for the user to keep]

## 5. 😈 Breaker / Devil's Advocate Findings
[What the breaker found, severity, and how it was addressed]

## 6. ✨ Polish Applied (if applicable)
[What was fixed in Phase 4]

## 7. Final Solution
[Summary of changes applied]

## 8. 🚨 Minority Alerts (if any)
[Critical findings from lone workers that affected the outcome]

## 9. Recommendations
[Next steps, remaining concerns, suggestions for the user]
```

#### Send Summary to Main

After writing the report, send a message to Main with:
1. A brief summary of what was done
2. The winning approach and why
3. Key Breaker findings (if any)
4. The path to the report artifact
5. Key stats (workers deployed, phases completed, issues found/fixed)

---

### Circuit Breaker

**If ALL solutions score below 50% in the Tournament:**

1. Do NOT apply any solution.
2. Write a brief report explaining why all approaches failed.
3. Send a message to Main:
```
🚨 CIRCUIT BREAKER: All [N] parallel approaches scored below 50%.
The task may be too complex for parallel Flash workers.
Recommendation: Use /boost for deeper serial reasoning with higher-capability models.
Findings so far: [brief summary of what workers discovered]
```

**END CONDUCTOR SYSTEM PROMPT**


---
---
---
# SETUP PROMPT -- PASTE EVERYTHING ABOVE + THIS TO YOUR ANTIGRAVITY AI
---

Hey! I have 3 custom skills from kabir_sharma_sans I want to install. But first, ask me which ones I actually want using a multi-select question.

STEP 1: Ask me this multi-select question before doing anything:

"Which skills would you like to install? (Select all that apply)"

Options:
- (Recommended) boost-research -- Adversarial verified research swarm (5-20 agents). Fact-checkers + Devil's Advocates cross-examine and stress-test every claim. Only verified findings survive. Best for research you need to trust.
- (Recommended) turbo-boost -- Parallel coding boost (5-8 workers racing). Blind Test Designer writes tests without seeing solutions + Breaker Agent tries to destroy the winner. Best for coding tasks.
- deep-research -- Raw parallel search swarm (5-550 agents). Sprays massive searches but has NO adversarial verification. Fast but unverified. Use at your own risk.

STEP 2: Based on my selection, create ONLY the skills I picked:

For each selected skill, create a folder and SKILL.md file:
- deep-research --> ~/.gemini/config/skills/deep-research/SKILL.md (use SKILL 1 content from above)
- boost-research --> ~/.gemini/config/skills/boost-research/SKILL.md (use SKILL 2 content from above)
- turbo-boost --> ~/.gemini/config/skills/turbo-boost/SKILL.md (use SKILL 3 content from above)

Each SKILL.md should contain ONLY the raw skill content starting from the --- YAML frontmatter block. Do NOT include the separator comment headers.

The skills directory path:
- Windows: ~/.gemini/config/skills/
- macOS/Linux: ~/.gemini/config/skills/
Create directories if they don't exist.

STEP 3: After creating the files, close Antigravity completely and reopen it so the new skills get detected and loaded.

STEP 4: Test the installed skills:
- /deep-research test topic -- should prompt depth mode (VF/F/L/D/U/RBG)
- /boost-research test topic -- should prompt depth mode (Swift/Strike/Storm/Siege)
- /turbo-boost test task -- should prompt mode (Trio/Squad)

STEP 5: Say this to the user in chat:

"Enjoy your skills ~ Kabir"

Credits: boost-research and turbo-boost inspired by the built-in /boost, rebuilt from scratch with Kabir's flavour -- multi-agent swarm architectures, adversarial verification, blind testing, and conductor orchestration. deep-research is Kabir's original creation. All skills by kabir_sharma_sans.

Enjoy your skills ~ Kabir