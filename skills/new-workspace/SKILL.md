---
name: new-workspace
description: Provision a new pr-media-work workspace on disk. Use when the user wants to start a new PR/media-monitoring project (media monitoring archive, PR response workspace, or comms strategy workspace). Accepts a workspace name and optional variant (media-monitoring | pr-response | comms-strategy). Scaffolds the workspace, personalises CLAUDE.md from the user's global memory, and (by default) creates a GitHub repo.
disable-model-invocation: true
allowed-tools: Bash(mkdir *), Bash(cp *), Bash(cat *), Bash(git init *), Bash(git add *), Bash(git commit *), Bash(gh repo create *), Bash(gh auth status), Bash(git push *), Read
---

# Provision pr-media-work Workspace

Creates a new workspace for PR/media work. This plugin's commands (`/pr-media-work:scan-coverage`, `/pr-media-work:media-fetch`, `/pr-media-work:comms-initialize`, etc.) are globally available once installed — this skill only provisions the **data scaffold** (CLAUDE.md, context/, outputs/, etc.) that those commands read from and write to.

## Arguments

`$ARGUMENTS` is parsed as:

- **First positional**: workspace name (kebab-case, used as directory and GitHub repo name). Required.
- **Second positional** (optional): target parent path. Defaults to `~/repos/github/my-repos`.
- **`--variant=<media-monitoring|pr-response|comms-strategy>`** (optional): which scaffold to copy. Default: `media-monitoring`.
- **`--local-only`** (optional): skip GitHub repo creation and push. Default: create a public GitHub repo and push.
- **`--private`** (optional): create the GitHub repo as private. Default: public.

### Examples

```
/pr-media-work:new-workspace acme-coverage
/pr-media-work:new-workspace acme-pr --variant=pr-response
/pr-media-work:new-workspace acme-comms --variant=comms-strategy --private
/pr-media-work:new-workspace scratch-monitor --local-only
```

## Procedure

### 1. Parse arguments

Extract workspace name, target parent path, variant, and flags from `$ARGUMENTS`. If workspace name is missing, ask the user for it before proceeding.

### 2. Resolve the scaffold path

The bundled scaffold lives at `${CLAUDE_SKILL_DIR}/../../template/<variant>/`. Confirm it exists. If the variant isn't `media-monitoring`, `pr-response`, or `comms-strategy`, tell the user which variants are available.

### 3. Read ambient facts

Read `~/.claude/CLAUDE.md` if it exists. Extract OS, locale, timezone, and user identity facts. These will personalise the workspace's CLAUDE.md at step 6.

### 4. Create the workspace directory

```bash
mkdir -p <target-parent>/<workspace-name>
cp -r ${CLAUDE_SKILL_DIR}/../../template/<variant>/. <target-parent>/<workspace-name>/
```

Do **not** copy any `.claude/` tree. The plugin's primitives are global.

### 5. Personalise CLAUDE.md

Open the new workspace's `CLAUDE.md` and:

- Replace any placeholder identity with the facts from step 3.
- Add a short header noting the workspace name and variant.
- If ambient facts include OS/locale, embed them so downstream commands can skip re-asking.

### 6. Prompt for workspace-specific facts

Ask the user only for facts this plugin can't infer:

- **media-monitoring variant**: the monitoring subject (person, company, topic) and any priority publications. Suggest running `/pr-media-work:media-setup` afterwards to build out the full monitoring context.
- **pr-response variant**: the client/brand being represented and the types of responses they most often need (statements, pitches, corrections, Q&A).
- **comms-strategy variant**: the client/brand name. Suggest running `/pr-media-work:comms-initialize` afterwards for the full interview-based setup.

### 7. Initialise git and (optionally) publish

```bash
cd <target-parent>/<workspace-name>
git init
git add .
git commit -m "Initial workspace from pr-media-work plugin"
```

Unless `--local-only` is set:

```bash
gh repo create <workspace-name> --<public|private> --source=. --push
```

Use `--public` by default, `--private` if the flag was passed.

### 8. Print next steps

Tell the user:

- Workspace path.
- Variant chosen.
- Which plugin commands apply:
  - `media-monitoring`: `/pr-media-work:media-setup`, `/pr-media-work:media-fetch`, `/pr-media-work:media-batch`, `/pr-media-work:scan-coverage`, `/pr-media-work:summarize-press`.
  - `pr-response`: `/pr-media-work:scan-coverage`, `/pr-media-work:pr-monitor-news`, `/pr-media-work:draft-response`, `/pr-media-work:pr-media-pitch`, `/pr-media-work:pr-build-media-list`.
  - `comms-strategy`: `/pr-media-work:comms-initialize`, `/pr-media-work:comms-refresh-strategy`, `/pr-media-work:comms-create-campaign`, `/pr-media-work:comms-client-report`.
- Reminder that the workspace is **data** — they can delete/move it freely without losing the plugin's commands.

## Notes

- The scaffold path must be resolved via `${CLAUDE_SKILL_DIR}/../../template/` (not `${CLAUDE_PLUGIN_ROOT}` — that variable isn't exported in skill bash injection, only in hooks/MCP).
- Never copy `.claude/commands/`, `.claude/agents/`, or `.claude/skills/` into the new workspace. If the user wants workspace-local overrides, they can add them manually later.
- Don't hard-code any personal paths or identifiers here — everything comes from user memory or prompts.
