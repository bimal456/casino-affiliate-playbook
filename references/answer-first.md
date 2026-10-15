# Answer-first content rules

Page-level rewriting method. Each sentence states a verified fact with certainty. Each heading is answered at once. Finish the whole page unless the mode is single-component.

Do not invent numbers, operators, bonuses or tests to satisfy a rule. Unconfirmed: `[NUMBER NEEDED: …]` or `[VERIFY: …]` and list it in the report.

## Modes

- **Rewrite:** return the copy, then the checklist report.
- **Audit:** report only; quote each violation and the fix. Do not rewrite the whole page.
- **Single component:** return only that heading/paragraph/list, paste-ready.

Unclear: rewrite for short inputs, audit for full pages.

## Workflow

1. Read the whole page. Note the H1 and the job of the page.
2. Fix heading structure first (rule 10). Everything else depends on it.
3. Rewrite each section: first sentence, second sentence, then the body.
4. Grammar (A) sentence by sentence, then styling/lists/references (C-E).
5. Final pass. Then the checklist report.

## A. Grammar

### 1. Remove fluff connectors
Remove "furthermore", "additionally", "also". If there is something to say, say it at once.

### 2. Be certain: remove modality
Remove and rephrase outside questions: could, would, should, maybe, probably, perhaps, might, seems, potentially, likely, supposedly, "it's believed that", "can be", "some of the". State verified facts in the present tense.

Do not make a sentence certain by making it false. If a claim is only sometimes true, state the condition ("Withdrawals arrive within 24 hours if the account is verified").

### 3. Contextual verbs
Prefer "A [verb] B" with concrete verbs: improves, helps, reduces, depends. Avoid "A has a [verb] effect on B".

### 4. Examples after every plural
Every plural is followed by named examples that exist in the source.

### 5. Use and qualify numbers
Replace "many" with a count of items actually on the page, or `[NUMBER NEEDED]`. Never invent a figure.

### 6. Do not delay the answer
After a plural or a question, jump to the information. No "the truth is that this varies…".

### 7. Cut the fluff
If a sentence does not cut to the chase, remove or rephrase it.

## B. Headings

### 8. First sentence answers the heading
Treat every heading as a question. The first sentence is the definitive answer, no lead-in. "How to do X" is followed by "To do X, …".

### 9. Second sentence uses IF
Formula: "Do X if A becomes B". Acceptable inverse: "If you value Y, Z is the fit."

### 10. Nest headings
Propose the new outline before rewriting when structure changes. Mark it as needing SEO sign-off.

## C. Styling

### 11. Steps as verb + noun
No uncertainty words in steps.

### 12. Bold only the answer
Bold the answer to the heading, nothing else. Never bold the keyword for its own sake.

## D. Numbered lists

### 13. At least one numbered list per page, where it fits.
### 14. Real ordered list (`<ol><li>` in HTML; `1.` in markdown, published as a list).
### 15. Under a plural heading, state how many items, list them, then H3s that elaborate.

## E. References

### 16. Suggest internal-anchor rewrites so the anchor matches the target page title. Table: current anchor, target title, suggested anchor. Do not silently change links. Unknown title: `[TARGET TITLE NEEDED]`.

## Non-English pages

Translate to English to find banned connectors/modals, remove the source-language equivalents, list them under "Words to remember", deliver the rewrite in the page language.

## Trade-offs

Priority: answer-first sentence, certainty on verified facts, IF sentence, then the rest. Say in the report which rule gave way. Keep human rhythm; one inverted sentence is enough when a section feels mechanical.

## Final pass

For each section: does it sound confident, and does it answer the heading? Then scan rules 1 and 2 banned words.

## Checklist report

Tick only when the whole page satisfies the rule. Unticked: quote the text and the fix.

```
Grammar
[ ] 1. No furthermore / additionally / also
[ ] 2. No modals or uncertainty words outside questions
[ ] 3. Declaratory sentences follow "A [verb] B"
[ ] 4. Every plural is followed by examples
[ ] 5. Numbers used and qualified; none vague; none invented
[ ] 6. No delayed answers
[ ] 7. Fluff removed
Headings
[ ] 8. First sentence under every heading answers it
[ ] 9. Second sentence under every heading uses IF
[ ] 10. Headings nested logically (needs SEO sign-off)
Styling
[ ] 11. Steps are verb + noun
[ ] 12. Only the answer is bold
Numbered lists
[ ] 13. At least one numbered list
[ ] 14. Proper ordered list
[ ] 15. Lists sit under plural headings with a quantified intro
References
[ ] 16. Anchor rewrites suggested

Open items: [NUMBER NEEDED], [VERIFY], [TARGET TITLE NEEDED], trade-offs
Words to remember (non-English only)
```
