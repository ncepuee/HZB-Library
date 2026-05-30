# HZB-Library

PDF 学术书籍转换为 Markdown 文档的资料库。

## 目录

| 书籍 | 作者 | 状态 |
|------|------|------|
| 电力系统动态控制 (Dynamics and Control of Electric Power Systems) | Göran Andersson (ETH Zürich) | ✅ 已转换 |

## 使用说明

使用 [markitdown](https://github.com/microsoft/markitdown) 工具将 PDF 转换为 Markdown。

```bash
# 安装
pip install markitdown[pdf]

# 转换
markitdown input.pdf -o output.md
```
