# sen-skills

Language: English | [中文](README.zh-CN.md)

Sen's collection of Claude skills.

## Skills

### [i-write](skills/i-write/) - Personal Writing System

Make AI write in a way that feels like you wrote it yourself.

`i-write` breaks public writing into four parts: frame, style, craft, and medium.
The first two belong to the writer and are extracted through a Deep Interview. The last two are shared writing tools and distribution rules.

Understand the writer first, then write. See [skills/i-write/README.md](skills/i-write/README.md).

### [humanizer-en](skills/humanizer-en/) - Author-Led English Writing

Revise or co-write English prose using the author's own language instead of generic LLM habits.

`humanizer-en` separates ideas from expression, learns voice only from confirmed human-written or human-spoken material, and asks for more language when the author's wording is missing. It improves prose quality without optimizing for AI-detector scores or fabricating human quirks.

## Installation

### Claude

Download the latest [`i-write.skill`](https://github.com/senlindesign/sen-skills/releases/latest/download/i-write.skill), then upload and enable it in Claude's Skills settings.

### Claude Code

Copy the Skill you want into your Claude Code skills directory:

```bash
mkdir -p ~/.claude/skills
cp -R skills/i-write ~/.claude/skills/
cp -R skills/humanizer-en ~/.claude/skills/
```

### Codex

Copy the Skill you want into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cp -R skills/humanizer-en ~/.codex/skills/
```
