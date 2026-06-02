# Prompt-KB 快速启动指南

> **版本**: v1.18.0
> **最近更新**: 2026-05-28（Prompt-KB v1.1 已发布，项目进入日常使用和按需扩展阶段）
> **用途**: 30 秒找到你需要的那个文件

---

## 🔍 按需求查找

### 我有一个口语需求，该用哪个模板？

| 你的需求 | 推荐起点 | 文件位置 |
|----------|----------|----------|
| 第一次用 AI，不知道怎么提问 | 先看 Introduction | `01-fundamentals/dair-ai-introduction.md` |
| 让 AI 做一件事（翻译/总结/写文案） | Zero-Shot 提示 | `01-fundamentals/dair-ai-basic-prompting.md` §2 |
| 给几个例子让 AI 照着做 | Few-Shot 提示 | `01-fundamentals/dair-ai-basic-prompting.md` §3 |
| 让 AI 一步步思考再回答 | Chain-of-Thought | `01-fundamentals/advanced-techniques/cot.md` |
| **想做一个 XX 计划，但不知道怎么安排** | **T-TEXT-001 模糊需求转计划 Pipeline** | `02-text-prompts/templates/fuzzy-request-to-plan-pipeline.md` |
| **想生成图片，但不知道提示词怎么写** | **T-IMG-001 速查卡（日常使用）** | `03-image-prompts/image-prompt-quick-reference.md` |
| **想生成视频，但不知道提示词怎么写** | **T-VIDEO-001 速查卡（日常使用）** | `04-video-prompts/video-prompt-quick-reference.md` |
| **已有视频提示词，想适配到不同视频平台** | **T-VIDEO-002 平台适配模板** | `04-video-prompts/templates/video-platform-adaptation-template.md` |
| **想让 OpenClaw 执行复杂任务 / 多步骤任务** | **OpenClaw 工作流速查卡（日常使用）** | `05-openclaw-workflows/openclaw-workflow-quick-reference.md` |

---

### 我想做一个 XX 计划，但不知道怎么安排

如果你的需求类似以下任何一种：

- "我想做一个学习计划，但不知道怎么说。"
- "我想做一个 30 天内容创作计划，但不知道每天发什么。"
- "我想规划一个健身计划，但不知道怎么拆阶段。"
- "我想做一个项目推进计划，但不知道怎么安排步骤。"
- "我想转行但不知道怎么规划职业路径。"

**请使用** → [T-TEXT-001 模糊需求转计划类任务 Pipeline](02-text-prompts/templates/fuzzy-request-to-plan-pipeline.md)（v0.4 稳定版）

| 你的情况 | 推荐用法 |
|----------|----------|
| 需求相对明确，只想快速出结果 | → **简化版 Zero-Shot**（§9） |
| 需求模糊，不知道该提供什么信息 | → **三步 Prompt Chaining**：Step1 需求澄清 → Step2 计划框架 → Step3 详细生成 |
| 高价值 + 复杂计划（如转行/重要考试） | → **进阶版 CoT+GK**（§10），注意 token 成本约 3-4 倍 |
| 不想回答太多问题 | → **最小回答版**（§6），只需确认 3 个核心问题 |

**使用建议**：
- ⭐ **第一次使用**：先跑 **Step 1 需求澄清**，不要直接跳到生成完整计划
- 🔧 **默认执行方式**：单 Agent 顺序执行（无需多 Agent）
- 🔄 **信息不足时**：自动切换"最小回答版"，AI 会做合理假设并标注 `[待确认]`
- 📋 **完整流程**：README → QUICKSTART（本文件）→ T-TEXT-001 模板
- 📌 **参考资料**：有参考资料时优先使用；无参考资料写"无"
- ✅ **标记规范**：不确定信息统一标记为 `[待确认]`（不要用全角【待确认】）

> 📖 **想看实际使用示例？** 先查看已完成的案例，了解模板从"模糊需求"到"计划框架"的完整过程：
> - [CS-001 学习计划场景](06-case-studies/oral-request-to-learning-plan.md) — 原型案例，展示模板的诞生过程
> - [CS-002 小红书内容创作计划](06-case-studies/t-text-001-xiaohongshu-content-plan-test.md) — 迁移验证（93.3% A 通过），非学习计划实测

---

### 我不知道该用 Zero-Shot 还是 Few-Shot？

→ 查 **Basic Prompting** 决策指南：

