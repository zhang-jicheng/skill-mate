# skill-mate — 技能伙伴

> **先推荐，再执行，一直陪着。**
> 自动分析你的请求，从已安装的 Skill 中推荐最合适的。

---

## 安装

```bash
# 通过 skills CLI 安装（推荐）
npx skills add zhang-jicheng/skill-mate@skill-mate -g -y
```

## 用法

在任何对话中说以下任一句：

- "推荐一个能帮我做XXX的skill"
- "用什么工具做这个"
- "我不知道用什么"

skill-mate 会自动分析你的请求，从已安装的 Skill 中推荐最合适的，并说明理由。

## 它做什么

skill-mate 是 WorkBuddy/Claude Code 等 Agent 平台的**路由前置层**。它不替代任何 Skill，而是在你发出请求时：

1. **分析意图** — 提取核心动词、研究对象、产出物
2. **扫描匹配** — 检查所有已安装 Skill，按 4 维权重评分
3. **推荐最佳** — 输出 Top 1-3 候选 + 同类对比
4. **执行确认** — 你说"就用它"就加载执行，说"换一个"就换

## 工作流管线

```
用户请求
  → grill-me（需求追问，一次一问+推荐答案）
  → ljg Read（读透材料）
  → ljg Think（想清楚：概念解剖/追本之箭）
  → Design HARD-GATE（设计方案 → 四项自检 → 用户批准）
  → ljg Write（写出来：写作引擎）
  → ljg Publish（交付传播：内容铸卡）
```

## 依赖 Skill

skill-mate 本身是一个路由推荐器，要发挥完整价值需要搭配以下 Skill 使用。安装命令同样通过 skills CLI 一键完成：

| Skill | 作用 | 安装命令 |
|-------|------|---------|
| grill-me | 需求追问 | `npx skills add mattpocock/skills@grill-me -g -y` |
| 概念解剖 | 横向拆解概念 | 同 `ljg-skills` 套装（见下方） |
| 追本之箭 | 纵向钻根因 | 同 `ljg-skills` 套装 |
| 伴读 | 深度阅读 | 同 `ljg-skills` 套装 |
| 写作引擎 | 写文章/观点 | 同 `ljg-skills` 套装 |
| 内容铸卡 | 做视觉卡片 | 同 `ljg-skills` 套装 |
| 女娲 nuwa | 人物思维蒸馏 | 参见 `yjkj-nuwa-skill-qszf` |
| dbskill 系列 | 商业模式/决策 | `npx skills add dontbesilent2025/dbskill -g -y` |

> **一键安装 ljg-skills 全部 19 个技能**：
> ```bash
> npx skills add lijigang/ljg-skills#md -g --all
> ```

> 安装完依赖后，skill-mate 的路由推荐器会自动扫描它们并纳入推荐范围。

## 评分参考

- 本仓库版本经过 4 轮 hybrid-evolver 进化 + 7 轮 darwin 评估，评分约 **85-89/100** 🟢 优秀区间
- 如果你基于本仓库修改了 SKILL.md 内容，建议用 darwin-skill 重新评估

## License

MIT
