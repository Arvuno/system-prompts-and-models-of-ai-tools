# 00_STATE.md — Repository State Overview
**Repository:** system-prompts-and-models-of-ai-tools  
**Local Path:** /root/eagle-pr-big-1/repos/system-prompts-and-models-of-ai-tools  
**Upstream:** https://github.com/x1xhlol/system-prompts-and-models-of-ai-tools  
**Origin (fork):** https://github.com/okwn/system-prompts-and-models-of-ai-tools  

---

## Current Branch & Commit
- **Branch:** main (clean working tree)
- **HEAD commit:** b8e9589 "Update README.md"
- **Branch status:** up to date with origin/main and upstream/main

## Repository Purpose
Curated collection of AI system prompts, agent tools specifications, and model information from major AI platforms (Anthropic, Google, OpenAI, Cursor, Windsurf, etc.).

## File Statistics
- **Total files:** 139
- **Prompt/tool files:** 93 (txt/json/yaml)
- **Directories:** 38 (37 tool directories + .github + assets)
- **Largest file:** Google/Gemini/AI Studio vibe-coder.txt (1644 lines)

## Directory Structure
```
system-prompts-and-models-of-ai-tools/
├── Anthropic/          # Claude Code, Sonnet 4.5, 4.6
├── Augment Code/       # Augment Agent prompts
├── Cluely/             # Enterprise prompts
├── CodeBuddy Prompts/  # Craft & Chat prompts
├── Comet Assistant/    # System prompt + tools
├── Cursor Prompts/     # Agent v1.0–2.0, CLI, Chat
├── Devin AI/           # DeepWiki, Prompt
├── Emergent/           # Prompt + Tools
├── Google/             # Antigravity, Gemini vibe-coder
├── Junie/              # Prompt
├── Kiro/               # Mode Classifier, Spec, Vibe
├── Leap.new/           # Prompts + tools
├── Lovable/            # Agent Prompt + Tools
├── Manus Agent/        # Agent loop + Modules + tools
├── NotionAi/           # Prompt + tools
├── Open Source prompts/# Bolt, Cline, Codex CLI, Gemini CLI, Lumo, RooCode
├── Orchids.app/        # Decision-making, System prompt
├── Perplexity/         # Prompt
├── Poke/               # Poke agent + p1–p6 variants
├── Qoder/              # Quest Action/Design, prompt
├── Replit/             # Prompt + Tools
├── Same.dev/           # Prompt + Tools
├── Trae/               # Builder, Chat, Tools
├── Traycer AI/         # phase_mode, plan_mode
├── VSCode Agent/       # Claude/GPT prompts + chat titles
├── Warp.dev/           # Prompt
├── Windsurf/           # Prompt/Tools Wave 11
├── Xcode/              # System, Explain/Document/Playground/Message/Preview
├── Z.ai Code/          # prompt
├── v0 Prompts and Tools/ # Prompt + tools
├── Amp/                # README + YAML configs
├── dia/                # Prompt
└── README.md           # Main readme with sponsorship
```

## Remote Configuration
- **origin** → okwn/system-prompts-and-models-of-ai-tools (fork, fetch/push)
- **upstream** → x1xhlol/system-prompts-and-models-of-ai-tools (original, fetch only)

## Open Pull Requests (upstream)
29 open PRs detected (refs/pull/101 through 134+)

## Key Risks & Findings
1. **Documentation link drift:** Several prompts reference `docs.claude.com` and `support.claude.com` which may become stale
2. **Data staleness:** Prompt files reference model versions from 2025; no mechanism for updates
3. **Broken/outdated URLs:** Example URLs (example.com) present in some prompts
4. **No CI/CD:** No automated checks for link validity or prompt quality
5. **Low risk profile:** This is a read-only curated collection; no code execution risk

## Maintenance Posture
- Repository is actively maintained with last commit referencing May 2026 update
- Owner accepts contributions via PRs
- LICENSE.md is 35KB (AGPL-3.0 likely)
- No automated issue triage or quality gate
