---
name: humanizer-en
description: Revise or co-write English prose so its wording, rhythm, emphasis, and structure draw from the author's own language rather than generic LLM habits. Use when a user asks to humanize, de-slop, rewrite AI-sounding English, make a draft sound more like them, calibrate prose against their human-written samples, or turn notes and spoken ideas into English while keeping the author involved in the language itself.
---

# Humanizer English

Improve English prose by restoring author-specific language. Treat authorship as ownership of both the ideas and the words used to express them.

Do not optimize for an AI-detector score. Do not claim AI-written text is human-written. Improve the prose and increase genuine author participation.

## Use the container as a diagnostic

Use Michael J. Reddy's conduit metaphor as a simple diagnostic model:

- ideas and meanings are the objects;
- linguistic expressions are the containers;
- communication sends those containers to a reader.

Do not treat language as neutral packaging. Word choice, syntax, rhythm, and emphasis also shape the thought. The author must therefore participate in forming the container, not only supply the object.

## Establish the source hierarchy

First classify each input as **human-authored**, **AI-generated**, or **unknown**. Only confirmed human-authored or human-spoken material may define the author's voice. Use AI-generated and unknown drafts as sources of meaning and supported information, not as evidence of personal style.

Use confirmed human language sources in this order:

1. The author's own wording in the current conversation, transcript, notes, or rough draft.
2. Human-written samples from the same author, preferably in the same medium.
3. An explicit voice or style profile supplied by the author.
4. Plain, unornamented English when no author-language source exists.

Let current instructions override older samples. Never treat an AI-generated draft as evidence of the author's natural voice merely because the user approved its ideas.

## Choose a mode

Infer the mode from the request. Ask only when the choice changes the result.

### Audit

Identify generic or unsupported language without rewriting the whole text. Explain the problem in editorial terms, not as proof of AI authorship.

### Rewrite

Revise an existing English draft while preserving its supported claims and intended meaning. Change the structure freely when the original structure is formulaic.

### Co-write

Turn ideas, notes, or a transcript into prose. Run the language-input gate before producing a full draft.

## Run the language-input gate

Check for two separate kinds of material:

- **Thought material:** claims, observations, examples, evidence, judgment, and intended effect.
- **Language material:** characteristic phrases, preferred words, sentence fragments, emotional temperature, rhythm, metaphors, transitions, and lines the author would actually say.

Proceed when both are sufficient for the requested length. When thought material is sufficient but language material is thin, do not silently manufacture a personal voice.

First try to recover language from available human-written samples. If those are missing or do not cover the current register, ask one to three small questions that are easy to answer aloud, such as:

- "How would you explain this part to a designer you know?"
- "Which sentence here sounds least like you, and what would you say instead?"
- "Should this paragraph sound excited, skeptical, annoyed, or matter-of-fact?"
- "Is there a word, comparison, or phrase you keep returning to when you talk about this?"
- "What would you never say here?"

Invite a short voice note or rough, ungrammatical sentences when that is easier. Treat hesitations, self-corrections, repeated words, and code-switching as evidence about voice, not clutter to erase automatically.

If the user explicitly asks for an immediate draft without supplying more language, write plain English and describe it as an AI-led draft. Do not fabricate quirks, anecdotes, uncertainty, humor, or mistakes to simulate a person.

## Calibrate the author's language

Before rewriting with samples, extract a compact working map:

- sentence-length range and common sentence shapes;
- paragraph density and where short sentences appear;
- preferred verbs, nouns, transitions, and recurring phrases;
- first-person frequency and level of directness;
- punctuation, contractions, fragments, repetition, and code-switching;
- how openings enter the subject and how endings stop;
- which parts the author expands, compresses, doubts, or reacts to.

Use this map silently unless the user asks to see it. Match patterns, not isolated quirks. Do not copy distinctive sentences from old work into an unrelated draft.

Use cross-language samples cautiously. They can reveal attention, stance, paragraph movement, and preferred kinds of examples, but they cannot establish the author's English vocabulary, contractions, idioms, or punctuation. Ask for English language input when those choices matter.

## Rewrite from provenance

1. Trace every factual claim, anecdote, date, name, quotation, and citation to the input or an approved source.
2. Preserve the information, not the original shape. Merge, split, reorder, expand, or compress as the author's attention demands.
3. Reuse the author's live vocabulary before reaching for synonyms.
4. Prefer concrete nouns and active subjects when the source supports them.
5. Let emphasis be uneven. Spend more language where the author has judgment and less where the draft merely connects sections.
6. Keep uncertainty only when the author is uncertain. Remove generic hedging and generic confidence.
7. Preserve deliberate repetition, awkwardness, or register shifts when samples show they belong to the author.
8. Match the destination medium without replacing the author's voice with platform clichés.

For Audit and Rewrite modes, read [references/research-and-patterns.md](references/research-and-patterns.md) before editing.

## Protect factual and authorship integrity

- Never invent a personal experience, concrete detail, reaction, joke, source, or quotation.
- Never insert typos, grammar errors, unusual Unicode, random synonym swaps, or punctuation noise to appear human.
- Never use a detector, detector score, or "human percentage" as an acceptance test.
- Never flatten competent human prose merely because it is formal, grammatical, or structured.
- Never force sentence-length variation, first person, humor, or messiness when the author's samples do not support them.

## Quality gate

Before delivery, check five things:

1. **Meaning:** Did every supported claim survive?
2. **Provenance:** Can each personal detail and strong judgment be traced to the author?
3. **Voice:** Did the wording come from current language input or stable patterns in human-written samples?
4. **Shape:** Does the structure follow the author's attention rather than a generic complete outline?
5. **Readability:** Is the English clear without becoming smoother, grander, or more certain than the author?

Revise again if the text could plausibly carry any author's name after swapping the topic nouns.

## Deliver

Default to:

1. the revised English text;
2. a short note naming the main language choices, only when useful;
3. a **Needs your language** section when unresolved passages require the author's wording.

Do not output a human-likeness score. Do not narrate every removed pattern unless the user requested an audit.
