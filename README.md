# CN Emotional Support Dialogue Eval

中文情感支持对话评测集。

一个面向情感支持 / AI陪伴场景的中文微型评测集，用于评估模型在用户表达脆弱情绪时，是否能够：

- 准确识别情绪
- 理解真实诉求
- 避免未经请求的建议
- 避免说教、冒犯或轻视
- 保持合理的陪伴边界

当前版本为 `v0.1`，共 `24` 个评测 case，适合作为小型 benchmark、质检集或求职作品集样例。

## Scope

- Language: Chinese
- Size: 24 cases
- Format: JSONL
- Task type: open-ended dialogue evaluation
- Focus: empathy, intent understanding, advice restraint, tone safety, boundary safety

## Evaluation Dimensions

每条回复按以下 6 个维度打分，单项 `0-2` 分，总分 `0-12`：

- `emotion_reading`
- `intent_understanding`
- `advice_boundary`
- `non_preachy`
- `non_offensive`
- `boundary_safety`

详细说明见 `docs/rubric.md`。

## Dataset Coverage

当前 case 覆盖以下 6 类高频情绪支持场景：

- 失落与委屈
- 孤独与依恋
- 焦虑与自责
- 嫉妒与关系不安
- 求安慰但不求建议
- 边界测试与越界风险

## Repository Structure

- `cases/cn_emotional_support_eval_v0.1.jsonl`: 评测样例
- `docs/rubric.md`: 评分标准
- `docs/project-plan.md`: 项目规划
- `docs/demo_report.md`: 演示版评测报告（mock example）
- `annotations/annotation_template.csv`: 人工标注模板

## Example Workflow

1. 将 `user_message` 输入待测模型
2. 记录模型回复
3. 按 `docs/rubric.md` 对 6 个维度打分
4. 将结果写入 `annotations/annotation_template.csv`
5. 汇总不同模型或不同 prompt 的得分差异

## Notes

- 本项目聚焦回复质量评估，不涉及模型训练
- 当前版本为小样本、人工设计 benchmark
- 推荐将其与人工误差分析一起使用，而非单独作为最终结论

