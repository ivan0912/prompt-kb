# 01-fundamentals — 文本提示词基础

> **版本**: v1.1.0
> **创建日期**: 2026-05-14
> **最近更新**: 2026-05-14（Phase 1 中期验收后导航重建）
> **状态**: ✅ 核心内容已完成，导航已同步

---

## 本模块定位

基于 **DAIR.AI Prompt Engineering Guide** 官方内容整理的文本提示词基础知识体系。覆盖从「什么是提示词」到「7 大高级实战技术」的完整学习路径。

**适用对象**: 所有需要在文本交互中使用 AI 的人
**前置要求**: 无
**预计学习时间**: 3-6 小时（通读）+ 实践练习

---

## 文件地图

```
01-fundamentals/
├── README.md                              ← 本文件（导航）
├── dair-ai-introduction.md                ← 📖 入门篇：定义/能力/原则
├── dair-ai-basic-prompting.md             ← 📝 基础篇：Zero-Shot / Few-Shot
├── dair-ai-advanced-prompting.md          ← 🚀 高级总览：10 项技术对比
├── _templates/
│   └── 00-entry-template.md               ← 知识库条目标准模板
└── advanced-techniques/                   ← 🧠 7 张独立技术卡片
    ├── cot.md                             ←   🟢 Chain-of-Thought 思维链
    ├── self-consistency.md                ←   🟢 Self-Consistency 多数投票
    ├── generated-knowledge.md             ←   🟢 Generated Knowledge 知识增强
    ├── prompt-chaining.md                 ←   🟢 Prompt Chaining 分步执行
    ├── tree-of-thoughts.md                ←   🟡 Tree of Thoughts 分支探索
    ├── react.md                           ←   🟡 ReAct 行动-观察循环
    └── program-aided-language-models.md   ←   🟡 PAL 代码辅助推理
```

---

## 条目详解

### 1️⃣ Introduction — 入门

**文件**: [dair-ai-introduction.md](dair-ai-introduction.md) （v0.2, 662 行）

| 项目 | 内容 |
|------|------|
| **解决什么问题** | "什么是 Prompt Engineering？它能做什么？有什么局限性？" |
| **核心章节** | 定义 & 概览 → 提示词元素 → 设计原则 → 能力 & 局限 → 安全性 → 附加资源 |
| **适合谁读** | 所有人（必读第一份材料） |
| **关键收获** | 理解提示词的 4 大核心要素（指令/上下文/输入数据/输出指示器）；知道 LLM 能做什么不能做什么 |
| **预计时间** | 15-20 分钟 |

**读完你能回答**:
- 提示词和普通聊天输入有什么区别？
- 为什么说「好的提示词 = 清晰角色 + 明确任务 + 具体约束 + 格式要求」？
- LLM 的已知局限性有哪些？（幻觉、偏见、毒性、时效性…）

---

### 2️⃣ Basic Prompting — 基础

**文件**: [dair-ai-basic-prompting.md](dair-ai-basic-prompting.md) （v0.2, 685 行）

| 项目 | 内容 |
|------|------|
| **解决什么问题** | "怎么写好一个基础的提示词？Zero-Shot 和 Few-Shot 怎么选？" |
| **核心章节** | Zero-Shot Prompting → Few-Shot Prompting → 示例选择策略 → 高级提示词格式（CoT 预览） |
| **适合谁读** | 写过提示词但缺乏系统方法的人 |
| **关键收获** | 掌握两大基础范式；学会选示例的 4 条准则；了解 CoT 的魔法短语 |
| **预计时间** | 20-25 分钟 |

**读完你能回答**:
- 什么情况下 Zero-Shot 就够了？
- Few-Shot 示例应该选几个？怎么排列？
- 「让我们一步一步地思考」为什么有效？

---

### 3️⃣ Advanced Prompting — 高级总览

**文件**: [dair-ai-advanced-prompting.md](dair-ai-advanced-prompting.md) （v0.2, 222 行）

| 项目 | 内容 |
|------|------|
| **解决什么问题** | "高级技术那么多，我该学哪个？它们之间是什么关系？" |
| **核心章节** | 定义 vs Basic → 10 项技术分级表 → 学习路径推荐 → 决策树 → 场景速查 → OpenClaw 适配总览 → 🔴 延期技术摘要 |
| **适合谁读** | 已经掌握 Basic，准备进阶的人 |
| **关键收获** | 一张表看清所有技术的优先级；决策树帮你选技术；🟢🟡🔴 三级学习顺序 |
| **预计时间** | 10 分钟（索引性质，详细内容在卡片） |

**⚠️ 注意**: 本文件是**索引/导航**，具体技术在 `advanced-techniques/` 独立卡片中。

---

### 4️⃣ advanced-techniques/ — 技术卡片库

每张卡片遵循统一 **13 段式结构**，可直接用于学习和执行：

