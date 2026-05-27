# 05_PR_CANDIDATES.md — Pull Request Candidates

## Methodology
Scanned codebase for fixable issues. Identified 10 PR-worthy candidates based on:
- Impact (user-facing vs internal)
- Effort (low/medium/high)
- Risk (safe to apply vs needs maintainer review)
- Clarity (unambiguous fix vs interpretive)

---

## PR Candidates (Ranked by Quality)

### 🥇 Candidate 1: Fix example.com placeholder URLs
**Severity:** High | **Effort:** Low | **Risk:** Safe
**Files affected:**
- `Devin AI/Prompt.txt` (line 252: `url="https://www.example.com"`)
- `Comet Assistant/System Prompt.txt` (line 637: `"url": "https://example.com"`)
- `Anthropic/Claude for Chrome/Prompt.txt` (line 615: `"url": "https://example.com"`)

**Fix:** Replace `example.com` with a note like `[URL-placeholder]` or `https://placeholder.example.com` with a comment that this is an example template.

**Why quality:** Unambiguous fix, no community input needed, improves shipped content quality.

---

### 🥈 Candidate 2: Add Updated: timestamp header to all prompt files
**Severity:** Medium | **Effort:** Medium | **Risk:** Safe
**Files affected:** All 71 .txt prompt files

**Fix:** Prepend each file with:
```
---
Updated: [inferred or current date]
Model: [model version if known]
Source: [source URL if known]
---
```

**Why medium priority:** Requires bulk edit, but clearly improves long-term maintenance.
*Note: Can use AI-assisted timestamp inference from file content.*

---

### 🥉 Candidate 3: Add CONTRIBUTING.md
**Severity:** Medium | **Effort:** Low | **Risk:** Safe
**Fix:** Create `CONTRIBUTING.md` with:
- How to submit new prompts
- Required file format (header metadata)
- Version naming conventions
- Link validation requirements

**Why quality:** Enables better community contributions, reduces low-quality PRs.

---

### 4. Fix Claude Code 2.0.txt WebFetch doc map reference
**Severity:** Medium | **Effort:** Low | **Risk:** Medium (needs verification)
**File:** `Anthropic/Claude Code 2.0.txt` line 34
**Current:** `https://docs.claude.com/en/docs/claude-code/claude_code_docs_map.md`
**Fix:** Verify if URL is valid; if not, update to current docs URL structure.

---

### 5. Add .gitignore to exclude assets build artifacts
**Severity:** Low | **Effort:** Low | **Risk:** Safe
**Fix:** Create `.gitignore` with:
```
# Keep assets but ignore generated thumbnails
assets/*.png
```

---

### 6. Standardize file naming: spaces to underscores
**Severity:** Low | **Effort:** Medium | **Risk:** Medium (breaks links if relative paths used)
**Files:** Various — would need mass rename
**Note:** Too risky without confirming internal link consistency.

---

### 7. Add JSON schema for tools.json validation
**Severity:** Medium | **Effort:** Medium | **Risk:** Safe
**Fix:** Create `.github/schemas/tools.json` with JSON Schema for tool specifications.
Add GitHub Action workflow to validate all `tools.json` files.

---

### 8. Fix NotionAi Prompt.txt placeholder URLs (user data leak risk)
**Severity:** Low | **Effort:** Low | **Risk:** Safe
**Files:** `NotionAi/Prompt.txt` lines 466-468 (URLs to obsidian.md shown as user context)
**Note:** These appear to be intentional example placeholders, but should be clearly marked as `[EXAMPLE]` not actual URLs.

---

### 9. Create issue templates
**Severity:** Low | **Effort:** Low | **Risk:** Safe
**Fix:** Add `.github/ISSUE_TEMPLATE/` with templates for:
- Prompt update request
- New tool submission
- Broken link report

---

### 10. Add link-check GitHub Action
**Severity:** Medium | **Effort:** Low | **Risk:** Safe
**Fix:** Add `.github/workflows/link-check.yml` using `mloc的心态/link-check-action` or similar to periodically validate all URLs.

---

## Summary Table

| # | PR Title | Impact | Effort | Risk | Priority |
|---|----------|--------|--------|------|----------|
| 1 | Fix example.com placeholder URLs | High | Low | Safe | 🥇 |
| 2 | Add Updated: timestamp headers | Medium | Medium | Safe | 🥈 |
| 3 | Create CONTRIBUTING.md | Medium | Low | Safe | 🥈 |
| 4 | Fix Claude Code WebFetch doc URL | Medium | Low | Medium | 4 |
| 5 | Add .gitignore | Low | Low | Safe | 5 |
| 6 | Standardize file naming | Low | Medium | Medium | 6 (skip) |
| 7 | Add JSON schema for tools.json | Medium | Medium | Safe | 7 |
| 8 | Fix NotionAi placeholder URLs | Low | Low | Safe | 8 |
| 9 | Create issue templates | Low | Low | Safe | 9 |
| 10 | Add link-check workflow | Medium | Low | Safe | 10 |

---

## Top 5 Selected for Implementation
1. **Fix example.com placeholder URLs** (Candidate 1)
2. **Create CONTRIBUTING.md** (Candidate 3)
3. **Add link-check workflow** (Candidate 10)
4. **Create issue templates** (Candidate 9)
5. **Add JSON schema for tools.json** (Candidate 7)
