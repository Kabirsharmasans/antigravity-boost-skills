# Antigravity Boost Skills Pack

Custom multi-agent swarm skills for [Google Antigravity (AGY)](https://github.com/google/antigravity) by **kabir_sharma_sans**.

## Skills Included

| Skill | Agents | Type | Description |
|-------|--------|------|-------------|
| **boost-research** | 5-20 | Research | Adversarial verified research swarm. Fact-Checkers + Devil's Advocates cross-examine every claim. Only verified findings survive. **(Recommended)** |
| **turbo-boost** | 5-8 | Coding | Parallel coding races with Blind Test Designer + Breaker Agent. Multiple coders race, then adversarial testing destroys weak solutions. **(Recommended)** |
| **deep-research** | 5-550 | Research | Raw parallel search swarm. Massive firepower but no adversarial verification. Use at your own risk. |

## Quick Install (One-Shot Prompt)

1. Open `share_my_skills.md` in this repo
2. Copy the **entire file content**
3. Paste it into your Antigravity chat
4. Your AI will ask which skills you want, create the files, and set everything up

## Manual Install

Copy the skill folders you want into your Antigravity config:

`
~/.gemini/config/skills/
  boost-research/
    SKILL.md
  turbo-boost/
    SKILL.md
  deep-research/
    SKILL.md
`

Then close and reopen Antigravity.

## How They Work

### boost-research (Adversarial Verified Research)
- Phase 0: Strategist decomposes topic into non-overlapping angles
- Phase 1: Parallel researchers flood searches from every angle
- Phase 2a: Fact-Checkers independently verify every claim
- Phase 2b: Devil's Advocates try to DESTROY confirmed claims
- Phase 3: Pro/Con dispute court with Judges for contested claims
- Only claims surviving cross-examination make the final report

### turbo-boost (Parallel Coding Races)
- Phase 1: 3-5 coders race simultaneously with competing approaches
- A Blind Test Designer writes tests WITHOUT seeing any solution
- Phase 2: Tournament Selection scores and picks the winner
- Phase 3: Breaker Agent runs mutation testing + hostile fuzzing on the winner
- Phase 4: Polish Agent fixes any vulnerabilities found
- Circuit breaker if all approaches fail

### deep-research (Raw Parallel Swarm)
- 6 depth modes from Very Fast (5 agents) to Random Bullshit Go (550 agents)
- 2-minute hard timeout safety net
- 102% overthink verification on individual findings
- Mandatory full-page scraping (no lazy snippets)
- No adversarial cross-verification between agents

## Credits

- **boost-research** and **turbo-boost**: Inspired by the built-in /boost, with Kabir's flavour
- **deep-research**: Kabir's original creation

Made by **kabir_sharma_sans**

Enjoy your skills ~ Kabir