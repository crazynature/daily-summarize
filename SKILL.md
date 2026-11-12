---
name: daily-summarize
description: >-
  Maintain local project handoff notes in docs/local/. Use when the user first
  states a work goal or ticket, changes the goal or a standing rule, wraps up
  (including 收尾), asks for a handoff or an opening line, or starts a new
  conversation with an opening line that points to docs/local/.
---

# Daily Summarize

Keep project context in four Markdown files under `docs/local/` so a new conversation can resume from a two-sentence opening line. Work from the project root. Preserve the language of each existing file and use the user's language for new files.

## Files

| File | Contents |
| --- | --- |
| `OVERVIEW.md` | Keep it to about 50 lines. **Goal** holds the ticket ID, a one- or two-sentence goal, and the current status. **Notes** holds standing rules, lasting decisions, and recurring pitfalls. **Pointers** links to relevant documents. Rewrite stale entries in place. |
| `daily-context.md` | Keep the latest workday only. Record what happened, relevant commit, PR, or run IDs, and a `Start here` section with the next steps in order. Replace the file at wrap-up. |
| `TODO.md` | Track open items as `[ ]` and items waiting on someone as `[~]`. Add newly identified work and remove closed items. |
| `DONE.md` | Append finished or closed items under their ticket, with the date and the PR, commit, or fact that explains the outcome. |

Give each item one home. Use a short pointer when the handoff needs to reference a task or decision already recorded elsewhere.

## Keep the notes local

For a Git project, run `git check-ignore docs/local/OVERVIEW.md` after creating any of the four files. If Git reports that the path is unignored, use `git rev-parse --git-path info/exclude` to locate the repository's local exclude file, append `docs/local/` if it is absent, and rerun the check. Use `git ls-files -- docs/local/` to check for notes that are already tracked. Report any tracked notes to the user because an ignore rule only applies to untracked files. Leave tracked files and the index alone when setting up the local exclusion. If the ignore check fails for another reason, report what prevented verification.

## During a session

- When the user states a goal or ticket, create `OVERVIEW.md` or update its **Goal** in the same turn. Include a ticket ID when one is available.
- When the goal changes, update **Goal**. If the old goal was finished or dropped, record its outcome in `DONE.md`.
- When the user gives a standing rule or a recurring pitfall is discovered, update **Notes** in the same turn.
- As work progresses, keep `TODO.md` and `DONE.md` current.

## At wrap-up

1. Create any missing files and verify the local Git exclusion.
2. Update **Goal** and **Notes** in `OVERVIEW.md` and replace stale information.
3. Append newly completed or closed items to `DONE.md` under their tickets.
4. Remove closed items from `TODO.md` and add newly identified or waiting work.
5. Before replacing `daily-context.md`, move any information that still matters into its proper home. Replace the file with the latest workday's entry and the ordered `Start here` steps.
6. End the reply with the opening line as a quote.

## Opening line

Write two sentences in the user's language. The first names the three files to read. The second names the ticket when available and gives the next concrete step. Keep the full line in the reply only. The saved next steps live under `Start here` in `daily-context.md`.

> Read `docs/local/OVERVIEW.md`, `docs/local/daily-context.md`, and `docs/local/TODO.md`. Continue SHOP-41 by adding the refund rows.

## Resume in a new conversation

Read `OVERVIEW.md`, `daily-context.md`, and `TODO.md` in that order. Consult `DONE.md` if you need the history of a completed item. Continue with the next step from the opening line and `Start here`.
