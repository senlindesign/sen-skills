# Humanizer English: Author-Led AI Writing

Language: English | [中文](README.zh-CN.md)

Humanizer family: English writing | [Chinese writing](../humanizer-zh/README.md)

> Improve AI-assisted English by bringing the author back into the language itself.

`humanizer-en` is a Skill for auditing, revising, and co-writing English prose. It draws wording, rhythm, emphasis, and structure from the author's confirmed human-written or human-spoken language instead of relying on generic LLM habits. Its sibling, `humanizer-zh`, applies the same method to Chinese.

This project takes structural inspiration from [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh), [blader/humanizer](https://github.com/blader/humanizer), and [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop). Its core objective is different: it does not optimize for detector scores or pretend that AI-written text is human-written. It improves the prose and increases genuine author participation.

## Project overview

Most AI writing workflows ask a person for ideas, examples, and opinions, then let the model shape every sentence. The thought may belong to the author, while the expression still comes from the model's default habits. That is where the familiar AI tone enters: inflated meaning, staged contrasts, compulsory completeness, vague confidence, and endings that recap everything.

`humanizer-en` treats language as part of authorship. Alongside the author's ideas, it looks for words, fragments, rhythm, emotional temperature, repetition, and transitions that the author would actually use.

Use it for:

- editing or reviewing an AI-assisted English draft;
- rewriting a post, article, essay, script, or product narrative in your voice;
- calibrating prose against your confirmed human-written samples;
- turning notes or a transcript into English while keeping you involved in the wording;
- learning which generic LLM patterns weaken a piece of writing.

## The missing half of AI writing

The Skill separates two kinds of input:

- **Thought material:** claims, observations, examples, evidence, judgment, and intended effect.
- **Language material:** characteristic phrases, preferred words, sentence fragments, rhythm, metaphors, transitions, and lines the author would naturally say.

A draft needs both. When the ideas are clear but the language input is thin, the Skill asks one to three small questions instead of silently manufacturing a personality. A rough sentence or short voice note is enough.

The author stays involved in forming the language, not only approving the final draft.

## Installation

### Method 1: Install with `npx skills` (recommended)

```bash
npx skills add senlindesign/sen-skills --skill humanizer-en
```

The CLI detects supported coding agents and installs the selected Skill into the appropriate directory.

### Method 2: Clone and copy

```bash
git clone https://github.com/senlindesign/sen-skills.git
cd sen-skills
```

For Codex:

```bash
mkdir -p ~/.codex/skills
cp -R skills/humanizer-en ~/.codex/skills/
```

For Claude Code:

```bash
mkdir -p ~/.claude/skills
cp -R skills/humanizer-en ~/.claude/skills/
```

### Method 3: Install manually

1. Download this repository as a ZIP file.
2. Copy `skills/humanizer-en/` into your agent's skills directory.
3. Start a new task or restart the application so the Skill can be discovered.

### Verify the installation

Start a new task and enter:

```text
Use $humanizer-en to audit this paragraph and show me where the language becomes generic.
```

If the installation succeeded, the Skill will load and choose Audit mode.

## Usage

### 1. Audit a draft

```text
Use $humanizer-en to audit this English draft. Identify generic or unsupported language, but do not rewrite it yet.

[Paste the draft]
```

The Skill explains the editorial problem without treating any pattern as proof of AI authorship.

### 2. Rewrite with your language

```text
Use $humanizer-en to rewrite this post using my wording and the human-written samples I attached.

[Paste the draft and samples]
```

Only confirmed human-written or human-spoken material is allowed to define your voice.

### 3. Co-write from notes or a transcript

```text
Use $humanizer-en to co-write an English article from these notes. Ask me for language input when my voice is missing.

[Paste notes or transcript]
```

The Skill checks Thought material and Language material separately before producing a full draft.

### 4. Revise a file

```text
Use $humanizer-en to revise article.md. Preserve supported claims and mark any passage that still needs my language.
```

## Three working modes

### Audit

Identify generic, unsupported, or author-inconsistent language without rewriting the whole text. The output is an editorial diagnosis, not a prediction about an AI detector.

### Rewrite

Revise an existing draft while preserving supported claims and intended meaning. The Skill may merge, split, reorder, expand, or compress the original structure when that structure follows generic LLM habits.

### Co-write

Turn ideas, notes, or a transcript into prose. Before drafting, the Skill checks whether it has enough input about both the thought and the author's way of expressing it.

## How the Skill works

1. **Classify the sources.** Mark each input as human-authored, AI-generated, or unknown.
2. **Separate thought from language.** Identify what the author means and how the author actually speaks or writes.
3. **Recover the author's voice.** Prefer current wording, then confirmed human-written samples, then an explicit style profile.
4. **Ask for missing language.** Use one to three focused questions when the author's expression is under-specified.
5. **Rewrite from provenance.** Preserve supported information while reshaping the structure around the author's attention.
6. **Run the quality gate.** Check meaning, provenance, voice, shape, and readability.

AI-generated and unknown drafts can supply meaning and supported information. They do not count as evidence of the author's voice.

## Patterns it can identify

The editorial reference groups weak writing patterns into several families.

### Content and meaning

- ordinary facts inflated into turning points, symbols, or broader shifts;
- promotional adjectives without observable support;
- vague authorities such as “experts say” or “many believe”;
- conclusions that climb from a concrete fact to society, the future, or humanity.

### Language and grammar

- repeated `not X, but Y` and `not only X, but Y` constructions;
- forced triads and false ranges;
- synonym cycling that replaces an accurate noun in every sentence;
- passive or subjectless sentences that hide who acted or decided.

### Structure and rhythm

- symmetrical sections that give equal space to unequal ideas;
- generic challenge-and-future passages;
- paragraphs that all make the same rhetorical move;
- uniformly polished sentences with no author-specific emphasis.

### Chat residue and endings

- assistant openers, offers to continue, and copied Markdown residue;
- mechanical bolding, decorative emoji, and unnecessary bullet hierarchies;
- generic optimism and conclusions that repeat the article;
- fake intimacy and manufactured punchlines.

These patterns are editing prompts, not a word blacklist. Formal, grammatical, or structured prose should remain intact when it belongs to the author and serves the reader.

## Example: removing unsupported significance

**Before:**

> The update adds batch rename and offline mode, representing a transformative shift in how teams approach productivity. It is not merely a feature release, but a testament to our commitment to innovation.

**After:**

> The update adds batch rename and offline mode.

**What changed:**

- removed significance that the source did not support;
- removed the staged `not X, but Y` contrast;
- kept the two concrete product changes;
- stopped where the available information stopped.

## Example: asking for the author's language

**Input notes:**

```text
- I have experimented with coding agents in my design work for a year.
- I shared the material at several companies and design communities.
- Beginners may need a framework at first.
```

The notes provide enough Thought material, but very little Language material. Instead of writing a polished personal post immediately, the Skill may ask:

```text
How would you explain the beginner part to a designer you know?
What word do you use for the feeling that keeps you trying after the framework stops mattering?
Is there one sentence from your talk that you would want to keep exactly as you said it?
```

The answers become part of the writing material. Personal voice comes from the person, not from simulated quirks.

## What it will not do

- Optimize for an AI-detector score or report a “human percentage.”
- Insert typos, grammar mistakes, unusual Unicode, or punctuation noise.
- Invent personal experiences, reactions, jokes, quotations, facts, or sources.
- Learn an author's voice from an AI-generated draft.
- Add first person, humor, uncertainty, or messiness without evidence from the author.
- Flatten competent human prose merely because it is formal, grammatical, or structured.

## File structure

```text
skills/humanizer-en/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    └── research-and-patterns.md
```

- **`SKILL.md`** contains the source hierarchy, working modes, language-input gate, rewriting workflow, and quality checks.
- **`agents/openai.yaml`** contains the Skill's interface metadata.
- **`references/research-and-patterns.md`** contains the research model, editorial pattern families, Pangram evidence boundary, and source links.

## References

- [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh)
- [blader/humanizer](https://github.com/blader/humanizer)
- [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop)
- [Pangram: All About Supporting Evidence](https://www.pangram.com/supporting-evidence)
- [Michael J. Reddy: The conduit metaphor](https://doi.org/10.1017/CBO9781139173865.012)

## Contributing

If you find a weak pattern, unclear instruction, or better way to involve the author in language formation, open an Issue or Pull Request. Please include a concrete before-and-after example and explain which part came from the author.

The goal is not to make AI writing harder to detect. The goal is to make the language worth putting your name on.
