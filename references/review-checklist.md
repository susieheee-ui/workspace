# Product Broadcast Review Checklist

Use this checklist before final output.

- Output follows two-stage flow: diagnostic first, then final after confirmation.
- Requirement text is fully covered with no missing explicit logic.
- No extra logic is introduced beyond requirement text.
- Requirement type is judged using `classification-matrix.md` with evidence for core difference + A/B/C/D.
- No forbidden pronouns: `我们 / 我 / 团队 / 您 / 你`.
- Content keeps only customer-visible changes.
- Internal implementation, formulas, and acceptance logic are removed.
- Structure matches selected template `A/B/C`.
- Summary is 1-2 sentences.
- Summary includes: business scenario + capability + executable behavior + verifiable purpose (`用于...`).
- Summary does not contain abstract value words (e.g., `提升效率/增强体验/赋能/闭环/打造/优化体验/精细化运营`).
- Summary uses customer announcement language, not requirement-document wording.
- Summary and bullets do not expose internal system structure terms; all such text is rewritten to visible capability.
- Summary does not duplicate same capability wording ("新增能力 + 支持同一能力").
- Summary uses business-moment scenario wording before page-location wording when possible.
- Bullets are system behaviors (`新增/支持/调整/默认/可查看`).
- Bullets avoid test-step sequence wording (`点击后/保存后/返回后...`) and describe visible capability instead.
- Bullets avoid fine-grained UI location wording unless location change is itself the core user-visible change.
- Feature bullets are organized by customer cognitive units, not requirement sub-items.
- Feature bullets are preferably 3-4 items, maximum 6.
- Bullets with same capability are merged (e.g., send/stop/result as one management capability).
- Bullets stay within single-feature boundary; unrelated capability changes are split out.
- Ordering follows: function -> entry -> default behavior -> constraints.
- For new model/capability announcements, bullet priority is: availability -> usage -> limits -> impact on existing behavior.
- Protocol/parameter/API/internal routing details are excluded unless they directly affect customer decisions.
- For model/algorithm/engine/protocol updates, summary value is customer-actionable outcome (what users can do), not technical expansion wording.
- For endpoint capability extension updates, output is concise: 1 summary sentence + 1-3 bullets.
- For link-distribution/bulk-export updates, summary value uses concrete distribution actions (`直接分发/直接访问`), not abstract-only wording.
- For API integration updates, title avoids internal wording (e.g., `补齐`) and uses customer-facing wording (`支持配置/支持新增`).
- For API integration updates, summary uses API-scene phrasing and channel/platform bullets are merged when no visible difference exists.
- For query API updates, summary includes query conditions + result object + concrete purpose.
- For query API updates, bullets are concise and centered on `query conditions` and `return scope`.