[01-fundamentals/dair-ai-basic-prompting.md](01-fundamentals/dair-ai-basic-prompting.md)

**快速判断规则**:
- 任务描述清晰、AI 能理解 → **Zero-Shot**
- 输出格式有特殊要求、质量不稳定 → 加 **Few-Shot 示例**
- 还是不确定？从 Zero-Shot 开始，效果不好再加示例

---

### 我遇到复杂任务，该查哪个高级技术？

| 任务特征 | 推荐技术 | 卡片位置 |
|----------|----------|----------|
| 需要 AI 解释推理过程 | 🟢 **CoT** 思维链 | `advanced-techniques/cot.md` |
| 需要最高准确率（可多次调用） | 🟢 **Self-Consistency** 多数投票 | `advanced-techniques/self-consistency.md` |
| 任务太复杂，想拆成多步 | 🟢 **Prompt Chaining** 分步执行 | `advanced-techniques/prompt-chaining.md` |
| AI 缺少领域知识 | 🟢 **Generated Knowledge** 先补充知识 | `advanced-techniques/generated-knowledge.md` |
| 有多种可能方案需要探索 | 🟡 **Tree of Thoughts** 分支搜索 | `advanced-techniques/tree-of-thoughts.md` |
| 需要调用工具/查询/计算 | 🟡 **ReAct** 行动-观察循环 | `advanced-techniques/react.md` |
| 涉及数学/逻辑精确计算 | 🟡 **PAL** 代码辅助推理 | `advanced-techniques/program-aided-language-models.md` |

**不确定选哪个？** → 先看总览对比表：

[dair-ai-advanced-prompting.md](01-fundamentals/dair-ai-advanced-prompting.md) §2 技术分级表

---

### 我想创建新的提示词模板

请先查看：

[prompt-kb/_config/prompt-template-style-guide.md](_config/prompt-template-style-guide.md)（T-CONFIG-001 v0.2 正式版）

**使用建议**：

- 创建文本模板 → 参考「最小模板骨架」
- 创建带资料输入的模板 → 参考「参考资料机制」
- 创建复杂任务模板 → 参考「简化版 / 标准版 / 进阶版规则」
- 创建 OpenClaw 工作流模板 → 参考「OpenClaw 使用规范」
- 不确定是否该用 Few-shot → 参考「Few-shot 示例边界」
- 不确定是否该用 CoT → 参考「Thinking / CoT 使用边界」

---

### 我不知道这个任务该用哪种提示词策略

请查看：

[_config/model-strategy-selection-guide.md](_config/model-strategy-selection-guide.md)（T-CONFIG-003 v0.2 正式版）

**使用建议**：

- 任务简单、输入清楚 → 优先 **Zero-Shot**
- 输出格式不稳定 → 考虑 **Few-shot**
- 需求模糊或需要分阶段 → 考虑 **Prompt Chaining**
- 需要参考资料 → 加入 **Reference Text / 参考资料区**
- 需要外部信息或文件处理 → 考虑 **工具调用**
- 涉及高权限操作（删除/发送/日历/命令行） → 必须 **human-in-the-loop**
- 需要审查、并行或长期自动化 → 再考虑 **多 Agent**

---

### 我不知道模板里要不要加示例

请查看：

[_config/few-shot-example-guide.md](_config/few-shot-example-guide.md)（T-CONFIG-002 v0.2 正式版）

**使用建议**：
- 输出格式不稳定 → 考虑加入 Few-shot
- 用户不知道怎么填写 → 加入 1 个正常输入示例
- 经常出现信息缺失 → 加入信息不足示例
- 任务有边界或风险 → 加入边界输入示例
- 示例超过 3 个 → 优先迁移到案例库（`06-case-studies/`）
- 带参考资料的模板 → 示例须展示「参考资料」区块 + `[引用来源]` 标注
- 不要为了显得完整而给所有模板强行加示例

---

### 我不知道这个模板要不要加示例

请查看：

[_config/few-shot-usage-decision-guide.md](_config/few-shot-usage-decision-guide.md)（T-CONFIG-004 v0.1 正式版）

**使用建议**：

- 任务简单、输入清楚：通常不用 Few-shot
- 输出格式不稳定：考虑 Few-shot
- 需要固定风格或固定结构：考虑 Few-shot
- 用户不知道怎么填写：加入 1 个正常输入示例
- 经常出现信息不足：加入信息不足示例
- 有边界或风险场景：加入边界输入示例
- 示例超过 3 个：优先迁移到案例库
- 确认需要示例后，再参考 T-CONFIG-002 编写示例

