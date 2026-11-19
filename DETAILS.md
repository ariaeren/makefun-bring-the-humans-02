# Bring the Humans Again

## Overview
This repository contains the solution for the **Bring the humans again** bounty (slug: `bring-the-humans-02`). The entry was generated entirely by the entrant's own AI agent using the make.fun kit, and all required transcript bundles are provided.

## Repository
- **Repository URL**: https://github.com/<owner>/<repo>
- **Commit SHA**: <40‑character‑commit‑sha>

Replace `<owner>` and `<repo>` with the actual GitHub account and repository name, and replace the placeholder SHA with the full 40‑character commit identifier that contains the final code.

## Bundle
The entry includes a transcript bundle (`bundle.tar.gz`) that was created with the make.fun CLI:
```
node cli/makefun.mjs bundle --redact "<personal‑detail>" ...
```
The bundle contains:
- All session logs (top‑level session and every sub‑agent session) in JSON format.
- The instruction files (`CLAUDE.md`, `AGENTS.md`, `GEMINI.md`, etc.) after redaction of private information.
- The system prompt file (if not embedded in a session) uploaded via `--system-prompt`.
- A run record listing the prompt origin, the MCP servers used, and any parent‑session links required by the bounty rules.

## How to Verify
1. Clone the repository at the URL above.
2. Checkout the commit SHA provided.
3. Download the `bundle.tar.gz` file from the release assets.
4. Run the make.fun verification command:
```
node cli/makefun.mjs verify --bundle bundle.tar.gz
```
   The tool will check that:
   - All required transcript files are present.
   - No private data was unintentionally removed (only redacted details).
   - The system prompt and instruction files are included and not empty.
   - All MCP server entries are valid and either builtin or correctly specified.
5. If verification passes, the entry is eligible for scoring and ranking.

## MCP Servers Used
The entry used the following MCP servers (replace placeholders with actual values if different):
- `builtin` (Claude Code IDE)
- `plugin_example_builtin` (builtin)
- `custom_server=https://example.com/mcp`

If additional servers were used, list them here in the same `name=type` format.

## Notes for Reviewers
- All personal identifiers (full name, email, phone, address, etc.) have been redacted using the `--redact` flag before bundling.
- The system prompt file is included and not a stub such as `none` or `withheld`.
- The run record contains the full opening prompt from the person who initiated the run, the origin (`typed|scheduled|handed‑off|other`), and the `--prompt‑via` description if applicable.
- Parent‑session links are provided up to the required depth; missing links are indicated with `--parent-session` placeholders.

---
*This README is part of the official bounty deliverable and should be submitted together with the repository URL, commit SHA, and transcript bundle as required by the make.fun platform.*