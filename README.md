# Study Wingman 🛩️

Your personal study wingman —— 陪读式学习法。把「学会任何新知识」变成刻意练习：小步讲概念 → 即时出题 → 即时批改 → 过关才推进 → 动手实验。

Your personal study wingman: turn "learning anything new" into deliberate practice — explain in small steps → quiz immediately → grade immediately → advance only on pass → hands-on lab.

这是一个 **Cursor Agent Skill**。任何想系统学会某个框架 / 概念 / 领域的人，都能复用这套方法：你只要对 AI 说「陪我学 XX」。

This is a **Cursor Agent Skill**. Anyone who wants to systematically learn a framework / concept / domain can reuse it — just tell the AI "walk me through X".

## 核心方法 · The method

```text
定学习靶心 → 查最新 + 精读官方真源 → 规划课纲
   → 逐课讲 → 出 3-4 道自测 → 你答 → 逐题批改 → 过关进下一课
   → 概念收束 → 写最小实验你亲手跑 → 复盘掌握度
```

- **老师（Agent）**：讲清楚 + 考到位 + 改到位。
- **学习者（你）**：用自己的话答 + 亲手验证 + 定节奏。
- **过关是唯一推进信号**；实验是「真学会」的唯一证据。

```text
define goal → check latest + read official source → outline lessons
   → teach each lesson → ask 3-4 questions → you answer → grade each → advance on pass
   → wrap up concepts → run a hands-on mini-lab → review mastery
```

- **Teacher (Agent)**: explain clearly, quiz accurately, grade precisely.
- **Learner (you)**: answer in your own words, verify hands-on, set the pace.
- **Pass is the only advance signal**; the lab is the only proof of "really got it".

## 安装 · Install

把它放到 Cursor 的 Agent Store 个人 skills 目录下即可：

Copy this folder into your Cursor Agent Store's personal `skills/` directory:

```text
AgentStores/cursor_agent_stores/<你的 user id>/files/skills/study-wingman/
```

放好后，在新会话里说「陪我学 React / 带我过一遍 LangGraph / 我想学会 Docker」等，即可触发。

Once in place, start a new session and say "walk me through React" / "teach me LangGraph" / "help me truly understand Docker".

## 文件 · Files

| 文件 | 说明 |
|------|------|
| `SKILL.md` | 主流程：备课、怎么讲、怎么出题、怎么批改（红线）、实验环节、收束 |
| `examples.md` | 一次真实陪读课的批改样例（讲 → 答 → 批 → 掌握度表 → 预告） |

| File | Description |
|------|-------------|
| `SKILL.md` | Main flow: prep, how to teach, how to quiz, how to grade (hard rules), lab, wrap-up |
| `examples.md` | A real graded session as a reference (teach → answer → grade → mastery table → preview) |

## License

[MIT](LICENSE) © 2026 WilliamStellaAI
