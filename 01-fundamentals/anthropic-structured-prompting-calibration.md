# Anthropic Prompt Engineering 结构化提示词校准笔记

> **文件编号**: T-FUND-005
> **版本**: v0.1
> **创建日期**: 2026-05-14
> **来源**: Anthropic Claude Prompting Best Practices（基于官方文档深度解析）
> **依据资料**:
> - Anthropic 官方文档（`platform.claude.com/docs`）
> - [Claude 提示词工程最佳实践深度解析](https://www.iceyao.com.cn/2026/04/25/claude-prompting-best-practices/)
> - [Anthropic 发布 Prompt Engineering 全新指南](https://blog.csdn.net/TYLZVS007/article/details/150470429)
> **用途**: 用 Anthropic 方法论校准 Prompt-KB 已有结构，与 DAIR.AI / OpenAI 体系横向对齐，提出通用模板规范建议

---

## 1. 来源

**主来源**: Anthropic Claude Prompting Best Practices

- 官方文档（因区域限制无法直接访问，通过第三方解析获取）
- 原文链接: `platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices`
- 适用模型: Claude Opus 4.7 / 4.6, Claude Sonnet 4.6, Claude Haiku 4.5
- 核心定位: 从通用原则到高级代理系统的完整指南

**补充来源**: Anthropic 官方 Prompt Engineering 交互式教程

- GitHub: `github.com/anthropics/prompt-eng-interactive-tutorial`
- 结构: 9 个章节 + 配套练习

---

## 2. 主题类型

**结构化提示词校准**

Anthropic 的价值不在于提出全新方法论，而在于**对已有方法的工程化落地**——它把 DAIR.AI 和 OpenAI 体系中的"模糊直觉"转化为"可执行规范"。

---

## 3. 核心结论

Anthropic 对 Prompt-KB 的最大价值：**把提示词当作"接口契约"来设计，而非当作"对话"来随意发挥。**

三个最关键的认知升级：

1. **模型是缺上下文的新同事**——不是你肚子里的蛔虫，越具体越好
2. **格式即语义**——XML 标签不是装饰，是给模型的"文档树"
3. **effort 参数替代手动 CoT**——推理模型已经内置思考能力，不要重复引导

---

## 4. Anthropic 方法的关键原则

### 原则 1：把 Claude 当作"缺上下文的新同事"

**为什么清晰指令重要：**

Claude 不了解你的规范、风格、准则或偏好工作方式。隐式假设 = 模型猜测 = 幻觉风险。

**黄金法则**：把你的提示词拿给一位对任务缺乏背景的同事看，如果他看完感到困惑，那么 Claude 也会困惑。

**对比**：
- ❌ `Create an analytics dashboard`
- ✅ `Create an analytics dashboard. Include as many relevant features and interactions as possible. Go beyond the basics to create a fully-featured implementation.`

---

### 原则 2：为"为什么"提供理由，不只说"做什么"

**为什么理由重要：**

给指令附上动机能显著提升规则的泛化能力。模型能理解规则背后的逻辑，而不是机械执行字面意思。

**对比**：
- ❌ `NEVER use ellipses`（模型不知道为什么，效果差）
- ✅ `Your response will be read aloud by a text-to-speech engine, so never use ellipses since the text-to-speech engine will not know how to pronounce them.`（模型理解了原因，执行更稳定）

---

### 原则 3：Few-shot 示例——3~5 个、相关、多样、结构化

**为什么示例很重要：**

不是教模型"知识"（那是微调的工作），而是教模型"格式"和"边界"。

**关键要求**：

| 要求 | 说明 |
|------|------|
| **相关** | 贴近真实输入分布，不要用通用常识题 |
| **多样** | 覆盖边缘情况和边界条件 |
| **结构化** | 用 `<example>` 标签包裹，明确输入-输出对 |
| **数量** | 3~5 个通常最佳；过多会导致模型模仿格式而非理解规则 |

**Anthropic 补充**：示例的作用是"格式锁定"，不是"知识灌输"。这与 OpenAI 校准结论完全一致。

---

### 原则 4：用 XML 标签结构化提示

**为什么 XML 标签有价值：**

给模型一棵可以解析的文档树，明确区分指令、数据、输出样例。模型是自回归的——越靠近生成位置的 token，对输出的影响权重越大。

**核心模板**：

```xml
<documents>
  <document index="1">
    <source>annual_report_2023.pdf</source>
    <document_content>
      {{ANNUAL_REPORT}}
    </document_content>
  </document>
</documents>

Analyze the annual report. Identify strategic advantages and recommend Q3 focus areas.
```

**使用经验**：
- 标签名要一致且有语义（`<relevant_quotes>` vs `<answer>`）
- 有自然层级时再嵌套，不要为嵌套而嵌套
- 重要字段前后的空白行会提升可读性
- 指令放在末尾，文档放在顶部（详见长上下文原则）

---

### 原则 5：文档放在顶部，问题放在末尾

**为什么长上下文需要组织：**

模型是自回归生成的，越靠近生成位置的 token，对输出的影响权重越大。文档靠前 → 问题靠后 → 最多约 30% 的质量提升。

**配套规范**：
1. 用 XML 标签包装每份文档的元数据和正文
2. 要求模型先提取相关引用，再回答（防止幻觉）

```xml
请先用 <relevant_quotes> 标签列出你引用的原文片段，
再在 <answer> 标签中给出你的回答。
```

---

### 原则 6：复杂任务适合 Prompt Chaining

**为什么适合：**

Anthropic 的 Chaining 与 DAIR.AI 的 Prompt Chaining 逻辑一致，但补充了两个关键点：

1. **链式工作流示例**：
   ```
   Step 1: 分析用户需求 → 输出结构化需求清单
   Step 2: 基于需求设计框架 → 输出阶段表
   Step 3: 填充详细内容 → 输出完整计划
   ```

2. **高级：自我纠正链**
   - 输出初稿 → 自我审查 → 发现问题 → 修正 → 再审查
   - 适用于高价值、高准确性要求的场景

**Anthropic 补充**：不要在单个 prompt 里做太多事。把复杂任务拆成多个步骤，每步专注于一个目标。

---

### 原则 7：effort 参数替代手动 CoT

**为什么重要：**

Claude Opus 4.7 等推理模型已经内置思考链（Extended Thinking）。手动加 "让我们一步一步地思考" 对推理模型可能适得其反。

**effort 五档**：

| 档位 | 适用场景 |
|------|----------|
| `max` | 极限推理，但有过度思考风险 |
| `xhigh` | Opus 4.7 新增，编码和代理类最佳设置 |
| `high` | 平衡 token 使用和智能，智能敏感场景最低推荐 |
| `medium` | 成本敏感场景默认 |
| `low` | 短小任务、延迟敏感的高并发工作负载 |

**新陷阱**：Opus 4.7 会严格遵循 effort 档位。用 `low` 时，推理任务可能直接"想都不想"。

---

### 原则 8：控制冗长度和 Markdown 过度使用

**为什么重要：**

模型倾向于生成冗长的 markdown 列表和 bullet points，但长文本用流畅段落表达更清晰易读。

**模板**：

```xml
<avoid_excessive_markdown_and_bullet_points>
When writing reports, documents, technical explanations, analyses, or any
long-form content, write in clear, flowing prose using complete paragraphs
and sentences. Use standard paragraph breaks for organization and reserve
markdown primarily for `inline_code`, code blocks, and simple headings.
Avoid using **bold** and *italics*.

DO NOT use ordered lists or unordered lists unless: a) you're presenting
truly discrete items where a list format is the best option, or b) the user
explicitly requests a list or ranking
</avoid_excessive_markdown_and_bullet_points>
```

---

## 5. 与 DAIR.AI 的一致之处

| DAIR.AI 方法 | Anthropic 立场 | 说明 |
|--------------|----------------|------|
| **Zero-Shot** | ✅ 完全支持 | Anthropic 强调先试 Zero-Shot，效果不好再加示例 |
| **Few-Shot** | ✅ 支持并细化 | Anthropic 明确 Few-Shot = 格式锁定，不是知识灌输；3~5 个最佳；需要结构化（XML 标签） |
| **Chain-of-Thought** | ⚠️ 条件支持 | 对推理模型（Claude Opus 4.7）建议用 effort 参数替代手动 CoT；对非推理模型仍有效 |
| **Prompt Chaining** | ✅ 全面支持 | Anthropic 的 Chaining 与 DAIR.AI 逻辑一致，并补充了"自我纠正链" |
| **ReAct / 工具调用** | ✅ 全面支持 | Anthropic 有完整的工具调用系统，包括并行工具调用规范 |

**被 Anthropic 强化的 DAIR.AI 方法**：

1. **Few-Shot**——Anthropic 明确指出"格式 > 标签正确性"，比 DAIR.AI 更清晰地说明了示例的作用边界
2. **Prompt Chaining**——Anthropic 补充了链式提示的何时用、如何链的完整指南
3. **上下文组织**——Anthropic 提出了"文档靠前、问题靠后"的量化经验（+30% 质量提升）

---

## 6. 与 OpenAI 校准的一致之处

| OpenAI 校准项 | Anthropic 立场 | 说明 |
|---------------|----------------|------|
| **Reference Text（S2）** | ✅ 全面支持 | Anthropic 用 XML 标签包装参考资料，并要求"先引用后回答"防止幻觉 |
| **清晰分隔符（P2）** | ✅ 全面支持 | Anthropic 的 XML 标签是最严格版本；Markdown `###` 是轻量替代 |
| **结构化输出** | ✅ 全面支持 | Anthropic 用 XML 标签控制输出格式（`<answer>`, `<relevant_quotes>`）；推荐 Structured Outputs |
| **系统化测试** | ✅ 强调 | Anthropic 的迁移清单第 10 条："保持一个评估集，任何提示词变更都跑一遍固定样本" |
| **避免无依据生成** | ✅ 全面支持 | Anthropic 的 `<investigate_before_answering>` 模板：模型必须先读取文件再回答，不能猜测 |
| **不要过度展示推理过程** | ✅ 条件支持 | 对推理模型用 effort 参数替代手动 CoT；对非推理模型仍可用 CoT |

**Anthropic vs OpenAI 的关键差异**：

1. **分隔符严格程度**：Anthropic 偏好 XML 标签（严格），OpenAI 接受 Markdown `###`（宽松）
2. **CoT 策略**：Anthropic 区分推理模型 vs 非推理模型；OpenAI 未明确区分
3. **effort 参数**：Anthropic 独有；OpenAI 用 `reasoning_effort` 参数

---

## 7. 对 T-TEXT-001 v0.4 的影响

### 逐项判断

| 检查项 | 是否需要修改 | 说明 |
|--------|-------------|------|
| 1. 是否需要立刻修改 | **否** | T-TEXT-001 v0.4 已满足核心需求；Anthropic 的建议多为"锦上添花"而非"必须修复" |
| 2. Markdown 分隔符是否足够 | **足够** | `### 角色 / ### 任务 / ### 参考资料` 结构与 Anthropic 的区块化思想一致 |
| 3. 是否需要改成 XML 标签 | **不需要** | 中文用户友好度：Markdown `###` > XML 标签；XML 适合 API 调用，不适合手写模板 |
| 4. 是否需要增加 Few-shot 示例 | **可选** | T-TEXT-001 的场景是"模糊需求"，Few-shot 价值有限；示例更适合"格式锁定"场景 |
| 5. 是否需要增加长上下文说明 | **可选** | 可在模板中补充一行注释，但不影响核心逻辑 |
| 6. 是否需要调整 thinking / CoT 表述 | **不需要** | T-TEXT-001 的 CoT 引导仅在进阶版，且针对非推理模型设计；兼容 |
| 7. 是否需要升级到 v0.5 | **不需要** | 无阻塞性问题；所有建议均为 P1/P2 级优化 |

### 最终结论

**A. 不需要修改**

T-TEXT-001 v0.4 的结构与 Anthropic 方法高度兼容。差异集中在"分隔符严格程度"和"示例使用策略"，两者各有适用场景，不构成错误。

---

## 8. Prompt-KB 通用结构规范建议

基于 Anthropic 方法，提出适合 Prompt-KB 长期使用的通用提示词结构：

### 推荐结构 A：轻量版（适合中文手写模板）

```markdown
### 角色
你是一个{专业领域}规划顾问。

### 任务
帮助用户把模糊的想法变成清晰的规划需求。

### 参考资料
{在此粘贴参考资料；如果没有请写"无"}
AI 必须优先基于参考资料生成计划。不确定的信息标记为[待确认]。

### 原始需求
{在此处粘贴用户的原始想法}

### 输出要求
1. 已知信息汇总
2. 待确认问题清单
3. 初步方向判断
```

### 推荐结构 B：标准版（适合复杂任务）

```markdown
### 角色
你是一个{专业领域}规划顾问。

### 背景信息
{任务背景、受众、最终目标}

### 任务
{具体要做什么}

### 参考资料
{在此粘贴参考资料；如果没有请写"无"}
AI 必须优先基于参考资料。不确定的信息标记为[待确认]。

### 约束条件
{硬性限制、可接受范围}

### 输出格式
{格式要求、段落结构}

### 示例
{可选：1~3 个结构化示例}

### 原始需求
{在此处粘贴用户的原始想法}
```

### 各区块说明

| 区块 | 作用 | 是否必选 |
|------|------|----------|
| **角色** | 定义模型身份和知识范围 | 推荐 |
| **任务** | 明确要做什么，一次只做一件事 | 必须 |
| **背景信息** | 提供任务上下文，提升理解准确性 | 复杂任务推荐 |
| **参考资料** | 防幻觉核心；无资料写"无" | 推荐 |
| **约束条件** | 明确限制，避免模型自由发挥 | 按需 |
| **输出格式** | 控制输出结构，减少后处理 | 推荐 |
| **示例** | 格式锁定；只用于格式敏感任务 | 慎用（3~5 个最佳） |
| **原始需求** | 用户原始输入；放在末尾 | 必须 |

---

## 9. Markdown 分隔符 vs XML 标签

### 比较表

| 维度 | Markdown 标题 `###` | XML 标签 `<tag>` | 代码块 ``` ``` | 表格 `\| \|` |
|------|---------------------|------------------|----------------|-------------|
| **语义明确性** | 中 | 高 | 低 | 中 |
| **模型解析准确性** | 中 | 高 | 中 | 中 |
| **中文用户友好度** | 高 | 中 | 高 | 高 |
| **适合手写模板** | ✅ | ❌ | ✅ | ✅ |
| **适合 API 调用** | ✅ | ✅ | ✅ | ✅ |
| **适合长文档结构** | ✅ | ✅ | ✅ | ❌ |
| **适合多源资料组织** | ❌ | ✅ | ❌ | ❌ |

### Prompt-KB 推荐策略

**日常中文模板优先使用 Markdown 标题 `###`**

理由：
- 对中文用户最友好
- 手写可读性高
- 与 Anthropic 的"区块化思想"一致
- Claude 对 `### ` 和 `<tag>` 都能正确解析

**长上下文或多源资料使用 XML 标签**

```xml
<documents>
  <document index="1">
    <source>参考资料A</source>
    <content>...</content>
  </document>
</documents>

<task_instruction>
分析上述文档，回答：...
</task_instruction>
```

**代码、原始资料、用户输入使用代码块**

```markdown
以下是用户的原始输入：
```
{原始数据}
```

以下是参考资料：
```
{参考文档}
```
```

**不要为了形式复杂而滥用 XML**

| 场景 | 推荐分隔方式 |
|------|------------|
| 3 步 Prompt Chaining | `### 角色 / ### 任务 / ### 参考资料` |
| 10+ 页参考资料分析 | XML 标签包装每份文档 |
| 示例格式锁定 | `<example>` 标签包裹 |
| API 调用模板 | XML 或 Markdown 均可 |
| 手写教学模板 | Markdown `###` |
| 快速单 prompt | 不需要分隔符，直接写 |

---

## 10. 可复制中文提示词模板

### 模板 A：结构化任务提示词模板

```markdown
### 角色
你是一个{专业领域}专家。

### 任务
{具体任务描述，一次只做一件事}

### 背景
{任务背景、受众、目的}

### 约束
- {硬性限制1}
- {硬性限制2}
- 不确定的信息标记为 [待确认]

### 输出格式
{格式要求}

### 原始输入
{在此粘贴用户的原始输入}
```

---

### 模板 B：带参考资料的长上下文提示词模板

```markdown
### 任务
{具体任务描述}

### 参考资料
{在此粘贴参考资料；如果没有请写"无"}
AI 必须优先基于参考资料。不确定的信息标记为 [待确认]。
如果需要引用参考资料中的内容，请先在回答中标注[引用来源]。

### 格式要求
请先用 <relevant_quotes> 标签列出你引用的原文片段，
再在 <answer> 标签中给出你的完整回答。

### 原始需求
{在此处粘贴用户的原始想法}
```

---

### 模板 C：带示例 Few-shot 的提示词模板

```markdown
### 角色
你是一个{专业领域}专家。

### 任务
{具体任务描述}

### 示例
以下是正确的输入-输出对示例：

<example>
输入：{示例输入1}
输出：{示例输出1}
</example>

<example>
输入：{示例输入2}
输出：{示例输出2}
</example>

### 输出要求
严格按照示例的格式输出，不要偏离。

### 原始输入
{在此粘贴用户的原始输入}
```

**使用注意**：
- 示例数量控制在 3~5 个
- 示例要覆盖边界情况
- 示例用于格式锁定，不是教知识

---

## 11. OpenClaw 使用方式

### 适合单 Agent 吗？

**是。** Anthropic 的结构化提示方法非常适合单 Agent 场景：

- `###` 分隔符 → 明确指令区块
- `[待确认]` 标记 → 管理信息不确定性
- 先引用后回答 → 减少幻觉

### 适合多 Agent 吗？

**是，但需要明确分工：**

```yaml
# OpenClaw 配置示例
agents:
  analyzer:
    role: 需求澄清专家
    prompt: "使用 T-TEXT-001 Step 1 结构..."

  planner:
    role: 计划设计师
    prompt: "基于 Step 1 结果，设计计划框架..."
    requires: [analyzer]

  generator:
    role: 内容生成专家
    prompt: "基于 Step 1 + Step 2，生成详细计划..."
    requires: [analyzer, planner]
```

### 适合放入 system prompt 吗？

**是。** 可以将通用结构规范作为 system prompt 的一部分：

```markdown
[System Prompt]
你是一个结构化输出专家。当用户提出任务时：
1. 先确认是否有参考资料
2. 不确定的信息标记为 [待确认]
3. 输出使用 <answer> 标签包裹
4. 如果引用了参考资料，先列出 <relevant_quotes>
```

### 适合放入 workflow 模板吗？

**是。** T-TEXT-001 本身就是最佳示例。

### 适合放入模板库规范吗？

**是。** 本文件（anthropic-structured-prompting-calibration.md）可以作为未来模板的"规范参考"。

### 哪些操作需要 human-in-the-loop？

| 场景 | 是否需要人工确认 |
|------|-----------------|
| 高风险操作（删除文件、发送消息） | ✅ 必须确认 |
| 计划方向重大调整 | ✅ 建议确认 |
| Step 1 → Step 2 过渡 | ✅ 建议确认（确认需求后再做计划） |
| 内容细节调整 | ❌ 不需要 |
| 格式微调 | ❌ 不需要 |

---

## 12. 常见失败

### 1. 标签过多

**问题**：在 prompt 中堆砌 XML 标签或 Markdown 分隔符，导致结构混乱。

**表现**：
- 一个 prompt 里 20+ 个 `###` 分隔
- XML 嵌套超过 3 层
- 模型困惑哪个标签管哪个指令

**解决**：保持简单。`### 角色 / ### 任务 / ### 参考资料 / ### 输出要求` 4 个区块足够。

---

### 2. 提示词过长

**问题**：在一个 prompt 里做太多事。

**表现**：
- 5000+ token 的单 prompt
- 10+ 个任务要求压缩在一起
- 模型开始"摆烂"（忽略后半部分）

**解决**：拆成多个 prompt，用 Prompt Chaining 串联。

---

### 3. 示例污染输出

**问题**：Few-shot 示例过多或过于具体，导致模型模仿而非理解。

**表现**：
- 模型直接复制示例的内容，而非执行任务
- 8 个示例，模型只能处理这 8 种情况
- 新输入超出示例范围时质量暴跌

**解决**：
- 示例控制在 3~5 个
- 示例覆盖边界情况，不是具体答案
- 用 `<example>` 标签包裹，明确输入-输出对

---

### 4. XML 和 Markdown 混用混乱

**问题**：在一个模板里混用不同分隔风格。

**表现**：
- 有的地方用 `###`，有的地方用 `<tag>`
- 参考资料用 XML，指令用 Markdown
- 模型困惑结构

**解决**：
- 单一模板只选一种风格
- 中文手写模板 → Markdown `###`
- API 调用模板 → XML 或 Markdown 均可

---

### 5. 参考资料边界不清

**问题**：参考资料与任务指令混在一起，或参考资料过长。

**表现**：
- 模型把参考资料当指令执行
- 模型在参考资料不足时编造信息
- 100 页 PDF 全部塞进 prompt

**解决**：
- 参考资料放在 `### 参考资料` 或 `<documents>` 区块
- 明确标注"无参考资料时写'无'"
- 长文档先摘要，再用参考资料

---

### 6. 过度要求展示推理过程

**问题**：对推理模型也加 CoT 引导，或要求所有任务都展示思考过程。

**表现**：
- 简单任务（如翻译一句话）输出了 500 字的思考过程
- 推理模型已内置思考，手动引导反而干扰
- 输出冗余，用户需要跳过推理才能看到答案

**解决**：
- 推理模型（Claude Opus 4.7 / GPT-5 / o1）→ 用 effort 参数替代 CoT
- 非推理模型 → CoT 仅用于复杂推理任务
- 简单任务 → 直接回答，不展示推理

---

### 7. 模板对新手不友好

**问题**：模板过于复杂，新手不知道如何替换 `{占位符}`。

**表现**：
- 占位符太多（20+ 个）
- 占位符没有说明
- 填好后仍然报错

**解决**：
- 每个占位符给出填写说明和示例
- 提供"最小填充版"（只需填 3 个必填项）
- 高级参数用 `[可选]` 标注

---

## 13. 修正提示

### 修正 1：防止标签过多

```markdown
【结构简化原则】
保持 prompt 结构简单：
- 每个 prompt 不超过 4~5 个主要区块
- 每个区块不超过 3~5 条规则
- 如果规则太多，拆成多个 prompt
```

### 修正 2：防止提示词过长

```markdown
【单 Prompt 限制】
每个 prompt 只做一件事：
- 如果任务需要 5+ 分钟才能完成，可能需要拆解
- 复杂任务 → 用 Prompt Chaining 串联多个简单 prompt
- 每个 prompt 不超过 1000 token（含参考资料）
```

### 修正 3：防止示例污染

```markdown
【示例使用原则】
示例用于格式锁定，不是教知识：
- 数量：3~5 个最佳
- 覆盖：边界情况和边缘输入
- 明确：标注"这是格式示例，不是标准答案"
- 测试：用未在示例中出现的新输入验证效果
```

### 修正 4：防止 XML 和 Markdown 混用

```markdown
【分隔符选择规则】
单一模板只选一种风格：
- 中文手写模板 → Markdown `###` 区块
- API 调用模板 → XML 或 Markdown 均可
- 长文档分析 → XML 标签
- 切勿在同一模板中混用 `###` 和 `<tag>`
```

### 修正 5：防止参考资料边界不清

```markdown
【参考资料规范】
1. 参考资料必须放在独立区块（`### 参考资料` 或 `<documents>`）
2. 明确标注"无参考资料写'无'"
3. 参考资料不参与指令执行，只提供知识依据
4. 不确定信息必须标记为 [待确认]，不允许编造
5. 长文档（10+ 页）先摘要，再用参考资料
```

### 修正 6：防止过度推理

```markdown
【推理策略选择】
根据模型类型选择推理策略：
- 推理模型（Claude Opus 4.7 / GPT-5 / o1）：用 effort 参数，不加 CoT 引导
- 非推理模型（GPT-4 / Claude 3）：复杂任务加 CoT，简单任务直接回答
- 简单任务（翻译/总结/格式化）：不需要展示推理过程
- 复杂任务（分析/规划/推理）：建议展示推理过程
```

### 修正 7：防止模板不友好

```markdown
【模板友好原则】
1. 每个 {占位符} 给出填写说明
2. 标记必填 vs 可选
3. 提供"最小填充版"（只需填 3 个必填项）
4. 在模板头部给出"快速填充示例"
```

---

## 14. 对 Phase 2 Backlog 的影响

### 已有任务状态

| 任务 ID | 描述 | 当前状态 |
|---------|------|----------|
| P0-1 | 参考资料机制 | ✅ 已完成（T-TEXT-001 v0.3） |
| P0-2 | 分隔符规范 | ✅ 已完成（T-TEXT-001 v0.3） |
| P0-2b | [待确认] 标记统一 | ✅ 已完成（T-TEXT-001 v0.4） |
| P0-3 | 模型类型判断机制 | ⏳ 待完成 |
| P0-4 | Few-Shot 适用条件修正 | ⏳ 待完成 |
| P0-5 | 格式描述升级为占位符示例 | ⏳ 待完成 |

### 是否新增任务

**建议新增任务**：

| 任务 ID | 描述 | 优先级 | 说明 |
|---------|------|--------|------|
| **P1-5** | 通用模板结构规范 | 🟡 中期 | 基于 Anthropic 方法，制定 Prompt-KB 通用模板结构（轻量版/标准版） |
| **P1-6** | Few-shot 示例规范 | 🟡 中期 | Few-shot 使用原则：3~5 个、格式锁定、边界覆盖 |
| **P1-7** | 长上下文输入规范 | 🟡 中期 | 文档靠前、问题靠后、XML 结构化、先引用后回答 |

### 是否需要调整 T-TEXT-001

**不需要。** T-TEXT-001 v0.4 与 Anthropic 方法高度兼容，无阻塞性问题。

### 是否可以先不动 T-TEXT-001，只沉淀方法论

**可以。** 本文件（anthropic-structured-prompting-calibration.md）作为方法论沉淀，可用于：
- 未来新模板的规范参考
- Phase 2 后续任务的理论基础
- T-TEXT-001 v0.5 的优化方向

---

## 15. 推荐存放路径

```
prompt-kb/01-fundamentals/anthropic-structured-prompting-calibration.md
```

---

## 16. 版本记录

| 版本 | 日期 | 变更 |
|------|------|------|
| v0.1 | 2026-05-14 | 基于 Anthropic Claude Prompting Best Practices 官方文档生成结构化提示词校准笔记 |

---

## 17. 最终建议

**选择：A. T-TEXT-001 v0.4 已足够稳定，不再修改**

**理由**：

1. **核心结构兼容**：T-TEXT-001 v0.4 的 `### 分隔符 + 参考资料机制 + [待确认] 标记` 与 Anthropic 方法高度一致
2. **无阻塞问题**：所有 Anthropic 建议均为 P1/P2 级优化，不影响现有功能
3. **稳定优先**：刚完成 v0.4 验收，继续修改会造成版本不稳定
4. **方法论先行**：本文件已沉淀 Anthropic 方法，可在未来模板中复用

**下一步建议顺序**：

1. **A（立即）**：将本文件归档至 `01-fundamentals/`
2. **B（积累）**：用更多实战案例验证 Anthropic 方法的有效性
3. **C（中期）**：创建 Prompt-KB 通用模板结构规范（P1-5）
4. **D（后期）**：基于实战经验，再决定是否小修 T-TEXT-001

---

*本文件为 Prompt-KB Phase 1 学习任务 5 产出，仅作为方法论沉淀，不修改任何现有模板。*
