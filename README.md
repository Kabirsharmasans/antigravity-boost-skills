# :rocket: Antigravity Boost Skills Pack

Custom multi-agent swarm skills for **Google Antigravity (AGY)** by **kabir_sharma_sans**.

---

## :zap: What is Google Antigravity?

**Google Antigravity** is an agentic AI development platform designed to build, test, and deploy autonomous workflows, multi-agent systems, and coding tools.

### :inbox_tray: Downloads & Installation

| Platform | Install |
|----------|---------|
| :desktop_computer: **Antigravity 2.0** (v2.14.0) | Standalone installer for Windows (x64 / ARM64), macOS, and Linux |
| :keyboard: **CLI** (v1.2.0) | PowerShell: `irm https://antigravity.google/cli/install.ps1 \| iex` |
| :brain: **Antigravity IDE** (v2.5.5) | Dedicated desktop workspace with native agent execution panels |
| :snake: **Python SDK** (v0.1.16) | Library to configure and orchestrate agents, optimized for Gemini |

### :link: Supported IDE Integrations

- :blue_circle: **Visual Studio Code** -- Autonomous coding agent, inline completions, diff reviews
- :purple_circle: **Visual Studio 2026** (Preview) -- Multi-file code editing and tool execution
- :orange_circle: **JetBrains** (Preview) -- IntelliJ IDEA, PyCharm, WebStorm, GoLand, CLion, Rider
- :yellow_circle: **Zed** (Preview) -- High-performance orchestration and native multibuffer editing
- :white_circle: **Xcode** (Preview) -- Agentic dev for macOS, iOS, iPadOS, watchOS, visionOS

---

## :star2: Skills Included

| Skill | Agents | Type | Recommended? | Description |
|-------|--------|------|:---:|-------------|
| :shield: **boost-research** | 5-20 | Research | :white_check_mark: **YES** | Adversarial verified research. Fact-Checkers + Devil's Advocates cross-examine every claim. |
| :zap: **turbo-boost** | 5-8 | Coding | :white_check_mark: **YES** | Parallel coding races + Blind Test Designer + Breaker Agent. |
| :cyclone: **deep-research** | 5-550 | Research | :x: No | Raw parallel swarm. Massive firepower, zero verification. Use at own risk. |

### :trophy: Recommended Skills

> [!TIP]
> **turbo-boost** and **boost-research** are the two recommended skills. They both use adversarial verification -- agents actively try to BREAK and DISPROVE results before they reach you.

:zap: **turbo-boost (Parallel Coding Races)** -- Best for coding tasks. Spawns 3-5 coders racing simultaneously with genuinely different approaches. A Blind Test Designer writes tests WITHOUT ever seeing any solution. Tournament Selection picks the winner. A Breaker Agent runs hostile input fuzzing and mutation testing to destroy it. If critical issues found, a Polish Agent fixes them. Circuit breaker aborts if all approaches fail.

:shield: **boost-research (Adversarial Verified Research)** -- Best for research you need to trust. A Strategist decomposes your topic into non-overlapping angles. Parallel researchers flood searches. Fact-Checkers independently verify every claim. Devil's Advocates actively try to DISPROVE confirmed claims. Disputed claims go to a Pro/Con court with Judges. Only claims surviving cross-examination make the report. Zero blind trust.

---

## :sparkles: Install Methods

### :star: Method 1: One-Liner (Easiest -- Let Your AI Do Everything)

> [!IMPORTANT]
> **This is the recommended way.** Just paste this one line into your Antigravity chat and your AI handles everything:

```
Read this file and follow the setup instructions inside it: https://raw.githubusercontent.com/Kabirsharmasans/antigravity-boost-skills/master/share_my_skills.md
```

That's it. Your AI will:
1. Read the file from GitHub
2. Ask you which skills you want to install (multi-select)
3. Create the skill files in your config
4. Tell you to restart Antigravity

> [!NOTE]
> This works because Antigravity can read URLs directly. No copy-pasting walls of text needed.

---

### :page_facing_up: Method 2: Copy-Paste Prompt

1. Open [share_my_skills.md](share_my_skills.md) in this repo
2. Copy the **entire file content**
3. Paste it into your Antigravity chat
4. Your AI asks which skills you want, then sets them up

