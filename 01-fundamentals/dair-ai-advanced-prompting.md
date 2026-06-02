# DAIR.AI Prompt Engineering Guide - Advanced Prompting（总览索引）

## 1. 标题

**高级提示词技术：从思维链到智能体推理的完整指南**

---

## 2. 来源

| 项目 | 内容 |
|------|------|
| **来源名称** | DAIR.AI Prompt Engineering Guide |
| **链接** | https://github.com/dair-ai/Prompt-Engineering-Guide |
| **在线版本** | CoT: https://www.promptingguide.ai/techniques/cot / SC: /techniques/consistency / GK: /techniques/knowledge / Chaining: /techniques/prompt-chaining / ToT: /techniques/tot / ReAct: /techniques/react / APE: /techniques/ape / AP: /techniques/activeprompt / DSP: /techniques/dsp / PAL: /techniques/pal |
| **章节** | Prompting Techniques → Advanced Prompting（11 种技术） |
| **处理日期** | 2026-05-14 |

---

## 3. 主题类型

**进阶**

> 本条目覆盖提示工程中「让模型真正会思考」的高级技术体系。是 Basic Prompting（Zero-Shot + Few-Shot）的升级——从"给范例让它照做"进阶到"教它怎么一步步推理、搜索、验证、回溯"。

---

## 4. 与 Basic Prompting 的区别

| 维度 | Basic Prompting | Advanced Prompting |
|------|----------------|-------------------|
| 核心机制 | 示范（给例子） | 推理（展示思考过程） |
| 输出依赖 | 格式模仿 | 逻辑推导 |
| 适用任务 | 分类/提取/格式转换 | 数学/逻辑/规划/多步决策 |
| Token 消耗 | 低-中 | 中-高 |
| 实现难度 | 低 | 中-高 |
| 你的使用频率 | 每天 | 按需（复杂任务时） |

**学习建议：** 必须先掌握 Basic Prompting 的 Zero-Shot 和 Few-Shot，再学本条目。

---

## 5. 技术分级表

> 按「对你的实用价值」分为三级：
>
> - 🟢 **立即掌握**（日常高频可用）
> - 🟡 **了解概念**（特定场景有用）
> - 🔴 **暂缓学习**（偏研究/工程，当前阶段可跳过）

| # | 技术 | 分级 | 一句话解释 | 卡片位置 |
|---|------|------|-----------|----------|
| 1 | **Chain-of-Thought (CoT)** | 🟢 | 不直接要答案，让模型把推理过程一步步写出来 | [cot.md](advanced-techniques/cot.md) |
| 2 | **Self-Consistency (SC)** | 🟢 | 同一问题问多次，取多数投票结果 | [self-consistency.md](advanced-techniques/self-consistency.md) |
| 3 | **Generated Knowledge (GK)** | 🟢 | 先生成背景知识，再结合知识回答 | [generated-knowledge.md](advanced-techniques/generated-knowledge.md) |
| 4 | **Prompt Chaining (PC)** | 🟢 | 拆成多步子任务，每步独立 prompt，上一步输出→下一步输入 | [prompt-chaining.md](advanced-techniques/prompt-chaining.md) |
| 5 | **Tree of Thoughts (ToT)** | 🟡 | 同时探索多条思路，评估价值，必要时回溯 | [tree-of-thoughts.md](advanced-techniques/tree-of-thoughts.md) |
| 6 | **ReAct** | 🟡 | 交替进行"思考→行动→观察"，用外部工具辅助推理 | [react.md](advanced-techniques/react.md) |
| 7 | **Program-Aided Language Models (PAL)** | 🟡 | 让模型写代码（Python），交给解释器执行得精确答案 | [program-aided-language-models.md](advanced-techniques/program-aided-language-models.md) |
| 8 | **Automatic Prompt Engineer (APE)** | 🔴 | 让 LLM 自动生成和筛选最优 prompt | （暂无独立卡片，见下方摘要） |
| 9 | **Active-Prompt (AP)** | 🔴 | 根据不确定度自动选择最需要标注的样例 | （暂无独立卡片，见下方摘要） |
| 10 | **Directional Stimulus (DSP)** | 🔴 | 训练小型策略 LM 引导大模型输出方向 | （暂无独立卡片，见下方摘要） |

