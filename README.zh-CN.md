# sen-skills

语言: [English](README.md) | 中文

Sen 的 AI agent skills 合集。

## Skills

### [i-write](skills/i-write/) — 个人写作系统

让 AI 写出你亲笔写的文章。

把一篇公开文章拆成四个部件:观点(frame)、笔触(style)、技巧(craft)、媒介(medium)。
前两样属于你,由 Deep Interview 提取;后两样是公共的工具和规则。

先懂人,再写字。详见 [skills/i-write/README.zh-CN.md](skills/i-write/README.zh-CN.md)。

### Humanizer｜由作者参与塑形的写作

思想是物体，语言是容器。Humanizer 系列让作者同时参与两者的塑形。

| Skill | 语言 | 说明 |
| --- | --- | --- |
| `humanizer-en` | 英文 | [English](docs/humanizer-en/README.md) · [中文](docs/humanizer-en/README.zh-CN.md) |
| `humanizer-zh` | 简体中文 | [English](docs/humanizer-zh/README.md) · [中文](docs/humanizer-zh/README.zh-CN.md) |

两个 Skill 都会分开处理 Thought material 和 Language material，只从确认由人提供的材料中学习 voice。语言容器缺少作者输入时，它会继续提问。问题识别服务于写作流程，目标不在 detector 规避。

## 安装

### Skills CLI

使用 `npx skills` 安装需要的 Humanizer 版本：

```bash
npx skills add senlindesign/sen-skills --skill humanizer-en
npx skills add senlindesign/sen-skills --skill humanizer-zh
```

### Claude

下载最新的 [`i-write.skill`](https://github.com/senlindesign/sen-skills/releases/latest/download/i-write.skill)，然后在 Claude 的 Skills 设置里上传并启用。

### Claude Code

把需要的 Skill 文件夹放进你的 skills 目录:

```bash
mkdir -p ~/.claude/skills
cp -R skills/i-write ~/.claude/skills/
cp -R skills/humanizer-en ~/.claude/skills/
cp -R skills/humanizer-zh ~/.claude/skills/
```

### Codex

把需要的 Skill 文件夹放进 Codex 的 skills 目录:

```bash
mkdir -p ~/.codex/skills
cp -R skills/humanizer-en ~/.codex/skills/
cp -R skills/humanizer-zh ~/.codex/skills/
```
