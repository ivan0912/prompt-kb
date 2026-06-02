# OpenAI Prompt Guidance 校准笔记

> **模板编号**: T-CALIB-001
> **版本**: v0.1
> **创建日期**: 2026-05-14
> **校准目标**: DAIR.AI 提示词体系（Phase 1 已完成部分）
> **校准依据**: OpenAI 官方提示工程指南（2025-2026，含 GPT-5 推理模型专项）

---

## 1. 来源

| 项目 | 内容 |
|------|------|
| **来源名称** | OpenAI Prompt Engineering Guide + GPT-5 Model Guide |
| **链接 1** | https://platform.openai.com/docs/guides/prompt-engineering |
| **链接 2** | https://platform.openai.com/docs/guides/latest-model |
| **章节** | Six Strategies + Nine Principles + Reasoning Model Guidance |
| **处理日期** | 2026-05-14 |

---

## 2. 主题类型

**校准 / 元知识**

> 本条目不是提示技术的直接传授，而是用 OpenAI 官方标准来检验和修正已建立的 DAIR.AI 体系。
> 核心问题：**我已有的提示词方法在 2026 年现代模型（GPT-5 等）下是否仍然最优？**

---

## 3. 核心原则

### 3.1 OpenAI 六大策略（Six Strategies）

| # | 策略名称 | 一句话解释 |
|---|----------|-----------|
| S1 | **Write Clear Instructions** | 指令越清楚，输出越符合预期 |
| S2 | **Provide Reference Text** | 给参考文本，减少模型胡编 |
| S3 | **Split Complex Tasks** | 拆解复杂任务为简单子任务，降低错误率 |
| S4 | **Give Model Time to Think** | 让模型"想一会儿"再答，尤其是推理任务 |
| S5 | **Use External Tools** | 用 Embeddings/代码执行/函数调用弥补模型弱点 |
| S6 | **Test Changes Systematically** | 改变提示词必须系统化测试，不能凭感觉 |

### 3.2 OpenAI 九条补充原则

| # | 原则 | 原文关键词 |
|---|------|-----------|
| P1 | 使用最新模型 | Use the latest model |
| P2 | 指令放开头 + 用分隔符 | Position instructions at beginning, use `###` or `"""` |
| P3 | 越具体越好 | Be specific, descriptive, and detailed |
| P4 | 用范例展示输出格式 | Show output format through examples |
| P5 | 从 Zero-Shot → Few-Shot → Fine-tune 递进 | Progression strategy |
| P6 | 消除模糊描述 | Eliminate vague descriptions |
| P7 | 正面表述（要什么而非不要什么） | Frame instructions positively |
| P8 | 代码生成用"引导词" | Leading words for code |
| P9 | 用系统化测试 | Systematic prompt testing |

### 3.3 GPT-5 推理模型专项原则（2026 新增）

| # | 发现 | 对提示词的影响 |
|---|------|--------------|
| R1 | 推理强度 4 档（minimal/low/medium/high），minimal 下模型可能不够主动 | 低推理强度下需主动鼓励模型"想一步" |
| R2 | 冗长度控制（verbosity）是独立维度 | 可以直接控制输出详细程度，不必在 prompt 里约束 |
| R3 | 极简 prompt 在定义明确任务上效果更好 | 过度复杂化的 prompt 可能适得其反 |
| R4 | 前言（Preamble）机制：工具调用前有用户可见推理说明 | 模型已内置推理透明化，无需手动模拟 |
| R5 | 思考链可跨轮次传递 | 多轮对话中可继承推理过程，prompt 不必每次重述 |
| R6 | GPT-5 nano 在简单指令跟随/分类任务上性价比极高 | 不必所有任务都用最强模型 |

---

## 4. 与 DAIR.AI 方法的一致之处

### 4.1 高度一致（可直接保留）

