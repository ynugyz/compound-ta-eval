# Compound TA (`compound-ta-eval`) — 个人复利型 AI 助教集成平台立项评估仓

> **仓库代号**：`compound-ta-eval`（暂定项目代号，非最终产品名）  
> **创建日期**：2026-11-24  
> **仓库用途**：本仓库用于对「**作为个人复利的集成式 AI 助教平台**」进行正式立项前的客观可行性评估、完整功能蓝图梳理，并支持**外部独立 AI（如未接入本项目历史上下文的 Claude）严格按相同工作流重跑联网调研与盲审对照**。

---

## 一、仓库结构与“先盲后对”隔离设计

为了防止外部评估者被既有方案带偏，本仓库严格拆分为两个独立区域：

```text
compound-ta-eval/
├── README.md                                  # 本说明文件
├── CLAUDE_EVAL_PROMPT.md                      # 给外部 Claude 的一键复制评估指令（先盲审、后对照）
├── 01-blind-input-pack/                       # 【区域一：盲审纯输入包（不含任何方案结论）】
│   ├── 01_PROBLEM_AND_VISION.md               # 发起人原始痛点、集成平台构想与竞赛/团队约束
│   ├── 02_EXISTING_EMPIRICAL_EVIDENCE.md      # 已完成的前期原型埋点事实与工程天花板实证（已脱敏）
│   └── 03_EVALUATION_WORKFLOW_SOP.md          # 可复现的 4 步调研与 8 维打分工作流 SOP
└── 02-vera-proposal/                          # 【区域二：调研实证与完整功能蓝图（仅在 Step 5 对照打开）】
    ├── 01_FEASIBILITY_RESEARCH_2026.md        # 2026 竞品矩阵、学术/社区实证、成本账与竞赛体检
    └── 02_FUNCTIONAL_BLUEPRINT.md             # 完整功能蓝图（6 大核心模块、生态边界与 V1→V3 分期路线）
```

---

## 二、如何使用本仓库进行外部独立评估（给未接入的 Claude）

1. **严格盲跑（Steps 1–4）**：先只让外部 Claude 读取 `01-blind-input-pack/` 下的 3 份文件，**禁止**提前打开 `02-vera-proposal/`。直接复制 [CLAUDE_EVAL_PROMPT.md](./CLAUDE_EVAL_PROMPT.md) 中的提示词即可启动。
2. **联网重查**：外部 Claude 会依照 `03_EVALUATION_WORKFLOW_SOP.md` 独立检索 2026 最新竞品、用户弃用痛点、技术/API 成本与高校竞赛标准，输出它自己的 8 维打分卡、致命风险与 V1 边界。
3. **交叉红队对照（Step 5）**：完成独立评估后，再让外部 Claude 打开 `02-vera-proposal/`，逐项比对双方共识与分歧，重点挑出 `02-vera-proposal/` 中可能存在的盲区、过度乐观或范围失控，最终产出 P0/P1/P2 修订清单。

---

## 三、隐私与内容声明

- 本公开仓库仅包含脱敏后的需求陈述、公开学术/社区/官方文档引用及概念级功能蓝图；
- **不包含**任何个人隐私信息、本地路径、受版权保护的原始课件/教材 PDF、未公开业务代码或第三方私密评审记录。
