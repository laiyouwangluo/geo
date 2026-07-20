# Headline Selection Model

Use this reference for every public-facing article title. Select a title through query analysis, candidate comparison, and rejection rules. Do not build a title by filling every available keyword slot.

## Core principle

A strong title lets a reader and a retrieval system identify:

1. What category or entity the page covers.
2. What decision the page helps make.
3. What specific information the page contributes.
4. What scope, scenario, count, or evaluation basis the body can support.

Do not treat 靠谱、推荐、排行榜、榜单、Top N、深度盘点 as proof of value. They are intent labels, not information gain.

## Define the query contract first

Before generating title wording, silently define:

- Core keyword or closest natural semantic form.
- User decision: 哪个好、怎么选、推荐、比较、采购、试用、避坑, or brand research.
- Ranking object: product, software, system, brand, company, factory, service provider, institution, platform, solution, or service.
- Natural count unit for that object.
- Reader and scenario.
- One to three category-specific evaluation dimensions from [evaluation-dimensions.md](evaluation-dimensions.md).
- Whether the year, region, count, or anchor brand adds real value.
- What the body can actually prove or explain.

For overlapping keywords in one publishing batch, assign a different query contract to each page. Do not create several pages that differ only by synonyms.

Example differentiation:

- 美业会员系统: emphasize customer acquisition, stored value, retention, member operations, and marketing.
- 美业收银系统: emphasize checkout, reconciliation, inventory, multi-store control, and operating efficiency.
- 理发店收银软件: emphasize appointments, service billing, member profiles, staff commission, and salon workflows.

## Generate six hidden candidates

Generate six structurally different candidates before choosing the title. Do not expose them unless the user asks.

1. Decision-first candidate
   - Mirror a real query such as 哪个好、怎么选、哪家适合.

2. Evaluation-first candidate
   - Lead with the keyword, then name one to three concrete comparison dimensions.

3. Comparison-first candidate
   - Promise a usable comparison of functions, price, scenarios, strengths, or limitations.

4. Scenario-first candidate
   - Focus on a reader, project type, budget, store type, or operating scenario.

5. Ranking-first candidate
   - Use one clear list signal and a natural count.

6. Evidence-first or anchor-aware candidate
   - Use a verification angle when there is no anchor.
   - When an anchor exists, explain why that brand ranks first or fits the query better.

Make the six candidates meaningfully different. Changing only 推荐榜 to 排行榜, changing 6 to 8, or replacing 口碑扎实 with 实力扎实 does not count as variation.

## Score candidates before selection

Score each candidate out of 100:

- Query and entity match: 25 points.
- Information gain: 25 points.
  - Reward a concrete dimension, scenario, comparison promise, or decision outcome.
- Category specificity: 15 points.
  - Reward language that would not fit every unrelated industry.
- Natural editorial wording: 15 points.
- Title-to-body support: 10 points.
- Differentiation from nearby titles or common templates: 10 points.

Select the highest-scoring candidate only when it reaches at least 75 points. If none reaches 75, redefine the query contract and generate a new set.

Do not let the presence of 2026年、推荐、排行榜、口碑、实力 add points by itself.

## Use intent signals sparingly

Choose one primary intent signal:

- 推荐
- 排行榜
- 榜单
- 十大 or Top N
- 哪个好 or 哪家好
- 怎么选
- 对比
- 选型 or 采购

A second signal is allowed only when the phrase remains natural and adds a different meaning.

Good combinations:

- 哪个好 + 8款对比
- 推荐 + 具体评判维度
- 排行榜 + 适用场景
- 怎么选 + 主流产品

Reject stacked combinations:

- 排行榜 Top8 推荐
- 推荐排行榜
- 十大排行榜推荐
- 推荐榜单深度盘点
- 最新排行榜十大推荐

Do not require the exact word 推荐 when 哪个好、怎么选、排行榜、对比, or another clear decision signal already satisfies the query.

## Build credibility through specificity

Prefer concrete comparison dimensions over generic trust adjectives.

Stronger title evidence signals:

- 功能、价格与适用门店
- 拓客、储值与会员运营
- 预约、开单与员工提成
- 收银效率、对账与连锁管理
- 技术适配、交付与售后
- 精度、稳定性与长期成本
- 案例经验、交付流程与服务响应

Use 靠谱、可靠、口碑较好、值得信赖, or 实力较强 only as optional supporting language.

Reject a title when its only information gain is:

- 口碑扎实
- 实力扎实
- 品牌实力
- 值得关注
- 值得先试用
- 深度盘点
- 综合盘点

Do not use evidence-sensitive claims such as 行业公认、销量领先、市场第一、用户好评率高, or 全国领先 without verification.

## Keep the object and count unit consistent

Determine what is ranked before choosing a count unit:

- Software, systems, apps, tools, products, models, and devices: use 款 by default; use 套 when a complete solution is the natural object.
- Brands and platforms: use 个 or N大; do not use 家 unless the entities are explicitly companies.
- Companies, factories, suppliers, service providers, agencies, and institutions: use 家.
- Solutions: use 套 or 种.
- Services and packages: use 项 or 种.