| DAIR.AI 方法 | 对应 OpenAI 原则 | 一致程度 |
|-------------|-----------------|----------|
| **四大元素**（指令、上下文、输入、输出指示） | S1 (Write Clear Instructions) 的具体化 | ✅ **完全一致** |
| **五大设计原则**（从简单开始、明确指令、具体化、避免模糊、正面表述） | P2/P3/P6/P7 | ✅ **完全一致** |
| **Zero-Shot → Few-Shot → CoT 递进策略** | P5 (Zero-Shot → Few-Shot → Fine-tune) + S4 (Give time to think) | ✅ **完全一致** |
| **Few-Shot 核心机制**（格式锁定 > 标签准确性） | P4 (Show output format through examples) | ✅ **完全一致** |
| **Prompt Chaining（拆解复杂任务）** | S3 (Split Complex Tasks) | ✅ **完全一致** |
| **使用外部工具/代码执行（PAL）** | S5 (Use External Tools) | ✅ **完全一致** |

**结论：DAIR.AI 基础体系的核心与 OpenAI 官方高度吻合，无需大幅修改。**

### 4.2 细节差异（需小幅调整）

| 差异点 | DAIR.AI 现状 | OpenAI 建议 | 调整方向 |
|--------|-------------|-------------|----------|
| **分隔符使用** | DAIR.AI 模板大多没有显式分隔符 | 明确推荐 `###` 或 `"""` 分隔指令与上下文 | **建议补充分隔符规范** |
| **输出格式示范** | DAIR.AI 主要用文字描述格式要求 | 强调用具体范例展示格式（含占位符格式） | **强化范例 > 文字描述** |
| **系统性测试** | DAIR.AI 体系完全没有测试方法论 | S6 强调必须系统化测试 | **建议补充测试意识，但不急迫** |
| **角色设定（Role Prompting）** | DAIR.AI 大量使用，是核心技巧 | OpenAI 仅一笔带过（"adopt a persona"） | **保留，但注意现代模型角色设定的边际效益递减** |

---

## 5. 对 DAIR.AI 方法的修正

### 5.1 需要修正的认知偏差

#### 修正 A：「模板越详细越好」的假设

**问题诊断：**
DAIR.AI 模板体系（尤其是 T-TEXT-001）的特点是结构完整、内容详尽。但 OpenAI GPT-5 专项研究显示：**在现代模型 + 定义明确任务上，极简 prompt 效果更好。**

> OpenAI 原文：*"使用低推理强度和低文本冗长度的行为将更接近非推理模型，……当模型可以在需要时生成少量 token 时，效果更好。"*

**修正方向：**
- 不是「模板越详细越好」，而是「**任务定义越清晰越好**」
- 详细模板的价值在于**降低任务理解的歧义**，而不是堆砌结构
- 对于简单任务，Zero-Shot + 1-2 句具体描述 > 冗长模板

#### 修正 B：「给推理模型加 CoT 引导」可能多余

**问题诊断：**
DAIR.AI Advanced Prompting 将 CoT 作为「让模型真正会思考」的核心技术。但 GPT-5 作为推理模型：
- 已内置思考链机制（Preamble 可见）
- 推理强度可通过参数控制
- 跨轮次可传递思考链

**修正方向：**
- 对于 GPT-5/o1/o3 等推理模型：**不必手动加 CoT 引导**（如"让我们一步步思考"）
- CoT 的价值转移到：**推理模型的参数调优**（reasoning.effort）而非 prompt 文本
- DAIR.AI 的 CoT 知识仍保留，但标注适用条件：「主要用于非推理模型」

#### 修正 C：Few-Shot 在现代模型中的定位调整

**问题诊断：**
DAIR.AI 将 Few-Shot 作为格式控制的默认手段。但 OpenAI 的渐进策略显示：
- 现代模型在大多数任务上 Zero-Shot 已足够好
- Few-Shot 主要用于**格式锁定**和**边界情况界定**

**修正方向：**
- 默认策略改为：**先 Zero-Shot，不满意再加 Few-Shot**
- Few-Shot 的正确用途是「格式锁定」，而非「教模型知识」

### 5.2 需要补充的方法论

