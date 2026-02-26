---
name: product-broadcast
description: Convert internal requirement docs into concise customer-facing product update announcements for enterprise live-streaming products. Use when asked to write, rewrite, or review release notes/product updates from PRD or requirement tickets, especially when content must filter out technical details and keep only customer-visible changes.
---

# Workflow

1. Read [references/prompt-v4.md](references/prompt-v4.md) before drafting.
2. Run Stage 1 first and output a diagnostic report.
3. Pause after Stage 1 and wait for confirmation.
4. Run Stage 2 and generate the final announcement with the required structure.

# Stage 1 Output (Mandatory)

Always output:

`📋 需求诊断报告`

Include:

- `归类为：👉【类型】` where type is one of:
  - `新功能`
  - `核心流程优化`
  - `用户体验/功能细节优化`
  - `技术集成类优化`
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

1. Use zero-person narrative. Do not use:
   - `我们`
   - `我`
   - `团队`
   - `您`
   - `你`
2. Prioritize in this order:
   - Functional changes
   - Entry changes
   - Default behavior changes
   - Constraints/availability
3. Keep summary to 1-2 sentences.
4. Keep feature bullets to 4-6 items when feature details are needed.
5. Write bullets as system behavior, not value claims.

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

For detailed rules and full templates, follow [references/prompt-v4.md](references/prompt-v4.md).
