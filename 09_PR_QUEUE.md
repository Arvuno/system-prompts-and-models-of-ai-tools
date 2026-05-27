# 09_PR_QUEUE.md — Pull Request Queue

## PR Queue (from 05_PR_CANDIDATES.md)

| # | PR Title | Branch | Priority | Status |
|---|----------|--------|----------|--------|
| 1 | Fix example.com placeholder URLs | `contrib/placeholder-url-fix` | 🥇 | ✅ Committed |
| 2 | Create CONTRIBUTING.md | `contrib/contributing-guide` | 🥈 | ⬜ Planned |
| 3 | Add link-check GitHub Action | `contrib/link-check-workflow` | 🥉 | ⬜ Planned |
| 4 | Create GitHub issue templates | `contrib/issue-templates` | 4 | ⬜ Planned |
| 5 | Add JSON schema for tools.json | `contrib/tools-json-schema` | 5 | ⬜ Planned |
| 6 | Add Updated: timestamp headers | — | 6 | ⬜ Deferred |
| 7 | Fix Claude Code WebFetch doc URL | — | 7 | ⬜ Deferred |
| 8 | Fix NotionAi placeholder URLs | — | 8 | ⬜ Deferred |
| 9 | Add .gitignore | — | 9 | ⬜ Deferred |
| 10 | Fix file naming inconsistencies | — | 10 | ⬜ Skip |

---

## Ready to Submit (in order)
1. **`contrib/placeholder-url-fix`** — 3 files changed, clear fix, minimal risk

## Waiting on Maintainer Feedback
- None yet — PR not yet submitted to upstream

## Deferred Candidates
These require maintainer input or are too large for immediate scope:
- **Timestamp headers** — Requires bulk editing, no clear date for files
- **Claude WebFetch URL** — Needs manual link verification
- **File naming** — Risk of breaking things without full search

---

## PR Submission Notes
When submitting to upstream (x1xhlol/system-prompts-and-models-of-ai-tools):
- Fork: okwn (origin)
- Base: upstream/main
- Head: contrib/placeholder-url-fix
- Target maintainer: `x1xhlol`
