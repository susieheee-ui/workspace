# product-broadcast skill

将内部需求单转换为可直接发送给客户的产品动态公告（企业直播场景）。

## 目录结构

```text
product-broadcast/
├── SKILL.md
└── references/
    ├── prompt-v4.md
    └── review-checklist.md
```

## 能力说明

- 两阶段流程：
  - 阶段一：先输出“需求诊断报告”，并暂停等待确认
  - 阶段二：确认后输出“功能标题/功能概述/功能说明”
- 严格执行“客户可见变化”筛选
- 零人称叙事（不使用“我们/我/团队/您/你”）
- 按 V4 规范使用四类需求矩阵与模板 A/B/C

## 本地安装（给同事）

1. 克隆仓库
```bash
git clone <repo-url>
```

2. 复制 skill 到 Codex skills 目录
```bash
mkdir -p ~/.codex/skills
cp -R product-broadcast ~/.codex/skills/
```

3. 完成后可在对话中通过“产品动态撰写/需求转公告”类任务触发

## 更新流程（维护者）

1. 修改规则文件（通常是 `SKILL.md` 或 `references/*.md`）
2. 提交并推送
```bash
git add .
git commit -m "docs: update product-broadcast rules"
git push
```
3. 同事在本地仓库执行
```bash
git pull
```
4. 如同事已复制到 `~/.codex/skills/product-broadcast`，请同步覆盖最新目录

## 建议版本规则

- 大改（流程变化/模板变化）：`feat: ...`
- 小改（措辞、示例、检查项）：`docs: ...`
- 修正规则冲突：`fix: ...`

## 维护建议

- 每次规则调整都补一个最小示例（输入需求 + 期望输出）
- 保持 `prompt-v4.md` 为权威规范来源，`SKILL.md` 仅保留执行流程与约束
