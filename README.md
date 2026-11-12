# Daily Summarize

[简体中文](#简体中文) · [English](#english)

## 简体中文

**Daily Summarize** 是一个用于项目交接的 Claude Code 技能。开始任务时记录目标，工作中更新约定和进度，收尾时把下一步写清楚。第二天开一个新对话，贴上两句开场白，就能接着做。

技能将项目上下文保存在 `docs/local/` 下的四份 Markdown 文件中。

| 文件 | 记录内容 |
| --- | --- |
| `OVERVIEW.md` | 当前目标、进度、长期约定和相关链接 |
| `daily-context.md` | 最近一个工作日的进展，以及下次从哪一步开始 |
| `TODO.md` | 待办事项 `[ ]` 和等待中的事项 `[~]` |
| `DONE.md` | 按任务归档的完成记录，以及相关 PR、提交或结论 |

在 Git 项目里，技能通过本地排除文件 `.git/info/exclude` 将未跟踪的笔记留在本机。

### 安装与使用

1. 下载 [SKILL.md](SKILL.md)，放到 `~/.claude/skills/daily-summarize/SKILL.md`，就能在本机的多个项目中使用。只在一个项目里使用时，放到该项目的 `.claude/skills/daily-summarize/SKILL.md`。
2. 在 Claude Code 中输入 `/daily-summarize`，然后说明当前任务或说「帮我收尾」。收尾后，把生成的开场白贴进下一次对话。

> 读取 `docs/local/OVERVIEW.md`、`docs/local/daily-context.md` 和 `docs/local/TODO.md`。继续 SHOP-41，补上退款明细行。

## English

**Daily Summarize** is a Claude Code skill for handing off work between sessions. It records the goal when work starts, updates project rules and progress as they change, and captures the next step at wrap-up. Paste a two-sentence opening prompt into a new conversation to pick up where you left off.

The skill stores project context in four Markdown files under `docs/local/`.

| File | Contents |
| --- | --- |
| `OVERVIEW.md` | Current goal, status, standing rules, and useful links |
| `daily-context.md` | The latest workday's progress and where to start next |
| `TODO.md` | Open `[ ]` and waiting `[~]` items |
| `DONE.md` | Completed work by ticket, with the relevant PR, commit, or outcome |

In Git projects, the skill uses the local `.git/info/exclude` file to keep untracked notes on your machine.

### Install and use

1. Download [SKILL.md](SKILL.md) and save it as `~/.claude/skills/daily-summarize/SKILL.md` to use it across projects on your machine. For one project, save it as `.claude/skills/daily-summarize/SKILL.md` inside that project.
2. In Claude Code, type `/daily-summarize` and describe the current task or ask to wrap up. Paste the generated opening prompt into your next conversation.

> Read `docs/local/OVERVIEW.md`, `docs/local/daily-context.md`, and `docs/local/TODO.md`. Continue SHOP-41 by adding the refund rows.
