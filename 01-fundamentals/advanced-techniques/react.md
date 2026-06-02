# ReAct — 推理 + 行动交织

> 🟡 **了解概念** | DAIR.AI Advanced Prompting #6 | [返回总览](../dair-ai-advanced-prompting.md)

---

## 1. 一句话解释

**让模型交替进行"思考"和"行动"，通过外部工具获取信息来辅助推理。**

```
ReAct 循环：

Thought（思考）→ Action（行动/调用工具）→ Observation（观察结果）
      ↑                                                    │
      └────────────────────────────────────────────────────┘
                        循环直到得出最终答案
```

**完整示例（查 Olivia Wilde 的男朋友 + 算术）：**

```
Thought: 我需要查 Olivia Wilde 的男朋友是谁。
Action: Search["Olivia Wilde boyfriend"]
Observation: Harry Styles

Thought: 我需要知道 Harry Styles 多少岁。
Action: Search["Harry Styles age"]
Observation: 29 years

Thought: 计算 29 的 0.23 次方。
Action: Calculator[29^0.23]
Observation: 2.169

Final Answer: Harry Styles, 29 岁, 29^0.23 = 2.169
```

---

## 2. 适合什么时候用

- ✅ **需要实时信息的任务** — 搜索最新新闻/价格/数据
- ✅ **需要精确计算的任务** — 调用计算器/代码解释器
- ✅ **需要查询数据库的任务** — 查库存/订单/客户信息
- ✅ **Agent / 智能体开发** — **ReAct 是 Agent 的核心技术基础**
- ✅ **需要多步信息收集才能回答的问题** — 每一步都可能需要不同的工具

---

## 3. 不适合什么时候用

- ❌ **信息已经全部给定的场景** — 数据都在 prompt 里，不需要外部工具
- ❌ **纯推理/创作任务** — 写文案/做分析/翻译等，CoT 更合适
- ❌ **工具不可靠/不稳定的环境** — 外部 API 故障会导致整个循环中断
- ❌ **延迟敏感的实时对话** — 多轮工具调用累积延迟高
- ❌ **不需要验证/补充信息的简单问答** — Zero-Shot 就够了

---

## 4. ReAct vs. CoT 对比

| 维度 | CoT | ReAct |
|------|-----|-------|
| 信息来源 | 仅内部知识 | 内部 + 外部工具 |
| 幻觉风险 | 较高 | 较低（可验证） |
| 灵活性 | 高（自由发挥） | 较低（结构约束） |
| 最佳场景 | 知识充足的任务 | 需要实时信息/计算的任务 |
| 工具依赖 | 不需要 | 必须（搜索/API/计算器） |
| 实现复杂度 | 低（一句话 prompt） | 中（需要工具调用框架） |

**⚠️ 关键认知：ReAct 是 Agent 的核心技术基础。** 你现在用的 OpenClaw/Claude Code/LangChain Agent 本质上都运行在这种模式上。

---

## 5. 中文提示词模板

### ReAct Agent System Prompt 模板

```markdown
你是一个具备工具调用能力的智能助手。

## 可用工具
{工具列表及其描述}

## 工作模式
你需要按照以下模式进行思考和操作：

Thought: {思考下一步该做什么}
Action: {工具名}[{参数}]
Observation: {等待工具返回结果}

（重复 Thought → Action → Observation 循环，
直到你收集到足够的信息，然后给出 Final Answer）

Final Answer: {基于所有观察结果的最终答案}
```

**带具体工具的完整示例：**
```markdown
你是一个具备工具调用能力的助手。

## 可用工具
- search(query): 搜索互联网信息，返回相关摘要
- calculator(expr): 执行数学表达式计算
- lookup_data(table, condition): 查询本地数据库表

## 工作模式
Thought: {思考下一步该做什么}
Action: {工具名}[{参数}]
Observation: {等待工具返回结果}
（循环直到可以给出 Final Answer）
```

---

## 6. OpenClaw 使用方式

### 配置方案：ReAct Agent（工具调用型）

适用于：需要搜索、计算、API 调用等外部操作的 Agent。

```
┌───────────────────────────────────────────────────┐
│                ReAct Agent                         │
├───────────────────────────────────────────────────┤
│ System Prompt:                                    │
│   你是一个具备工具调用能力的助手。                    │
│                                                   │
│   可用工具：                                        │
│   - search(query): 搜索互联网信息                   │
│   - calculator(expr): 执行数学计算                  │
│   - lookup_data(table, condition): 查询数据库        │
│                                                   │
│   工作模式：                                        │
│   Thought: {思考下一步该做什么}                     │
│   Action: {工具名}[{参数}]                          │
│   Observation: {等待工具返回结果}                    │
│   （循环直到可以给出 Final Answer）                   │
│                                                   │
│ User Message:                                      │
│   {用户的原始输入}                                  │
└───────────────────────────────────────────────────┘
```

