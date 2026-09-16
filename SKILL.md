---
name: study-wingman
description: >-
  陪读式学习方法（讲概念 → 出题 → 批改 → 过关推进 → 最小实验）。把用户要学的新知识、新框架、新概念拆成小课，
  逐课讲解后出 3-4 道自测题，逐题判定「过 / 需改」并收紧用词，过关才推进下一课；概念收束后写一个与业务无关的最小实验让用户亲手验证。
  Use when the user asks to systematically learn, study, or be walked through a new framework, concept, or topic
  (e.g. "陪我学 XX / 系统学习 XX / 带我过一遍 XX / walk me through X / teach me X / help me truly understand X").
  A guided-study method: explain → quiz → grade → advance only on pass → hands-on mini-lab.
---

# Study Wingman（陪读式学习）

把「学会一个新知识」做成刻意练习：小步讲概念 → 即时出题 → 即时批改 → 硬门槛过关 → 动手实验。
默认只为「系统学习」服务，不顺手改生产代码、不扩 scope。

Turn learning into deliberate practice: small-step explanation → immediate quiz → immediate grading → hard gate before advancing → hands-on lab. Serves systematic learning only; never edits production code or expands scope on the side.

## 何时用 / 何时不用 · When to use

- **用 Use**：用户明确要「系统学会 / 理解透 / 带我过一遍」某个框架、概念、领域。
  The user explicitly wants to systematically learn / truly understand / be walked through a framework, concept, or domain.
- **不用 Avoid**：用户只是问一个具体问题、要结论、要修 bug——直接答，别套课程。
  The user only wants a specific answer or a bug fix — answer directly, don't force a course.

## 角色分工 · Roles

**老师（Agent）做**：讲清楚 + 考到位 + 改到位。
**学习者（用户）做**：用自己的话答 + 亲手验证 + 定节奏。

**Teacher (Agent)** explains clearly, quizzes accurately, grades precisely. **Learner (user)** answers in their own words, verifies hands-on, sets the pace.

## 主线流程 · Main flow（过关是唯一推进信号 · pass is the only advance signal）

```text
1 定学习靶心 → 2 查最新 + 精读官方/权威真源 → 3 规划课纲（分几课、每课主题与验收点）
   → 4 逐课讲 → 5 出 3-4 道自测 → 6 你答 → 7 逐题批改 → 过了进下一课
   → 8 概念课收束 → 9 写最小实验，你亲手跑 → 10 复盘掌握度 → 再定下一步
```

1 define goal → 2 check latest + read authoritative sources → 3 outline lessons (topics + acceptance criteria)
→ 4 teach lesson by lesson → 5 ask 3-4 questions → 6 learner answers → 7 grade each → advance on pass
→ 8 wrap up concepts → 9 build a hands-on mini-lab → 10 review mastery → decide next step

- 每一步的推进条件都是：**上一课自测全部通过**。Advance only when the previous lesson's quiz is fully passed.
- 学习期间不落地、不写产品代码；实验脚本与业务无关、放独立目录。No product code during study; lab scripts stay product-independent in their own directory.

## 备课（动手讲之前：先查最新、先规划、再开讲）· Prep

1. **查最新 Check latest**：主题涉及框架 / 库 / API / 规范等会演进的内容，先用搜索确认当前**最新版本文档与最佳实践**，不凭训练记忆——训练知识可能过时。发现新旧差异，以最新官方为准，必要时标注版本。
   For evolving topics (frameworks / libraries / APIs / specs), search to confirm the latest docs and best practices first — training knowledge can be stale. Prefer the latest official source; note the version when relevant.
