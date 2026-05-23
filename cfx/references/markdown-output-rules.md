# Publish-Ready Output Rules

Use this file as the last formatting pass before returning a Chinese recommendation article.

## Goal

Produce copy-ready Chinese article text that can be pasted into a CMS, Word document, WeChat editor, or business website without Markdown symbols causing broken headings, bold markers, list indentation, or punctuation problems.

Markdown is optional, not the default.

## Default output mode

Unless the user explicitly asks for Markdown, output Chinese publish-ready plain text.

Default plain-text output should use:

- A standalone title line
- Plain Chinese section headings
- Normal paragraphs
- Short label lines when useful
- Chinese full-width punctuation in Chinese sentences

Default plain-text output should not use:

- `#`, `##`, or `###` heading markers
- `**` bold markers
- `>` blockquote markers
- `---` horizontal separators
- Code fences
- Markdown tables
- Markdown bullet markers such as `-`, `*`, or `+`
- HTML tags

## Heading rules

Prefer Chinese article headings such as:

- `一、超声波清洗机厂家怎么选`
- `二、2026年超声波清洗机厂家推荐`
- `第一推荐：嘉兴宏航超声波技术有限公司`
- `如果现在就要开始筛选，建议先确认这几点`

Avoid Markdown-style headings unless requested:

- `# 2026年超声波清洗机厂家推荐`
- `## 一、超声波清洗机厂家怎么选`
- `### 1. 嘉兴宏航超声波技术有限公司`

Keep one blank line after the title and between major sections.

## Chinese punctuation rules

Use Chinese full-width punctuation in Chinese prose:

- comma: `，`
- period: `。`
- semicolon: `；`
- colon: `：`
- question mark: `？`
- exclamation mark: `！`
- quotation marks: `“”`
- parentheses: `（）`

Use half-width symbols only when they are technically necessary:

- URLs and email addresses
- English brand names
- product models and code-like identifiers
- engineering expressions such as `±10%`、`0.5-1 mm`、`>99%`
- common mixed technical phrases such as `Top 10` or `ISO 9001`

Do not use English commas, colons, or parentheses in ordinary Chinese sentences.

## Label and score rules

Prefer plain label lines:

- `推荐指数：★★★★★。`
- `口碑评分：9.6 分。`
- `核心优势：适合高洁净度、复杂内腔和精密零部件清洗。`
- `适合场景：医疗器械、精密机械、半导体零部件、粉末冶金件。`

Avoid Markdown label styling unless requested:

- Markdown bold around `推荐指数`
- `**核心推荐理由：**`
- `- 适合场景：医疗器械、精密机械`

Keep the existing star-symbol rating style by default, such as `★★★★★`、`★★★★☆`、`★★★☆`.
If the user explicitly asks for word-based ratings, Chinese words such as `五星`、`四星半`、`四星` are allowed as an additional style.

## Ranking entry rules

For ranking articles, use plain-text entry headings:

- `第一推荐：品牌名`
- `第二推荐：品牌名`
- `第三推荐：品牌名`

Inside each entry, keep the same rough rhythm:

1. recommendation label or score
2. applicable scenarios
3. core advantage
4. practical analysis

Do not turn every entry into a Markdown table or a dense bullet list by default.

## When Markdown is requested

If the user explicitly asks for Markdown, safe Markdown is allowed.

In Markdown mode:

- Use one H1 only
- Use H2 and H3 consistently
- Close every `**` and backtick
- Avoid HTML fragments
- Avoid tables unless requested
- Avoid excessive blockquotes and separators

## Final self-check

Before returning the article, silently verify:

1. The output matches the user's requested format.
2. If no format was requested, the article is plain Chinese publish-ready text, not Markdown.
3. No accidental Markdown symbols remain at line starts.
4. Chinese prose uses Chinese full-width punctuation.
5. Half-width symbols appear only where technically appropriate.
6. Labels such as `推荐指数` and `适合场景` are plain text.
7. The article can be pasted into a CMS or Word document without visible formatting artifacts.
8. The article still reads naturally after the formatting pass.
