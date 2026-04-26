## 项目概述

方大同 TI 专辑匹配趣味问答页面。用户通过回答问题匹配最适合自己的方大同 TI 专辑曲目。

## 技术栈

- 纯静态 HTML/CSS/JavaScript
- 无框架依赖
- 外部依赖：QRCode.js（通过 CDN 引入）

## 目录结构

```
/workspace/projects/
├── index.html          # 主页面入口
├── .coze               # Coze 项目配置
├── scripts/
│   ├── coze-preview-build.sh
│   ├── coze-preview-run.sh
│   ├── coze-deploy-build.sh
│   └── coze-deploy-run.sh
└── .gitignore
```

## 关键入口 / 核心模块

- `index.html`：单页应用，包含全部样式和脚本

## 运行与预览

**预览服务**：
- 构建：`bash scripts/coze-preview-build.sh`（静态文件无需构建）
- 运行：`bash scripts/coze-preview-run.sh`（启动 Python HTTP 服务器）
- 端口：5000

**部署服务**：
- 构建：`bash scripts/coze-deploy-build.sh`
- 运行：`bash scripts/coze-deploy-run.sh`
- 端口：5000

## 用户偏好与长期约束

- 项目为纯静态 HTML，无需 Node.js 或 Python 运行时依赖
- 预览和部署使用相同的 Python 内置 HTTP 服务器
- `requires = []` 因为无运行时语言依赖

## 常见问题和预防

- 端口固定为 5000（平台要求）
- 服务必须绑定到 `0.0.0.0` 而非 `127.0.0.1`
