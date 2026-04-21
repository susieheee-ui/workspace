# product-broadcast skill

将内部需求单转换为可直接发送给客户的产品动态公告，适用于企业直播产品场景。

## 目录结构

```text
product-broadcast/
├── SKILL.md
├── PROMPT_SHARE.md
└── references/
    ├── classification-matrix.md
    ├── prompt-v4.md
    └── review-checklist.md
```

## 能力说明

- 两阶段流程：
  - 阶段一先输出“需求诊断报告”，并暂停等待确认
  - 阶段二输出“功能标题 / 功能概述 / 功能说明 / 宣发建议”
- 严格执行“客户可见变化”筛选
- 使用零人称叙事，不使用“我们 / 我 / 团队 / 您 / 你”
- 按四类需求矩阵自动选择模板 A / B / C
- 支持判断宣发渠道：
  - 官网产品动态
  - 公众号产品月报
  - 月度培训

## 规则来源

- `references/prompt-v4.md`：权威规则版本
- `references/classification-matrix.md`：分类判定矩阵
- `references/review-checklist.md`：交付前自检清单
- `PROMPT_SHARE.md`：便于复制转发的统一提示词

## 输出结构

### 阶段一

固定输出：

- `📋 需求诊断报告`
- `归类为：👉【类型】`
- `分类判定依据`
- `要素提取`
- `拟定策略`

### 阶段二

固定输出：

- `【功能标题】`
- `【功能概述】`
- `【功能说明】`（仅模板 A / C 输出）
- `【宣发建议】`

`【宣发建议】` 仅允许以下结果：

- `官网产品动态`
- `官网产品动态 + 月报`
- `官网产品动态 + 培训`
- `官网产品动态 + 月报 + 培训`
- `无需宣发`

## 本地安装

1. 克隆仓库

```bash
git clone <repo-url>
```

2. 复制 skill 到 Codex skills 目录

```bash
mkdir -p ~/.codex/skills
cp -R product-broadcast ~/.codex/skills/
```

3. 完成后可在对话中通过“产品动态撰写 / 需求转公告”类任务触发

## 更新流程

1. 修改规则文件

通常更新：

- `SKILL.md`
- `references/prompt-v4.md`
- `references/review-checklist.md`
- `PROMPT_SHARE.md`

2. 提交并推送

```bash
git add .
git commit -m "docs: update product-broadcast rules"
git push
```

3. 已复制到 `~/.codex/skills/product-broadcast` 的同事，同步覆盖最新目录

## 建议版本规则

- 大改（流程变化 / 模板变化 / 宣发判断变化）：`feat: ...`
- 小改（措辞 / 示例 / 检查项）：`docs: ...`
- 修正规则冲突：`fix: ...`

## 维护建议

- 每次规则调整补一个最小示例：输入需求 + 期望输出
- `references/prompt-v4.md` 保持为唯一权威来源
- `SKILL.md` 保留执行流程与强约束
- `PROMPT_SHARE.md` 只保留适合直接转发的版本