#### 补充 1：分隔符使用规范

OpenAI 明确要求用分隔符区分指令和上下文，DAIR.AI 模板中普遍缺失。

**建议在所有模板中统一使用：**

```
### 指令
[任务描述]

### 上下文
[背景信息]

### 输入
[待处理内容]

### 输出要求
[格式规范]
```

#### 补充 2：系统性测试意识

DAIR.AI 体系完全没有提及提示词测试，但 OpenAI S6 强调：改变必须可测量。

**建议最低测试门槛：**
- 任务结果稳定（多次运行一致）
- 在 5-10 个不同输入样本上验证
- 对比修改前后的输出质量

---

## 6. 对 T-TEXT-001 的影响

### 6.1 当前版本问题诊断

T-TEXT-001（模糊需求转计划 Pipeline）是 DAIR.AI 体系中最复杂的模板之一。对照 OpenAI 标准，存在以下问题：

| 问题 | 严重程度 | 说明 |
|------|---------|------|
| **Step 数量偏多（3-4 步）** | 🟡 中 | OpenAI S3 鼓励拆解，但 GPT-5 可用更少步骤完成同等质量 |
| **温度参数硬编码** | 🟢 低 | 固定 0.7/0.3，但 GPT-5 有更精细的 reasoning.effort 控制 |
| **CoT 引导在进阶版中可能多余** | 🟡 中 | Step 1'/2' 中加了"让我们一步步思考"，对推理模型可能适得其反 |
| **简化版提示词缺少分隔符** | 🟢 低 | 与 OpenAI P2 不一致 |
| **「人工确认门」设计优秀** | ✅ 亮点 | OpenAI 无此设计，保留 |

### 6.2 修正建议（列为 Phase 2 后续任务）

```
【后续任务清单】

□ T-TEXT-001 v0.2 修正项：
  1. 所有子模板补充 `###` 分隔符规范
  2. 进阶版 Step 1'/2' 中的 CoT 引导改为条件性（检测到非推理模型时启用）
  3. 温度参数建议改为「参数调整参考」，而非硬编码
  4. 补充极简版（1-prompt 版本），用于简单需求场景
  5. 简化版补充"是否需要多步"的判断决策树
