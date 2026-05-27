# 03_ISSUE_TRIAGE.md — Issue & Improvement Triage

## Detected Issues (No GitHub Issues API — inferred from codebase scan)

### 🔴 High-Priority Issues

#### 1. Stale Documentation Links
- **File:** `Anthropic/Claude Code 2.0.txt` line 34
  - Reference: `https://docs.claude.com/en/docs/claude-code/claude_code_docs_map.md`
  - Risk: This docs map page may have been moved/renamed
- **File:** `Anthropic/Claude Code/Prompt.txt` line 10
  - Reference: `https://docs.anthropic.com/en/docs/claude-code`
  - Risk: General docs URL may be valid but specific sections change
- **Files:** `Anthropic/Claude Sonnet 4.6.txt`, `Anthropic/Sonnet 4.5 Prompt.txt`
  - References to `support.claude.com` — may have changed

#### 2. Placeholder URLs in Prompts
- **Files:** `Devin AI/Prompt.txt` (line 252), `Comet Assistant/System Prompt.txt` (line 637), `Anthropic/Claude for Chrome/Prompt.txt` (line 615)
  - Pattern: `https://www.example.com` as placeholder
  - Risk: Leaving example.com in shipped prompts is misleading

### 🟡 Medium-Priority Issues

#### 3. Model Version Staleness
- All model version references are from 2025 (e.g., `claude-sonnet-4-5-20250929`)
- No mechanism to track if these versions are still current
- Newer Claude 4.7/4.8 or other model updates may have changed behaviors

#### 4. Open PRs Not Processed
- 29 open PRs in upstream (PR #101–#134+)
- Some may be valid improvements waiting for review
- No indication of why they're unprocessed (maintainer bandwidth? quality?)

#### 5. Duplicate Prompt Coverage
- Multiple versions of similar prompts (e.g., `Cursor Prompts/Agent Prompt v1.0.txt`, `v1.2.txt`, `2.0.txt`)
- No clear changelog between versions
- Users unclear which version is "current"

### 🟢 Low-Priority / Informational

#### 6. Inconsistent File Naming
- Mix of spaces and underscores: `Claude Sonnet 4.6.txt` vs `claude_code_docs_map.md`
- Date formats vary: `Agent CLI Prompt 2025-08-07.txt` vs `openai-codex-cli-system-prompt-20250820.txt`

#### 7. No Automation
- No link checking CI
- No prompt versioning scheme
- No contribution guidelines

#### 8. Sensitive Information in Prompts
- `NotionAi/Prompt.txt` lines 466-468 expose `obsidian.md` URLs as user data placeholders
- Context suggests these are meant as placeholder examples, but they may confuse users into thinking real URLs are being sent

### Issue Count Summary
| Severity | Count |
|----------|-------|
| High | 2 |
| Medium | 3 |
| Low | 4 |
| **Total** | **9** |
