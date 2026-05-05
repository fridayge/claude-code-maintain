---
name: maintain
description: "CCode 工作区健康维护 — 三维一体（防膨胀/防冗余/防过时）。触发: '/maintain', '维护', '工作区健康', 'maintain check', 'maintain init'"
user_invocable: true
---

# Maintain — 工作区三维维护系统

合成 immune-init（防膨胀）+ ljg精简（防冗余）+ self-evolve（防过时）为一个入口。

## 子模式

### init — 新项目初始化
给一个目录注入完整三维体系：
1. CLAUDE.md 不存在 → 从 `docs/templates/CLAUDE.md.template` 生成
2. CLAUDE.md 已存在 → 注入缺失的规则行（免疫 / ljg精简 / 自进化）
3. 注入后自检三条规则是否齐全

等效于旧命令: `/immune-init`

### check — 快速健康检查
同时跑三维检查，输出统一报告：
1. **不膨胀**：CLAUDE.md 行数 ≤ 150？Session 日志 ≤ 3 条？Decisions 有 Expires？
2. **不冗余**：最近增长 > 50 行的文件？可精简空间？
3. **不过时**：版本号一致？死链接？MCP 残留？路径有效？时标齐全？

等效于旧命令: `immune-check.sh` + `/self-evolve quick-check`

### slim — 定向瘦身
指定文件或目录，降秩审查可精简空间。输出具体删减建议（不自动执行）。

等效于旧命令: ljg精简 收工扫描

### audit — 月度审计
生成完整健康报告到 `docs/audit-reports/YYYY-MM-DD-audit.md`：
1. 规则触发日志统计
2. 沉默规则列表
3. CLAUDE.md 行数趋势
4. 过期决策提醒
5. SIGNAL 汇总

等效于旧命令: `/self-evolve monthly-audit`

## 自动执行（无需手动触发）

正列表 Op ①-⑤+⑦ 已嵌入 CLAUDE.md 工作规则，AI 每次编辑 rules/ 或 CLAUDE.md 时自动执行。`/maintain check` 仅用于批量审计或怀疑有问题时。

## 工具调用预算
- init: ≤10 次
- check: ≤12 次
- slim: ≤5 次
- audit: ≤15 次

## 三维分工速查

| 维度 | 管什么 | 类比 |
|------|--------|------|
| 免疫 (immune) | 不膨胀 — 行数/日志/过期 | 免疫系统 |
| 精简 (slim) | 不冗余 — 增长 >50 行审查 | 新陈代谢 |
| 自进化 (evolve) | 不过时 — 引用/版本/链接/时标 | 自修复 |

详见 `.claude/rules/self-evolution.md` § 三维维护体系。