---

### 我不知道模板里的格式和占位符怎么写

请查看：

[_config/format-and-placeholder-guide.md](_config/format-and-placeholder-guide.md)（T-CONFIG-005 v0.1 正式版）

**使用建议**：

- 不知道占位符怎么写：查看「占位符基础规范」和「占位符命名规则」
- 不知道输入区怎么写：查看「输入区格式规范」
- 不知道输出用 Markdown、表格、JSON 还是 YAML：查看「输出格式描述规范」
- 需要机器读取：优先 JSON
- 需要 OpenClaw 配置：优先 YAML
- 面向中文用户阅读：优先 Markdown
- 表格只适合短字段，不适合承载长段落
- 不确定信息统一标记为 [待确认]

---

### 我有很多资料，不知道怎么让 AI 处理

请查看：

[_config/long-context-input-guide.md](_config/long-context-input-guide.md)（T-CONFIG-006 v0.1 正式版）

**使用建议**：

- 资料超过 1000 字：先判断是否属于长上下文任务（查 §4 判断表）
- 多个来源：先编号并标注来源名称、类型、日期、可信度（查 §6）
- 有会议纪要 / 网页 / 报告 / 表格 / 聊天记录：先整理来源类型（查 §7）
- 资料很长：先摘要，再分析（查 §11 摘要规范）
- 资料冲突：先列冲突点，不要直接选择一个当事实（查 §9）
- 资料不足：标记 [待确认] 或 [假设]，高风险任务应停止并补充资料（查 §10）
- 需要 OpenClaw 执行：优先单 Agent 顺序执行（查 §15-16）
- 任务复杂或需要审查：再考虑 human-in-the-loop 或多 Agent（查 §16）

---

### 我想生成图片，但不知道提示词怎么写

> **Phase 3 图像提示词模块已完成阶段性闭环。✅**

**快速使用（日常优先）：**

[prompt-kb/03-image-prompts/image-prompt-quick-reference.md](03-image-prompts/image-prompt-quick-reference.md)（T-IMG-001 速查卡 v0.2，已通过轻量验收）

**完整规范（深度查阅）：**

[prompt-kb/03-image-prompts/image-prompt-foundation.md](03-image-prompts/image-prompt-foundation.md)（T-IMG-001 v0.2 正式版）

**使用建议**：

| 你的情况 | 推荐用法 |
|----------|----------|
| 只是快速生成图像提示词 | → **先用 quick-reference** |
| 只有口语化需求 | → quick-reference 中的「口语需求转图像提示词」模板 |
| 已有提示词但效果不好 | → quick-reference 中的「优化已有图像提示词」模板 |
| 不确定提示词是否完整 | → quick-reference 中的「图像提示词验收清单」 |
| 需要系统学习图像提示词结构 | → 查看 image-prompt-foundation.md |
| 需要平台专用参数 | → [T-IMG-002 平台适配模板](03-image-prompts/templates/image-platform-adaptation-template.md)（v0.1，已通过质量验收） |

---

### 我已经有图像提示词，想适配到不同平台

请使用：

[prompt-kb/03-image-prompts/templates/image-platform-adaptation-template.md](03-image-prompts/templates/image-platform-adaptation-template.md)（T-IMG-002 v0.1，已通过质量验收）

**使用建议**：

| 你的情况 | 推荐用法 |
|----------|----------|
| 已有通用图像提示词 | → 使用 T-IMG-002 改写为多平台版本 |
| 想同时测试多个平台 | → 使用"多平台输出模板"（§12） |
| 用 ChatGPT Images / 豆包 | → 优先使用自然语言描述 |
| 用 Midjourney | → 优先使用英文提示词和通用参数建议，不写死版本号 |
| 用 Stable Diffusion / Flux | → 区分正向提示词和负面限制 |
| 用 Hugging Face | → 先确认具体模型说明 |
| 不确定平台差异 | → 先使用 T-IMG-001 和 quick-reference 生成通用提示词，再用 T-IMG-002 适配 |

---

### 我想生成视频，但不知道提示词怎么写

> **Phase 4 视频提示词模块 — T-VIDEO-001 v0.1 已通过质量验收（A级 / 91/100），速查卡 v0.2 已完成（98/100 A级）✅**

**日常快速使用（推荐首选）**：