```

---

## 7. 推荐保留的提示词写法

以下 DAIR.AI 方法经 OpenAI 标准验证，确认保留：

| 方法 | 保留理由 | 优先级 |
|------|---------|--------|
| **四大元素结构**（指令/上下文/输入/输出指示） | OpenAI S1 的具体化，结构清晰 | ⭐⭐⭐⭐⭐ |
| **Few-Shot 格式锁定** | OpenAI P4 明确推荐，用范例展示格式 | ⭐⭐⭐⭐⭐ |
| **从简单开始 + 渐进复杂** | OpenAI P5 核心原则，Zero-Shot → Few-Shot → CoT | ⭐⭐⭐⭐⭐ |
| **正面表述**（要什么 > 不要什么） | OpenAI P7 明确要求 | ⭐⭐⭐⭐⭐ |
| **Prompt Chaining 拆解复杂任务** | OpenAI S3 核心策略 | ⭐⭐⭐⭐ |
| **具体化描述**（越具体越好） | OpenAI P3/P6 强调 | ⭐⭐⭐⭐ |
| **Role Prompting（角色设定）** | OpenAI S1 战术之一（有限保留，见下方说明） | ⭐⭐⭐ |

### Role Prompting 保留条件

Role Prompting 在 OpenAI 体系中仅作为战术之一（而非核心原则），建议：

- ✅ **保留场景**：需要特定语气/视角的任务（客服对话、模拟练习）
- ⚠️ **谨慎使用**：对于 GPT-5 等现代模型，角色设定对输出质量的影响边际递减
- ❌ **避免**：为所有任务默认加角色设定（如"你是一个 10 年经验的 XX 专家"）

---

## 8. 建议减少或避免的提示词写法

| 写法 | 问题 | 替代方案 |
|------|------|---------|
| **为简单任务使用复杂模板** | 过度工程化，现代模型无需 | 直接 Zero-Shot + 1-2 句具体描述 |
| **为推理模型加"让我们一步步思考"** | 模型已内置推理能力，手动引导多余 | 改为调高 reasoning.effort 参数 |
| **用文字描述输出格式**（如"用表格输出，包含以下列"） | OpenAI P4：范例比文字更可靠 | 直接给格式示例（含占位符） |
| **不给具体数字约束**（如"简短说明""不要太长"） | OpenAI P6：模糊约束不可控 | 明确数字（"3-5 句""不超过 100 字"） |
| **大量使用负面约束**（"不要xxx""禁止xxx"） | OpenAI P7：正面指令效果更好 | 改为"请仅输出以下格式" |
| **System Prompt 中塞 Few-Shot 范例** | token 浪费，维护困难 | 范例放入 User Message 动态加载 |
| **为所有任务预设角色设定** | 现代模型对角色设定的依赖降低 | 按需添加，不要默认加 |

---

## 9. OpenClaw 使用建议

### 9.1 与 OpenAI 标准的对齐

| OpenAI 策略 | OpenClaw 中的对应实现 | 建议 |
|------------|---------------------|------|
| S1 Write Clear Instructions | Agent 的 System Prompt | 强制使用分隔符（`###`） |
| S2 Provide Reference Text | RAG 或工具调用提供上下文 | 在 OpenClaw 的工具层实现 |
| S3 Split Complex Tasks | Prompt Chaining 多步 Pipeline | 保留 T-TEXT-001 等模板，但可简化 |
| S4 Give Model Time to Think | CoT / Self-Consistency | 区分推理模型 vs GPT 模型，对推理模型跳过手动 CoT |
| S5 Use External Tools | OpenClaw 工具调用生态 | 核心优势，重点强化 |
| S6 Test Changes Systematically | 当前缺失 | **建议 Phase 2 补充** |

### 9.2 模型适配建议

```
OpenClaw Agent 提示词策略选择：

是否使用推理模型（GPT-5/o1/o3 等）？
  │
  ├─ 是 → 
  │    - 跳过手动 CoT 引导
  │    - 优先用极简 prompt
  │    - 通过 reasoning.effort 控制推理深度
  │    - 考虑用 gpt-5-nano 处理简单分类任务
  │
  └─ 否（GPT-4o / Claude 等）→
       - 保留 DAIR.AI 现有模板体系
       - 按原计划使用 CoT / Few-Shot / Chaining
```

---

## 10. 可复制中文提示词模板

### 模板 O1：OpenAI 标准版（对齐官方六大策略）

```markdown
### 指令
{具体任务描述，一句话}

### 上下文
{背景信息、角色设定（可选）、约束条件}

### 输入
{待处理的具体内容}

### 输出要求
{格式规范，尽量用示例展示}
示例：
{占位符格式示例 1}
{占位符格式示例 2}

### 约束（如有）
- 必须：{不可妥协的条件}
- 禁止：{绝对不能出现的内容}
```

### 模板 O2：极简版（适合现代推理模型 + 简单任务）

```markdown
任务：{具体要做什么}
输入：{待处理内容}
格式：{格式示例或字数要求}
```

### 模板 O3：代码生成引导版

```markdown
任务：{描述要实现的功能}
约束：{输入/输出的数据结构}
引导词：{以什么关键字开头，如 "import"、"SELECT"、"def" }

# 请在下方补全代码：
{引导词}
```

### 模板 O4：带测试意识的迭代版

```markdown
### 任务
{描述}

### 验证标准
1. {成功的标准 1}
2. {成功的标准 2}
3. {禁止出现的问题}

### 测试输入
{样本 1}
期望输出：{样本 1 对应输出}

{样本 2}
期望输出：{样本 2 对应输出}

### 待处理
{实际输入}
```

---

## 11. 常见失败

