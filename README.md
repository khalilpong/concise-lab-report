# concise-lab-report

一个适用于各学科与工作场景的通用报告写作、修订和审查 Agent Skill，覆盖实验、课程、研究、文献综述、项目、数据分析及业务报告。按用途选择结构与证据要求，保留简洁英文、模板优先、无模板使用 LaTeX 和可编辑 Word 优先的交付偏好；当前明确要求优先。用户补齐适用的身份信息、导出 PDF，并默认交给另一个 AI 交叉检查。

保留名称 `concise-lab-report` 以兼容现有调用。数字电路规则移至 `references/digital-circuits.md`，仅在相关报告中按需读取，其他报告无需进行电路检查或仿真。

本仓库的 README 用于说明用途和安装方式，不属于技能正文，也不要默认放进报告提交包。

## 文件

| 文件 | 作用 | 是否必需 |
| --- | --- | --- |
| `SKILL.md` | 技能正文，遵循 [Agent Skills](https://agentskills.io) 开放格式 | 必需 |
| `references/digital-circuits.md` | 数字电路报告专项规则，按需读取；安装时一并复制 | 相关报告必需 |
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
撰写、修改或审查报告前，先完整阅读并遵守 skills/concise-lab-report/SKILL.md。
```

## 在网页聊天中使用

ChatGPT、Claude.ai、Gemini 等网页端没有本地文件时，把 `SKILL.md` 的正文粘贴到项目说明、自定义指令或对话开头，并提供报告要求、模板及已有材料。技能会按实际能力执行或降级：只能对话时给出可粘贴的内容，不编造结果或引用，并说明 Word 文件是否已生成。涉及数字电路报告时，一并提供 `references/digital-circuits.md`。

## 更新

多个工具各装一份时，副本容易过期。建议把本仓库作为唯一来源，修改后同步到各技能目录。
