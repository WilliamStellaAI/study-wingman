# 批改样例 · Grading examples（模板参考 · template reference）

取自一次真实的 LangGraph 陪读课。展示「出题 → 学习者作答 → 批改」的语气与格式。
讲课时用官方概念 + 通用例子，不绑业务。

From a real LangGraph guided-study session. Shows the tone and format of "quiz → learner answer → grading".
Use official concepts and generic examples, not project-specific ones.

---

## 出题（第 1 课结尾）· Quiz（end of lesson 1）

> 1. 人审跨 HTTP 请求时，最小合格配置是什么三件套？What three pieces form the minimum viable setup for cross-request human-in-the-loop?
> 2. 为什么开发时热重载后点「确认」会碎？（用官方术语说）Why does "confirm" break after hot-reload in dev? (answer in official terms)
> 3. Resume 时节点从哪开始跑？对「闸门节点该多厚」意味着什么？Where does a node resume from, and what does that imply for how "thin" the gate node should be?
> 4. `Command({ goto })` 和 `Command({ resume })` 在官方语义里分别给谁用？In official semantics, what are `Command({ goto })` and `Command({ resume })` each used for?

## 学习者作答 · Learner answers

> 1. checkpointer、thread_id、interrupt(payload)
> 2. 缺少 checkpointer，导致 thread_id 为空，记不住上一次运行到哪里了
> 3. 从调用了 interrupt 的那个节点开头重新执行，interrupt 之前这个节点里的代码会再跑一遍……如果闸门做薄，就只跑失败的部分？
> 4. Command({ goto }) 针对图里的某个节点，而 Command({ resume }) 针对的是整张图，需要恢复。

## 批改（参考语气与结构）· Grading（reference tone and structure）

```markdown
# 批改 · 第 1 课

## 1 — 对
三件套就是：checkpointer + thread_id + interrupt(payload)。

## 2 — 方向对，用词要改
不是「缺 checkpointer」或「thread_id 为空」。是有 MemorySaver（也是 checkpointer，只是存 RAM）、有 thread_id；没有的是「跨进程仍在的存档内容」。
更准确：人审跨请求时，若 checkpointer 不持久，thread_id 再稳定也读不到上次的 interrupt 检查点。

## 3 — 半对；「超级步里已成功部分」和另一概念搅在一起了
Resume 只会从调用了 interrupt 的那个节点开头再跑，已经跑完并离开的上游节点不会重跑。
薄闸门 = 每次确认少做废话；不是「只重跑失败那段」——框架没有节点内断点续跑，是整节点重来。

## 4 — 需要纠正
| Command({ resume }) 作 invoke 输入 | 人审续跑的唯一正统入口；值变成 interrupt() 的返回值 |
| Command({ goto / update }) 作节点返回值 | 节点内部决定改状态 / 跳到哪 |

## 小结你的掌握度
| 题 | 判定 |
|----|------|
| 1 | 过 |
| 2 | 过（改口：非持久化，不是 thread 空） |
| 3 | 过（改口：整节点重跑；薄 = 少重复，≠ 只跑失败段） |
| 4 | 需改（resume/goto 的官方边界） |

# 第 2 课预告（你回「继续」就开始）
1. 校验人输入：为何不要 while + interrupt，要用边绕回
2. 多道闸门：多次 interrupt vs 多个闸门节点
3. Checkpointer vs Store
4. 一张「正统 HITL vs 当前实现」对照表
```

---

## 要点提炼 · Key takeaways

- **每道题三个动作**：落判定 → 指出「哪句对 / 哪句要收紧」→ 给准确说法。Three moves per question: verdict → point out what's right vs. needs tightening → give the precise phrasing.
- **概念混淆单独拎出来**：用表格/对照，不糊弄。Call out concept confusion explicitly with a table / contrast.
- **结尾给掌握度表**：让学习者清楚自己卡在哪。End with a mastery table so the learner sees exactly where they're stuck.
- **给下一课预告 + 明确推进信号**（「你说继续」），把节奏交给学习者。Preview the next lesson and hand the pace to the learner ("say continue").