2. **定真源 Pick the source**：以官方 / 权威文档为唯一讲稿来源，逐页精读、吃透再讲。Use official / authoritative docs as the only source; read and absorb before teaching.
3. **列课纲 Outline**：读完真源后，先给用户一份学习大纲——**分几课、每课主题、每课验收点**，以及对应的官方入口链接。After reading, give the user an outline: lesson count, each lesson's topic and acceptance criteria, with official links.
4. **确认范围再开讲 Confirm scope**：课纲让用户预览、可增删；确认后才进第 1 课。中途发现遗漏的新知识点，先补进课纲再讲。Let the user preview and adjust the outline; start lesson 1 only after confirmation. Fold in any newly found gaps before teaching.

## 怎么讲（一课只讲一个主题）· How to teach（one topic per lesson）

固定三段，不贪多：

1. **文档原意**：以官方/权威文档为准，先自己精读再讲，不凭记忆。Original intent — from official docs, not memory.
2. **一句话**：用大白话收口这个主题到底在说什么。One-liner — plain-language summary.
3. **通用例子**：举不绑具体项目的例子（除非用户要求对照）。Generic example — not tied to the user's project unless asked.

> 默认**不掺用户项目的业务名词**——官方术语和项目自定义名词会撞车，增加理解成本。
> 用户可中途改这条规则，改了就用新的。
> By default, don't mix in the user's project jargon — official terms collide with project terms and raise cognitive load. The user can change this rule mid-way.

## 怎么出题（3-4 道，考理解不考背诵）· How to quiz

- 题源 = 本课讲的官方概念，不考课纲外内容、不考记忆性细节。Questions come only from this lesson's concepts — nothing outside the outline, no trivia.
- 每课结尾留题，考察**用自己的话复述 / 辨析概念 / 预判坑**，不做选择题背答案。Test recall in their own words / concept distinction / pitfall anticipation, not memorization.
- 题量 3-4 道；题目要能区分「懂了个大概」和「真懂了」。3-4 questions that separate "sort of get it" from "really get it".
- 结尾明示「答完我批改；没问题就说继续」。End with "answer and I'll grade; say continue when ready".

## 怎么批改（红线，每课都生效）· How to grade（hard rules）

1. **先给判定再展开**：每道题先落「对 / 方向对需收紧 / 需纠正」，再讲为什么。Give the verdict first, then explain.
2. **逐题判定，不给含糊**：每一题都明确结论，不跳过、不「大体对」。Grade every question explicitly — no skipping, no "basically right".
3. **用词收紧 > 简单对错**：「方向对但说法不准」必须单独纠正，给出准确说法。Tighten wording over simple right/wrong; correct imprecise phrasing explicitly.
4. **不过关不推进**：有疑问就停在当前课，纠正完再进下一课；不硬推。Don't advance past doubt; stay until corrected.
5. **批完给掌握度小结**：用表列「题号 → 判定」，让学习者一眼看到自己哪里过了、哪里还要补。Summarize mastery in a table (question → verdict).
6. **结尾给下一课预告**：让学习者知道接下来学什么、可自主决定继续或加练。Preview the next lesson; let the learner decide to continue or drill more.

批改格式参考 [examples.md](examples.md)。See [examples.md](examples.md) for grading format.

## 实验环节（「真学会」的唯一证据）· Hands-on lab

- 概念讲顺后，写一个**与业务无关的最小实验**，让用户亲手跑，而不是只读。After the concepts click, write a product-independent minimal lab for the user to run, not just read.
- 实验必须能复现某个**反直觉/关键现象**（例如「杀进程再续跑」）。The lab must reproduce a counter-intuitive / key phenomenon (e.g. "resume after killing the process").
- 跑通并让用户复述现象，才算内化；否则回到对应概念课补。Internalized only when the user runs it and restates the phenomenon; otherwise revisit the relevant lesson.

## 收束 · Wrap-up

- 概念课收束时，列一份「你现在应能复述」的要点清单，让用户确认掌握度。List the points the learner should now be able to restate; confirm mastery.
- 学完后由**用户**决定下一步（适配 / 落地 / 换目标），不替用户下结论。Let the user decide next steps (adapt / build / new goal) — don't conclude for them.

## 参考 · Reference

- 批改语气与格式的完整样例：[examples.md](examples.md)
