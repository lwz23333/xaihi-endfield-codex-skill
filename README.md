# Xaihi Endfield Codex Skill

赛希（Xaihi / 塞拉菲娜·赛希）角色 Skill，面向 Codex 的角色扮演与角色知识调用。

本 Skill 基于公开资料、公开剧情语料与可追溯来源进行整理和行为蒸馏，用于模拟赛希的表达风格、知识边界、世界观锚点和 Baker 特殊交互。

## Build And Sources

This Skill was primarily built with [qian-gugugaga/Character_Skill_Producer](https://github.com/qian-gugugaga/Character_Skill_Producer).

[AngChow/endfield-story-corpus](https://github.com/AngChow/endfield-story-corpus) was used as one of the public story corpus sources for selected Baker, mission, operator file and worldbuilding references.

## Acknowledgements

- Built primarily with [Character_Skill_Producer](https://github.com/qian-gugugaga/Character_Skill_Producer).
- Public story corpus references include [endfield-story-corpus](https://github.com/AngChow/endfield-story-corpus).
- Skill generation and refinement were assisted by [Codex](https://github.com/codex).

> 愿知识庇护您的道路。

## Installation

Recommended: clone this repository directly into your local Codex skills directory.

Windows PowerShell:

```powershell
git clone https://github.com/lwz23333/xaihi-endfield-codex-skill.git "$env:USERPROFILE\.codex\skills\xaihi-endfield"
```

If the directory already exists and you want to update it:

```powershell
cd "$env:USERPROFILE\.codex\skills\xaihi-endfield"
git pull
```

After installation, start a new Codex conversation and invoke the skill with:

```text
使用 xaihi-endfield skill，扮演赛希小姐和我聊天
```

or reference the local skill file explicitly:

```text
[$xaihi-endfield](C:\Users\<your-user>\.codex\skills\xaihi-endfield\SKILL.md)
赛希小姐，晚上好
```

If the skill does not appear immediately, restart Codex or start a fresh conversation so the skills list can reload.

## Using With Other Agents

This repository is designed as a Codex Skill, but most of its content is plain Markdown and can be adapted to other agents.

General adaptation method:

1. Put the full content of `SKILL.md` into the agent's system prompt, character prompt, custom instruction, or long-term memory.
2. Keep `manifest.json` and `references/` as retrieval or knowledge files if the agent supports file-based knowledge.
3. Tell the agent to follow the role-play rules, knowledge boundaries and source boundary in `SKILL.md` before entering character mode.
4. If the agent has limited context, load `SKILL.md` first and only add selected files from `references/` when needed.

Minimal prompt:

```text
Read and follow the character instructions in SKILL.md.
Use references/ only as supporting knowledge.
Stay within the stated source boundary and do not invent unreleased canon.
Now role-play as Xaihi / 赛希.
```

Suggested mapping:

| Agent type | How to adapt |
|---|---|
| ChatGPT / custom GPT-style agents | Put `SKILL.md` into Instructions and upload `references/` as knowledge files. |
| Claude Projects | Add `SKILL.md` as project instructions and upload `references/` as project knowledge. |
| Local LLM frontends | Paste `SKILL.md` into the system prompt; use `references/` with RAG if available. |
| RAG agents | Index `references/`, but keep `SKILL.md` as the highest-priority behavior prompt. |
| Simple chatbots | Use only `SKILL.md`; skip research files if context is too small. |

Do not treat `references/` as higher priority than `SKILL.md`. The research files explain the distillation, while `SKILL.md` defines the actual runtime behavior.

## Contents

- `SKILL.md`: main skill instructions
- `manifest.json`: metadata, coverage boundary and source summary
- `CHANGELOG.md`: update history
- `references/sources.json`: source index
- `references/distillation.md`: behavior distillation notes
- `references/worldbuilding.md`: usable worldbuilding boundaries
- `references/research/`: research notes by topic

## Boundary

This is a fan-made Codex Skill.

It is not affiliated with, endorsed by, or sponsored by Hypergryph, Gryphline, or any official Arknights: Endfield entity.

Original character, setting, story and related official materials belong to their respective rights holders.

## Privacy

This repository is a cleaned release package. It does not include private chat logs, local workspace caches, raw terminal logs, local account credentials, or unrelated working files.

## Update Date

Current source boundary: 2026-06-10.
