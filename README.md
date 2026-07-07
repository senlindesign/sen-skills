# sen-skills

Language: English | [中文](README.zh-CN.md)

Sen's collection of Claude skills.

## Skills

### [i-write](skills/i-write/) - Personal Writing System

Make AI write in a way that feels like you wrote it yourself.

`i-write` breaks public writing into four parts: frame, style, craft, and medium.
The first two belong to the writer and are extracted through a Deep Interview. The last two are shared writing tools and distribution rules.

Understand the writer first, then write. See [skills/i-write/README.md](skills/i-write/README.md).

## Installation

### Claude

Download the latest [`i-write.skill`](https://github.com/senlindesign/sen-skills/releases/latest/download/i-write.skill), then upload and enable it in Claude's Skills settings.

### Claude Code

Copy the whole `skills/i-write/` folder into your Claude Code skills directory:

```bash
mkdir -p ~/.claude/skills
cp -R skills/i-write ~/.claude/skills/
```
