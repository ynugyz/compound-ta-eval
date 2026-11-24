# 给外部 Claude 的一键复制评估提示词

> **使用方式**：将下方代码块内的完整内容直接复制发给外部 Claude（确保开启联网搜索能力，并将本仓库 URL 替换/附在提示词开头）。建议先在对话 A 跑完 **第一段（严格盲审）**，拿到独立评估后再发 **第二段（交叉红队对照）**，效果最干净、最防带偏。

---

## 第一段：严格盲审指令（先只读 `01-blind-input-pack/`）

```text
请你作为一名严苛、客观的产品架构师与高校科创竞赛评委，对这个正在考虑正式立项的项目进行独立可行性调研与评估：
仓库地址：https://github.com/ynugyz/compound-ta-eval

【严格隔离纪律】
1. 本轮只允许读取 `01-blind-input-pack/` 目录下的 3 个文件：
   - `01-blind-input-pack/01_PROBLEM_AND_VISION.md`
   - `01-blind-input-pack/02_EXISTING_EMPIRICAL_EVIDENCE.md`
   - `01-blind-input-pack/03_EVALUATION_WORKFLOW_SOP.md`
2. 在你完成本轮独立评估之前，**严禁**打开或读取 `02-vera-proposal/` 目录中的任何文件！
3. 请严格按照 `03_EVALUATION_WORKFLOW_SOP.md` 中的 **Step 1 至 Step 4** 执行：
   - 必须亲自联网检索核验 2026 最新竞品（NotebookLM / Gemini Notebook、ChatGPT Study Mode、RemNote、Anki FSRS、Open DeepTutor、YouLearn/TurboLearn、腾讯 ima、Kimi/豆包等）的真实功能边界与用户差评，附真实可验证 URL；
   - 必须核查真实学生 Day-7 弃用原因、PDF/公式解析与自动出题质量风险、API 单位成本、以及挑战杯（大挑 vs 小挑）/ 高校 AI 教育应用赛 / 大创的竞赛适配性；
   - 严禁迎合发起人设想——对于 1–3 名在读学生团队想做“个人复利型集成学习平台”的范围失控风险，请直接指出哪些该砍、哪些该用导入/导出对接现成生态、哪些必须放进 V1。
4. 输出要求：
   - 明确标注【已核验事实 + URL】与【估算/推断】；
   - 给出完整 Step 1–4 报告、明确裁决（GO / CONDITIONAL GO / PIVOT / KILL）、8 维打分卡（总分 /40）、Top 3 致命风险、V1 做什么/不做什么边界、以及进入下一阶段前必须先拿到的 3 个量化门禁。
```

---

## 第二段：交叉红队对照指令（仅在拿到第一段独立结论后再发）

```text
很好，现在你已经完成了完全独立的盲审评估。请现在打开仓库的 `02-vera-proposal/` 目录，阅读以下两份文件：
- `02-vera-proposal/01_FEASIBILITY_RESEARCH_2026.md`
- `02-vera-proposal/02_FUNCTIONAL_BLUEPRINT.md`

请严格按 `03_EVALUATION_WORKFLOW_SOP.md` 的 **Step 5**，输出一份冷酷的交叉对照与红队审校报告：
1. **高置信共识**：哪些判断、风险和边界你与 `02-vera-proposal/` 不谋而合？
2. **致命盲区与反驳**：`02-vera-proposal/` 在哪些地方过于乐观、低估了 2026 竞品、低估了自动出题/解析成本、或存在隐性范围失控（功能堆砌）？请逐条给出反证。
3. **互补增益**：有哪些设计是 `02-vera-proposal/` 提出得比你更到位（值得保留），哪些是你独立想到的更优解法（应该替换进去）？
4. **最终修订清单（P0 / P1 / P2）**：结合两套视角，给发起人一份可直接照着落地或调整立项边界的最终建议清单。
```
