---
name: product-broadcast
description: Convert internal requirement docs into concise customer-facing product update announcements for enterprise live-streaming products. Use when asked to write, rewrite, or review release notes/product updates from PRD or requirement tickets, especially when content must filter out technical details, keep only customer-visible changes, and determine announcement channels.
---

# Workflow

1. Read [references/prompt-v4.md](references/prompt-v4.md) before drafting.
2. Read [references/classification-matrix.md](references/classification-matrix.md) before classifying requirement type.
3. Run Stage 1 first and output a diagnostic report.
4. Pause after Stage 1 and wait for confirmation.
5. Run Stage 2 and generate the final announcement with the required structure and promotion recommendation.

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
- `【宣发建议】`

Valid values for `【宣发建议】`:

- `官网产品动态`
- `官网产品动态 + 月报`
- `官网产品动态 + 培训`
- `官网产品动态 + 月报 + 培训`
- `无需宣发`

Do not explain the reason for the promotion recommendation.

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
5. Keep only customer-visible changes:
   - Functional changes
   - Entry changes
   - Default behavior changes
   - Permission/timing constraints visible to customers
6. Remove:
   - User stories
   - Acceptance condition breakdowns
   - Algorithms and formulas
   - Examples used only for explanation
   - Technical implementation details
7. Prioritize in this order:
   - Functional changes
   - Entry changes
   - Default behavior changes
   - Constraints/availability
8. Keep summary to 1-2 sentences.
9. Set feature bullet count by customer cognitive units, not requirement sub-items.
10. Prefer 3-4 bullets, maximum 6.
11. Merge bullets when they describe the same capability.
12. Prefer this structure when applicable: entry -> core capability -> data source/constraints.
13. Write bullets as system behavior, not value claims.
14. Write `【功能概述】` with this formula whenever applicable:
   - `在【业务场景】中，新增/支持【功能能力】，支持【可执行行为】，用于【具体业务用途】。`
15. `【功能概述】` must answer:
   - What could not be done before, and what can be done now?
16. Include only verifiable value in summary purpose (`用于...`), not abstract value words.
17. Use customer announcement language, not requirement/test wording.
18. Avoid step-by-step test flow phrasing in bullets; summarize as customer-visible capability.
19. Keep bullet sentence pattern consistent, prefer `新增/支持/默认/可查看` starters.
20. Do not expose internal system structure in announcement wording; rewrite to user-visible capability.
21. Avoid fine-grained UI position wording unless position change is the core change.
22. For new model/capability updates, prioritize bullets by: availability -> usage -> limits -> impact on existing behavior.
23. Exclude protocol/parameter/API/internal routing details unless they affect customer decisions.
24. For model/algorithm/engine/protocol updates, summary value must describe what customers can do, not technical capability expansion.
25. Avoid duplicated summary capability phrasing (e.g., "新增能力 + 支持同一能力"); keep one clear capability statement.
26. Prefer business-moment scenarios in summary (e.g., live session, demo flow, creation flow) over page-location phrasing.
27. Keep single-feature boundary under one title; split bullets that introduce a different capability into a separate feature entry.
28. For endpoint capability extension updates, prefer concise form: 1 summary sentence + 1-3 bullets.
29. For link-distribution/bulk-export updates, summary value should use concrete distribution actions (e.g., direct distribution/direct access), not abstract outcomes.
30. For API integration updates, use customer-facing titles (avoid internal wording like "补齐") and prefer "支持配置/支持新增".
31. For API integration summaries, prefer "在 {{API场景}} 中新增/支持 {{能力}}" phrasing.
32. Merge channel/platform bullets when capability is identical and has no user-visible difference.
33. For query API updates, summary should use "按条件查询结果对象 + 用途" and avoid duplicated capability phrasing.
34. For query API bullets, prefer concise two-part structure: query conditions + return scope.
35. In `【功能概述】`, anchor the scenario to a real business moment or usage timing, not a generic module name or page name.
36. Do not expand environmental constraints into user identity assumptions; for example, keep "海外网络环境" as a network/access scenario rather than rewriting it as "海外用户" unless the requirement explicitly says so.
37. When several acceptance items describe one customer-perceived capability, merge them into one bullet and keep only the customer-visible result.
38. Organize `【功能说明】` by user cognition blocks such as "entry + what can be done there", "operation boundary", and "permission/availability", instead of flattening every acceptance item into separate bullets.
39. If one entry carries a cluster of related capabilities (for example, viewing, creating, and reading details in the same drawer), prefer one merged bullet that describes the complete customer-visible workflow.
40. When some actions are unavailable in the current entry and must be handled elsewhere, state the customer-facing routing explicitly (for example, "需前往…管理") instead of only saying the action is not supported.
41. Final self-check before output:
   - Can the copy answer what is newly possible now?
   - Is the summary clear in one sentence when possible?
   - Is duplicate capability phrasing removed?
   - Is the business purpose concrete and verifiable?
42. Promotion-channel judgment is mandatory in Stage 2:
   - `官网产品动态`: any customer-visible change in function, default behavior, entry, permission, configuration, statistics, or usage pattern
   - `公众号产品月报`: clear customer value, clear business scenario, or strong product capability signal
   - `月度培训`: support/ops teams may need to explain usage, behavior changes, or customer configuration

For detailed rules and full templates, follow [references/prompt-v4.md](references/prompt-v4.md) and [references/classification-matrix.md](references/classification-matrix.md).
