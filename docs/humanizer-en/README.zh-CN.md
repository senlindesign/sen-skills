# Humanizer English：让作者参与语言塑形

语言：[English](README.md) | 中文

Humanizer 系列：英文写作 | [中文写作](../humanizer-zh/README.zh-CN.md)

> 改善 AI 辅助写作，要让作者重新参与语言本身。

`humanizer-en` 是一个用于审阅、修改和共同写作英文内容的 Skill。它会从作者确认由人亲自写下或说出的材料中寻找用词、节奏、重点和结构，减少通用的 LLM 写作习惯。它的 sibling `humanizer-zh` 会把同一套方法用于中文。

这个项目在 README 结构上参考了 [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh)、[blader/humanizer](https://github.com/blader/humanizer) 和 [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop)。我们的核心目标有所不同：不追求 detector 分数，也不把 AI 写出的内容伪装成人类写作。它要改善文字质量，同时提高作者真实参与的程度。

## 项目简介

多数 AI 写作流程会让人提供观点、例子和判断，然后由模型来组织每一句话。思想属于作者，语言表达却很容易落入模型默认的习惯。我们熟悉的 AI 味往往从这里进来，包括意义被拔高、为了转折而转折、为了完整而凑结构、没有根据的笃定，以及把前文再总结一次的结尾。

`humanizer-en` 把语言表达也视为作者工作的一部分。除了观点，它还会寻找作者真正使用过的词、句子碎片、节奏、情绪温度、重复方式和连接句。

它适合这些场景：

- 编辑或审阅一份 AI 辅助完成的英文草稿；
- 用自己的 voice 改写 post、文章、essay、脚本或产品叙事；
- 根据确认由自己亲自写下的样本校准语言；
- 把笔记或口述整理成英文，同时继续参与具体措辞；
- 了解哪些通用 LLM 写作习惯正在削弱一篇内容。

## AI 写作里缺失的另一半

Skill 会先把输入分成两类：

- **Thought material：** 观点、观察、例子、证据、判断和希望产生的效果。
- **Language material：** 常用表达、偏好的词、句子碎片、节奏、比喻、连接方式，以及作者平时真的会说出口的话。

一份草稿需要两类材料。当观点已经足够，语言输入却很少时，Skill 会先问一到三个很小的问题，不会擅自制造一个人的性格。一句粗糙的话或一段简短的语音就可以成为输入。

作者参与的不只是最终确认，也包括语言本身怎么被塑形。

## 安装

### 方法一：使用 `npx skills` 安装（推荐）

```bash
npx skills add senlindesign/sen-skills --skill humanizer-en
```

CLI 会识别本机支持的 coding agents，并把选中的 Skill 安装到对应目录。

### 方法二：克隆仓库后复制

```bash
git clone https://github.com/senlindesign/sen-skills.git
cd sen-skills
```

安装到 Codex：

```bash
mkdir -p ~/.codex/skills
cp -R skills/humanizer-en ~/.codex/skills/
```

安装到 Claude Code：

```bash
mkdir -p ~/.claude/skills
cp -R skills/humanizer-en ~/.claude/skills/
```

### 方法三：手动安装

1. 下载这个仓库的 ZIP 文件。
2. 把 `skills/humanizer-en/` 复制到 coding agent 的 skills 目录。
3. 新建一个任务或重新启动应用，让系统重新发现这个 Skill。

### 验证安装

新建一个任务，然后输入：

```text
Use $humanizer-en to audit this paragraph and show me where the language becomes generic.
```

如果安装成功，Skill 会被加载并进入 Audit 模式。

## 使用

### 1. 审阅一份草稿

```text
Use $humanizer-en to audit this English draft. Identify generic or unsupported language, but do not rewrite it yet.

[粘贴草稿]
```

Skill 会解释具体的编辑问题，不会把某一种模式当作 AI 写作的证明。

### 2. 用你的语言改写

```text
Use $humanizer-en to rewrite this post using my wording and the human-written samples I attached.

[粘贴草稿和样本]
```

只有确认由人亲自写下或说出的材料，才可以用来定义你的 voice。

### 3. 从笔记或口述开始共同写作

```text
Use $humanizer-en to co-write an English article from these notes. Ask me for language input when my voice is missing.

[粘贴笔记或口述]
```

Skill 会分别检查 Thought material 和 Language material，然后再决定是否开始完整起草。

### 4. 修改文件

```text
Use $humanizer-en to revise article.md. Preserve supported claims and mark any passage that still needs my language.
```

## 三种工作模式

### Audit

找出泛化、缺乏依据或不符合作者习惯的表达，不重写整篇内容。它给出的是编辑判断，不会预测 AI detector 将如何识别这段文字。

### Rewrite

在保留事实、观点和原意的前提下修改现有草稿。当原结构带有明显的通用 LLM 习惯时，Skill 可以重新合并、拆分、排序、扩写或压缩段落。

### Co-write

把想法、笔记或口述整理成英文内容。正式起草前，Skill 会分别检查观点输入和作者的语言输入是否足够。

## Skill 的工作流程

1. **判断材料来源。** 把每份输入标记为 human-authored、AI-generated 或 unknown。
2. **分开思想和语言。** 识别作者想讲什么，以及作者本人平时怎么说、怎么写。
3. **寻找作者的 voice。** 优先使用当前对话里的原话，再看确认由人写下的样本，最后参考明确的 style profile。
4. **补充缺失的语言。** 当表达输入不足时，提出一到三个容易回答的小问题。
5. **按照来源改写。** 保留有依据的信息，同时按照作者真正关心的部分重组结构。
6. **完成质量检查。** 检查意思、来源、voice、结构和可读性。

AI 生成或来源不明的草稿可以提供意思和有依据的信息，但不能用来定义作者的 voice。

## 它会识别哪些问题

编辑参考会从几个方向观察一份草稿。

### 内容和意义

- 把普通事实拔高成转折点、象征或更广泛的变化；
- 使用没有具体支撑的宣传性形容词；
- 引用「专家表示」「许多人认为」之类没有名字的权威；
- 从一条具体事实一路上升到社会、未来或人类。

### 语言和语法

- 反复使用 `not X, but Y` 和 `not only X, but Y`；
- 为了完整而凑出三点，或制造并不存在的范围；
- 为了避免重复而不断替换准确的名词；
- 用被动句或没有主语的句子隐藏真正做决定的人。

### 结构和节奏

- 让重要程度不同的观点拥有完全对称的篇幅；
- 自动补上一段通用的「挑战与未来」；
- 每个段落都完成相同的修辞动作；
- 每句话拥有同样的光滑程度，看不出作者真正强调什么。

### 对话残留和结尾

- 助手式开场、继续提供帮助的客套话和复制过来的 Markdown；
- 机械加粗、装饰性 emoji 和没有必要的多层列表；
- 通用的乐观句，以及把全文重新说一次的结尾；
- 假装亲密的开场和刻意制造的金句。

这些内容是编辑时的观察线索，不是一份禁词表。如果正式、工整或结构清楚本来就是作者的习惯，并且对读者有用，它们应该被保留下来。

## 示例：删除没有依据的意义

**修改前：**

> The update adds batch rename and offline mode, representing a transformative shift in how teams approach productivity. It is not merely a feature release, but a testament to our commitment to innovation.

**修改后：**

> The update adds batch rename and offline mode.

**发生了什么：**

- 删除了原始信息无法支撑的宏大意义；
- 删除了为了制造重点而加入的 `not X, but Y`；
- 保留了两个具体的产品变化；
- 让文字停在现有信息能够抵达的位置。

## 示例：向作者索取 Language material

**输入笔记：**

```text
- I have experimented with coding agents in my design work for a year.
- I shared the material at several companies and design communities.
- Beginners may need a framework at first.
```

这些笔记提供了足够的 Thought material，Language material 却很少。Skill 不会立即生成一篇光滑的个人 post，它可能先问：

```text
How would you explain the beginner part to a designer you know?
What word do you use for the feeling that keeps you trying after the framework stops mattering?
Is there one sentence from your talk that you would want to keep exactly as you said it?
```

回答会成为写作材料的一部分。个人 voice 来自这个人真正使用的语言，不来自模拟出来的习惯。

## 它不会做什么

- 为 AI detector 分数优化，或输出所谓的「人类写作比例」。
- 加入错别字、语法错误、异常 Unicode 或标点噪音。
- 编造个人经历、反应、笑话、引语、事实或来源。
- 从 AI 生成的草稿里学习作者的 voice。
- 在没有作者依据时，擅自加入第一人称、幽默、不确定感或刻意的混乱。
- 因为一段人写的内容正式、工整或结构清楚，就把它强行改松散。

## 文件结构

```text
skills/humanizer-en/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    └── research-and-patterns.md
```

- **`SKILL.md`** 包含材料来源顺序、三种工作模式、Language material 检查、改写流程和质量检查。
- **`agents/openai.yaml`** 包含 Skill 在界面里显示的 metadata。
- **`references/research-and-patterns.md`** 包含研究模型、编辑问题、Pangram 的 supporting evidence 边界和来源链接。

## 参考资源

- [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh)
- [blader/humanizer](https://github.com/blader/humanizer)
- [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop)
- [Pangram：All About Supporting Evidence](https://www.pangram.com/supporting-evidence)
- [Michael J. Reddy：The conduit metaphor](https://doi.org/10.1017/CBO9781139173865.012)

## 贡献

如果你发现新的弱写作模式、含糊的指令，或更适合让作者参与语言塑形的方法，欢迎提交 Issue 或 Pull Request。请尽量提供一组具体的修改前后对比，并说明其中哪些语言真正来自作者。

目标不在于让 AI 写作更难被检测。目标是让这段语言值得你把名字放上去。
