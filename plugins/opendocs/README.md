# OpenDocs for Claude

Write, organize and publish documentation to [OpenDocs.cloud](https://opendocs.cloud) from a conversation with Claude. OpenDocs hosts branded docs sites, help centers and SOPs on your own domain.

## What it adds

Four skills that Claude uses with the OpenDocs connector:

- **repo-to-docs**: turns the code repository you're working in into a documentation site (getting started, guides, reference, troubleshooting), confirming the outline with you before writing and publishing only when you ask.
- **publish-to-opendocs**: publishes something from the conversation (a policy, SOP, help article, release notes) as a page in the right space, updating an existing page instead of duplicating it.
- **write-sop**: writes a standard operating procedure in a consistent structure and saves it to OpenDocs.
- **docs-audit**: reviews a docs space for missing, stale or hard-to-use pages, using reader search data where your plan includes analytics.

## Set up

The skills use the tools of the OpenDocs connector, so connect it first:

- **claude.ai or Claude Desktop**: find OpenDocs in [Claude's connector directory](https://claude.ai/directory/opendocs) and choose Connect, then sign in to OpenDocs and choose your organization. Available on every OpenDocs plan, including Free.
- **Claude Code**: add the server with an OpenDocs API key (created in Settings > API; API keys need the Enterprise or Compliance plan):

  ```
  claude mcp add --transport http opendocs https://app.opendocs.cloud/mcp --header "Authorization: Bearer od_YOUR_KEY"
  ```

No OpenDocs account yet? [Start free](https://app.opendocs.cloud/Identity/Account/Register); every account begins with a 14-day Pro trial, no card required.

## Use it

Ask in plain words, for example "Document this repo in OpenDocs", "Publish this refund policy to our help center", "Write an SOP for onboarding a new client" or "Audit our Help Center space". Claude shows drafts before saving and publishes only when you ask. Every change is saved in OpenDocs page history and can be restored.

## Data

This plugin contains instructions only; it stores nothing and runs no code. Content you ask Claude to save is sent to your OpenDocs organization through the OpenDocs connector at `https://app.opendocs.cloud/mcp`, limited to the organization you chose and to your role there. See the [OpenDocs privacy policy](https://opendocs.cloud/privacy/).

## Support

support@opendocs.cloud · [opendocs.cloud/claude](https://opendocs.cloud/claude)
