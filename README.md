# document-style — 中文技术文档写作规范 Agent Skill

让 Agent 按中文技术文档写作规范，对用户的中文技术文档进行**校对**（评估、修改、更新）。

## 技能本体

| 文件 | 作用 |
|------|------|
| [`SKILL.md`](SKILL.md) | 技能入口：三个分支（评估/修改/更新）与流程、完成判据 |
| [`references/rules.md`](references/rules.md) | **主规范**：6 模块规则唯一事实源（规则 ID、严重级、正误示例、检查提示） |
| [`references/provenance.md`](references/provenance.md) | 溯源注记：冲突裁决、外部指南可用状态（不参与判定） |
| [`CONTEXT.md`](CONTEXT.md) | 领域词汇表（校对、主规范、违规、严重级、例外清单等） |
| [`docs/adr/`](docs/adr/) | 架构决策记录 |

## 设计决策（grilling 阶段确定）

- **仓库即技能**：仓库根目录即技能目录，安装 = 软链/拷贝到 `~/.pi/agent/skills/document-style/`
- **跨 harness**：按 agentskills.io 标准编写，pi / Claude Code / Codex 通用
- **model-invoked**：description 带触发词，agent 遇到中文技术文档自动调用
- **一个技能三分支**：评估（报告）/ 修改（全文）/ 更新（落盘），共享同一套主规范
- **v1 纯提示词**：无脚本零依赖；脚本化检查（正则扫描）留作 v2 演进
- **主规范唯一**：冲突以仓库为准，外部指南只作溯源（ADR-0001）

## 安装

```bash
mkdir -p ~/.pi/agent/skills
ln -s "$(pwd)" ~/.pi/agent/skills/document-style   # 或拷贝
```

## 素材

原始研究材料在 `output/`（**不入库**，已被 .gitignore 排除）：仓库规则原文 + 12 个外部链接的联网检索记录。
