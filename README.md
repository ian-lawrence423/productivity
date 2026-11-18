# Productivity

General workflow tools, not code-specific.

## Use in Cursor

Cursor does not load a GitHub skills repo until it is a plugin. This repo ships `.cursor-plugin/marketplace.json` so you can import it once, then invoke the skills with `/` in any Agent chat.

1. Open **Customize** in the Cursor sidebar.
2. **Plugins → Add → From GitHub Repository** (or type `/add-plugin` in Agent chat).
3. Paste `https://github.com/ian-lawrence423/productivity` and import.
4. Install the **productivity** plugin. Use **user** scope if you want the skills in every project.
5. Confirm they appear under **Customize → Skills**.

Then type `/` in Agent chat:

| Skill | How it fires | Slash |
| --- | --- | --- |
| grill-me | Only when you type it | `/grill-me` |
| handoff | Only when you type it | `/handoff` |
| teach | Only when you type it | `/teach` |
| to-questionnaire | Only when you type it | `/to-questionnaire` |
| wait-what | Only when you type it | `/wait-what` |
| grilling | You or the agent | `/grilling` (or say "grill me") |
| writing-for-agents | You or the agent | `/writing-for-agents` |

Keep a skill on for the whole session by using it as a Custom Mode (`Option+Enter` / `Alt+Enter`).

Team alternative: **Dashboard → Plugins & MCPs → Add Marketplace → Import from Repo** with the same URL, then install **productivity**.

Opening this repo as a workspace is not enough on its own. Cursor does not scan `plugins/*/skills/`; it needs the plugin install above.

## User-invoked

Reachable only when you type them (Cursor and Claude Code: `disable-model-invocation: true`; Codex: `policy.allow_implicit_invocation: false` in `agents/openai.yaml`).

- **[grill-me](./plugins/productivity/skills/grill-me/SKILL.md)**: Get relentlessly interviewed about a plan or design until every branch of the design tree is resolved.
- **[handoff](./plugins/productivity/skills/handoff/SKILL.md)**: Compact the current conversation into a handoff document so another agent can continue the work.
- **[teach](./plugins/productivity/skills/teach/SKILL.md)**: Teach the user a new skill or concept over multiple sessions, using the current directory as a stateful teaching workspace.
- **[to-questionnaire](./plugins/productivity/skills/to-questionnaire/SKILL.md)**: Turn a decision you can't answer alone into a Markdown questionnaire for the one person who can (filled in async, or together over a meeting).
- **[wait-what](./plugins/productivity/skills/wait-what/SKILL.md)**: Fire this the moment a message doesn't land. The agent re-pitches it with the context you're missing, in plain English, using your `GLOSSARY.md` vocabulary.

## Model-invoked

Model- or user-reachable (rich trigger phrasing so the model can reach for them).

- **[grilling](./plugins/productivity/skills/grilling/SKILL.md)**: Interview the user relentlessly about a plan, decision, or idea until every branch of the design tree is resolved.
- **[writing-for-agents](./plugins/productivity/skills/writing-for-agents/SKILL.md)**: Writing documents for agents: skills, AGENTS.md/CLAUDE.md, and any doc an agent reaches by a pointer.
