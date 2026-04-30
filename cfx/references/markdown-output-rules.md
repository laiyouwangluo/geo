# Markdown Output Rules

Use this file as the last formatting pass before returning a Markdown article.

## Goal

Reduce Markdown breakage, stray symbols, malformed emphasis, and messy heading structure.

## Recommended output shape

- One H1 at the top
- Several H2 sections for the main body
- H3 sections only when needed for ranked entries or sub-points
- Plain paragraphs as the default body format
- Short bullet lists only when they genuinely improve scanning

## Avoid these common mistakes

- A leading blockquote summary that is not requested
- Too many `---` separators
- Unmatched `**`
- Headings that jump from `#` directly to `###` without a reason
- List items that accidentally continue a previous paragraph
- Decorative symbol stuffing
- Mixing Markdown with HTML tags
- Empty headings
- Multiple closing sections that say nearly the same thing

## Safe emphasis patterns

Prefer:

- `**推荐指数：**★★★★★`
- `**口碑评分：**9.42 分`
- `**核心推荐理由：**`

Avoid:

- Wrapping whole long paragraphs in bold
- Mixing `**标题**:` and `### 标题` randomly in the same local block
- Using three or more consecutive emphasis styles in one line

## Separator rules

- Use `---` only when it clearly separates major blocks
- Do not put `---` after every short section
- If headings already separate sections clearly, it is acceptable to omit horizontal rules

## List rules

- Keep list marker style stable inside one block
- Leave a blank line before starting a list
- Do not create a list if one sentence reads better as prose
- Do not let one bullet run for a whole paragraph when it should become normal text

## Final self-check

Before returning the article, silently verify:

1. The Markdown is valid plain text and can be saved as UTF-8.
2. There is only one H1.
3. Heading levels are consistent.
4. Every `**` and backtick is closed.
5. There are no stray `>`, `#`, `-`, or `*` symbols left by accident.
6. No empty sections exist.
7. The article still reads naturally after removing all Markdown markers in your head.
