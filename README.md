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

一个 skill 仓库，可在任何支持 Agent Skills 标准的 agent 里一键安装（Cursor、Codex、Copilot、Gemini CLI、Claude Code、WorkBuddy 等）。

Install in one command on any agent that supports the Agent Skills open standard (Cursor, Codex, Copilot, Gemini CLI, Claude Code, WorkBuddy, etc.).

### 方式 1 · GitHub CLI（推荐 · Recommended）

```bash
gh skill install WilliamStellaAI/study-wingman --agent cursor --scope user
```

把 `--agent cursor` 换成 `codex` / `claude-code` / `github-copilot` / `gemini-cli` 等即可装到对应 agent；`--scope project` 则装进当前项目。

Swap `--agent cursor` for `codex` / `claude-code` / `github-copilot` / `gemini-cli` etc.; use `--scope project` to install into the current repo.

### 方式 2 · skills.sh（npm 式 · npm-style）

```bash
npx skills add WilliamStellaAI/study-wingman --agent cursor
```

### 方式 3 · 手动 clone（Manual）

```bash
git clone https://github.com/WilliamStellaAI/study-wingman ~/.cursor/skills/study-wingman
```

装好后，在新会话里说「陪我学 React / 带我过一遍 LangGraph / 我想学会 Docker」等即可触发。

Once installed, start a new session and say "walk me through React" / "teach me LangGraph" / "help me truly understand Docker".

## 文件 · Files

```text
.
├── README.md
├── LICENSE
└── skills/
    └── study-wingman/
        ├── SKILL.md       # 主流程：备课、怎么讲、怎么出题、怎么批改（红线）、实验、收束
        └── examples.md    # 一次真实陪读课的批改样例
```

| File | Description |
|------|-------------|
| `skills/study-wingman/SKILL.md` | Main flow: prep, how to teach, how to quiz, how to grade (hard rules), lab, wrap-up |
| `skills/study-wingman/examples.md` | A real graded session as a reference |

## License

[MIT](LICENSE) © 2026 WilliamStellaAI