| # | 失败模式 | OpenAI 对应策略 | DAIR.AI 覆盖情况 |
|---|----------|---------------|-----------------|
| 1 | **指令模糊，模型自由发挥** | S1 Write Clear Instructions | ✅ DAIR.AI 五大原则有覆盖 |
| 2 | **模型胡编乱造（幻觉）** | S2 Provide Reference Text | ❌ **DAIR.AI 体系缺失**，建议补充 |
| 3 | **复杂任务一次 prompt 搞定** | S3 Split Complex Tasks | ✅ T-TEXT-001/Advanced Prompting 有覆盖 |
| 4 | **推理模型还手动加 CoT 引导** | S4 Give Model Time to Think（仅对非推理模型） | ❌ **DAIR.AI 未区分模型类型** |
| 5 | **不验证就上线提示词** | S6 Test Changes Systematically | ❌ **DAIR.AI 体系完全缺失** |
| 6 | **用文字描述格式而非示例** | P4 Show output format | ✅ DAIR.AI 有 Few-Shot 示范 |
| 7 | **输出长度不可控** | P6 Eliminate vague descriptions | 🟡 部分覆盖，缺少具体数字约束建议 |
| 8 | **负面指令过多** | P7 Frame positively | ✅ DAIR.AI 五大原则有覆盖 |
| 9 | **简单任务用了最复杂模板** | P5 Progression | ✅ DAIR.AI Basic Prompting 有覆盖 |

**关键发现：DAIR.AI 体系最大的两个盲区是「S2 幻觉控制」和「S6 系统化测试」。**

---

## 12. 修正提示

### 修正 A：防止幻觉（新增）

**❌ 缺失：** DAIR.AI 体系完全没有处理模型胡编的问题

**✅ 修正：**
```
【防幻觉提示追加内容】

你只能基于以下信息回答，不要编造：
{提供参考文本/数据}

如果信息不足以回答，说："根据提供的信息，我无法确定..."，不要猜测。
引用你使用的具体信息：[引用格式：第X段/数据来源名称]
```

### 修正 B：强化格式示范优于文字描述

**❌ 不足：** 模板中大量用文字描述格式要求（如"用表格输出"）

**✅ 修正：**
```
【格式规范升级规则】

文字描述格式 → 至少配一个格式示例

❌ "输出格式：表格，包含品类、销量、环比三列"
✅ "输出格式：
| 品类 | 销量 | 环比 |
|------|------|------|
| {名称} | {数字} | {百分比} |"
```

---

## 13. 示例

### 示例：同一个「品类销售分析」需求的两种写法对比

#### ❌ 旧写法（DAIR.AI 模板风格，过度结构化）

```markdown
# 角色
你是一个电商数据分析助手。

# 任务
分析以下品类销售数据，判断周表现状态。

# 判断标准
- 增长强劲：销量 > 500 且 环比 > +10%
- ...（文字描述标准）

# 参考示例
[3 个 Few-Shot 范例]

# 待分析数据
品类：慢回弹玩具 | 销量: 2100 | 环比: +8%

请按以下格式输出：
品类：{名称} | 销量: {数值} | 环比: {百分比}% | 状态：{状态}
```

#### ✅ 新写法（对齐 OpenAI 标准，针对 GPT-5）

```markdown
### 任务
根据销量和环比，判断每个品类的周表现状态。

### 判断标准
- 增长强劲：销量 > 500 且 环比 > +10%
- 稳步增长：销量 > 300 或 环比在 0%~+10%
- 平稳：环比在 -10%~+10%
- 预警：环比 < -10% 且 销量 > 100
- 下滑严重：环比 < -20% 或 销量 < 50

### 格式
品类：{名称} | 销量: {数字} | 环比: {百分比}% | 状态：{状态}

### 待分析
品类：慢回弹玩具 | 销量: 2100 | 环比: +8%
```

**对比说明：**
- 移除了角色设定（对 GPT-5 非必要）
- 用 `###` 分隔符结构化（对齐 OpenAI P2）
- 格式用真实占位符示例而非文字描述（对齐 OpenAI P4）
- 减少了 60% 的 prompt 长度

