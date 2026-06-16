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

| 原始名称 | 作用 | 作者 | 安装 / 下载 |
|---------|------|------|------------|
| **grill-me** | 需求追问：一次一问+推荐答案，动手前把需求问清楚 | [Matt Pocock](https://github.com/mattpocock/skills) | `npx skills add mattpocock/skills@grill-me -g -y` |
| **ljg-learn**（原"概念解剖"） | 8 维度横向剖开一个概念，压成一句顿悟 | [李继刚](https://github.com/lijigang/ljg-skills) | 见下方 ljg-skills 套装 |
| **ljg-think**（原"追本之箭"） | 纵向深钻到不可再分的本质 | 同上 | 同套装 |
| **ljg-read**（原"伴读"） | 逐段陪你读任何文本，含翻译+旁逸 | 同上 | 同套装 |
| **ljg-writes**（原"写作引擎"） | 写有人格有立场的文章，1000-1500字 | 同上 | 同套装 |
| **ljg-card**（原"内容铸卡"） | 把内容转为 PNG 视觉卡片，7种模式 | 同上 | 同套装 |
| **ljg-roundtable**（原"圆桌思辨"） | 多人辩证对话，测试观点是否站得住 | 同上 | 同套装 |
| **ljg-paper**（原"论文研读"） | 提取论文核心想法，重理解不重批判 | 同上 | 同套装 |
| **ljg-paper-river**（原"论文倒读"） | 递归挖引用链，从源头讲问题演化史 | 同上 | 同套装 |
| **ljg-book**（原"拆书"） | 拆解一本书的骨架：问题→假设→框架→观点 | 同上 | 同套装 |
| **ljg-qa**（原"信息提问"） | 抽成 Q-A 链，每个 A 含结论+形式化+步骤+边界条件 | 同上 | 同套装 |
| **nuwa-skill**（原"女娲"） | 三源调研法蒸馏人物思维框架为新 Skill | [邱数智方](https://github.com/alchaincyf/nuwa-skill) | 从上游仓库安装：`npx skills add alchaincyf/nuwa-skill -g -y` |
| **dbskill** | 消解问题→行动路径，含 21 个子技能（商业模式诊断/决策系统等） | [dontbesilent](https://github.com/dontbesilent2025/dbskill) | `npx skills add dontbesilent2025/dbskill -g -y` |

> **一键安装 ljg-skills 全部 19 个技能**（覆盖 Read→Think→Write→Publish 整条管线）：
> ```bash
> npx skills add lijigang/ljg-skills#md -g --all
> ```
> GitHub 仓库 → [lijigang/ljg-skills](https://github.com/lijigang/ljg-skills)

> 安装完依赖后，skill-mate 的路由推荐器会自动扫描它们并纳入推荐范围。你也可以只装其中几个，skill-mate 会根据实际已安装的 Skill 做匹配。

## 评分参考

- 本仓库版本经过 4 轮 hybrid-evolver 进化 + 7 轮 darwin 评估，评分约 **85-89/100** 🟢 优秀区间
- 如果你基于本仓库修改了 SKILL.md 内容，建议用 darwin-skill 重新评估

## License

MIT
