# Humanizer Chinese：一起塑形语言的容器

语言：[English](README.md) | 中文

Humanizer 系列：[英文写作](../humanizer-en/README.zh-CN.md) | 中文写作

> 作者应该同时参与思想和语言的塑形。

`humanizer-zh` 是一个用于审阅、修改和共同写作简体中文的 Skill。它与 `humanizer-en` 使用同一套 author-led 方法，同时为中文词汇、句法、节奏、标点、中英混排和修辞习惯保留独立的语言层。

它不为 AI detector 分数优化，也不试图把 AI 写出的内容冒充为人类作品。它通过让作者真正参与表达过程来改善文字。

## Humanizer 统一使用的模型

Humanizer 系列使用 Michael J. Reddy 的 conduit metaphor 诊断写作过程：

- 思想和观点是要传递的物体；
- 语言表达是承载它们的容器；
- 交流把容器送到读者面前。

现在很多 AI 写作流程已经让人参与了第一层。作者提供观点、例子和判断，然后模型独自塑造整个容器，最终文字便带上模型默认的用词、节奏、结构和确定程度。

`humanizer-zh` 把人带回第二层。它会在写作前和写作过程中收集 Language material，再用中文特有的编辑问题寻找容器从哪里开始失去作者。

## 如何参考上游 Humanizer-zh

[op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) 整理了许多有用的中文问题，包括意义拔高、宣传语言、模糊归因、仪式化对比、三段式、同义词循环、虚假范围、填充词、聊天残留和通用结尾。

本 Skill 会把这些观察放进 Audit 和 Rewrite 工作流。它不会照搬上游的表述、固定 24 条结构、个性注入规则或质量评分。问题识别仍然只是一种诊断手段。当作者语言缺失时，工作流会向作者提问，不让模型自行模拟个性。

## 适用场景

- 审阅一份显得泛化或过分光滑的中文草稿；
- 使用作者自己的词和确认由人写下的样本改写 AI 辅助内容；
- 把口述整理成中文文章，同时保留说话者的表达；
- 根据既有中文 voice profile 校准一份草稿；
- 找出意义拔高、主体缺失、节奏同质或平台套话。

## 安装

### 使用 `npx skills` 安装（推荐）

```bash
npx skills add senlindesign/sen-skills --skill humanizer-zh
```

### 手动安装到 Codex

```bash
git clone https://github.com/senlindesign/sen-skills.git
mkdir -p ~/.codex/skills
cp -R sen-skills/skills/humanizer-zh ~/.codex/skills/
```

### 手动安装到 Claude Code

```bash
git clone https://github.com/senlindesign/sen-skills.git
mkdir -p ~/.claude/skills
cp -R sen-skills/skills/humanizer-zh ~/.claude/skills/
```

安装完成后，请新建一个任务或重新启动应用。

## 使用

### Audit

```text
Use $humanizer-zh to audit this Chinese draft. Explain where the language becomes generic, but do not rewrite it yet.

[粘贴草稿]
```

### Rewrite

```text
Use $humanizer-zh to rewrite this Chinese post using my wording and the confirmed human-written samples I attached.

[粘贴草稿和样本]
```

### Co-write

```text
Use $humanizer-zh to co-write a Chinese article from these notes. Ask me for Language material before you invent phrasing that is supposed to sound like me.

[粘贴笔记或口述]
```

## Thought material 和 Language material

Skill 会分别检查两类输入：

- **Thought material：** 观点、例子、证据、判断和希望产生的效果。
- **Language material：** 偏好的词、句子碎片、节奏、情绪温度、连接方式、标点和中英混排习惯。

如果观点已经清楚，语言输入却不够，Skill 可能会问：

```text
这一段如果讲给同领域的朋友，你会怎么说？
哪一句最不像你？你平时会换成什么说法？
口述里有没有一句话需要完全保留原来的说法？
```

回答会成为写作材料的一部分。

## 中文特有的诊断问题

参考文件包括这些模式：

- 把意义拔高成里程碑、转折、象征或行业变化；
- `赋能`、`助力`、`打造`、`构建` 等宣传词成组出现；
- 模糊归因和没有来源的专家判断；
- 用 `从而`、`进而`、`确保`、`彰显`、`体现` 自动补出的分析尾巴；
- 重复使用 `不是 X，而是 Y` 和 `不仅是 X，更是 Y`；
- 强行凑三点、堆叠四字格，以及虚假的 `从 X 到 Y`；
- 同义词循环，以及回避 `是`、`有`、`可以` 等简单谓语；
- 机械连接、同质节奏、格式残留和通用乐观结尾；
- 假亲密、制造金句和助手式收尾。

这些模式是编辑判断的线索，不是禁词。某种表达确实来自作者、符合媒介并承担真实含义时，应该保留。

## 示例：诊断语言容器

**修改前：**

> 此次更新不仅是一次功能升级，更是团队持续创新的重要里程碑。通过新增批量重命名与离线模式，进一步赋能用户在不断演进的工作场景中高效协作。

**修改后：**

> 这次更新增加了批量重命名和离线模式。

这次修改删除了没有依据的意义拔高和仪式化对比，保留了两个具体变化。作者没有提供笑话、经历或个人反应，因此结果里也不会擅自加入这些内容。

## 它不会做什么

- 输出人类写作比例，或针对 detector 进行优化；
- 加入错别字、语病、随机标点或异常 Unicode；
- 编造经历、事实、反应、幽默、引语或来源；
- 从 AI 生成的草稿里学习作者的 voice；
- 强制加入第一人称、长短句变化、口语或刻意的混乱；
- 把上游问题清单当成替换表。

## 文件结构

```text
skills/humanizer-zh/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    └── research-and-patterns.md
```

## 参考资源

- [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh)
- [Wikipedia：Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)
- [Michael J. Reddy：The conduit metaphor](https://doi.org/10.1017/CBO9781139173865.012)
- [Can You Make It Sound Like You?](https://aclanthology.org/2026.acl-long.2030/)

目标不在于混淆作者身份的检测。目标是确保作者参与了思想所使用的语言容器。