[prompt-kb/04-video-prompts/video-prompt-quick-reference.md](04-video-prompts/video-prompt-quick-reference.md)（T-VIDEO-001 速查卡 v0.2）

→ 覆盖 L1-L5 分级、20 维度速查表、口语需求转写模板、分镜模板、平台参数速查、验收清单

**基础规范（深度查阅）**：

[prompt-kb/04-video-prompts/video-prompt-foundation.md](04-video-prompts/video-prompt-foundation.md)（T-VIDEO-001 v0.1）

→ 进入 **视频提示词模块**：[04-video-prompts/README.md](04-video-prompts/README.md)

**当前状态**: ✅ 基础规范 v0.1 已验收（A级 / 91/100）；✅ 速查卡 v0.2 已完成（98/100 A级）；✅ T-VIDEO-002 v0.1 已通过质量验收（A级 / 110/110）

**适用场景**：
- 简单动态画面
- 单主体动作视频
- 产品展示视频
- 社交媒体短视频
- 动态海报
- 广告短片
- 多镜头分镜视频
- 需要中英文视频提示词
- 需要负面提示词
- 需要平台适配建议

**使用建议**：

| 你的情况 | 推荐用法 |
|----------|----------|
| 日常快速生成（L1-L2 简单任务） | → 用 **速查卡** 的「L1-L2 最小输出结构」（5 项：需求解析 + 中文视频提示词 + 英文视频提示词 + 负面提示词 + 待补充问题） |
| 只有一句口语化视频需求 | → 使用速查卡或 T-VIDEO-001 中的「口语需求转视频提示词模板」 |
| 视频任务较复杂 | → 使用「分镜视频提示词模板」（9 列 storyboard 格式，速查卡和完整规范均有） |
| 不确定视频提示词是否完整 | → 使用速查卡的「验收清单」或完整规范的「视频提示词验收清单」（20 项 / 5 组） |
| 有参考图或参考视频 | → 在「参考资料」区明确说明用途（首帧参考 / 风格参考 / 动作参考） |
| 涉及平台差异 | → 先用速查卡的「平台参数速查表」，深度适配再参考 T-VIDEO-001 §16 的通用平台适配原则 |
| 已有视频提示词，需要改写到不同平台 | → 优先使用 **T-VIDEO-002 平台适配模板**（`04-video-prompts/templates/video-platform-adaptation-template.md`，v0.1，A级 / 110/110） |
| L4-L5 高价值视频任务 | → 建议拆分镜并人工确认 |

**视频提示词将复用图像提示词中的结构**：
- 复用：主体 / 场景 / 风格 / 构图 / 光线 / 色彩 / 材质细节 / 负面限制（来自 T-IMG-001）
- 新增：动作 / 镜头运动 / 时间顺序 / 节奏 / 转场 / 首帧 / 末帧 / 画面稳定性 / 时长 / 分辨率比例

---

### 我已经有视频提示词，想适配到不同视频平台

优先使用：

[prompt-kb/04-video-prompts/templates/video-platform-adaptation-template.md](04-video-prompts/templates/video-platform-adaptation-template.md)（T-VIDEO-002 v0.1，A级 / 110/110，已通过质量验收）

**适用场景**：
- 已有通用视频提示词，需要改写为平台版本
- 同一视频需求要在多个平台测试
- 需要生成 Runway / Pika / Kling / Luma / Sora / 豆包 / 即梦等平台版本
- 需要比较不同平台的提示词写法
- 需要避免写死平台版本号
- 需要避免跨平台误用参数
- 需要生成平台差异说明
- 需要为视频案例生成平台适配测试

**使用建议**：
- 先用 video-prompt-quick-reference 生成通用视频提示词
- 再用 T-VIDEO-002 改写为平台适配版本
- 不确定平台能力时，不写死参数，以当前平台文档为准
- 有参考图、首帧图或末帧图时，必须说明用途
- 高价值视频任务需要人工确认动作、镜头运动、时长和风险

---

### 我想让 OpenClaw 多 Agent 协作

> **Phase 5 OpenClaw 工作流模块已完成阶段性闭环 ✅**

**优先使用（日常快速查阅）**：

[prompt-kb/05-openclaw-workflows/openclaw-workflow-quick-reference.md](05-openclaw-workflows/openclaw-workflow-quick-reference.md)（v0.1，A级 / 120/120）

**完整规范（深度查阅）**：

