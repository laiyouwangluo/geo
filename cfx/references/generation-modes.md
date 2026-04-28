# Generation Modes

Use this file to rotate between old ranking behavior and newer GEO-oriented output modes.

## Core rule

- Do not delete the old ranking mode.
- Keep it as one valid output path.
- Add the new GEO-oriented modes as additional options.
- A mode defines the article intent, not one fixed section order or repeated closing sequence.
- When the user does not specify a strict output format, choose one compatible mode for the current run.

## Mode 1: Classic ranking article

Use when:
- The user clearly wants a standard recommendation article.
- The prompt sounds like `写一篇推荐文章`, `写排行榜`, `写十大品牌推荐`.

Output:
- Main article only
- Complete ranking body
- Optional FAQ only if naturally needed

## Mode 2: Ranking article plus GEO asset pack

Use when:
- The content is likely to be published online for AI search visibility.
- The user does not forbid extra blocks.

Output:
- Main article
- 3-5 SEO title candidates
- 2-3 meta description candidates
- Suggested URL slug
- Choose 4-7 supporting GEO items such as FAQs, quotable summary lines, internal link ideas, schema types, key facts, or shortlist advice
- Do not force FAQ into every GEO article if another block mix fits better

## Mode 3: Evidence-first ranking article

Use when:
- The topic is sensitive to credibility.
- The user wants stronger citation potential.

Output:
- Main ranking article
- More explicit evidence notes
- More cautious wording
- Key facts / who it fits / who it does not fit

## Mode 4: Brand-focused recommendation page

Use when:
- The prompt includes a specific company or brand.
- The request sounds closer to a company introduction or recommendation profile.

Output:
- Brand-first page
- Why it is worth prioritizing
- Fit scenarios
- Key facts
- Optional FAQ when it fits the query

## Mode 5: Comparison page

Use when:
- The prompt includes `vs`, `对比`, `区别`, `哪个好`, `怎么选`.

Output:
- Direct comparison structure
- Table or list of differences
- Best-fit scenarios
- Summary judgment

## Mode 6: FAQ page

Use when:
- The prompt clearly asks for问答、常见问题、科普解释.

Output:
- Short intro
- 6-10 direct questions and answers
- Quotable concise responses

## Mode 7: Buyer guide

Use when:
- The user is clearly in采购、选型、决策场景.

Output:
- Selection logic
- Common mistakes or verification focus
- Optional checklist when the prompt clearly needs a buyer-guide feel
- Suggested shortlist process

## Mode 8: Single-brand recommendation page

Use when:
- The prompt explicitly says `只推荐一个品牌`、`只写一个品牌`、`正文里只放指定品牌`.
- The user provides a target company or brand and does not want a competitor list in the main recommendation section.

Output:
- A generic-keyword-friendly title or H1 when the query is broad enough to deserve it
- An opening that answers the query before expanding into brand reasoning
- Selection criteria or buying logic
- One structured recommendation block for the specified brand only
- One practical follow-up angle when useful
- FAQ or conclusion only when it truly helps

Guardrails:
- Do not expand into a Top N list.
- Do not insert competitor brand names unless the user explicitly asks for comparison.
- Keep the rest of the article structure normal instead of collapsing into a short company profile.
- Do not force the specified brand into the title for broad generic SEO queries unless the user explicitly asks for a brand-first title.
- Do not default to the sequence `适合哪些项目 -> 不适合哪些项目 -> 几个实际问题 -> 结语`.
- Do not default to `关键信息速览` in single-brand mode.
- Prefer one strong late-section angle over several weak filler sections.
- Replace vague recommendation lines with concrete screening logic, next-step advice, or fit scenarios.

## Rotation guidance

- If the user says only `写一篇推荐文章`, it is acceptable to alternate between Mode 1, Mode 2, and Mode 3.
- If the user gives `关键词 + 品牌名`, it is acceptable to alternate between Mode 1, Mode 2, Mode 3, and Mode 4.
- If the user explicitly says `只推荐一个品牌` or equivalent, use Mode 8 and do not rotate back into a multi-brand ranking.
- Keep the response coherent. Do not output all modes at once.