---

## 6. 学习路径推荐

### 第一优先级：🟢 立即掌握（建议按此顺序）

```
1. CoT → 2. Self-Consistency → 3. Generated Knowledge → 4. Prompt Chaining
```

**理由：**
- **CoT** 是所有高级技术的基础——其他技术大多建立在 CoT 之上
- **Self-Consistency** 是 CoT 的直接升级（多票投票），学完 CoT 自然衔接
- **Generated Knowledge** 解决"模型不懂领域"的问题，与 CoT 互补
- **Prompt Chaining** 是构建工作流的核心模式，学完后可以搭建真正的多步骤 AI pipeline

**预计学习时间：** 每个 30-60 分钟，总计 2-4 小时。

### 第二优先级：🟡 了解概念（有需要时再深入）

```
5. PAL → 6. ReAct → 7. ToT
```

- **PAL**：当你需要精确保真（数学/日期计算）时，比 CoT 更可靠
- **ReAct**：当你需要 Agent 调用工具（搜索/API/数据库）时必学
- **ToT**：当你需要多方案对比选优时使用（计算开销大，谨慎使用）

### 第三优先级：🔴 暂缓学习

- **APE / Active-Prompt / DSP** 偏学术研究和工程自动化，个人日常使用意义有限。等有具体需求时再看。

---

## 7. 快速决策树：什么时候用什么？

```
你的任务需要推理或复杂操作？
│
├─ 不需要 → 用 Basic Prompting（Zero-Shot / Few-Shot）
│
└─ 需要 → 任务类型是什么？
    │
    ├─ 多步数学/逻辑题
    │   ├─ 先试 Zero-Shot CoT（加"让我们一步步思考"）
    │   ├─ 还不够准？加 Self-Consistency（多票投票）
    │   └─ 需要精确保真？用 PAL（写代码让解释器算）
    │
    ├─ 需要外部信息（搜索/查询/计算）
    │   └─ 用 ReAct（思考→行动→观察 循环）
    │       → 这就是 Agent 的核心模式
    │
    ├─ 复杂任务可拆分
    │   └─ 用 Prompt Chaining（拆成多步 pipeline）
    │
    ├─ 需要多方案对比选优
    │   └─ 用 Tree of Thoughts（🟡 暂缓，计算开销大）
    │
    ├─ 缺乏背景知识/常识
    │   └─ 用 Generated Knowledge（先生成相关知识再回答）
    │
    ├─ 要批量自动化优化 prompt
    │   └─ 用 APE（🔴 暂缓，偏工程工具）
    │
    ├─ 追求极致推理精度
    │   └─ 用 Active-Prompt（🔴 暂缓，偏学术研究）
    │
    └─ 需要用 RL 引导输出方向
        └─ 用 DSP（🔴 暂缓，需要训练额外模型）
```

---

## 8. 适用场景概览

- ✅ **多步数学运算** — Zero-Shot CoT 一句话解决大部分简单数学题
- ✅ **逻辑推理题** — 年龄问题、追击问题、排列组合等
- ✅ **数据分析与解读** — 让 AI 展示数据如何一步步导出结论（CoT）
- ✅ **长文档问答** — Prompt Chaining 先提取相关片段再做回答
- ✅ **需要实时信息的任务** — ReAct 模式调搜索/API 获取最新数据
- ✅ **代码生成 + 执行** — PAL 写 Python 代码保证计算精确
- ✅ **周报自动化中的异常检测** — CoT 让 AI 说明为什么某个品类被标记为预警
- ✅ **OpenClaw Agent 工作流设计** — Prompt Chaining + ReAct 构建多步 Agent pipeline
- ✅ **高可靠性需求的关键推理** — Self-Consistency 多次投票减少错误率
- ✅ **常识推理易错领域** — Generated Knowledge 补充背景事实后再判断

## 不适用场景概览

- ❌ **简单分类/情感分析** — Zero-Shot 或 Few-Shot 足够
- ❌ **创意写作/开放生成** — 过度约束推理过程反而限制创造力
- ❌ **实时对话/聊天场景** — 用户不想等模型"想半天"
- ❌ **Token 成本敏感的大规模批处理** — CoT/SC/ToT 显著增加 token 消耗
- ❌ **小模型（< 7B 参数）** — CoT 是涌现能力，小模型不具备
- ❌ **图像/视频/音频生成提示词** — 这些模态有自己的专用技术体系

