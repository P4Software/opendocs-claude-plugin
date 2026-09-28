---
name: docs-audit
description: Audit an OpenDocs documentation space for gaps, stale content and inconsistencies. Use when the user asks to review, audit, clean up, check or improve their docs, find outdated pages, or find what their readers can't find.
---

Review a documentation space in OpenDocs and report what to fix, using the OpenDocs connector's read tools (if they are missing, ask the user to connect OpenDocs first).

1. **Pick the space.** Call `list_spaces`, confirm which space to audit, and read its structure with `get_page_tree`.
2. **Read the pages** with `get_page`. For a large space, start with the most important sections the user names.
3. **Check reader demand.** If `get_analytics` is available on the user's plan, look at top pages and searches that returned no results: each no-result search is a missing or badly titled page.
4. **Report findings, grouped and ranked:**
   - Missing: topics readers search for, or that the product has, with no page
   - Wrong or stale: contradictions between pages, outdated versions, prices, names or screenshots described in text
   - Hard to use: pages with no summary, walls of text, broken or missing cross-links, duplicate pages
   - Structure: pages in the wrong category, categories with one page
   Quote the page title and the exact passage for each finding.
5. **Offer to fix.** Ask which findings to act on. Then update pages with `update_page_content` or `update_page`, move pages with `move_page`, and create missing pages with `create_page`. Never delete pages without explicit confirmation. Every change is saved in page history.
