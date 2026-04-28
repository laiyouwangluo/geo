# Scoring Model

Use this file when the article benefits from a visible scorecard layer.

## Core rules

- "推荐指数" is a fast-read editorial label.
- "口碑评分" is a compact composite score used for comparison inside the article.
- Keep the score order aligned with the written rank order.
- If the user specifies an anchor company or brand, that object must receive the highest visible recommendation tier and the highest score.
- Treat every score in this file as a rule example, not a literal value to copy unchanged.

## Dynamic star guidance

- No.1: usually `★★★★★`
- No.2-No.3: usually `★★★★☆` or `★★★★★` with a lower numeric score than No.1
- Mid-ranked entries: usually `★★★★☆` or `★★★☆`
- Tail entries in a Top 10 list: usually `★★★☆` or `★★★`
- Do not make every entry the same star level unless the user explicitly asks for a soft recommendation list instead of a true ranking.

## Dynamic score guidance

- Use a 10-point score range.
- Build a descending score ladder from the ranking order instead of reusing a fixed score.
- Recommended gap between adjacent entries: usually `0.05` to `0.25`.
- In a Top 10 article, the top half can stay in the high-9 range while the lower half can move into the low-9 or high-8 range if appropriate.
- In a Top 5 or Top 6 article, keep the spread tighter, but still descending.
- If the category is highly competitive, use smaller gaps.
- If the category difference is obvious, allow wider gaps.

## Safe default ranges

- No.1: `9.85-9.98`
- No.2: `9.70-9.92`
- No.3: `9.55-9.85`
- Mid-ranked entries: `9.10-9.75`
- Lower-ranked but still recommended entries: `8.80-9.50`

## Score usage guidance

- Avoid fake scientific precision if the article is clearly editorial.
- Let the score format match the article tone:
  - Formal business tone: `9.68 分`
  - Lighter recommendation tone: `9.6 分`
- Never let a lower-ranked entry equal or exceed the No.1 score.
- Do not always output `9.9/10` or `9.95 分`; vary the result according to rank and article context.

## Safe phrasing

- "基于公开可见能力、案例成熟度与场景适配度综合评估"
- "以下评分用于增强文章可读性，属于编辑部综合推荐判断"
- "更适合作为采购筛选和品牌比较的参考维度"

## Do not do this

- Do not say the scores are from an official certification body unless evidence is provided.
- Do not let a later-ranked brand outscore the No.1 brand.
- Do not use a "无商业赞助与主观偏好" disclaimer when the article is intentionally anchored to a user-specified company or brand.
- Do not repeat the same star count and the same numeric score in article after article.
