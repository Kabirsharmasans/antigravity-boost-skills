# Antigravity Boost Skills Pack

Custom multi-agent swarm skills for **Google Antigravity (AGY)** by **kabir_sharma_sans**.

---

## What is Google Antigravity?

**Google Antigravity** is an agentic AI development platform designed to build, test, and deploy autonomous workflows, multi-agent systems, and coding tools.

### Downloads & Installation

- **Antigravity 2.0 (v2.14.0)**: Standalone installer for Windows (x64 / ARM64; requires Windows 10 64-bit or later), macOS, and Linux.
- **CLI (v1.2.0)**:
  - PowerShell:
    ```
    irm https://antigravity.google/cli/install.ps1 | iex
    ```
  - Windows CMD:
    ```
    curl -fsSL https://antigravity.google/cli/install.cmd -o install.cmd && install.cmd && del install.cmd
    ```
- **Antigravity IDE (Standalone v2.5.5)**: Dedicated desktop workspace with native windowing and agent execution panels (x64 / ARM64).
- **Python SDK (v0.1.16)**: Library to configure and orchestrate agents, optimized for Gemini models.

### Supported IDE Integrations

- **Visual Studio Code**: Autonomous coding agent, inline completions, and diff reviews.
- **Visual Studio 2026 (Preview)**: Multi-file code editing and tool execution.
- **JetBrains (Preview)**: IntelliJ IDEA, PyCharm, WebStorm, GoLand, CLion, Rider.
- **Zed (Preview)**: High-performance orchestration and native multibuffer editing.
- **Xcode (Preview)**: Agentic development for macOS, iOS, iPadOS, watchOS, and visionOS.

---

## Skills Included

| Skill | Agents | Type | Recommended? | Description |
|-------|--------|------|:---:|-------------|
| **boost-research** | 5-20 | Research | Yes | Adversarial verified research swarm. Fact-Checkers + Devil's Advocates cross-examine every claim. Only verified findings survive. |
| **turbo-boost** | 5-8 | Coding | Yes | Parallel coding races with Blind Test Designer + Breaker Agent. Multiple coders race, then adversarial testing destroys weak solutions. |
| **deep-research** | 5-550 | Research | No | Raw parallel search swarm. Massive firepower but no adversarial verification. Use at your own risk. |

### Recommended Skills

**turbo-boost (Parallel Coding Races)** -- Best for coding tasks. Spawns 3-5 coders racing simultaneously with genuinely different approaches (different algorithms, trade-offs, scope). A Blind Test Designer writes comprehensive tests WITHOUT ever seeing any solution. Tournament Selection picks the winner. Then a Breaker Agent runs hostile input fuzzing and mutation testing to try to destroy it. If the Breaker finds critical issues, a Polish Agent fixes them. Includes a circuit breaker that aborts if all approaches score below 50%.

**boost-research (Adversarial Verified Research)** -- Best for research you need to trust. A Strategist decomposes your topic into non-overlapping angles. Parallel researchers flood searches from every angle with mandatory full-page scraping. Then Fact-Checkers independently verify every claim with fresh searches. Then Devil's Advocates actively try to DISPROVE confirmed claims by finding counter-evidence. Disputed claims go to a Pro/Con court with independent Judges. Claims survive ONLY if independently corroborated by 2+ sources across agents. Zero blind trust.

---

## Quick Install (One-Shot Prompt)

1. Open `share_my_skills.md` in this repo
2. Copy the **entire file content**
3. Paste it into your Antigravity chat
4. Your AI will ask which skills you want to install, create the files, and set everything up automatically

---

## Manual Install

### Step 1: Locate your Antigravity config directory

The skills directory lives inside your Antigravity global config:

| OS | Path |
|----|------|
| **Windows** | `C:\Users\<YourUsername>\.gemini\config\skills\` |
| **macOS** | `/Users/<YourUsername>/.gemini/config/skills/` |
| **Linux** | `/home/<YourUsername>/.gemini/config/skills/` |

If the `skills` folder does not exist yet, create it:

- **Windows (PowerShell)**:
  ```
  New-Item -ItemType Directory -Path "C:\Users\Kabir\.gemini\config\skills" -Force
  ```
- **macOS / Linux**:
  ```
  mkdir -p ~/.gemini/config/skills
  ```

### Step 2: Copy the skill folders

Clone this repo or download the ZIP, then copy the skill folders you want into your config:

```
git clone https://github.com/Kabirsharmasans/antigravity-boost-skills.git
```

Then copy whichever skills you want:

- **Windows (PowerShell)**:
  ```
  Copy-Item -Recurse "antigravity-boost-skills\boost-research" "C:\Users\Kabir\.gemini\config\skills\"
  Copy-Item -Recurse "antigravity-boost-skills\turbo-boost" "C:\Users\Kabir\.gemini\config\skills\"
  ```

- **macOS / Linux**:
  ```
  cp -r antigravity-boost-skills/boost-research ~/.gemini/config/skills/
  cp -r antigravity-boost-skills/turbo-boost ~/.gemini/config/skills/
  ```

Your final directory structure should look like this:

```
~/.gemini/config/skills/
  boost-research/
    SKILL.md
  turbo-boost/
    SKILL.md
  deep-research/        (optional, not recommended)
    SKILL.md
```

### Step 3: Restart Antigravity

Close Antigravity completely and reopen it so the new skills get detected and loaded.

### Step 4: Test

Type any of these in your Antigravity chat to verify they work:

- `/boost-research test topic` -- should ask you to pick a depth mode (Swift / Strike / Storm / Siege)
- `/turbo-boost test task` -- should ask you to pick a mode (Trio / Squad)
- `/deep-research test topic` -- should ask you to pick a depth mode (VF / F / L / D / U / RBG)

---

## How They Work

### boost-research (Adversarial Verified Research)
- **Phase 0**: Strategist decomposes topic into non-overlapping research angles
- **Phase 1**: Parallel researchers flood searches from every angle (mandatory full-page scraping)
- **Phase 2a**: Fact-Checkers independently verify every claim with fresh searches
- **Phase 2b**: Devil's Advocates try to DESTROY confirmed claims with counter-evidence
- **Phase 3**: Pro/Con dispute court with independent Judges for contested claims
- Only claims surviving cross-examination make the final report
- Confidence scoring: Verified / Likely / Disputed / Debunked / Unverified

### turbo-boost (Parallel Coding Races)
- **Step 1**: Complexity check (trivial tasks handled directly, no swarm needed)
- **Phase 1**: 3-5 coders race simultaneously with genuinely different approaches + Blind Test Designer
- **Phase 2**: Tournament Selection scores solutions (blind test compatibility 40%, tool receipts 20%, completeness 20%, code quality 10%, edge cases 10%)
- **Phase 3**: Breaker Agent runs hostile input fuzzing + mutation testing on the winner
- **Phase 4**: Polish Agent fixes critical/medium vulnerabilities (if any found)
- **Phase 5**: Final solution applied to project files + report generated
- Circuit breaker aborts if all approaches score below 50%

### deep-research (Raw Parallel Swarm)
- 6 depth modes from Very Fast (5 agents) to Random Bullshit Go (550 agents)
- 2-minute hard timeout safety net
- 102% overthink verification on individual findings
- Mandatory full-page scraping (no lazy snippets)
- No adversarial cross-verification between agents

---

## Credits

- **boost-research** and **turbo-boost**: Inspired by the built-in /boost, with Kabir's flavour
- **deep-research**: Kabir's original creation

Made by **kabir_sharma_sans**

Enjoy your skills ~ Kabir