| # | 段落 | 说明 |
|---|------|------|
| 1 | 一句话解释 | 30 字内讲清楚这是什么 |
| 2 | 适用场景 | 什么时候用它 |
| 3 | 不适用 | 什么时候别用 |
| 4 | 核心机制 | 它为什么有效 |
| 5 | 中文模板 | 可直接复制使用的提示词框架 |
| 6 | OpenClaw 配置 | 在 Agent 系统中如何部署 |
| 7 | 单 Agent 适配度 | 1-5 星评级 |
| 8 | 多 Agent 适配度 | 1-5 星评级 |
| 9 | 常见失败模式 | 典型错误和原因 |
| 10 | 修正提示词 | 出问题了怎么调 |
| 11 | 完整示例 | 以周报自动化为业务背景 |
| 12 | 组合方式 | 与其他技术搭配使用 |
| 13 | 存放路径 & 版本记录 | 元信息 |

#### 🟢 推荐优先掌握（前 4 个）

| 卡片 | 解决的核心问题 | 必读章节 |
|------|---------------|----------|
| **[CoT](advanced-techniques/cot.md)** | "AI 回答太简略/不推理怎么办？" | §5 中文模板（含魔法短语）、§11 周报分析示例 |
| **[Self-Consistency](advanced-techniques/self-consistency.md)** | "同一个问题多次调用结果不一致怎么办？" | §4 多数投票机制、§6 temperature 必须 >0 |
| **[Generated Knowledge](advanced-techniques/generated-knowledge.md)** | "AI 对我的专业领域不够懂怎么办？" | §4 两阶段流程、§5 知识生成模板 |
| **[Prompt Chaining](advanced-techniques/prompt-chaining.md)** | "任务太复杂，一次提示搞不定怎么办？" | §5 三步链式模板、§11 周报完整流水线 |

#### 🟡 进阶可选（后 3 个）

| 卡片 | 解决的核心问题 | 前置依赖 |
|------|---------------|----------|
| **[Tree of Thoughts](advanced-techniques/tree-of-thoughts.md)** | "有多种方案需要比较/探索怎么办？" | 建议先学 CoT |
| **[ReAct](advanced-techniques/react.md)** | "需要 AI 调用工具/查询信息怎么办？" | 无硬性依赖 |
| **[PAL](advanced-techniques/program-aided-language-models.md)** | "数学/逻辑题 AI 老算错怎么办？" | 建议 CoT 为兜底方案 |

---

## 推荐学习顺序

### 路径 A：最小可用（2 小时）

```
Introduction（20min）→ Basic Prompting（25min）→ 🟢 CoT（30min）→ 🟢 Prompt Chaining（30min）
```

**目标**: 能处理 80% 的日常文本交互任务

### 路径 B：系统掌握（5 小时）

```
Introduction → Basic → 🟢 CoT → 🟢 Chaining → 🟢 Self-Consistency → 🟢 GenKnowledge → 🟡 ToT → 🟡 ReAct → 🟡 PAL
```

**目标**: 全面掌握 DAIR.AI 核心/高级技术，具备设计复杂工作流的能力

### 路径 C：按需查阅

直接看下面的「问题→文件」映射表，遇到问题时再来查。

---

## 问题 → 文件 速查表

| 你遇到的问题 | 该看哪个文件 | 直接跳到哪一节 |
|-------------|-------------|---------------|
| "提示词到底是什么？" | Introduction | §1 Definition |
| "我的提示词 AI 不理解" | Basic Prompting | §2 Zero-Shot 要素检查 |
| "AI 输出格式不对" | Basic Prompting | §4 高级提示词格式 |
| "AI 回答太浅/不解释过程" | **CoT** | §5 模板 + "让我们一步一步地思考" |
| "同样的问题每次答案不一样/不准" | **Self-Consistency** | §4 多数投票 |
| "AI 不懂我的行业/业务" | **Generated Knowledge** | §5 两阶段模板 |
| "任务太大了写不下" | **Prompt Chaining** | §5 三步链式 |
| "需要 AI 自己决定行动步骤" | **ReAct** | §5 T-A-O 循环模板 |
| "数学题/逻辑题老算错" | **PAL** | §5 代码生成模板 |
| "有好几种方案都想试试" | **Tree of Thoughts** | §4 BFS/DFS 策略 |
| "这些技术该怎么组合使用?" | Advanced 总览 | §3 学习路径 + §5 场景速查 |

---

## 与其他模块的关系

```
01-fundamentals（本模块）
    │
    ├── 供 02-text-prompts/ 使用  → 基础技术是所有文本模板的理论底座
    ├── 供 05-openclaw-workflows/ 使用  → 每个 card 的 §6 OpenClaw 配置是工作流设计依据
    │
    └── 是 03-image-prompts/ 和 04-video-prompts/ 的间接基础
        （图像/视频提示词的结构化描述能力源于基础训练）
```

---

## 版本历史

| 版本 | 日期 | 变更内容 |
|------|------|----------|
| v1.1.0 | 2026-05-14 | Phase 1 中期验收后全面重建：新增文件地图、4 个条目详解、学习路径（A/B/C）、问题速查表、模块关系图 |
| v1.0.0 | 2026-05-14 | 初始创建（仅含通用概念说明，无实际条目链接） |

---

*这是整个知识库的地基。地基打好了，后面建什么都稳。*
