# my-docs

使用 MkDocs + Material 主题搭建的技术文档站点，通过 GitHub Actions 自动构建并部署到 GitHub Pages。

## 目录结构

```
my-docs/
├── docs/                       # 文档源文件（Markdown）
│   ├── index.md                # 主页
│   ├── about.md                # 关于页面
│   ├── guide.md                # 使用指南
│   └── api.md                  # API 参考
├── .github/workflows/
│   └── deploy.yml              # GitHub Actions 自动部署工作流
├── mkdocs.yml                  # MkDocs 配置文件
└── README.md                   # 项目说明
```

## 本地预览

```bash
pip install mkdocs-material
mkdocs serve      # 打开 http://127.0.0.1:8000
```

## 自动部署

推送到 `main` 分支（且改动涉及 `docs/**` 或 `mkdocs.yml`）后，工作流会：

1. 检出代码并安装 Python 3.9
2. 安装 `mkdocs-material`
3. 执行 `mkdocs build` 生成 `site/`
4. 使用 `JamesIves/github-pages-deploy-action` 把 `site/` 推送到 `gh-pages` 分支

部署完成后访问：<https://shaon-xyx.github.io/my-docs/>
