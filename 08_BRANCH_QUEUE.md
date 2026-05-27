# 08_BRANCH_QUEUE.md — Branch Queue Management

## Current Active Branch
- **`contrib/placeholder-url-fix`** — Initial fix branch
  - Status: **committed** (pushed to origin)
  - Changes: 3 files (example.com → placeholder.example.com)

---

## Planned Follow-Up Branches

### Branch 2: `contrib/contributing-guide`
**PR:** Create CONTRIBUTING.md  
**Status:** Planned  
**Depends on:** None (can run parallel)  
**Changes:** New `CONTRIBUTING.md` file

### Branch 3: `contrib/link-check-workflow`
**PR:** Add link-check GitHub Action  
**Status:** Planned  
**Depends on:** Branch 2 (CONTRIBUTING.md context)  
**Changes:** New `.github/workflows/link-check.yml`

### Branch 4: `contrib/issue-templates`
**PR:** Create GitHub issue templates  
**Status:** Planned  
**Depends on:** None (can run parallel)  
**Changes:** New `.github/ISSUE_TEMPLATE/` directory

### Branch 5: `contrib/tools-json-schema`
**PR:** Add JSON schema + validation workflow for tools.json  
**Status:** Planned  
**Depends on:** None (can run parallel)  
**Changes:** New `.github/schemas/tools-schema.json` + `.github/workflows/validate-tools.yml`

---

## Branch Dependencies
```
contrib/placeholder-url-fix  [ACTIVE]
contrib/contributing-guide   [PLANNED] ──┬──┐
contrib/link-check-workflow  [PLANNED] ──┴──┤ (can be merged independently)
contrib/issue-templates     [PLANNED] ────-─┤
contrib/tools-json-schema    [PLANNED] ─────┘
```

## Queue Order (Recommended Priority)
1. ✅ `contrib/placeholder-url-fix` — Done
2. ⬜ `contrib/issue-templates` — Low effort, no dependencies
3. ⬜ `contrib/contributing-guide` — Medium effort, enables better PRs
4. ⬜ `contrib/tools-json-schema` — Medium effort, validation
5. ⬜ `contrib/link-check-workflow` — Medium effort, automation

## Notes
- Each branch targets one PR for maintainer simplicity
- No branch depends on another being merged first
- Branches can be developed in parallel
- Keep each PR focused on a single clear improvement
