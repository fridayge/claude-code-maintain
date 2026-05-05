# /maintain — Claude Code 三维工作区维护技能

> 防膨胀（免疫）+ 防冗余（精简）+ 防过时（自进化），一个入口。

## 一句话

`/maintain` 让你的 Claude Code 工作区规则体系持续保持高信息密度、低维护负担、零腐化残留。

## 安装

```bash
claude skill install fridayge/claude-code-maintain
```

## 四个子模式

```
/maintain
  ├─ init    — 新项目初始化（注入三维规则体系）
  ├─ check   — 快速健康扫描（一次检查三个维度）
  ├─ slim    — 定向瘦身（审查可精简空间）
  └─ audit   — 月度审计报告
```

### init — 新建项目一把配齐

```bash
/maintain init
```

自动生成含三条规则的 CLAUDE.md：

- **免疫规则**：行数 ≤ 150、日志 ≤ 3 条、决策有过期条件
- **精简规则**：文件增长 > 50 行自动审查可精简空间
- **自进化规则**：自动维护引用一致性（版本号/死链接/路径/时标）

### check — 三维健康扫描

```bash
/maintain check
```

同时检查：
1. **不膨胀**：CLAUDE.md 超标？Session 日志超限？Decisions 缺 Expires？
2. **不冗余**：最近增长 > 50 行的文件？可精简空间？
3. **不过时**：版本号残留？死链接？MCP 残留？路径失效？时标缺失？

### slim — 定向瘦身

```bash
/maintain slim <文件路径>
```

降秩审查指定文件的可精简空间，输出删减建议（不自动执行，等你确认）。

### audit — 月度健康报告

```bash
/maintain audit
```

生成完整健康报告，包含：规则触发统计、沉默规则列表、CLAUDE.md 行数趋势、过期决策提醒、SIGNAL 汇总。

## 自动执行（零操作）

正列表 Op ①-⑤+⑦ 已嵌入 CLAUDE.md 工作规则，**每次编辑规则文件时自动触发**：

| Op | 操作 | 方式 |
|----|------|------|
| ① | 过期版本号更新 | 自动 |
| ② | 死链接标记 | 自动 |
| ③ | 已移除 MCP 残留清理 | 自动 |
| ④ | 已变更文件路径更新 | 自动 |
| ⑤ | 外部数据时间戳标注 | 自动 |
| ⑥ | 过期决策归档提醒 | 产 SIGNAL，等人确认 |
| ⑦ | 规则触发日志自动补录 | 自动 |

## 硬边界（AI 永不自动突破）

- ✗ 简化/缩短/合并规则文本
- ✗ 判断某条规则"不再需要"
- ✗ 调整规则严重性层级（SHOULD ↔ MUST）
- ✗ 删除任何带"Why"或事故来源的段落
- ✗ 新增规则（需人起草和批准）

## 理论基础

源自 2026 年 5 月 5 日一场圆桌讨论。六位思想家——Claude Shannon、John von Neumann、Donella Meadows、Edsger Dijkstra、Hannah Arendt、李飞飞——围绕「Claude Code 能否自我进化」展开了五轮辩论。

核心结论：**AI 不可全量自优化，但可在行政权正面清单内安全自动维护。**

von Neumann 最终综合出了六层架构：

```
第 0 层：不变宪章 — "自优化的最终决策权永远在人手中"（不可修改）
第 1 层：正面清单 — 7 项 AI 可自动执行的维护操作
第 2 层：自动执行 — Ops ①-⑤+⑦ 每次编辑规则时自动触发
第 3 层：注意信号 — AI 发现问题后写 SIGNAL，等人确认
第 4 层：周期审计 — 月度活跃度报告 + 季度正面清单审查
第 5 层：硬边界 — AI 永远不得进入
```

第 0 层作为外部锚点，终止了自指涉规则的无限回归。

## 三维分工

| 维度 | 管什么 | 类比 |
|------|--------|------|
| **immune**（免疫） | 不膨胀 — 行数/日志/过期 | 免疫系统 |
| **slim**（精简） | 不冗余 — 文件增长审查 | 新陈代谢 |
| **evolve**（自进化） | 不过时 — 引用/版本/链接/时标 | 自修复 |

三者互补不重叠。immune 防胖，slim 防虚，evolve 防旧。

## 与已有技能的关系

`/maintain` 合并了两个旧技能：

- `/immune-init` → `/maintain init`（向后兼容，旧命令自动委托）
- `/self-evolve` → `/maintain check` + `/maintain audit`（同上）

旧技能已更新为薄包装器，调用时自动转发到 `/maintain`。

## 许可证

MIT

---

*Generated with [Claude Code](https://claude.ai/code) via [Happy](https://happy.engineering)*