**⚠️ 这是 Agent 技术的核心架构。** Claude Code、OpenClaw、LangChain Agent 本质上都运行在这种模式上。

---

## 7. 单 Agent 适配度

# ★★★★★ (5/5)

**原因：**
- ReAct 就是**为单 Agent 设计的**——一个 Agent 内部完成 Thought→Action→Observation 循环
- 单 Agent + 工具调用是最常见的 ReAct 实现形式
- **这是你构建工具调用型 Agent 的标准模式**

---

## 8. 多 Agent 适配度

# ★★★★☆ (4.5/5)

**原因：**
- **ReAct 是多 Agent 系统中单个 Agent 的核心行为模式**
- 在多 Agent 系统中，某些 Agent 是 ReAct 型（需要外部信息），另一些是纯 CoT 型（纯推理）
- ReAct Agent 可以作为 Prompt Chaining pipeline 中的一个或多个步骤

---

## 9. 常见失败

| # | 失败模式 | 典型表现 | 根本原因 |
|---|----------|----------|----------|
| 1 | **进入死循环** | Agent 反复搜索同一个关键词，无法终止 | 缺少最大循环次数限制和终止条件 |
| 2 | **选错工具** | 需要搜数据库时却用了搜索引擎 | 工具描述不清楚或 Agent 理解偏差 |
| 3 | **Observation 过载** | 工具返回大量无关信息，Agent 被干扰 | 缺少结果过滤/截断机制 |
| 4 | **过早给出 Final Answer** | 信息还没收集完就草率结论 | 需要在 prompt 中强调"确认信息充足后再回答" |
| 5 | **工具调用格式错误** | Action 输出不符合工具的 API 规格 | 需要提供清晰的工具使用示例 |
| 6 | **在不该用 ReAct 的场景使用** | 信息全在 prompt 里还去搜索 | 浪费 token 和延迟 |

---

## 10. 修正提示

### 修正：ReAct 死循环 → 加入护栏机制

**❌ 错误：** Agent 一直在搜索同一个东西

**✅ 修正——在 System Prompt 或代码层面加入循环控制：**
```
System Prompt 增加：
- 每轮最多执行 {max_actions} 次 Action（建议 5-10 次）
- 如果连续 2 次 Observation 没有新信息，换一个搜索策略
- 如果已经找到了足够的信息，直接给出 Final Answer
- 不要重复执行相同的 Action

代码层面（如果可控）：
  max_iterations = 10
  action_history = []
  for i in range(max_iterations):
      if current_action in action_history[-2:]:
          # 最近做过同样的动作，强制切换策略
          ...
```

---

## 11. 示例

### 场景：竞品监控 Agent

**需求：** 自动查找 3 个主要竞品的本周促销活动，并给出应对建议。

**ReAct Agent 执行过程：**
```
Thought: 我需要查找竞品 A 的本周促销信息
Action: Search["竞品A品牌名 本周促销 优惠活动"]
Observation: [找到：满100减20，限时3天]

Thought: 接着查找竞品 B
Action: Search["竞品B品牌名 本周促销"]
Observation: [找到：买二送一，全品类参与]

Thought: 再查找竞品 C
Action: Search["竞品C品牌名 本周促销活动"]
Observation: [未找到近期促销信息]

Thought: 已收集完 3 个竞品信息，现在进行分析对比并给出建议
Final Answer: 竞品A满100减20（力度约8折）...
         建议我们的应对策略为...
```

**什么时候该用 ReAct 替代周报中的纯 CoT？**
- 当你希望 AI **主动去查**竞品价格、行业趋势、天气预报等因素来做归因
- 当前周报数据由 Python 准备好 → 用 CoT（数据已在手中）
- 未来希望 AI 自主搜集信息做分析 → 升级到 ReAct

---

## 12. 与其他技术的组合方式

| 组合 | 方式 | 效果 |
|------|------|------|
| **ReAct + CoT** | ReAct 的 Thought 步骤内部使用 CoT 推理 | 增强 Thought 的推理深度和质量 |
| **ReAct + Prompt Chaining** | ReAct 作为 Chaining pipeline 中的一个步骤 | 混合架构——信息收集用 ReAct，分析和生成用 CoT/Chaining |
| **ReAct + Self-Consistency** | 多个 ReAct Agent 并行探索，投票选出最佳 Final Answer | 高可靠性场景下的增强版 |

**ReAct vs Chaining 的选择：**
- 需要动态决定调用什么工具 → **ReAct**
- 步骤固定、流程明确 → **Prompt Chaining**
- 很多实际系统两者结合使用

---

## 13. 推荐存放路径

```
prompt-kb/01-fundamentals/advanced-techniques/react.md
```

---

## 14. 版本记录

| 版本 | 日期 | 变更说明 |
|------|------|----------|
| v0.1 | 2026-05-14 | 从 dair-ai-advanced-prompting.md v0.1 拆分独立为技术卡片 |
