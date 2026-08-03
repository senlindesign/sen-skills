# sen-skills

语言: [English](README.md) | 中文

Sen 的 Claude skills 合集。

## Skills

### [i-write](skills/i-write/) — 个人写作系统

让 AI 写出你亲笔写的文章。

把一篇公开文章拆成四个部件:观点(frame)、笔触(style)、技巧(craft)、媒介(medium)。
前两样属于你,由 Deep Interview 提取;后两样是公共的工具和规则。

先懂人,再写字。详见 [skills/i-write/README.zh-CN.md](skills/i-write/README.zh-CN.md)。

### [humanizer-en](skills/humanizer-en/) — 由作者参与塑形的英文写作

用作者自己的语言修改或共同写作英文内容，减少通用的 LLM 写作习惯。

`humanizer-en` 会把观点和语言表达分开处理，只从确认由人亲自写下或说出的材料中学习 voice。当作者的语言输入不够时，它会先继续提问，而不是擅自制造个人风格。它优化的是文字质量，不以 AI detector 分数为目标，也不会靠错别字或人为瑕疵伪装成人类写作。

## 安装

### Claude

下载最新的 [`i-write.skill`](https://github.com/senlindesign/sen-skills/releases/latest/download/i-write.skill)，然后在 Claude 的 Skills 设置里上传并启用。

### Claude Code

把需要的 Skill 文件夹放进你的 skills 目录:

```bash
mkdir -p ~/.claude/skills
cp -R skills/i-write ~/.claude/skills/
cp -R skills/humanizer-en ~/.claude/skills/
```

### Codex

把需要的 Skill 文件夹放进 Codex 的 skills 目录:

```bash
mkdir -p ~/.codex/skills
cp -R skills/humanizer-en ~/.codex/skills/
```
