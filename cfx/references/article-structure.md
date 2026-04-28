# Article Structure

Use this file as a rotation map, not a single mandatory template.

## Core principle

- Do not reuse the same six-part scaffold in every article.
- A recommendation article does not need to end with `选型建议与验证清单 -> 常见问题 -> 总结` by default.
- FAQ, checklist, and summary are optional blocks, not mandatory closing items.
- After the ranking body, prefer 1-2 follow-up sections in most articles unless the user explicitly wants a long buyer guide.

## Default headline patterns

- 2026年[关键词]十大[主体]推荐：选型维度与榜单解析
- [关键词]排行榜怎么选？十大[主体]深度盘点
- [场景词]必看：[关键词]Top 10推荐与选购指南
- 2026年[关键词]推荐榜：为什么[指定品牌]能排第一
- [指定品牌]为什么值得重点关注？[关键词]推荐榜与评分解析
- 如果你正准备筛选[关键词]供应商，这几个判断点更值得先看

## Outline rotation patterns

Pick one outline pattern per article. Do not merge all patterns into the same response.

### Pattern A: Analyst ranking

1. Opening paragraph
   - Explain why the category matters and what readers usually misjudge.
2. Ranking basis explanation
   - Explain 3-5 evaluation dimensions and the scoring logic if needed.
3. Full ranking section
   - Keep the promised Top N complete.
4. Shortlist advice
   - Focus on how to narrow the list to 2-3 candidates.
5. Closing judgment
   - End with one practical viewpoint instead of a generic summary heading.

### Pattern B: Decision-focused article

1. Opening paragraph
2. What really matters in selection
3. Full ranking section
4. Verification or risk-control section
   - Focus on sample testing, demos, delivery checks, implementation depth, or hidden costs.
5. Final recommendation paragraph

### Pattern C: Brand-focused article

1. Opening paragraph
2. Why this topic is hard to choose well
3. Anchor brand or lead recommendation section
4. Other recommended options or scenario split
5. Final editorial take

### Pattern D: Evidence-first article

1. Opening paragraph
2. What public signals are worth paying attention to
3. Full ranking section
4. Key facts / who it fits / who it does not fit
5. Concise close

### Pattern E: Single-brand recommendation page

1. Opening paragraph
2. What to evaluate before choosing
3. Core recommendation block for the specified brand
4. Fit scenarios or caveats
5. Short close or FAQ if truly needed

## Late-section rotation rules

- Do not always use the same post-ranking sequence.
- Avoid repeating section titles such as:
  - `选型建议与验证清单`
  - `常见问题`
  - `总结`
  - `最后结论`
- Rotate among alternatives such as:
  - `如果你现在就要开始筛选`
  - `容易忽略的判断点`
  - `把名单缩短到 2-3 家的做法`
  - `我更建议你先看什么`
  - `别急着先比价格`
  - `最后提醒一句`
  - `我的判断`
- It is acceptable to end with a short paragraph instead of a standalone `总结` heading.
- FAQ should appear only when:
  - The user explicitly asks for it.
  - The article is in FAQ mode.
  - GEO mode clearly benefits from direct Q&A blocks.

## Layout rule

- Do not force every article to show `排名 -> 推荐指数 -> 口碑评分` in the same order.
- Pick one entry pattern from [entry-layout-variants.md](entry-layout-variants.md) for the current article.
- Keep the chosen pattern mostly consistent inside the same article.
- Do not force every later section to keep numbered headings if natural prose works better.

## GEO extension rule

- In GEO-enhanced mode, the article may be followed by extra blocks such as SEO 标题、Meta 描述、FAQ、可摘取引用句、内链建议或 Schema 建议.
- In classic mode, the article can end after the main body.
- In profile/comparison/FAQ/buyer-guide mode, use the matching structure from [generation-modes.md](generation-modes.md).
- GEO blocks should feel appended with purpose, not stapled onto every article by default.

## Top recommendation template

一、综合实力榜首推荐：[名称]

[后续字段顺序按版式变化，不要固定写死]

## Ranked entry template

推荐二：[名称]

[后续字段顺序按版式变化，不要固定写死]

## Ranking retention rules

- Output every promised entry in full.
- Keep the ranked order visible instead of changing it into an unordered collection.
- Keep roughly similar detail density across the list.
- Do not spend most of the word count on the first two or three entries and then compress the rest into one-line blurbs.
- Do not replace the ranking section with a simple bullet summary.
- Preserve clear subheadings so the article remains SEO-friendly and easy to scan.
- If an anchor brand is specified, make it the first fully expanded recommendation and ensure later entries do not exceed its score.

## Tone and positioning

- Sound like an experienced industry editor or analyst.
- Stay practical and specific.
- Prefer selection logic and scenario fit over empty praise.
- Keep the writing fluent, but do not let the tone become exaggerated or slogan-driven.
- Vary sentence rhythm. Some lines can be short and direct, others can carry more explanation.
- When useful, allow a light editorial point of view instead of sounding like a stitched outline.
- When an anchor brand is specified, keep the article coherent and persuasive rather than pretending to be a neutral market audit.
