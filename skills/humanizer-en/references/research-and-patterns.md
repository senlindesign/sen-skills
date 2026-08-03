# Research and editorial patterns

Use this reference when auditing or revising English prose. Treat the patterns as editing prompts, not proof of AI authorship and not a detector-evasion checklist.

## Research model

Michael J. Reddy's "conduit metaphor" describes a common model in which ideas are objects, linguistic expressions are containers, and communication sends the containers to a recipient. Reddy presented the metaphor critically. Language does not carry a thought unchanged, so involve the author in shaping the expression instead of treating wording as interchangeable packaging.

Research on post-editing LLM drafts found that people can move a draft closer to their own style, but the result may remain measurably closer to LLM prose and less stylistically diverse than fully human-authored writing. This supports collecting author language before and during drafting rather than relying only on cleanup afterward.

Studies comparing human and machine prose report broader signals than a blacklist of words. Human writing often shows greater semantic and stylistic variation, while experienced readers also notice formality, originality, clarity, factual grounding, and the relationship between detail and argument.

## Pattern families

Flag a pattern only when it harms the prose or conflicts with the author's samples.

### Inflated meaning

Look for ordinary facts inflated into turning points, testaments, transformations, broader shifts, enduring legacies, or symbols. Restore the specific claim and explain its significance only when the author supplied that judgment.

### Promotional adjectives

Look for clusters such as seamless, vibrant, groundbreaking, powerful, compelling, profound, remarkable, and transformative. Replace evaluation with observable detail or retain the adjective only when it expresses the author's actual reaction.

### Vague authority

Look for "experts say," "industry reports suggest," "many believe," and unnamed critics. Name the source, qualify the claim honestly, or remove it.

### Superficial explanatory tails

Look for participial endings that add symbolic meaning without evidence: "highlighting," "showcasing," "ensuring," "reflecting," or "underscoring." State the relationship directly or cut it.

### Formulaic contrast

Look for repeated "not only X but Y," "not X, but Y," false binaries, and staged reveal structures. Keep a real distinction when the author's reasoning depends on it; remove ceremonial contrast.

### Compulsory completeness

Look for forced triads, symmetrical sections, generic challenge-and-future passages, or outlines that give equal space to unequal ideas. Let the author's attention determine length and order.

### Synonym cycling

Look for a person, product, or idea renamed in every sentence to avoid repetition. Reuse the accurate noun.

### False ranges and abstraction ladders

Look for "from X to Y" when the endpoints do not form a real scale, or for prose that repeatedly climbs from a concrete fact to society, the future, or humanity. Stop at the strongest supported level.

### Missing actors

Look for passive or subjectless sentences that hide who decided, observed, designed, or changed something. Name the actor when known. Do not force active voice when the actor is unknown or irrelevant.

### Chat and formatting residue

Remove assistant openers, offers to continue, copied Markdown markers, mechanical bolding, decorative emoji, and unnecessary bullet hierarchies when they do not belong to the destination medium.

### Filler and overqualification

Cut throat-clearing, redundant signposting, excessive hedging, and repeated explanations of what the text is about to do. Preserve caution that reflects real uncertainty.

### Generic optimism and recap endings

Cut upbeat send-offs and conclusions that repeat the article. End where the author's thought actually ends, whether that is a concrete consequence, unresolved tension, question, or short judgment.

### Manufactured punchlines

Look for stacked fragments, universal aphorisms, and sentences engineered to become quotations. A short ending is useful only when the preceding thought earns it and the author's samples support that rhythm.

### Fake intimacy

Look for "Honestly?", "Here's the thing," "Let's be real," and other staged candid openers used before an ordinary claim. Keep conversational phrasing only when it is natural for this author.

### Homogeneous rhythm

Look beyond sentence length. Check whether every paragraph makes the same move, every sentence has the same level of polish, and every transition explains itself. Restore the author's natural distribution rather than alternating long and short sentences mechanically.

## Pangram evidence boundary

Pangram publicly lists Markdown residue, AI-associated phrases, em-dash overuse, bullet lists, triads, "not just X but Y," unusual Unicode, AI-style headers, and misplaced emoji as supporting evidence. Pangram also states that these extracted patterns are not direct inputs to its classifier, which synthesizes many document-level signals.

Use that list to notice weak prose already worth editing. Do not treat it as a blacklist, remove legitimate author habits, or tune text against Pangram.

## Sources

- Michael J. Reddy, "The conduit metaphor: A case of frame conflict in our language about language," in *Metaphor and Thought*: https://doi.org/10.1017/CBO9781139173865.012
- op7418, *Humanizer-zh*: https://github.com/op7418/Humanizer-zh
- blader, *humanizer*: https://github.com/blader/humanizer
- hardikpandya, *stop-slop*: https://github.com/hardikpandya/stop-slop
- Pangram, "All About Supporting Evidence": https://www.pangram.com/supporting-evidence
- Russell, Karpinska, and Iyyer, "People who frequently use ChatGPT for writing tasks are accurate and robust detectors of AI-generated text": https://aclanthology.org/2025.acl-long.267/
- Zanotto and Aroyehun, "Linguistic and Embedding-Based Profiling of Texts Generated by Humans and Large Language Models": https://aclanthology.org/2025.emnlp-main.1163/
- Lee et al., "Can You Make It Sound Like You? Post-Editing LLM-Generated Text for Personal Style": https://aclanthology.org/2026.acl-long.2030/
