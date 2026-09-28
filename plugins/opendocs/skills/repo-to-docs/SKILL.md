---
name: repo-to-docs
description: Turn a code repository into a published OpenDocs documentation site. Use when the user asks to document a repo, project or codebase, generate docs from code, write a getting-started guide or API reference for their project, or publish project docs to OpenDocs.
---

Build a documentation site in OpenDocs from the repository in the current working directory. The OpenDocs tools (`list_spaces`, `create_space`, `create_page`, `get_page_tree`, `update_page_content`, `publish_pages`, `publish_space` and the rest) come from the OpenDocs connector. If they are not available, stop and tell the user how to connect OpenDocs: in claude.ai or Claude Desktop, find OpenDocs in the connector directory and choose Connect; in Claude Code, run `claude mcp add --transport http opendocs https://app.opendocs.cloud/mcp --header "Authorization: Bearer od_YOUR_KEY"` with an OpenDocs API key (Settings > API, Enterprise or Compliance plan).

## 1. Understand the project

Read, in this order, only what exists:

- `README*`, `CONTRIBUTING*`, `CHANGELOG*`, and any `docs/` or `documentation/` folder
- the package manifest (`package.json`, `*.csproj`, `pyproject.toml`, `go.mod`, `Cargo.toml`, `pom.xml`) for the name, purpose, entry points and scripts
- the public surface: exported modules, CLI commands and flags, HTTP routes or an OpenAPI file, configuration options and their defaults
- examples and tests, which show real usage

Never read or quote `.env` files, credentials, keys, tokens or anything under a secrets folder, and never put such values in a page.

## 2. Propose an outline and confirm it

Propose a space name and a page tree before writing anything, for example:

- Getting started: overview, installation, quickstart
- Guides: one page per real task a user performs
- Reference: configuration, CLI, API endpoints (one page per resource)
- Troubleshooting and FAQ

Ask the user to confirm or change the outline, the space name, and whether the site should be public, unlisted or private. Check `list_spaces` first so you add to an existing space instead of creating a duplicate.

## 3. Write the pages

- Create the space with `create_space` if needed, then category pages, then content pages under them with `create_page`, passing Markdown.
- One topic per page. Start each page with one sentence saying what it covers and who it is for.
- Use real commands, file names and defaults from the code. If something is unclear from the code, say so on the page rather than guessing.
- Link related pages to each other.
- Keep code samples short and runnable.

## 4. Publish only when asked

Pages are created as drafts unless the user says otherwise. Show the page tree (`get_page_tree`) and ask before calling `publish_pages` and `publish_space`. After publishing, give the user the site URL.

Every change is saved in the page history in OpenDocs, so the user can review and restore any page.
