# 仓库结构检查与基础文件建议

## 当前结构（2026-05-22）

当前仓库几乎为空：

- 仅有 `.gitkeep`
- 以及 Git 元数据目录 `.git/`

这说明项目尚未初始化语言栈、构建系统与工程规范。

## 建议优先补齐的基础文件（按优先级）

### P0：立刻补齐（任何项目都建议）

1. `README.md`
   - 写清项目目标、核心功能、快速开始、目录结构、开发命令。
2. `LICENSE`
   - 明确开源协议（如 MIT / Apache-2.0 / GPL-3.0）。
3. `.gitignore`
   - 屏蔽构建产物、依赖目录、临时文件、环境变量文件。
4. `.editorconfig`
   - 统一缩进、换行、编码、行尾空格规则。
5. `CONTRIBUTING.md`
   - 贡献流程（分支、提交规范、PR 规范、评审要求）。

### P1：工程化与协作

6. `CHANGELOG.md`
   - 按版本记录变更（建议 Keep a Changelog 格式）。
7. `CODE_OF_CONDUCT.md`
   - 社区协作行为准则。
8. `SECURITY.md`
   - 漏洞上报渠道、响应 SLA、支持版本策略。
9. `.gitattributes`
   - 统一文本文件换行（如 `* text=auto`）。
10. `.github/PULL_REQUEST_TEMPLATE.md`
    - 约束 PR 信息质量。
11. `.github/ISSUE_TEMPLATE/`
    - 缺陷 / 功能请求模板。

### P2：质量保障（按技术栈启用）

12. CI 配置（`.github/workflows/ci.yml`）
    - 至少包含 lint、test、build 三步。
13. 代码规范配置
    - JS/TS: `eslint.config.*`, `.prettierrc.*`
    - Python: `pyproject.toml`（ruff/black/mypy）
    - Go: `golangci.yml`
14. 提交规范
    - `.commitlintrc.*` + `commitizen`（可选）

## 推荐的最小目录骨架

```text
.
├─ README.md
├─ LICENSE
├─ .gitignore
├─ .editorconfig
├─ CONTRIBUTING.md
├─ CHANGELOG.md
├─ SECURITY.md
├─ CODE_OF_CONDUCT.md
├─ .gitattributes
├─ .github/
│  ├─ workflows/ci.yml
│  ├─ PULL_REQUEST_TEMPLATE.md
│  └─ ISSUE_TEMPLATE/
│     ├─ bug_report.yml
│     └─ feature_request.yml
└─ src/ 或 app/ 或 packages/
```

## 下一步建议（可执行）

1. 先确定技术栈（Node / Python / Go / Rust / Java）。
2. 先补齐 P0 文件并提交一次 `chore: bootstrap repository metadata`。
3. 再落地 CI 与 lint（P1/P2），确保新代码入库即有质量门禁。
