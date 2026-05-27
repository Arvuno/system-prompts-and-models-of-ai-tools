# 02_SETUP_AND_BASELINE.md — Setup Validation & Baseline

## Repository Setup

### Remote Configuration
```
origin  → https://github.com/okwn/system-prompts-and-models-of-ai-tools.git
upstream → https://github.com/x1xhlol/system-prompts-and-models-of-ai-tools.git
```

### Sync Commands
```bash
git fetch upstream
git log upstream/main --oneline          # view upstream history
git ls-remote upstream refs/pull/*/head   # list open PRs
```

### Local Branch
- **main** — clean, synchronized with origin/main and upstream/main
- No feature branches currently exist

---

## Baseline: Upstream Is Ahead
The upstream repository has **29 open pull requests** (PR #101–#134+).
The local `main` branch is at commit `b8e9589`, which matches upstream/main.

## Baseline: File Count
- **139 total files** tracked by git
- **93 content files** (.txt/.json/.yaml)
- No binary异物 detected

## Baseline: Last Commit Analysis
- `b8e9589` "Update README.md" — Readme update (sponsorship section)
- Previous: `cf83448` "Update README.md", `0c512ba` "Update README.md"
- Pattern: Frequent small README updates suggest active maintenance

## Baseline: Content Freshness
| File | Model/Version Mentioned | Date Context |
|------|-------------------------|--------------|
| `Anthropic/Claude Sonnet 4.6.txt` | claude-sonnet-4-6, claude-haiku-4-5-20251001 | Oct 2025 |
| `Anthropic/Claude Code 2.0.txt` | claude-sonnet-4-5-20250929 | Sep 2025 |
| `Anthropic/Sonnet Prompts 4.5.txt` | claude-sonnet-4-5-20250929 | Sep 2025 |
| `Cursor Prompts/Agent Prompt 2025-09-03.txt` | dated 2025-09-03 | Sep 2025 |
| `Open Source prompts/Codex CLI/openai-codex-cli-system-prompt-20250820.txt` | dated 2025-08-20 | Aug 2025 |

## Baseline: Link Surface Area
Scanned all .txt/.md files — found:
- `docs.claude.com` references in 5 files (Anthropic prompts)
- `support.claude.com` references in 2 files (Anthropic prompts)
- `docs.anthropic.com` references in 1 file (NotionAi prompt)
- `example.com` placeholder URLs in 4 files

## Baseline: No Automated Checks
- No GitHub Actions workflows found (`.github/workflows/` absent)
- No link validation CI
- No syntax linting for prompt files
- No freshness checks for version references

## Baseline: Open PRs (from `git ls-remote upstream refs/pull/*/head`)
| PR | Status |
|----|--------|
| #101–#110 | open (various topics) |
| #114, #117, #118, #120, #121, #124–#134 | open |

---

## Health Summary
- ✓ Repository accessible and synced
- ✓ No broken git state
- ⚠ Upstream has many open PRs (contribution activity but unprocessed)
- ⚠ No automated quality gates
- ⚠ Documentation links may be stale
