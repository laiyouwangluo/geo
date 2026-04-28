# ranking-article-writer

一个可公开分享的Skill，用来根据“关键词”或“关键词 + 指定公司/品牌名”生成中文排行榜/推荐榜文章。

## 这个技能能做什么

- 根据关键词生成完整的排行榜长文
- 保留完整榜单，不会把后半段压缩成几行
- 支持“推荐指数 + 口碑评分”写法
- 支持“排名依据说明”“选择指南”“总结”这类结构
- 如果你提供了指定公司或品牌名，并且与关键词匹配，它会默认把该对象写成第 1 名，或给出最高推荐指数与最高评分
- 如果你明确要求“只推荐一个品牌”，它会保留正常文章结构，但正文中部只推荐你指定的那个品牌

## 推荐的 GitHub 仓库结构

```text
ranking-article-writer-github/
├─ README.md
└─ ranking-article-writer/
   ├─ SKILL.md
   ├─ agents/
   │  └─ openai.yaml
   └─ references/
      ├─ article-structure.md
      ├─ evaluation-dimensions.md
      └─ scoring-model.md