---

### :wrench: Method 3: Manual Install

#### Step 1: Locate your config directory

| OS | Skills Path |
|----|-------------|
| :window: **Windows** | `C:\Users\<YourUsername>\.gemini\config\skills\` |
| :apple: **macOS** | `/Users/<YourUsername>/.gemini/config/skills/` |
| :penguin: **Linux** | `/home/<YourUsername>/.gemini/config/skills/` |

Create it if it doesn't exist:

**Windows (PowerShell):**
```
New-Item -ItemType Directory -Path "$env:USERPROFILE\.gemini\config\skills" -Force
```

**macOS / Linux:**
```
mkdir -p ~/.gemini/config/skills
```

#### Step 2: Clone & copy

```
git clone https://github.com/Kabirsharmasans/antigravity-boost-skills.git
```

**Windows (PowerShell):**
```
Copy-Item -Recurse "antigravity-boost-skills\boost-research" "$env:USERPROFILE\.gemini\config\skills\"
Copy-Item -Recurse "antigravity-boost-skills\turbo-boost" "$env:USERPROFILE\.gemini\config\skills\"
```

**macOS / Linux:**
```
cp -r antigravity-boost-skills/boost-research ~/.gemini/config/skills/
cp -r antigravity-boost-skills/turbo-boost ~/.gemini/config/skills/
```

Your final structure:
```
~/.gemini/config/skills/
  boost-research/
    SKILL.md          <-- Adversarial verified research
  turbo-boost/
    SKILL.md          <-- Parallel coding races
  deep-research/      <-- (optional, not recommended)
    SKILL.md
```

#### Step 3: Restart

Close Antigravity completely and reopen it.

#### Step 4: Test

- `/boost-research test topic` -- prompts: Swift / Strike / Storm / Siege
- `/turbo-boost test task` -- prompts: Trio / Squad
- `/deep-research test topic` -- prompts: VF / F / L / D / U / RBG

---

## :gear: How They Work

### :shield: boost-research (Adversarial Verified Research)
| Phase | What Happens |
|-------|-------------|
| **Phase 0** | :dart: Strategist decomposes topic into non-overlapping angles |
| **Phase 1** | :mag: Parallel researchers flood searches from every angle |
| **Phase 2a** | :white_check_mark: Fact-Checkers independently verify every claim |
| **Phase 2b** | :smiling_imp: Devil's Advocates try to DESTROY confirmed claims |
| **Phase 3** | :balance_scale: Pro/Con dispute court with independent Judges |
| **Output** | :page_facing_up: Only verified claims survive. Confidence: Verified / Likely / Disputed / Debunked |

### :zap: turbo-boost (Parallel Coding Races)
| Phase | What Happens |
|-------|-------------|
| **Step 0** | :thinking: Complexity check -- trivial tasks handled directly |
| **Phase 1** | :running_man: 3-5 coders race with different approaches + Blind Test Designer |
| **Phase 2** | :trophy: Tournament Selection scores solutions (blind tests 40%, receipts 20%, completeness 20%, quality 10%, edges 10%) |
| **Phase 3** | :skull: Breaker Agent runs hostile fuzzing + mutation testing |
| **Phase 4** | :sparkles: Polish Agent fixes vulnerabilities (if any) |
| **Phase 5** | :white_check_mark: Final solution applied + report generated |

### :cyclone: deep-research (Raw Parallel Swarm)
| Feature | Detail |
|---------|--------|
| **Modes** | Very Fast (5) / Fast (4) / Lite (9) / Deeper (16) / Ultra (36) / RBG (550) |
| **Timeout** | 2-minute hard safety net |
| **Verification** | 102% overthink on individual findings (no cross-agent verification) |
| **Scraping** | Mandatory full-page (no lazy snippets) |

---

## :handshake: Credits

- :shield: **boost-research** and :zap: **turbo-boost**: Inspired by the built-in /boost, with Kabir's flavour
- :cyclone: **deep-research**: Kabir's original creation

Made with :heart: by **kabir_sharma_sans**

**Enjoy your skills ~ Kabir**