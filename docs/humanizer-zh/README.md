# Humanizer Chinese: Co-shape the Language

Language: English | [中文](README.zh-CN.md)

Humanizer family: [English writing](../humanizer-en/README.md) | Chinese writing

> The author should shape both the thought and the language carrying it.

`humanizer-zh` is a Skill for auditing, revising, and co-writing Simplified Chinese. It shares the same author-led method as `humanizer-en`, with a separate language layer for Chinese vocabulary, syntax, rhythm, punctuation, code-switching, and rhetorical habits.

It does not optimize for AI-detector scores or attempt to pass AI-written text off as human work. It improves the prose by giving the author a real role in shaping its expression.

## The shared Humanizer model

The Humanizer family uses Michael J. Reddy's conduit metaphor as a diagnostic model:

- ideas and opinions are the objects;
- linguistic expressions are the containers;
- communication sends those containers to a reader.

Many AI writing workflows already involve the person at the first layer. The author supplies the ideas, examples, and judgment. The model then shapes the entire container on its own, so the final text carries the model's default wording, rhythm, structure, and degree of certainty.

`humanizer-zh` brings the person into that second layer. It collects Language material before and during writing, then uses Chinese-specific editing patterns to find where the container has become generic.

## What it borrows from upstream Humanizer-zh

[op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) documents useful Chinese-language symptoms, including inflated significance, promotional language, vague attribution, formulaic contrast, forced triads, synonym cycling, false ranges, filler, chat residue, and generic endings.

This Skill uses those observations inside its Audit and Rewrite workflow. It does not copy the upstream wording, fixed 24-pattern structure, personality injection rules, or quality score. Pattern recognition remains a diagnostic tool. When the author's language is missing, the workflow asks the author instead of asking the model to simulate personality.

## When to use it

- Review a Chinese draft that feels generic or overly polished.
- Rewrite AI-assisted Chinese using the author's own words and human-written samples.
- Turn spoken notes into a Chinese article while preserving the speaker's phrasing.
- Compare a draft with an established Chinese voice profile.
- Find where a document has inflated meaning, hidden actors, uniform rhythm, or platform clichés.

## Installation

### Install with `npx skills` (recommended)

```bash
npx skills add senlindesign/sen-skills --skill humanizer-zh
```

### Install manually for Codex

```bash
git clone https://github.com/senlindesign/sen-skills.git
mkdir -p ~/.codex/skills
cp -R sen-skills/skills/humanizer-zh ~/.codex/skills/
```

### Install manually for Claude Code

```bash
git clone https://github.com/senlindesign/sen-skills.git
mkdir -p ~/.claude/skills
cp -R sen-skills/skills/humanizer-zh ~/.claude/skills/
```

Start a new task or restart the application after installation.

## Usage

### Audit

```text
Use $humanizer-zh to audit this Chinese draft. Explain where the language becomes generic, but do not rewrite it yet.

[Paste the draft]
```

### Rewrite

```text
Use $humanizer-zh to rewrite this Chinese post using my wording and the confirmed human-written samples I attached.

[Paste the draft and samples]
```

### Co-write

```text
Use $humanizer-zh to co-write a Chinese article from these notes. Ask me for Language material before you invent phrasing that is supposed to sound like me.

[Paste notes or transcript]
```

## Thought material and Language material

The Skill checks two inputs separately:

- **Thought material:** claims, examples, evidence, judgment, and intended effect.
- **Language material:** preferred words, sentence fragments, rhythm, emotional temperature, transitions, punctuation, and Chinese-English code-switching.

If the thought is clear but the language is under-specified, the Skill may ask:

```text
How would you explain this part to a friend who works in the same field?
Which sentence sounds least like you, and what would you say instead?
Is there one phrase from your voice note that should stay exactly as you said it?
```

The answers become part of the writing material.

## Chinese-specific diagnostics

The reference covers patterns such as:

- significance inflated into milestones, shifts, symbols, or industry change;
- clusters of promotional terms such as `赋能`, `助力`, `打造`, and `构建`;
- vague attribution and unsupported expert claims;
- explanatory tails built with `从而`, `进而`, `确保`, `彰显`, or `体现`;
- repeated `不是 X，而是 Y` and `不仅是 X，更是 Y` constructions;
- forced triads, stacked four-character phrases, and false `从 X 到 Y` ranges;
- synonym cycling and avoidance of simple predicates such as `是`, `有`, and `可以`;
- mechanical transitions, homogeneous rhythm, formatting residue, and generic optimism;
- fake intimacy, manufactured punchlines, and assistant-style closings.

These are prompts for editorial judgment, not banned expressions. Keep a pattern when it belongs to the author, fits the medium, and carries real meaning.

## Example: diagnose the container

**Before:**

> 此次更新不仅是一次功能升级，更是团队持续创新的重要里程碑。通过新增批量重命名与离线模式，进一步赋能用户在不断演进的工作场景中高效协作。

**After:**

> 这次更新增加了批量重命名和离线模式。

The rewrite removes unsupported significance and ceremonial contrast while preserving the two concrete changes. It does not add a joke, anecdote, or personal reaction because the author did not supply one.

## What it will not do

- Report a human percentage or optimize against a detector.
- Add typos, grammar mistakes, random punctuation, or unusual Unicode.
- Invent experiences, facts, reactions, humor, quotations, or sources.
- Learn the author's voice from an AI-generated draft.
- Force first person, sentence-length variation, informality, or messiness.
- Treat an upstream pattern list as a replacement table.

## File structure

```text
skills/humanizer-zh/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    └── research-and-patterns.md
```

## References

- [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh)
- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)
- [Michael J. Reddy: The conduit metaphor](https://doi.org/10.1017/CBO9781139173865.012)
- [Can You Make It Sound Like You?](https://aclanthology.org/2026.acl-long.2030/)

The goal is not to confuse authorship detection. The goal is to make sure the author helped shape the language carrying the thought.
