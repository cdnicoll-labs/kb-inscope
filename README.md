# kb-inscope

InScope's half of the shared knowledge base: InScope's own skills, and the marketplace the InScope team
installs from. This repo is both a plugin and a marketplace, so a teammate adds one marketplace, this one,
and never sees another client's entries.

```
.claude-plugin/plugin.json       the inscope plugin manifest
.claude-plugin/marketplace.json  this plugin at ./. The core skills come from the kb-skills marketplace
skills/inscope-rules/             what must never be saved for InScope, and the document kinds
skills/inscope-assessment/        one scoring assessment, written as a contract
```

There is no connection here on purpose. The server is added separately, so the skills never carry a way in.

## Install

In the Claude apps:

1. Add both marketplaces: **Settings → Plugins → Add → Add marketplace**, `https://github.com/cdnicoll-labs/kb-skills`,
   then `https://github.com/cdnicoll-labs/kb-inscope`. Install `kb-core` and `inscope`.
   Two marketplaces, not one: an entry pointing into another repo is fetched over SSH, which fails for anyone
   without an SSH key on GitHub (tested 2026-09-24).
2. Add the knowledge base as a custom connector, using the server's `/mcp` URL.
3. Sign in with your email when asked.

In Claude Code, from an InScope client hub: the hub's `.claude/settings.json` enables this plugin and its
`.mcp.json` points at the server. The first session asks you to sign in.

## What goes in

Kinds: `assessment`, `decision`, `concept`, `system`, `overview`. Never client data, health information, commercial
terms, or vendors and code in product documents. The rules and the kind table are in `skills/inscope-rules/`.

## Changing a skill

Edit it, bump `version` in both `.claude-plugin/plugin.json` and this repo's marketplace entry, open a pull
request, merge. Everyone has it next session. `npm run check:plugins` in `shared-context` catches a missed bump.
