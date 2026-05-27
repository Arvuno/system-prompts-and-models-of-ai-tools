# 06_SELECTED_5_PR_PLAN.md — Five-PR Implementation Plan

## Selected PRs for Implementation
Based on quality-audit scoring and effort/risk assessment, these 5 PRs are selected:

---

## PR #1: Fix example.com placeholder URLs
**Files:** `Devin AI/Prompt.txt`, `Comet Assistant/System Prompt.txt`, `Anthropic/Claude for Chrome/Prompt.txt`
**Change:** Replace `https://www.example.com` and `https://example.com` with `https://placeholder.example.com` and add inline comment `# [placeholder - replace with actual URL]`
**Rationale:** Simplest high-impact fix, unambiguous.

## PR #2: Create CONTRIBUTING.md
**File:** New `CONTRIBUTING.md` in root
**Change:** Document submission guidelines, file format requirements, link-check guidance
**Rationale:** Low effort, enables better community contributions.

## PR #3: Add link-check GitHub Action workflow
**File:** New `.github/workflows/link-check.yml`
**Change:** Weekly workflow using `lycheeq/actions` or similar to check all URLs
**Rationale:** Automated quality gate, finds future link rot proactively.

## PR #4: Create GitHub issue templates
**Files:** New `.github/ISSUE_TEMPLATE/bug-report.md`, `.github/ISSUE_TEMPLATE/prompt-update.md`
**Change:** Structured templates for broken link and prompt update reports
**Rationale:** Low effort, improves issue quality from contributors.

## PR #5: Add JSON schema + validation workflow for tools.json
**Files:** New `.github/schemas/tools-schema.json`, `.github/workflows/validate-tools.yml`
**Change:** JSON Schema for agent tool specifications + CI to validate all 19 tools.json files
**Rationale:** Ensures consistency across tool definitions, catches malformed JSON.

---

## Execution Strategy
1. **Branch naming:** `contrib/placeholder-url-fix` for PR #1
2. **Batch submission:** PRs #2–#5 may be batched if maintainer prefers fewer PRs
3. **Keep PRs small** — each PR does one thing clearly

## Notes
- PR #1 (placeholder URLs) is the **initial PR** to be implemented immediately
- PRs #2–#5 to follow in sequence pending maintainer feedback
