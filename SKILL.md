---
name: product-broadcast
description: Convert internal requirement docs into concise customer-facing product update announcements for enterprise live-streaming products. Use when asked to write, rewrite, or review release notes/product updates from PRD or requirement tickets, especially when content must filter out technical details and keep only customer-visible changes.
---

# Workflow

1. Read [references/prompt-v4.md](references/prompt-v4.md) before drafting.
2. Read [references/classification-matrix.md](references/classification-matrix.md) before classifying requirement type.
3. Run Stage 1 first and output a diagnostic report.
4. Pause after Stage 1 and wait for confirmation.
5. Run Stage 2 and generate the final announcement with the required structure.

# Stage 1 Output (Mandatory)

Always output:

`📋 需求诊断报告`

Include:

- `归类为：👉【类型】` where type is one of:
  - `新功能`
  - `核心流程优化`
  - `用户体验/功能细节优化`
  - `技术集成类优化`
- `分类判定依据（必须引用矩阵）`:
  - `核心差异`
  - `A. 操作链路`
  - `B. 用户决策`
  - `C. 学习成本`
  - `D. 功能普适性`
- `要素提取`:
  - `模块`
  - `功能名称`
  - `客户可见变化`
  - `默认行为变化`
  - `入口变化`
- `拟定策略`:
  - Filter internal implementation details
  - Keep only customer-visible changes
  - Use template `A/B/C`

Stop after Stage 1 and wait for user confirmation.

# Stage 2 Output (Mandatory)

After confirmation, output only:

- `【功能标题】`
- `【功能概述】`
- `【功能说明】` (only when required by the selected template)

# Writing Constraints

1. Fully understand requirement text before writing.
2. Do not extend logic not present in requirement text.
3. Do not omit explicit requirement logic.
4. Use zero-person narrative. Do not use:
   - `我们`
   - `我`
   - `团队`
   - `您`
   - `你`
5. Prioritize in this order:
   - Functional changes
   - Entry changes
   - Default behavior changes
   - Constraints/availability
6. Keep summary to 1-2 sentences.
7. Set feature bullet count by customer cognitive units, not requirement sub-items.
8. Prefer 3-4 bullets, maximum 6.
9. Merge bullets when they describe the same capability.
10. Prefer this structure when applicable: entry -> core capability -> data source/constraints.
11. Write bullets as system behavior, not value claims.
12. Write `【功能概述】` with required formula:
   - `在【业务场景】中，新增/支持【功能能力】，支持【可执行行为】，用于【具体业务用途】。`
13. Include only verifiable value in summary purpose (`用于...`), not abstract value words.
14. Use customer announcement language, not requirement/test wording.
15. Avoid step-by-step test flow phrasing in bullets; summarize as customer-visible capability.
16. Keep bullet sentence pattern consistent, prefer `新增/支持/默认/可查看` starters.
17. Do not expose internal system structure in announcement wording; rewrite to user-visible capability.
18. Avoid fine-grained UI position wording unless position change is the core change.
19. For new model/capability updates, prioritize bullets by: availability -> usage -> limits -> impact on existing behavior.
20. Exclude protocol/parameter/API/internal routing details unless they affect customer decisions.
21. For model/algorithm/engine/protocol updates, summary value must describe what customers can do, not technical capability expansion.
22. Avoid duplicated summary capability phrasing (e.g., "新增能力 + 支持同一能力"); keep one clear capability statement.
23. Prefer business-moment scenarios in summary (e.g., live session, demo flow, creation flow) over page-location phrasing.
24. Keep single-feature boundary under one title; split bullets that introduce a different capability into a separate feature entry.
25. For endpoint capability extension updates, prefer concise form: 1 summary sentence + 1-3 bullets.

# Filtering Rules

Keep only customer-visible content:

- Functional changes
- Default behavior changes
- Entry/path changes
- Visible permission/timing constraints

Remove:

- User stories
- Acceptance condition breakdowns
- Algorithms and formulas
- Examples used only for explanation
- Technical implementation details

For detailed rules and full templates, follow [references/prompt-v4.md](references/prompt-v4.md) and [references/classification-matrix.md](references/classification-matrix.md).
