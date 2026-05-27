# 10_REMAINING_4_PR_SCHEDULE.md — Schedule for Remaining 4 PRs

## Completed
- ✅ PR #1: Fix example.com placeholder URLs — **DONE**

## Remaining 4 PRs

### PR #2: Create CONTRIBUTING.md
**Target:** Create `CONTRIBUTING.md`  
**Effort:** 2–3 hours (create guide file)  
**Key sections to include:**
1. How to submit new prompts
2. File header metadata requirements:
   ```
   ---
   Updated: [YYYY-MM-DD]
   Model: [model version]
   Source: [original source URL]
   ---
   ```
3. Naming conventions for files
4. Link validity requirements
5. tools.json format expectations

---

### PR #3: Add link-check GitHub Action
**Target:** `.github/workflows/link-check.yml`  
**Effort:** 2–4 hours (write workflow + test)  
**Technology:** `lycheeq/actions/link-checker@v4` or `peter-evans/check-link`
**Scope:** Weekly scan of all `.txt` and `.md` files
**Exclusions:** Known-safe URLs (star-history.com, Discord, etc.)

---

### PR #4: Create GitHub issue templates
**Target:** `.github/ISSUE_TEMPLATE/` directory  
**Effort:** 1–2 hours  
**Templates:**
1. **Bug Report** — Broken link/template issue
   - Broken link URL
   - File containing link
   - Expected behavior
2. **Prompt Update Request** — New model version
   - Tool/platform name
   - New model version
   - Source of update
3. **New Tool Submission** — New prompt file
   - Tool name
   - File contents
   - tools.json update (if applicable)

---

### PR #5: Add JSON schema for tools.json validation
**Target:** `.github/schemas/tools-schema.json` + CI  
**Effort:** 3–5 hours  
**Schema structure:**
```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "type": "object",
  "required": ["tools"],
  "properties": {
    "tools": {
      "type": "array",
      "items": {
        "type": "object",
        "required": ["name"],
        "properties": {
          "name": { "type": "string" },
          "description": { "type": "string" },
          "parameters": { "type": "object" }
        }
      }
    }
  }
}
```
**Workflow:** `.github/workflows/validate-tools.yml` to validate all 19 tools.json files

---

## Schedule Estimate

| Week | PR | Focus |
|------|----|-------|
| 1 | #2: CONTRIBUTING.md | Draft guide, submit for review |
| 2 | #4: Issue templates | Parallel with week 1 if time permits |
| 3 | #3: Link-check workflow | Set up and test URL scanner |
| 4 | #5: JSON schema | Validate 19 existing tools.json files |

**Total estimated effort:** 8–14 hours over 4 weeks

---

## Dependencies
- PRs #2, #3, #4, #5 are **independent** — can be developed in any order
- PR #5 depends on understanding tools.json schema (analyze first before drafting)

## Notes
- Order prioritized by **ease of merge** (CONTRIBUTING.md is safest, JSON schema most complex)
- Maintainer feedback on PR #1 will inform approach for remaining PRs
- If maintainer is unresponsive, queue up to 2 PRs before pausing
