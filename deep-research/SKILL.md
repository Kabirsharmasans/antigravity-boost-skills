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
