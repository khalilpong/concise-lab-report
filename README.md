# concise-lab-report

一个按实验手册核对、撰写和审查实验报告的 Agent Skill。它让 AI 先交可编辑 Word，再由用户填写身份信息、导出 PDF 并交给另一个 AI 交叉检查。

本仓库的 README 只用于说明安装方式，不属于技能本身，也不要放进实验提交包。

## 文件

| 文件 | 作用 | 是否必需 |
| --- | --- | --- |
| `SKILL.md` | 技能正文，遵循 [Agent Skills](https://agentskills.io) 开放格式 | 必需 |
| `agents/openai.yaml` | Codex 界面显示名和默认提示词，其他工具会忽略 | 可选 |

## 安装

把整个 `concise-lab-report` 文件夹放到对应工具的技能目录。路径以各工具当前官方文档为准。

| 工具 | 项目级 | 用户级 |
| --- | --- | --- |
| Claude Code | `.claude/skills/concise-lab-report/` | `~/.claude/skills/concise-lab-report/` |
| Codex CLI / App | `.agents/skills/concise-lab-report/` | `~/.codex/skills/concise-lab-report/` |
| Gemini CLI | `.gemini/skills/` 或 `.agents/skills/` | `~/.gemini/skills/` |
| GitHub Copilot | `.github/skills/concise-lab-report/` | 见官方文档 |
| Cursor | `.cursor/skills/` 或 `.agents/skills/` | 见官方文档 |

不支持技能目录的工具，可以在项目根目录的 `AGENTS.md`、`CLAUDE.md` 或 `GEMINI.md` 中写一句：

```markdown
撰写、修改或审查实验报告前，先完整阅读并遵守 skills/concise-lab-report/SKILL.md。
```

## 在网页聊天中使用

ChatGPT、Claude.ai、Gemini 等网页端没有本地文件时，把 `SKILL.md` 的正文粘贴到项目说明、自定义指令或对话开头，并上传手册和模板。技能会按第 0 节的 C 档工作：给出可粘贴的报告内容，不编造实验结果，并说明 Word 文件是否已生成。

## 更新

多个工具各装一份时，副本容易过期。建议把本仓库作为唯一来源，修改后同步到各技能目录。
