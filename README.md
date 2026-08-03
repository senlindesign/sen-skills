# sen-skills

Language: English | [中文](README.zh-CN.md)

Sen's collection of AI agent skills.

## Skills

### [i-write](skills/i-write/) - Personal Writing System

Make AI write in a way that feels like you wrote it yourself.

`i-write` breaks public writing into four parts: frame, style, craft, and medium.
The first two belong to the writer and are extracted through a Deep Interview. The last two are shared writing tools and distribution rules.

Understand the writer first, then write. See [skills/i-write/README.md](skills/i-write/README.md).

### Humanizer - Author-Led Writing

Ideas are the objects; language is the container. The Humanizer family brings the author into shaping both.

| Skill | Language | Guide |
| --- | --- | --- |
| `humanizer-en` | English | [English](docs/humanizer-en/README.md) · [中文](docs/humanizer-en/README.zh-CN.md) |
| `humanizer-zh` | Simplified Chinese | [English](docs/humanizer-zh/README.md) · [中文](docs/humanizer-zh/README.zh-CN.md) |

Both Skills separate Thought material from Language material, learn voice only from confirmed human input, and ask the author for language when the container is under-specified. Pattern recognition supports the workflow; detector evasion is not the goal.

## Installation

### Skills CLI

Install either Humanizer variant with `npx skills`:

```bash
npx skills add senlindesign/sen-skills --skill humanizer-en
npx skills add senlindesign/sen-skills --skill humanizer-zh
```

### Claude

Download the latest [`i-write.skill`](https://github.com/senlindesign/sen-skills/releases/latest/download/i-write.skill), then upload and enable it in Claude's Skills settings.

### Claude Code

Copy the Skill you want into your Claude Code skills directory:

```bash
mkdir -p ~/.claude/skills
cp -R skills/i-write ~/.claude/skills/
cp -R skills/humanizer-en ~/.claude/skills/
cp -R skills/humanizer-zh ~/.claude/skills/
```

### Codex

Copy the Skill you want into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cp -R skills/humanizer-en ~/.codex/skills/
cp -R skills/humanizer-zh ~/.codex/skills/
```
