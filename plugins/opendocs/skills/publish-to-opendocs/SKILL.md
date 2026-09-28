---
name: publish-to-opendocs
description: Publish something written in the conversation to OpenDocs as a hosted documentation page. Use when the user asks to publish, save, share or post a document, policy, SOP, guide, help article, FAQ, release notes or meeting outcome to OpenDocs, their help center, knowledge base or docs site.
---

Turn content from this conversation into a page in the user's OpenDocs organization. The OpenDocs tools come from the OpenDocs connector; if they are not available, tell the user to connect OpenDocs (claude.ai or Claude Desktop: find OpenDocs in the connector directory and choose Connect).

1. **Find where it goes.** Call `list_spaces`. If the user named a space, use it; otherwise suggest the best match and confirm. Use `get_page_tree` to pick the parent category, and `search_pages` to check whether a page on the same topic already exists. If one does, offer to update it (`update_page_content`) instead of creating a duplicate.
2. **Shape the content as a doc, not a chat.** Give it a clear title, a one-sentence summary at the top, headings, numbered steps for procedures and tables where they help. Remove conversational phrasing ("As we discussed", "Sure!"). Keep the user's facts exactly; don't invent details.
3. **Show it before saving.** Show the title, location and the Markdown, and ask for a go-ahead.
4. **Create the page** with `create_page` (or update the existing one). Leave it as a draft unless the user asked to publish.
5. **Publish if asked** with `publish_pages`, and give the user the page link.

Every change is saved in page history in OpenDocs and can be restored.
