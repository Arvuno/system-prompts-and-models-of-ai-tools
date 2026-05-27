# 04_QUALITY_AUDIT.md — Quality Audit Report

## Audit Scope
Repository: system-prompts-and-models-of-ai-tools
Files audited: 139 total, 93 content files (.txt/.json/.yaml)
Scan date: May 27, 2026

---

## ✅ Quality Strengths

### 1. Good File Organization
- Tool-by-tool directory structure is logical and navigable
- Consistent subdirectories per AI platform
- README exists in root and in Amp/ subdirectory

### 2. Version Documentation
- Several prompts include model version strings (e.g., `claude-sonnet-4-6`)
- Date-labeled files exist (e.g., `Agent CLI Prompt 2025-08-07.txt`)

### 3. Diverse Coverage
- 37+ AI platforms/tools represented
- Mix of model providers (Anthropic, Google, OpenAI) and agent frameworks (Cursor, Windsurf, etc.)
- Both open-source and commercial tools captured

### 4. Tools.json Coverage
- 19 JSON tool specification files accompany text prompts
- Standardized structure for tool definitions

---

## ⚠️ Quality Deficiencies

### 1. Broken Link Surface
| URL Pattern | Occurrences | Risk |
|-------------|-------------|------|
| `docs.claude.com` | 5 files | Medium — docs structure changes |
| `support.claude.com` | 2 files | Medium — help desk URL changes |
| `example.com` (placeholder) | 4 files | High — misleading in shipped prompts |

### 2. No Format Validation
- Prompts are raw text with no schema validation
- No consistent prompt template format
- JSON tool files have no schema enforcement

### 3. No freshness tracking
- No `last_updated` metadata in any file
- No changelog or version history per prompt
- Difficult to determine if a prompt is current

### 4. Obsolete model references
- `Claude Sonnet 4.5 Prompt.txt` references `claude-sonnet-4-5-20250929` (Sep 2025 model)
- Newer models (4.6, Opus, Haiku 4.5) may render some older prompts inconsistent
- No noteabiiltiy system for "this prompt was for model version X"

### 5. README issues
- README contains promotional content (sponsorship links) mixed with documentation
- "Latest Update" field only in README, not in individual files
- Image references use relative paths (`assets/latitude-dark.png`) — works in GitHub but not if served elsewhere

---

## Quality Score: 6/10

| Category | Score | Notes |
|----------|-------|-------|
| Organization | 8/10 | Logical directory structure |
| Link Health | 4/10 | 11+ problematic URLs detected |
| Freshness | 3/10 | No timestamp/freshness metadata |
| Consistency | 6/10 | Naming conventions vary |
| Completeness | 8/10 | Good coverage of AI tools |
| Automation | 2/10 | No CI, no validation |

---

## Recommendations (Priority Order)
1. **Fix example.com placeholder URLs** — Replace with a comment or remove entirely
2. **Add freshness metadata** — `Updated:` tag in each file header
3. **Create CONTRIBUTING.md** — Contribution guidelines for prompt submissions
4. **Add link check CI** — GitHub Action to validate URLs periodically
5. **Version-stamp prompts** — Include model version and date in file content
