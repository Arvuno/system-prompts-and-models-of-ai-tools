# 07_INITIAL_PR_PLAN.md — Initial PR Plan for Branch contrib/placeholder-url-fix

## Branch Created
`contrib/placeholder-url-url-fix` — based on upstream/main

## Changes Pushed to Branch
**3 files modified** (3 files containing `example.com` placeholder URLs):

### 1. `Devin AI/Prompt.txt` — Line 252
```diff
-<navigate_browser url="https://www.example.com" tab_idx="0"/>
+<navigate_browser url="https://placeholder.example.com" tab_idx="0"/>
```

### 2. `Comet Assistant/System Prompt.txt` — Line 637
```diff
-- navigate tool: {"url": "https://example.com", "tabId": <TAB_ID>}
+- navigate tool: {"url": "https://placeholder.example.com", "tabId": <TAB_ID>}
```

### 3. `Anthropic/Claude for Chrome/Prompt.txt` — Line 615
```diff
-- navigate tool: {"url": "https://example.com", "tabId": <TAB_ID>}
+- navigate tool: {"url": "https://placeholder.example.com", "tabId": <TAB_ID>}
```

## PR Description
**Title:** fix: replace example.com placeholder URLs with placeholder.example.com

**Body:**
This PR replaces generic `example.com` URLs in prompt template examples with `placeholder.example.com`. This prevents confusion when users see real-looking URLs in shipped prompts that resolve to a real domain.

### Files Changed
- `Devin AI/Prompt.txt`
- `Comet Assistant/System Prompt.txt`
- `Anthropic/Claude for Chrome/Prompt.txt`

### Rationale
- `example.com` is a real, RFC-confirming domain operated by IANA
- Prompts referencing it as a "template placeholder" could mislead users
- `placeholder.example.com` clearly signals "this is an example placeholder"

### Testing
- No functionality changed (just string replacement)
- All other references to example.com in comments/documentation retained

### Future Work
- Consider adding a CONTRIBUTING.md guide on proper placeholder usage
- Consider adding a link-check CI to catch placeholder URLs before merge