---

## 9. OpenClaw 总体使用建议

| 维度 | 说明 |
|------|------|
| **单 Agent 适配度** | ★★★★★ (5/5) — Zero-Shot CoT 是单 Agent 最大免费升级 |
| **多 Agent 适配度** | ★★★★☆ (4.5/5) — Prompt Chaining + ReAct 是多 Agent 编排核心模式 |
| **System Prompt 适配** | ✅ 部分适合 — CoT 指令适合放入 system prompt；Few-Shot 示例放 user message |
| **工作流骨架适配** | ✅ 非常适合 — Prompt Chaining 就是工作流的自然表达 |

### 三种核心配置模式

| 方案 | 适用场景 | 核心技术 | 详情见卡片 |
|------|---------|---------|-----------|
| **CoT Agent** | 单 Agent 推理增强（数据分析/逻辑判断） | CoT 嵌入 System Prompt | [cot.md](advanced-techniques/cot.md) §5 |
| **Chaining Pipeline** | 复杂业务流程（周报自动化/客户分析） | 多步骤结构化数据传递 | [prompt-chaining.md](advanced-techniques/prompt-chaining.md) §5 |
| **ReAct Agent** | 工具调用型（搜索/API/数据库查询） | Thought→Action→Observation 循环 | [react.md](advanced-techniques/react.md) §5 |

---

## 10. 🔴 暂缓学习技术摘要

以下三种技术在当前阶段不需要深入学习，仅做简要记录备查：

### Automatic Prompt Engineer (APE)
- **定义：** 让 LLM 自动生成和筛选最优提示词
- **流程：** 生成 N 个候选 → 评分筛选 → 选最优
- **定位：** 工程/自动化工具，个人日常使用意义有限
- **有趣发现：** APE 发现的 CoT prompt 比人工写的还好

### Active-Prompt (AP)
- **定义：** 根据不确定度自动选择最有价值的标注样例
- **定位：** 偏学术研究，适合医疗/法律等追求极致精度场景

### Directional Stimulus Prompting (DSP)
- **定义：** 训练小型策略 LM 为大模型生成引导 hint
- **定位：** 偏学术研究，需要训练额外模型 + 强化学习

> 这三种技术的详细内容保留在原始 v0.1 文件的归档中。当有具体工程需求时可回溯查阅。

---

## 11. 版本记录

| 版本 | 日期 | 变更说明 |
|------|------|----------|
| v0.2 | 2026-05-14 | **拆分重构。** 从 1084 行单体文件拆分为：总览索引（本文件）+ 8 个独立技术卡片。移除冗余内容，保留导航、分级、决策链、适用场景。|
| v0.1 | 2026-05-14 | 基于 DAIR.AI Advanced Prompting（11 种技术）生成初版知识条目（已拆分） |

---

## 附录：技术卡片清单

| 序号 | 卡片文件 | 技术名 | 分级 | 建议阅读顺序 |
|------|---------|--------|------|-------------|
| 1 | [cot.md](advanced-techniques/cot.md) | Chain-of-Thought 思维链 | 🟢 | 第 1 个读 |
| 2 | [self-consistency.md](advanced-techniques/self-consistency.md) | Self-Consistency 自洽性验证 | 🟢 | 第 2 个读 |
| 3 | [generated-knowledge.md](advanced-techniques/generated-knowledge.md) | Generated Knowledge 生成知识增强 | 🟢 | 第 3 个读 |
| 4 | [prompt-chaining.md](advanced-techniques/prompt-chaining.md) | Prompt Chaining 提示词链式调用 | 🟢 | 第 4 个读 |
| 5 | [tree-of-thoughts.md](advanced-techniques/tree-of-thoughts.md) | Tree of Thoughts 思维树 | 🟡 | 有需要时读 |
| 6 | [react.md](advanced-techniques/react.md) | ReAct 推理+行动交织 | 🟡 | 做 Agent 时读 |
| 7 | [program-aided-language-models.md](advanced-techniques/program-aided-language-models.md) | Program-Aided Language Models 程序辅助语言模型 | 🟡 | 需要精确计算时读 |
