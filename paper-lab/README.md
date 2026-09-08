# Paper Lab

个人论文实验室。把 arXiv / PDF 链接发给 Grok，按 `AGENT.md` 生成中文导读页并更新目录。

站点模板与视觉来自 [1parado/multi-agent-article](https://github.com/1parado/multi-agent-article)（[CC BY-NC 4.0](LICENSE)）。

## 本地预览

克隆后双击 `index.html`，或：

```bash
python3 -m http.server 8080
```

打开 http://127.0.0.1:8080/

## GitHub Pages

仓库 Settings → Pages → Source 选 **Deploy from a branch** → `main` / `/(root)` → Save。

几分钟后地址：https://ericjamie.github.io/paper-lab/

## 加论文

在 Grok 对话里丢论文链接即可，不必手改 HTML。规则见 `AGENT.md`。