---

## 14. 推荐存放路径

```
prompt-kb/01-fundamentals/openai-prompt-guidance-calibration.md
```

**关联文件：**
- DAIR.AI Introduction：`prompt-kb/01-fundamentals/dair-ai-introduction.md`
- DAIR.AI Basic Prompting：`prompt-kb/01-fundamentals/dair-ai-basic-prompting.md`
- DAIR.AI Advanced Prompting：`prompt-kb/01-fundamentals/dair-ai-advanced-prompting.md`
- T-TEXT-001：`prompt-kb/02-text-prompts/templates/fuzzy-request-to-plan-pipeline.md`

---

## 15. 版本记录

| 版本 | 日期 | 变更说明 |
|------|------|----------|
| v0.1 | 2026-05-14 | 初版完成。基于 OpenAI 官方指南（Six Strategies + Nine Principles + GPT-5 推理模型专项）与 DAIR.AI Phase 1 完成内容进行全量校准 |

---

## 附录 A：OpenAI vs DAIR.AI 原则对照表

| OpenAI 策略/原则 | DAIR.AI 对应 | 关系 | 建议动作 |
|-----------------|-------------|------|---------|
| S1 Write Clear Instructions | 四大元素 + 五大设计原则 | ✅ 一致 | 保留 |
| S2 Provide Reference Text | 无对应 | ❌ 缺失 | Phase 2 补充 |
| S3 Split Complex Tasks | T-TEXT-001 / Prompt Chaining | ✅ 一致 | 保留，适度简化 |
| S4 Give Model Time to Think | CoT / Self-Consistency | ⚠️ 部分正确 | 区分推理模型后保留 |
| S5 Use External Tools | PAL / ReAct | ✅ 一致 | 保留 |
| S6 Test Changes Systematically | 无对应 | ❌ 缺失 | Phase 2 补充 |
| P1 Use Latest Model | 无 | ⚠️ 缺失 | 补充至元知识层 |
| P2 Instructions First + Delimiters | 无显式规范 | ⚠️ 缺失 | 模板规范补充 |
| P3 Be Specific | 五大原则之一 | ✅ 一致 | 保留 |
| P4 Show Format with Examples | Few-Shot / 模板示例 | ✅ 一致 | 强化示例优先 |
| P5 Zero→Few→Fine-tune Progression | Zero/Few-Shot 选择策略 | ✅ 一致 | 保留 |
| P6 Eliminate Vague | 五大原则之一 | ✅ 一致 | 保留 |
| P7 Frame Positively | 五大原则之一 | ✅ 一致 | 保留 |
| P8 Leading Words for Code | 无 | ⚠️ 缺失 | 代码类模板补充 |
| P9 Systematic Testing | 无对应 | ❌ 缺失 | Phase 2 补充 |

---

## 附录 B：Phase 2 任务优先级

| 优先级 | 任务 | 来源 | 建议时间 |
|--------|------|------|---------|
| 🔴 高 | 补充「防止幻觉」方法论 | 本校准（常见失败 #2） | Phase 2 早期 |
| 🔴 高 | T-TEXT-001 v0.2 修正 | 本校准 §6.2 | Phase 2 早期 |
| 🔴 高 | 模板体系补充 `###` 分隔符规范 | 本校准（补充 #1） | Phase 2 早期 |
| 🟡 中 | 区分推理模型 vs GPT 模型的 CoT 策略 | 本校准（修正 B） | Phase 2 中期 |
| 🟡 中 | 补充「提示词系统化测试」方法论 | 本校准（附录 A P9） | Phase 2 中期 |
| 🟡 中 | 代码生成模板补充「引导词」规范 | 本校准（附录 A P8） | Phase 2 中期 |
| 🟢 低 | DAIR.AI Basic Prompting 补充 P8 leading words | 本校准 | Phase 2 后期 |
| 🟢 低 | Advanced Prompting CoT 部分更新模型区分说明 | 本校准 | Phase 2 后期 |