[prompt-kb/05-openclaw-workflows/openclaw-workflow-foundation.md](05-openclaw-workflows/openclaw-workflow-foundation.md)（T-OPENCLAW-001 v0.1，A级 / 120/120）

**案例参考**：

[prompt-kb/06-case-studies/cs-openclaw-001-module-delivery-workflow.md](06-case-studies/cs-openclaw-001-module-delivery-workflow.md)（CS-OPENCLAW-001 v0.1，A级 / 110/110）

**OpenClaw 工作流模块已覆盖**：
- 任务识别与复杂度判断
- 单 Agent / 多 Agent 判断
- 执行计划与产物生成
- 质量验收与小修处理
- 导航登记与下一步决策
- 失败与返工处理
- 输出报告与工作流验收清单

**理论基础**（可选参考）：

| 协作模式 | 对应技术 | 卡片 |
|----------|----------|------|
| 串行流水线 | Prompt Chaining | `advanced-techniques/prompt-chaining.md` |
| 并行投票 | Self-Consistency | `advanced-techniques/self-consistency.md` |
| 并行分支探索 | Tree of Thoughts | `advanced-techniques/tree-of-thoughts.md` |
| Agent 工具调用循环 | ReAct | `advanced-techniques/react.md` |

每个 Advanced 技术卡片的 §6 都有「OpenClaw 配置建议」，可直接参考。

---

## 🚀 最快上手路径（5 分钟）

```
1. 读 Introduction 前 3 节（约 5 分钟）
   ↓
2. 用 Zero-Shot 试一个真实需求
   ↓
3. 效果不好？加Few-Shot示例 or 加CoT "让我们一步一步地思考"
   ↓
4. 还是不满意？翻 Advanced 总览，按表查技术
```

**从零到能用的最小集合**: Introduction + Basic + CoT = 3 个文件

---

## 📋 关键文件索引