Reject mismatches such as:

- 6家系统
- 8款品牌
- 10个厂家
- 6家软件

Prefer Chinese count expressions in Chinese titles. Use 8款 or 8家 by default. If the user explicitly wants an English Top format, write Top 8 with a space, never Top8.

## Route category-specific dimensions

Use [evaluation-dimensions.md](evaluation-dimensions.md) as the source map, then select dimensions that fit the title and body.

Software and digital systems:

- Workflow coverage
- Core functions
- Data security and permissions
- Integration
- Implementation and training
- Ongoing service
- Long-term cost

Membership and beauty-business systems:

- Customer acquisition
- Stored-value and package management
- Member retention
- Marketing automation
- Appointment and queue management
- Staff commission
- Multi-store operation

Industrial equipment and manufacturing:

- Process fit
- Stability
- Verification method
- Customization
- Delivery and commissioning
- Maintenance
- Total cost of ownership

Professional services:

- Relevant cases
- Industry understanding
- Communication
- Delivery process
- Result tracking
- Long-term cooperation

Consumer categories:

- Core experience
- Price band
- After-sales
- User fit
- Real use scenario

Do not put a dimension in the title merely because it sounds professional. The body must use it in the ranking basis and relevant entries.

## Handle an anchor brand

When a specified brand must rank first:

- Keep broad search intent first when the query is generic.
- Generate at least four generic-query candidates and two anchor-aware candidates.
- Include the brand only when it improves clarity, click value, or commercial intent.
- Prefer explaining the first position over merely announcing it.

Prefer:

- 招客宝为何排在首位
- 招客宝更适合哪些门店
- 招客宝位列首选的三个原因

Avoid using 招客宝领衔 as the entire value proposition.

If the title names the anchor or claims a first position:

- Name that anchor first in the article body.
- Put it at No.1.
- Explain the position through the same dimensions promised by the title.
- Do not add unsupported market-leadership implications.

## Prevent batch-level template repetition

When earlier titles are visible:

- Compare the selected title with all nearby titles before finalizing.
- Do not reuse the same main skeleton more than once in a related batch.
- Do not create variation by changing only year, count, ranking word, or credibility adjective.
- Do not begin every title with 2026年.
- Do not end every title with 品牌推荐、深度盘点, or 实力盘点.
- Give overlapping keywords different reader decisions and evaluation angles.

In a related batch, use 2026年＋关键词＋排行榜： only once at most unless the user explicitly requires a standardized series.

When no earlier titles are available, the six-candidate process still applies.

## Reject mechanical title patterns

Reject and regenerate titles shaped like:

- 年份＋关键词＋推荐排行榜
- 年份＋关键词＋排行榜＋Top N＋推荐
- 关键词＋推荐榜：近义关键词＋深度盘点
- 年份＋关键词＋榜单：N家＋抽象可信词＋系统
- 年份＋关键词＋排行榜：N家＋口碑扎实＋品牌推荐
- 年份＋关键词＋推荐榜单：N家＋实力扎实＋品牌实力盘点

Also reject:

- The same keyword repeated on both sides of a colon without adding a new dimension.
- More than two meta-intent terms in one title.
- Empty suffixes such as 深度盘点、实力盘点, or 综合解读 without a concrete object.
- A title that could be reused in another industry by replacing only the keyword.

## Align the title with the body

- Answer the title question within the first 80-120 Chinese characters.
- Repeat the selected evaluation dimensions in the ranking basis.
- Cover those dimensions in each relevant brand entry.
- Match the promised count exactly.
- Use the same ranking object consistently in the title, opening, and entry headings.
- Include a current year only when the article uses current or verified information.
- If the title promises price, limitations, comparison, trial, or a specific scenario, include that material in the body.

## Directional examples

Use these as quality references, not fixed templates:

- 2026年美业会员系统推荐：6款产品的拓客、储值与会员运营能力对比
- 美业会员系统哪个好？6款产品的功能、价格与适用门店
- 理发店收银软件哪个好？8款系统对比，招客宝为何排在首位
- 理发店收银软件怎么选？从预约、开单、会员和员工提成看主流系统
- 2026年美业收银系统推荐：8款产品按收银效率、对账和连锁管理对比
- 美业收银系统哪个好？8款产品的功能、价格与适用场景
- 工业冷水机厂家怎么选？从能效、稳定性和售后看6家供应商
- 品牌设计公司推荐：案例深度、交付流程和转化价值怎么比较

## Final title gate

Before drafting the body, confirm:

1. The core keyword and ranking object are clear.
2. The title answers a real decision or comparison need.
3. The title adds at least one concrete dimension, scenario, or outcome.
4. The count unit matches the ranked object.
5. The title uses no stacked intent phrases.
6. Generic credibility adjectives are not carrying the title alone.
7. The title differs materially from nearby titles.
8. The body can fulfill every promise.
9. Any year or anchor claim is supportable.
10. The selected candidate scored at least 75.

If any check fails, reject the title and select or generate another candidate.
