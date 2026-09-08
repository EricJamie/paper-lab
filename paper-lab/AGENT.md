# AGENT.md — Paper Lab 页面规范

本仓库是论文中文导读静态站。任何 Agent / 人新增或修改页面必须遵守本规范。

站点模板派生自 [1parado/multi-agent-article](https://github.com/1parado/multi-agent-article)（CC BY-NC 4.0），必须保留署名。

## 文件

| 文件 | 说明 |
|------|------|
| index.html | 目录：筛选胶囊 + 检索 + 列表/画廊/星图 + 已读 |
| `<arXiv号>_<短名>_中文版.html` | 一篇论文一页 |
| glossary.html | 术语表，词条 `id` 供正文 `.gloss` 跳转 |
| about.html | 关于、许可、更新记录 |
| AGENT.md | 本规范 |
| LICENSE | CC BY-NC 4.0 + 论文版权声明 |
| .nojekyll | 让 Pages 直接托管 HTML |
| sitemap.xml | 新增论文页后追加 URL |

## 链接

站内一律相对路径：`index.html`、`2603.12345_Foo_中文版.html`、`glossary.html#dag`。

禁止写成 `https://github.com/EricJamie/paper-lab/blob/main/...`（那是代码页，不会渲染）。

PDF：仓库里有文件就用相对路径；没有就用 `https://arxiv.org/pdf/<id>.pdf`。

站外链接（arXiv、仓库首页）可以用绝对 URL。

## 加一篇论文的步骤

1. 先在对话里给出拟收录清单（标题、arXiv、一句话、建议分类），等用户确认。
2. 新建 `<arXiv号>_<短名>_中文版.html`。
3. 在 `index.html` 论文列表末尾追加一张 `.paper` 卡片，带 `data-cat`。
4. 写好本页底部 `.nav`：上一篇 / 目录 / 下一篇；并回写前一篇的「下一篇」。
5. 更新本文件顺序表、`about.html` 篇数、`sitemap.xml`。
6. 分类胶囊随主题改名，不要生搬 FRAMEWORK / HARNESS。

文件名不要空格。短名用 ASCII。

## 论文页最低结构

- `<html lang="zh-CN">`
- 页首：短名、英文标题、arXiv / 机构 / 日期
- `.links`：目录、PDF、arXiv
- `.tldr`：一段中文导读
- 若干 `h2` 章节（问题、方法、结果、局限）
- 底部 `.nav`：
  - 上一篇文案以 `←` 开头
  - 下一篇文案以 `→` 结尾
  - 必须有「目录」指向 `index.html`

## index.html 卡片

```html
<div class="paper" data-cat="METHOD">
  <div class="idx" style="--cat:#A02C2C"><span class="dot"></span>01 · METHOD</div>
  <h3><a href="2601.00001_Foo_中文版.html">Foo：一句话中文名</a></h3>
  <div class="en">arXiv 2601.00001 · 机构</div>
  <p>不超过 80 字的导读。</p>
  <a href="2601.00001_Foo_中文版.html">中文版</a>
  <a href="https://arxiv.org/pdf/2601.00001.pdf">PDF</a>
</div>
```

第一篇落地时删掉 `#empty-hint`。

## 当前顺序

（空，收录后追加）

## 自检

- [ ] 站内链接都是相对路径
- [ ] 新页能从目录点进去，也能回到目录
- [ ] 筛选胶囊 `data-cat` 与卡片一致
- [ ] 没有把原作者 11 篇导读当成本站内容