| 文件 | 状态 | 一句话说明 |
|------|------|-----------|
| [README.md](README.md) | ✅ 当前 | 知识库总览、进度、全模块入口 |
| [QUICKSTART.md](QUICKSTART.md) | ✅ 当前 | 本文件，按需求速查 |
| [01-fundamentals/README.md](01-fundamentals/README.md) | ✅ 已更新 | 基础模块导航与学习顺序 |
| [dair-ai-introduction.md](01-fundamentals/dair-ai-introduction.md) | ✅ v0.2 | 入门：定义/能力/原则/局限 |
| [dair-ai-basic-prompting.md](01-fundamentals/dair-ai-basic-prompting.md) | ✅ v0.2 | 基础：Zero-Shot/Few-Shot/格式技巧 |
| [dair-ai-advanced-prompting.md](01-fundamentals/dair-ai-advanced-prompting.md) | ✅ v0.2 | 高级总览：10 项技术对比+决策树 |
| [advanced-techniques/](01-fundamentals/advanced-techniques/) | ✅ 7 卡片 | 每个技术一张独立卡片（含模板+配置） |
| [T-TEXT-001 模糊需求转计划 Pipeline](02-text-prompts/templates/fuzzy-request-to-plan-pipeline.md) | ✅ v0.4 稳定版 | 首个文本模板：模糊需求→可执行计划（10 类场景）；含参考资料机制、分隔符规范、[待确认] 标记统一 |
| [_config/kb-rules.md](_config/kb-rules.md) | ✅ | 知识库运作规则 |
| [T-CONFIG-001 通用模板结构规范](_config/prompt-template-style-guide.md) | ✅ v0.2 | 模板结构标准（元数据/输入区/分隔符/CoT 边界等） |
| [T-CONFIG-002 Few-shot 示例规范](_config/few-shot-example-guide.md) | ✅ v0.2 | 模板示例设计标准（数量/三类示例/参考资料/验收清单） |
| [T-CONFIG-003 策略判断规范](_config/model-strategy-selection-guide.md) | ✅ v0.2 | 策略选择标准（L1-L5分级/Zero-Shot/Few-Shot/Chaining/CoT/工具调用/Agent/模型类型/决策树） |
| [T-CONFIG-004 Few-shot 适用条件判断规范](_config/few-shot-usage-decision-guide.md) | ✅ v0.1 | Few-shot 启用判断（16场景决策表/Zero-Shot vs Few-shot vs 案例库边界/数量规则/Prompt Chaining判断/决策树/可复制提示词） |
| [T-CONFIG-005 格式描述与占位符规范](_config/format-and-placeholder-guide.md) | ✅ v0.1 | 格式与占位符标准（输入区4分区/Markdown表格JSON YAML输出格式/图像视频OpenClaw格式/占位符示例库/常见错误/可复制格式判断提示词） |
| [T-CONFIG-006 长上下文输入规范](_config/long-context-input-guide.md) | ✅ v0.1 | 长上下文输入标准（长文档/多来源资料/资料冲突/资料不足/OpenClaw长流程/多Agent边界/图像视频参考资料/可复制模板） |
| [T-IMG-001 图像提示词基础规范](03-image-prompts/image-prompt-foundation.md) | ✅ v0.2 | 图像提示词基础规范（15维度核心结构/标准输入输出/复杂度分级/负面提示词/参考图/平台适配/生成器模板/优化模板/验收清单） |
| [T-IMG-001 速查卡](03-image-prompts/image-prompt-quick-reference.md) | ✅ v0.2 已通过轻量验收 | T-IMG-001 日常快速使用入口（核心公式/15维度速查表/可复制模板/验收清单/常见错误） |
| [T-IMG-002 平台适配模板](03-image-prompts/templates/image-platform-adaptation-template.md) | ✅ v0.1 已通过质量验收 | 将通用图像提示词改写为 ChatGPT Images / 豆包 / Midjourney / SD / Flux / HF 平台版本 |
| [T-VIDEO-001 视频提示词基础规范](04-video-prompts/video-prompt-foundation.md) | ✅ v0.1 已通过质量验收（A级/91分） | 视频提示词基础规范（20维度核心结构/L1-L5分级/动作7要素/12种运镜/3种时间结构/负面提示词/平台适配/口语转视频模板/分镜模板/验收清单） |
| [T-VIDEO-001 速查卡](04-video-prompts/video-prompt-quick-reference.md) | ✅ v0.2 已通过验收（98/100 A级） | T-VIDEO-001 日常快速使用入口（L1-L5分级/20维度速查表/口语需求转写模板/分镜模板/平台参数速查/验收清单） |
| [T-VIDEO-002 平台适配模板](04-video-prompts/templates/video-platform-adaptation-template.md) | ✅ v0.1 已通过质量验收（A级/110/110） | 将通用视频提示词改写为多平台适配版本（Runway / Pika / Kling / Luma / Sora / 豆包 / 即梦 / 其他模型）；保留动作、镜头运动、时间顺序、节奏，并按平台能力调整表达方式 |
| [07-learning/_plans/execution-prompt-dair-ai-intro.md](07-learning/_plans/execution-prompt-dair-ai-intro.md) | ✅ | DAIR.AI Introduction 执行提示词 |

---

## ⚠️ 重要提醒

### 安全第一
涉及以下操作，必须人工确认：
- 文件删除/覆盖
- 命令执行
- 邮件/消息发送
- 外部 API 调用

### 使用原则
- ❌ 全文搬运外部资源内容
- ❌ 只做摘要不转可执行模板
- ❌ 不测试就声称可用
- ✅ 每次使用后记录复盘 → `06-case-studies/`

---

*30 秒找到文件，5 分钟开始使用。有问题看 [README.md](README.md) 总览。*

---

## 📖 新用户推荐阅读顺序

1. [README.md](README.md) — 知识库总览、进度、全模块入口
2. [QUICKSTART.md](QUICKSTART.md) — 本文件，按需求速查
3. [RELEASE_NOTES_v1.1.md](RELEASE_NOTES_v1.1.md) — v1.1 发布说明，了解完整能力清单
4. [FINAL_ACCEPTANCE_REPORT_v1.1.md](FINAL_ACCEPTANCE_REPORT_v1.1.md) — 总体验收报告，了解验收结论
5. 根据任务类型选择文本 / 图像 / 视频 / OpenClaw 工作流模块
6. 需要案例时查看 [06-case-studies/README.md](06-case-studies/README.md)

**当前 Prompt-KB v1.1 已覆盖**：
- 文本提示词（T-TEXT-001）
- 图像提示词（T-IMG-001 + T-IMG-002 + 速查卡）
- 视频提示词（T-VIDEO-001 + T-VIDEO-002 + 速查卡）
- 平台适配（图像 6 平台 + 视频 7 平台）
- OpenClaw 工作流（T-OPENCLAW-001 + 速查卡）
- 案例与测试（9 个，覆盖四大类别）
- 知识库维护流程（10 项能力）
