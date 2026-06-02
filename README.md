# Prompt Engineering 知识库 (Prompt-KB)

> **版本**: v2.20.0
> **创建日期**: 2026-05-14
> **最近更新**: 2026-05-28（Prompt-KB v1.1 正式发布，Phase 1-5 全部完成阶段性闭环，项目进入日常使用和按需扩展阶段）
> **维护者**: KB-Admin
> **用途**: AI 提示词学习、复用、复盘的长期知识积累系统

---

## 知识库目标

构建一个**以 DAIR.AI Prompt Engineering Guide 为主线**的提示词知识库，覆盖文本/图像/视频三大媒介，支持单 Agent 和多 Agent (OpenClaw) 执行场景，实现「学→练→复用→复盘」的闭环。

> **关于 OpenClaw**：OpenClaw 在本知识库中指代多 Agent 工作流执行环境，可迁移理解为 Claude Code、OpenClaw 或其他 Agent 工作流工具。本知识库的工作流规范和案例不绑定特定平台，可按需迁移到任意支持多步骤任务编排的 Agent 环境。

**当前聚焦**: Prompt-KB v1.1 已发布 / 进入使用阶段

---

## 总体进度

| 阶段 | 模块 | 状态 | 说明 |
|------|------|------|------|
| Phase 1 | Prompt Engineering 基础学习 | ✅ 已完成 | DAIR.AI / OpenAI / Anthropic 学习与校准完成 |
| Phase 2 | 配置规范层建设 | ✅ 已完成 | T-CONFIG-001 到 T-CONFIG-006 全部完成并登记 |
| Phase 3 | 图像提示词模块 | ✅ 已完成阶段性闭环 | 7 个交付物全部完成；形成"规范→速查→案例→平台适配→测试"五层闭环；覆盖抽象概念图和实体产品图两类场景；2 个平台适配测试全部通过 |
| Phase 4 | 视频提示词模块 | ✅ 已完成阶段性闭环 | 5 个交付物全部完成（A级）；形成"规范→速查→案例→平台适配→测试"完整闭环；四条子闭环全部成立；后续第二个视频案例、参考图/首帧/末帧案例、音频/字幕/口播规范可按需扩展 |
| Phase 5 | OpenClaw 多 Agent 工作流 | ✅ 已完成阶段性闭环 | 3/3 交付物完成（A级）；形成"规范→速查→案例→登记"基础闭环；四条闭环全部成立；20/20 能力项覆盖；后续多 Agent 协作模板等可按需扩展 |

> **总体进度**: Prompt-KB v1.0 可用版已完成
>
> **发布说明**: [RELEASE_NOTES_v1.0.md](RELEASE_NOTES_v1.0.md)（v1.0 基础可用版）· [RELEASE_NOTES_v1.1.md](RELEASE_NOTES_v1.1.md)（v1.1 完整能力扩展版）
>
> **验收报告**: [FINAL_ACCEPTANCE_REPORT_v1.1.md](FINAL_ACCEPTANCE_REPORT_v1.1.md)
> **交接说明**: [HANDOFF_PROMPT-KB_v1.1.md](HANDOFF_PROMPT-KB_v1.1.md)：Prompt-KB v1.1 交接说明，用于迁移到新 Claude Code / OpenClaw / Agent 环境

---

## 已完成模块

### ✅ 01-fundamentals/ — 文本提示词基础（DAIR.AI 全系列）

基于 DAIR.AI Prompt Engineering Guide 官方内容整理，包含三层递进结构：

| 层级 | 内容 | 核心文件 |
|------|------|----------|
| **入门** | Prompt Engineering 定义、能力概览、大模型基础 | [dair-ai-introduction.md](01-fundamentals/dair-ai-introduction.md) |
| **基础** | Zero-Shot / Few-Shot 提示 + 示例选择策略 + 高级提示词格式 | [dair-ai-basic-prompting.md](01-fundamentals/dair-ai-basic-prompting.md) |
| **高级** | 7 大进阶技术总览 + 3 个延期技术摘要 | [dair-ai-advanced-prompting.md](01-fundamentals/dair-ai-advanced-prompting.md) |

**高级技术独立卡片**（`01-fundamentals/advanced-techniques/`）：

| 技术 | 文件 | 适配度 |
|------|------|--------|
| 🟢 Chain-of-Thought (CoT) | [cot.md](01-fundamentals/advanced-techniques/cot.md) | 单Agent ★★★ / 多Agent ★★★ |
| 🟢 Self-Consistency | [self-consistency.md](01-fundamentals/advanced-techniques/self-consistency.md) | 单Agent ★★ / 多Agent ★★★★★ |
| 🟢 Generated Knowledge | [generated-knowledge.md](01-fundamentals/advanced-techniques/generated-knowledge.md) | 单Agent ★★★★ / 多Agent ★★ |
| 🟢 Prompt Chaining | [prompt-chaining.md](01-fundamentals/advanced-techniques/prompt-chaining.md) | 单Agent ★★★★★ / 多Agent ★★★ |
| 🟡 Tree of Thoughts | [tree-of-thoughts.md](01-fundamentals/advanced-techniques/tree-of-thoughts.md) | 单Agent ★★★ / 多Agent ★★★★ |
| 🟡 ReAct | [react.md](01-fundamentals/advanced-techniques/react.md) | 单Agent ★★ / 多Agent ★★★★★ |
| 🟡 Program-Aided LM | [program-aided-language-models.md](01-fundamentals/advanced-techniques/program-aided-language-models.md) | 单Agent ★★★ / 多Agent ★★ |

🔴 延期技术：APE / Active-Prompt / DSP（详见 Advanced 总览文件）

### ✅ 02-text-prompts/ — 文本提示词模板库

> **状态**: ✅ 稳定版（T-TEXT-001 v0.4 已验收）
>
> **核心模板**:

| 模板 | 编号 | 文件 | 用途 | 推荐执行 |
|------|------|------|------|----------|
| **模糊需求转计划类任务 Pipeline** | T-TEXT-001 | [fuzzy-request-to-plan-pipeline.md](02-text-prompts/templates/fuzzy-request-to-plan-pipeline.md) | 把模糊的计划类需求转成可执行计划 | 单 Agent 顺序 Prompt Chaining |

**适用场景**: 学习计划 · 健身计划 · 写作计划 · 项目计划 · 考试计划 · 内容创作计划 · 职业规划 · 产品规划 · 运营计划

**当前版本**: v0.4（已通过质量验收；已包含参考资料机制 + 分隔符规范 + [待确认] 标记统一）

**验证案例**:

| 案例 | 场景 | 评分 | 结论 | 文件 |
|------|------|------|------|------|
| CS-001 | 学习计划（原型场景） | — | 来源案例 | [oral-request-to-learning-plan.md](06-case-studies/oral-request-to-learning-plan.md) |
| CS-002 | 小红书内容创作计划（迁移验证） | **93.3%** | ✅ A 通过 | [t-text-001-xiaohongshu-content-plan-test.md](06-case-studies/t-text-001-xiaohongshu-content-plan-test.md) |

### ✅ _config/ — 知识库配置与规范

> **状态**: ✅ 已完成（T-CONFIG-001 至 T-CONFIG-006 全部正式版）
>
> **核心规范**:

| 规范 | 编号 | 文件 | 用途 | 状态 |
|------|------|------|------|------|
| **Prompt-KB 通用模板结构规范** | T-CONFIG-001 | [_config/prompt-template-style-guide.md](_config/prompt-template-style-guide.md) | 作为后续所有 Prompt-KB 模板的结构标准 | ✅ v0.2 正式版 |
| **Prompt-KB Few-shot 示例规范** | T-CONFIG-002 | [_config/few-shot-example-guide.md](_config/few-shot-example-guide.md) | 指导后续 Prompt-KB 模板如何设计 Few-shot 示例 | ✅ v0.2 正式版 |
| **Prompt-KB 模型类型与提示策略判断规范** | T-CONFIG-003 | [_config/model-strategy-selection-guide.md](_config/model-strategy-selection-guide.md) | 判断任务应该使用哪种提示词策略和执行方式 | ✅ v0.2 正式版 |
| **Prompt-KB Few-shot 适用条件判断规范** | T-CONFIG-004 | [_config/few-shot-usage-decision-guide.md](_config/few-shot-usage-decision-guide.md) | 判断模板是否应该启用 Few-shot，以及是否应迁移到案例库 | ✅ v0.1 正式版 |
| **Prompt-KB 格式描述与占位符规范** | T-CONFIG-005 | [_config/format-and-placeholder-guide.md](_config/format-and-placeholder-guide.md) | 统一模板中的输入区、输出格式、占位符、JSON/YAML/Markdown/表格描述 | ✅ v0.1 正式版 |
| **Prompt-KB 长上下文输入规范** | T-CONFIG-006 | [_config/long-context-input-guide.md](_config/long-context-input-guide.md) | 统一长文档、多来源资料、参考资料、资料冲突、资料不足和 OpenClaw 长流程任务的输入组织方式 | ✅ v0.1 正式版 |

**覆盖内容**：
- 模板元数据 / 适用场景 / 不适用场景
- 标准输入区 / 参考资料机制 / 分隔符规范
- Few-shot 示例边界 / Thinking / CoT 使用边界
- 简化版 / 标准版 / 进阶版版本选择
- OpenClaw 执行规范 / 版本记录 / 质量验收清单

> 后续新建模板默认应遵守 T-CONFIG-001，除非是学习笔记、案例复盘或临时草稿。

**T-CONFIG-002 Few-shot 示例规范覆盖内容**：
- 什么时候需要 / 不需要 Few-shot
- 示例数量规则（默认 1，复杂 2-3，超 3 迁移案例库）
- 三类标准示例：正常输入 / 信息不足 / 边界输入
- 带参考资料输入的示例格式（含 `[引用来源]` 标注规范）
- 图像 / 视频示例边界（通用原则适用，具体格式由各模块定义）
- 示例污染风险 / 示例验收标准

> 后续新建模板如需示例，应优先遵守 T-CONFIG-002，避免示例堆砌和示例污染输出。

> 当不确定某个任务应该用简单提示词、Few-shot、Prompt Chaining、工具调用还是多 Agent 时，优先查阅 T-CONFIG-003。

> 当不确定某个模板是否需要示例时，优先查阅 T-CONFIG-004；如果确认需要示例，再参考 T-CONFIG-002 编写示例。

> 当不确定模板中的输入区、输出格式、占位符、表格、JSON、YAML 应该怎么写时，优先查阅 T-CONFIG-005。

**T-CONFIG-006 长上下文输入规范覆盖内容**：
- 长上下文任务判断（8 条标准 + 判断表）
- 长上下文输入总结构（7 区块：任务目标 / 背景信息 / 参考资料 / 资料来源说明 / 限制条件 / 输出格式 / 原始需求）
- 多来源资料组织（编号 / 来源 / 日期 / 可信度）
- 资料来源标注（10 种来源类型）
- 资料可信度和时效性规范（14 种资料类型可信度表）
- 资料冲突处理（5 种冲突类型 + 处理模板）
- 资料不足处理（4 级风险等级 + 处理模板）
- 长资料摘要规范（摘要模板）
- 分块处理规范（7 条分块原则）
- 引用和依据说明规范（5 种引用格式）
- OpenClaw 长上下文工作流（6 步流程）
- 多 Agent 长上下文协作边界（判断表）
- 图像 / 视频参考资料处理（输入规范）
- 可复制长上下文输入模板
- 可复制长上下文处理提示词

> 当任务涉及长文档、多来源资料、会议纪要、网页摘要、历史记录、参考资料或资料冲突时，优先查阅 T-CONFIG-006。

**T-CONFIG-005 格式描述与占位符规范覆盖内容**：
- 占位符基础规范（中文方括号 `[中文描述]`）
- 占位符命名规则
- 标准输入区（4 个分区的格式规范）
- Markdown 输出格式
- 表格输出格式
- JSON 输出格式
- YAML 输出格式
- 图像提示词格式描述
- 视频提示词格式描述
- OpenClaw 工作流格式
- 占位符示例库
- 常见格式错误
- 可复制格式判断提示词

**T-CONFIG-003 模型类型与提示策略判断规范覆盖内容**：
- L1-L5 任务复杂度分级
- Zero-Shot 使用规范
- Few-shot 使用规范
- Prompt Chaining 使用规范
- Thinking / CoT 使用边界
- 工具调用判断（含 human-in-the-loop）
- 单 Agent / 多 Agent 判断
- 模型类型判断（7 类模型）
- 图像 / 视频任务策略边界
- 任务策略决策树
- 可复制策略判断提示词

**T-CONFIG-004 Few-shot 适用条件判断规范覆盖内容**：
- Few-shot 决策总表（16 场景）
- 应该使用 Few-shot 的场景（7 子场景）
- 不应该使用 Few-shot 的场景（6 子场景）
- Zero-Shot / Few-shot / 案例库三者边界与迁移规则
- 示例数量判断规则
- Prompt Chaining 中的 Few-shot 判断
- 图像 / 视频提示词中的 Few-shot 判断
- OpenClaw 工作流中的 Few-shot 判断
- Few-shot 启用决策树（9 步文字树）
- 可复制判断提示词
- 常见误判（10 项）

---

## 各模块入口

### 📖 01-fundamentals/ — 文本提示词基础

> **状态**: ✅ 已完成
>
> **适合人群**: 刚接触 Prompt Engineering 或需要系统化梳理基础知识
>
> **入口文件**: [01-fundamentals/README.md](01-fundamentals/README.md)

**快速跳转**:
- 从零开始 → [Introduction](01-fundamentals/dair-ai-introduction.md)
- 掌握 Zero-Shot / Few-Shot → [Basic Prompting](01-fundamentals/dair-ai-basic-prompting.md)
- 学习 7 大高级技术 → [Advanced Prompting 总览](01-fundamentals/dair-ai-advanced-prompting.md)
- 查阅具体技术卡片 → [advanced-techniques/](01-fundamentals/advanced-techniques/)

---

### 📝 02-text-prompts/ — 文本生成提示词模板库

> **状态**: ✅ 稳定版（T-TEXT-001 v0.4 已验收）
>
> **规划内容**: 写作/翻译/总结/分析/代码生成等场景的可复用模板
>
> **已有模板** → [T-TEXT-001 模糊需求转计划类任务 Pipeline](02-text-prompts/templates/fuzzy-request-to-plan-pipeline.md)
>
> **入口文件**: [02-text-prompts/README.md](02-text-prompts/README.md)

---

### ✅ 03-image-prompts/ — 图像生成提示词

> **状态**: ✅ 已完成阶段性闭环（T-IMG-001 v0.2 已完成，CS-IMG-001/002 已验收，T-IMG-002 已通过质量验收）
>
> **核心规范**:

| 规范 | 编号 | 文件 | 用途 | 状态 |
|------|------|------|------|------|
| **Prompt-KB 图像提示词基础规范** | T-IMG-001 | [image-prompt-foundation.md](03-image-prompts/image-prompt-foundation.md) | 统一图像生成提示词的主体、场景、风格、构图、镜头、光线、色彩、材质细节、负面提示词、参考图和平台适配方式 | ✅ v0.2 正式版 |
| **T-IMG-001 图像提示词速查卡** | — | [image-prompt-quick-reference.md](03-image-prompts/image-prompt-quick-reference.md) | T-IMG-001 的日常快速使用入口，覆盖核心公式、15 维度速查表、可复制模板、验收清单、常见错误等 | ✅ v0.2 已通过轻量验收 |
| **T-IMG-002 图像提示词平台适配模板** | T-IMG-002 | [image-platform-adaptation-template.md](03-image-prompts/templates/image-platform-adaptation-template.md) | 将同一个图像需求或通用提示词改写为 ChatGPT Images / 豆包 / Midjourney / Stable Diffusion / Flux / Hugging Face 等平台适配版本 | ✅ v0.1 已通过质量验收 |

**案例**:

| 案例 | 编号 | 文件 | 用途 | 状态 |
|------|------|------|------|------|
| **Prompt-KB 知识库封面图提示词案例** | CS-IMG-001 | [cs-img-001-prompt-kb-cover-image.md](06-case-studies/cs-img-001-prompt-kb-cover-image.md) | 验证 T-IMG-001 和 quick-reference 在真实任务中的可用性；演示「口语需求 → 15 维度拆解 → 提示词 → 验收清单」完整流程 | ✅ v0.2 已通过轻量验收 |
| **极简智能水杯产品主视觉图提示词案例** | CS-IMG-002 | [cs-img-002-product-hero-image.md](06-case-studies/cs-img-002-product-hero-image.md) | 验证 T-IMG-001、quick-reference 和 T-IMG-002 在产品图 / 商业摄影 / 智能硬件展示图场景下的可用性；与 CS-IMG-001 形成「抽象概念图 + 实体产品图」互补覆盖 | ✅ v0.1 已通过轻量验收 |

**平台适配测试记录**:

| 测试 | 编号 | 文件 | 用途 | 状态 |
|------|------|------|------|------|
| **CS-IMG-001 平台适配测试** | TEST-IMG-002-001 | [cs-img-001-platform-adaptation-test.md](06-case-studies/cs-img-001-platform-adaptation-test.md) | 验证 T-IMG-002 是否能将同一个图像需求改写为 ChatGPT Images / 豆包 / Midjourney / Stable Diffusion / Flux / Hugging Face 六个平台适配版本 | ✅ 已完成 / 12 项检查全部通过 |
| **CS-IMG-002 产品图平台适配测试** | TEST-IMG-002-002 | [cs-img-002-platform-adaptation-test.md](06-case-studies/cs-img-002-platform-adaptation-test.md) | 验证 T-IMG-002 在产品主视觉图 / 商业摄影场景中的可用性；生成 ChatGPT Images、豆包、Midjourney、Stable Diffusion、Flux、Hugging Face 六个平台适配版本 | ✅ 已完成 / 15 项检查全部通过（N/A 1 项） |

> 如果想查看一个完整的图像提示词实战样例，优先参考 CS-IMG-001。
>
> 当已经有通用图像提示词，但需要改写到 ChatGPT Images、豆包、Midjourney、Stable Diffusion、Flux 或 Hugging Face 时，优先使用 T-IMG-002。

**适用工具**：ChatGPT Images、豆包、Midjourney、Stable Diffusion、Flux、Hugging Face 等

**覆盖内容**：
- 图像提示词 15 维度核心结构
- 标准输入区
- 标准输出结构
- 主体描述规范
- 场景描述规范
- 风格描述规范
- 构图和镜头规范
- 光线和色彩规范
- 细节和材质规范
- 负面提示词规范
- 参考图 / 参考资料规范
- 平台适配原则
- L1-L5 图像任务复杂度分级
- 可复制图像提示词生成器模板
- 可复制图像提示词优化模板
- 图像提示词验收清单

> 当需要把口语化图像需求转成高质量图像提示词时，优先查阅 T-IMG-001。
>
> **如果只是日常快速写图像提示词，优先使用 [image-prompt-quick-reference.md](03-image-prompts/image-prompt-quick-reference.md)；如果需要完整规则，再查看 [image-prompt-foundation.md](03-image-prompts/image-prompt-foundation.md)。**
>
> **入口文件**: [03-image-prompts/README.md](03-image-prompts/README.md)

#### Phase 3 收尾说明

Phase 3 图像提示词模块已于 2026-05-25 完成阶段性闭环，共 7 个交付物：

| 交付物 | 文件 | 状态 |
|--------|------|------|
| T-IMG-001 图像提示词基础规范 | `03-image-prompts/image-prompt-foundation.md` | ✅ v0.2 正式版 |
| 图像提示词速查卡 | `03-image-prompts/image-prompt-quick-reference.md` | ✅ v0.2 已通过轻量验收 |
| CS-IMG-001 知识库封面图案例 | `06-case-studies/cs-img-001-prompt-kb-cover-image.md` | ✅ v0.2 已通过轻量验收 |
| T-IMG-002 平台适配模板 | `03-image-prompts/templates/image-platform-adaptation-template.md` | ✅ v0.1 已通过质量验收 |
| TEST-IMG-002-001 封面图平台适配测试 | `06-case-studies/cs-img-001-platform-adaptation-test.md` | ✅ 12/12 检查通过 |
| CS-IMG-002 产品主视觉图案例 | `06-case-studies/cs-img-002-product-hero-image.md` | ✅ v0.1 已通过轻量验收 |
| TEST-IMG-002-002 产品图平台适配测试 | `06-case-studies/cs-img-002-platform-adaptation-test.md` | ✅ 15/15 检查通过 |

Phase 3 已形成「规范 → 速查 → 案例 → 平台适配 → 测试」的完整闭环，三条子闭环（基础图像提示词闭环、平台适配闭环、案例验证闭环）全部成立。后续图像案例和平台专项模板可按需扩展，不再阻塞 Phase 4。

后续可按需扩展：人物/角色图案例、场景概念图案例、社交媒体配图案例、参考图输入案例、图像编辑/局部重绘案例、平台专项模板。

---

### 🎬 04-video-prompts/ — 视频生成提示词

> **状态**: ✅ Phase 4 已完成阶段性闭环（5 个交付物全部完成，四条闭环成立）
>
> **规划工具**: Sora / Runway / Pika / Kling / Luma / 豆包视频
>
> **核心规范**:

| 规范 | 编号 | 文件 | 用途 | 状态 |
|------|------|------|------|------|
| **Prompt-KB 视频提示词基础规范** | T-VIDEO-001 | [video-prompt-foundation.md](04-video-prompts/video-prompt-foundation.md) | 统一视频生成提示词的目标、主体、场景、动作、镜头运动、时间顺序、节奏、风格、构图、光线、色彩、材质细节、首帧末帧、负面提示词和平台适配方式；继承 T-IMG-001 的 15 视觉维度，新增 8 个视频专属维度 | ✅ v0.1 已通过质量验收（A级 / 91/100） |
| **视频提示词速查卡** | T-VIDEO-001 QR | [video-prompt-quick-reference.md](04-video-prompts/video-prompt-quick-reference.md) | T-VIDEO-001 压缩版快速参考；L1-L5 分级速查、20 维度速查表、口语需求转写模板、分镜模板、平台参数速查、验收清单；日常快速使用入口 | ✅ v0.2 已完成验收（98/100 A级） |
| **T-VIDEO-002｜视频提示词平台适配模板** | T-VIDEO-002 | [video-platform-adaptation-template.md](04-video-prompts/templates/video-platform-adaptation-template.md) | 将同一个通用视频提示词改写为 Runway / Pika / Kling / Luma / Sora / 豆包 / 即梦等平台适配版本；保留动作、镜头运动、时间顺序、节奏等视频专属信息，并按平台能力调整表达方式 | ✅ v0.1 已通过质量验收（A级 / 110/110） |

**案例**:

| 案例 | 编号 | 文件 | 用途 | 状态 |
|------|------|------|------|------|
| **智能水壶产品展示视频提示词案例** | CS-VIDEO-001 | [cs-video-001-product-showcase-video.md](06-case-studies/cs-video-001-product-showcase-video.md) | 验证 T-VIDEO-001 基础规范和速查卡 v0.2 在 L4 产品广告/多镜头视频场景下的完整可用性；演示「口语需求 → 20 维度拆解 → 双语提示词 → 动作镜头同步矩阵 → 变体 → 平台适配 → 验收」完整流程；与 CS-IMG-002 形成图像→视频案例继承链 | ✅ v0.2（A级 / 20/20 通过，已通过质量验收） |
| **T-VIDEO-002｜视频提示词平台适配模板** | T-VIDEO-002 | [video-platform-adaptation-template.md](04-video-prompts/templates/video-platform-adaptation-template.md) | 将通用视频提示词改写为多平台适配版本，覆盖平台适配总原则、平台类型分类、Runway / Pika / Kling / Luma / Sora / 豆包 / 即梦 / 其他模型规则、多平台输出模板和适配检查清单 | ✅ v0.1（A级 / 110/110，已通过质量验收） |
| **CS-VIDEO-001 视频平台适配测试** | TEST-VIDEO-002-001 | [cs-video-001-platform-adaptation-test.md](06-case-studies/cs-video-001-platform-adaptation-test.md) | 验证 T-VIDEO-002 在真实产品展示视频案例中的可用性，生成 Runway / Pika / Kling / Luma / Sora / 豆包 / 即梦 / 其他视频生成模型适配版本，并通过 20 项视频平台适配检查 | ✅ v0.1（已完成 / 20/20 通过） |

**T-VIDEO-001 覆盖内容**：
- 视频提示词核心公式（14 要素）
- 20 个视频提示词核心维度表
- 标准输入区（6 字段）
- 标准输出结构（11 项 + 简化规则）
- L1-L5 视频任务复杂度分级
- 主体描述规范（10 类 × 6 要素）
- 动作描述规范（7 要素 + 10 例库）
- 镜头运动规范（12 类型 × 5 字段 + 5 原则）
- 时间顺序 / 分镜规范（3 结构 + 6 原则）
- 节奏与时长规范（6 元素 + 平台时长参考）
- 首帧 / 末帧规范（各 5 要素 + 写作模板）
- 风格 / 光线 / 色彩 / 材质连续性规范
- 负面提示词规范（15 通用 + 3 分类 + 平台兼容性）
- 视频平台适配原则（7 平台 + 7 原则 + 选择指南）
- 口语需求转视频提示词模板
- 分镜视频提示词模板（9 列表格式）
- 视频提示词验收清单（20 项 / 5 组）
- 常见错误（15 项 + 修正）

**T-VIDEO-002 覆盖内容**：
- 标准输入区
- 视频平台适配总原则
- 7 类平台能力类型
- Runway / Pika / Kling / Luma / Sora / 豆包 / 即梦 / 其他视频生成模型适配规则
- 多平台输出模板
- 视频平台适配检查清单
- 常见平台适配错误
- 与 T-VIDEO-001 / 速查卡 / CS-VIDEO-001 的关系

**可复制模板**：
- 口语需求转视频提示词模板（9 输出字段）
- 分镜视频提示词模板（9 列 storyboard 表格）
- 视频提示词验收清单（20 项检查）

**v0.2 候选改进**：
1. 占位符格式对齐 T-CONFIG-005
2. 扩充动作示例库
3. 建立平台参数季度校验机制
4. 创建 CS-VIDEO-001 视频案例文件

> **额外维度**: 动作 / 镜头运动 / 时间顺序 / 节奏 / 转场 / 首帧末帧 / 画面稳定性 / 时长 / 分辨率比例
>
> **复用维度**: 主体 / 场景 / 风格 / 构图 / 光线 / 色彩 / 材质细节 / 负面限制（来自 T-IMG-001）
>
> T-VIDEO-002 用于平台适配；日常生成视频提示词优先使用 video-prompt-quick-reference，需要完整规则时查阅 T-VIDEO-001，需要多平台改写时使用 T-VIDEO-002。
>
> **入口文件**: [04-video-prompts/README.md](04-video-prompts/README.md)

---

### 🤖 05-openclaw-workflows/ — OpenClaw 工作流

> **状态**: ✅ Phase 5 已完成阶段性闭环（3/3 交付物完成，四条闭环成立）
>
> **核心规范**:

| 规范 | 编号 | 文件 | 用途 | 状态 |
|------|------|------|------|------|
| **OpenClaw 多 Agent 工作流基础规范** | T-OPENCLAW-001 | [openclaw-workflow-foundation.md](05-openclaw-workflows/openclaw-workflow-foundation.md) | 系统化组织复杂任务、多步骤任务、知识库维护任务和多 Agent 协作任务；定义工作流核心公式、18 维度、16 种任务类型、L1-L5 复杂度分级、单/多 Agent 判断、8 个角色设计、6 种标准工作流、保护文件规范、失败处理和输出报告 | ✅ v0.1 已通过质量验收（A级 / 120/120） |
| **OpenClaw 工作流速查卡** | T-OPENCLAW-001 QR | [openclaw-workflow-quick-reference.md](05-openclaw-workflows/openclaw-workflow-quick-reference.md) | T-OPENCLAW-001 日常快速使用入口；18 维度速查、16 种任务类型速查、L1-L5 复杂度速查、单/多 Agent 判断、8 角色速查、6 种标准流程、保护文件速查、失败处理速查、输出报告模板、验收清单 | ✅ v0.1 已通过质量验收（A级 / 120/120） |

**T-OPENCLAW-001 覆盖内容**：
- OpenClaw 工作流核心公式（10 环节）
- 18 个工作流核心维度
- 16 种任务类型分类
- L1-L5 复杂度分级
- 单 Agent / 多 Agent 判断规范
- 8 个多 Agent 角色设计
- 创建类 / 验收类 / 小修类 / 导航登记类 / 测试记录类 / 阶段性验收类工作流
- 保护文件与范围控制规范
- 失败与返工处理规范
- 输出报告规范与工作流验收清单

> **与 fundamentals 的关系**: Advanced 技术卡片中已标注各技术的 OpenClaw 适配建议，可作为工作流设计的理论依据
>
> **入口文件**: [05-openclaw-workflows/README.md](05-openclaw-workflows/README.md)

#### Phase 5 OpenClaw 工作流模块阶段性完成

Phase 5 已完成 3 个交付物：

| 交付物 | 文件 | 状态 |
|--------|------|------|
| T-OPENCLAW-001 OpenClaw 多 Agent 工作流基础规范 | `05-openclaw-workflows/openclaw-workflow-foundation.md` | ✅ A级，120/120 |
| OpenClaw 工作流速查卡 | `05-openclaw-workflows/openclaw-workflow-quick-reference.md` | ✅ A级，120/120 |
| CS-OPENCLAW-001 模块产物创建—验收—登记工作流案例 | `06-case-studies/cs-openclaw-001-module-delivery-workflow.md` | ✅ A级，110/110 |

Phase 5 已形成"规范 → 速查 → 案例 → 登记"的基础闭环，后续多 Agent 协作模板、第二个 OpenClaw 工作流案例、复杂失败恢复案例、跨模块重构案例和长上下文资料整理案例可按需扩展，不再阻塞 Prompt-KB 总体验收 / 收尾。

---

## 推荐学习路径

```
┌─────────────────────────────────────────────────────┐
│                  新手路径（推荐）                     │
│                                                     │
│  ① Introduction        → 了解"提示词能做什么"         │
│  ② Basic Prompting     → 学会 Zero-Shot / Few-Shot  │
│  ③ 🟢 CoT              → 掌握思维链（最实用）         │
│  ④ 🟢 Prompt Chaining  → 学会分步拆解复杂任务         │
│  ⑤ 🟡 ReAct            → 理解 Agent 循环模式         │
│                                                     │
│  完成以上 5 步 → 具备处理大多数日常任务的能力          │
└─────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────┐
│                  进阶路径（可选）                     │
│                                                     │
│  ⑥ 🟢 Self-Consistency    → 多数投票提升准确率       │
│  ⑦ 🟢 Generated Knowledge → 外部知识增强推理          │
│  ⑧ 🟡 Tree of Thoughts    → 分支探索复杂决策          │
│  ⑨ 🟡 PAL                  → 代码辅助推理             │
│                                                     │
│  完成以上 9 步 → 掌握 DAIR.AI 全部核心技术            │
└─────────────────────────────────────────────────────┘
```

**按场景速查**:
- 「我有一个简单需求」→ Basic Prompting（Zero-Shot）
- 「效果不好，想优化」→ 加示例 → Basic（Few-Shot）还不够 → CoT
- 「任务很复杂，一步做不完」→ Prompt Chaining
- 「需要调用工具/API」→ ReAct
- 「涉及数学/逻辑推理」→ CoT 或 PAL
- 「需要最高准确率」→ Self-Consistency
- 「模型缺少领域知识」→ Generated Knowledge
- **「我想做一个 XX 计划，但不知道怎么安排」→ T-TEXT-001 模糊需求转计划 Pipeline**（`02-text-prompts/templates/fuzzy-request-to-plan-pipeline.md`）
- **「我想生成图片，但不知道提示词怎么写」→ 日常使用：T-IMG-001 速查卡**（`03-image-prompts/image-prompt-quick-reference.md`）；完整规范：T-IMG-001（`03-image-prompts/image-prompt-foundation.md`）
- **「想看一个完整的图像提示词实战样例（封面图/抽象概念方向）」→ CS-IMG-001 图像案例**（`06-case-studies/cs-img-001-prompt-kb-cover-image.md`）
- **「想看产品图 / 商业摄影 / 智能硬件展示类图像提示词样例」→ CS-IMG-002 产品图案例**（`06-case-studies/cs-img-002-product-hero-image.md`）
- **「已经有图像提示词，想适配到不同平台」→ T-IMG-002 平台适配模板**（`03-image-prompts/templates/image-platform-adaptation-template.md`）
- **「想看平台适配模板的实测效果（封面图方向）」→ TEST-IMG-002-001 平台适配测试**（`06-case-studies/cs-img-001-platform-adaptation-test.md`）
- **「想看平台适配模板的实测效果（产品图方向）」→ TEST-IMG-002-002 产品图平台适配测试**（`06-case-studies/cs-img-002-platform-adaptation-test.md`）
- **「想看视频平台适配模板的实测效果」→ TEST-VIDEO-002-001 视频平台适配测试**（`06-case-studies/cs-video-001-platform-adaptation-test.md`）
- **「我想生成视频，但不知道提示词怎么写」→ 日常使用：T-VIDEO-001 速查卡**（`04-video-prompts/video-prompt-quick-reference.md`）（v0.2，98/100 A级）；完整规范：T-VIDEO-001（`04-video-prompts/video-prompt-foundation.md`）（v0.1，A级 / 91/100）
- **「已有视频提示词，想适配到不同视频平台」→ T-VIDEO-002 平台适配模板**（`04-video-prompts/templates/video-platform-adaptation-template.md`）（v0.1，A级 / 110/110）
- **「想看一个完整的视频提示词实战样例（产品展示/广告方向）」→ CS-VIDEO-001 视频案例**（`06-case-studies/cs-video-001-product-showcase-video.md`）（v0.2，A级 / 20/20 通过）
- **「想让 OpenClaw 执行复杂任务 / 多步骤任务」→ OpenClaw 工作流速查卡（日常使用）**（`05-openclaw-workflows/openclaw-workflow-quick-reference.md`）（v0.1，A级 / 120/120）；完整规范：T-OPENCLAW-001（`05-openclaw-workflows/openclaw-workflow-foundation.md`）
- **「想看 OpenClaw 工作流的实战样例（模块产物交付方向）」→ CS-OPENCLAW-001 工作流案例**（`06-case-studies/cs-openclaw-001-module-delivery-workflow.md`）（v0.1，A级 / 110/110）

---

## v1.0 已知不足

- ~~视频提示词模块尚未建设~~ → **Phase 4 T-VIDEO-001 v0.1 已通过质量验收（A级 / 91/100）**；
- 文本模板数量仍较少（当前仅 T-TEXT-001）；
- 案例库仍可继续扩充（当前已有 CS-001、CS-002、CS-IMG-001、CS-IMG-002、TEST-IMG-002-001、TEST-IMG-002-002、CS-VIDEO-001、TEST-VIDEO-002-001、CS-OPENCLAW-001）。

> 以上不足不阻塞 v1.0 发布，因为 v1.0 的目标是完成底层规范和首个模板闭环。详见 [RELEASE_NOTES_v1.0.md](RELEASE_NOTES_v1.0.md)。

## 下一步路线

| 阶段 | 目标 |
|------|------|
| **Phase 3** | ✅ 已完成阶段性闭环 — 7 个交付物全部完成，三条闭环成立，图像提示词基础能力稳定 |
| **Phase 4** | ✅ 已完成阶段性闭环 — 5 个交付物全部完成，四条闭环成立，后续可按需扩展 |
| **Phase 5** | ✅ 已完成阶段性闭环 — 3/3 交付物完成，四条闭环成立；后续多 Agent 协作模板等可按需扩展 |
| **v1.1 发布** | ✅ 已发布 — 总体验收通过（A级），RELEASE_NOTES_v1.1.md 和 FINAL_ACCEPTANCE_REPORT_v1.1.md 已归档 |

### 后续路线

1. 日常使用 Prompt-KB
2. 根据真实使用反馈小修具体模块
3. 按需扩展多 Agent 协作模板
4. 按需补充第二个视频案例
5. 按需补充参考图 / 首帧 / 末帧案例
6. 按需补充真实生成结果复盘
7. 按需扩展音频 / 字幕 / 口播规范

---

## 版本历史

| 版本 | 日期 | 变更内容 |
|------|------|----------|
| v2.20.0 | 2026-05-28 | **Prompt-KB v1.1 正式发布**：Phase 1-5 全部完成阶段性闭环，RELEASE_NOTES_v1.1.md 和 FINAL_ACCEPTANCE_REPORT_v1.1.md 已归档，项目进入日常使用和按需扩展阶段；当前聚焦更新为"v1.1 已发布 / 进入使用阶段"；下一步路线更新为后续按需扩展；版本历史新增 v2.20.0 |
| v2.19.0 | 2026-05-27 | **Prompt-KB v1.1 发布整理**：创建 RELEASE_NOTES_v1.1.md（覆盖 Phase 1-5 完整内容）；修正 03-image-prompts/README.md 中过时的 Phase 4 状态（v1.8.0→v1.9.0）；README 发布说明链接新增 v1.1；总体验收状态从"🟡 待执行"更新为"✅ 已通过"；当前聚焦更新为"v1.1 正式发布整理"；版本历史新增 v2.19.0 |
| v2.18.0 | 2026-05-27 | **Phase 5 OpenClaw 工作流模块阶段性收尾**：3/3 交付物完成，四条闭环全部成立，Prompt-KB 进入总体验收 / 发布整理阶段；Phase 5 状态从"🔨 进行中"更新为"✅ 已完成阶段性闭环"；当前聚焦更新为"Prompt-KB 总体验收 / 发布整理"；新增 Phase 5 收尾说明表；下一步路线更新；版本历史新增 v2.18.0 |
| v2.17.0 | 2026-05-27 | **登记 CS-OPENCLAW-001 v0.1**：OpenClaw 工作流案例通过质量验收（A级 / 110/110）；06-case-studies 索引新增 CS-OPENCLAW-001；README 按场景速查新增 OpenClaw 案例入口；05-openclaw-workflows/README 新增案例入口；Phase 5 更新为完成基础规范+速查卡+案例闭环；版本历史新增 v2.17.0 |
| v2.16.0 | 2026-05-27 | **登记 OpenClaw 工作流速查卡 v0.1**：速查卡通过质量验收（A级 / 120/120）；README Phase 5 规范表新增速查卡行；QUICKSTART 更新 OpenClaw 入口为速查卡优先；05-openclaw-workflows/README 新增速查卡条目；phase-2-calibration-backlog 更新 Phase 5 已完成两项核心入口；版本历史新增 v2.16.0 |
| v2.15.0 | 2026-05-27 | **登记 T-OPENCLAW-001 v0.1**：OpenClaw 多 Agent 工作流基础规范通过质量验收（A级 / 120/120）；README 新增 Phase 5 规范表和按场景速查入口；QUICKSTART 新增 OpenClaw 工作流入口；05-openclaw-workflows/README 新建；phase-2-calibration-backlog 更新 Phase 5 状态；版本历史新增 v2.15.0 |
| v2.14.0 | 2026-05-27 | **Phase 4 收尾 + Phase 5 启动**：Phase 4 视频提示词模块标记为"已完成阶段性闭环"（5/5 交付物，四条闭环成立）；Phase 5 OpenClaw 多 Agent 工作流模块标记为"进行中"；README / QUICKSTART / 04-video-prompts/README / phase-2-calibration-backlog 同步更新；版本历史新增 v2.14.0 |
| v2.13.0 | 2026-05-27 | **登记 TEST-VIDEO-002-001**：视频平台适配测试记录通过登记；06-case-studies 索引新增 TEST-VIDEO-002-001，04-video-prompts/README 新增视频平台适配测试入口，README 视频模块和 Phase 4 状态同步更新为已完成第一条视频平台适配闭环；版本历史新增 v2.13.0 |
| v2.12.0 | 2026-05-26 | **登记 T-VIDEO-002 v0.1**：视频平台适配模板通过质量验收（A级 / 110/110）；04-video-prompts 入口新增 T-VIDEO-002 行与覆盖内容；Phase 4 更新为已完成基础规范、速查卡、第一个视频案例和视频平台适配模板；下一步路线更新为 TEST-VIDEO-002-001；按场景速查新增视频平台适配入口；版本历史新增 v2.12.0 |
| v2.11.0 | 2026-05-26 | **登记 CS-VIDEO-001 v0.2**：Prompt-KB 第一个视频提示词案例（智能水壶产品展示视频）；A级 / 20/20 验收通过；04-video-prompts 入口新增案例表；06-case-studies 索引新增 CS-VIDEO-001 章节；按场景速查新增视频案例入口；Phase 4 状态更新为含 3 个交付物；案例总数更新为 7 |
| v2.9.0 | 2026-05-26 | **登记 T-VIDEO-001 v0.1**：Phase 4 视频提示词基础规范通过质量验收（A级 / 91/100）；在 04-video-prompts 入口新增 T-VIDEO-001 核心规范表、覆盖内容、可复制模板、v0.2 候选改进；更新"下一步路线"Phase 4 状态；新增视频模块按场景速查入口；更新"已知不足" |
| v2.8.0 | 2026-05-25 | **Phase 3 图像提示词模块阶段性收尾**：7 个交付物完成，Phase 3 标记为「✅ 已完成阶段性闭环」；新增 Phase 3 收尾说明表；Phase 4 视频提示词模块标记为「🔨 进行中」；更新视频模块维度列表（新增复用维度、首帧末帧、时长、分辨率比例）；更新「当前聚焦」「总体进度」「下一步路线」 |
| v2.6.0 | 2026-05-25 | 登记 CS-IMG-002 v0.1 为 Prompt-KB 第二个图像提示词案例（已通过轻量验收）；在 03-image-prompts 案例区新增 CS-IMG-002 行；更新 Phase 3 进度、"当前聚焦"、"下一步路线"、"按场景速查"和"已知不足" |
| v2.5.0 | 2026-05-25 | 登记 TEST-IMG-002-001 为图像平台适配测试记录（12 项检查全部通过）；在 03-image-prompts 入口新增平台适配测试记录表；更新 Phase 3 进度、"当前聚焦"、"下一步路线"、"按场景速查"和"已知不足" |
| v2.4.0 | 2026-05-25 | 登记 T-IMG-002 v0.1 为正式图像平台适配模板（已通过质量验收）；在 03-image-prompts 入口新增 T-IMG-002 行；更新 Phase 3 进度、"当前聚焦"和"下一步路线"；新增"按场景速查"平台适配入口 |
| v2.3.0 | 2026-05-25 | 登记 CS-IMG-001 v0.2 为正式图像案例（已通过轻量验收）；在 03-image-prompts 入口新增案例表和引用；更新 Phase 3 进度和已知不足；更新"按场景速查"图像入口 |
| v2.2.0 | 2026-05-25 | 登记 T-IMG-001 速查卡 v0.2（已通过轻量验收）；在 03-image-prompts 入口新增速查卡行；更新 Phase 3 状态描述；更新"按场景速查"图像入口引用 |
| v2.1.0 | 2026-05-19 | 新增 T-IMG-001 v0.2 正式版登记（Prompt-KB 图像提示词基础规范）；更新 Phase 3 状态为进行中；更新导航和索引 |
| v2.0.0 | 2026-05-19 | **Prompt-KB v1.0 可用版发布**：完成 Phase 1 Prompt Engineering 学习、Phase 2 配置规范层建设（T-CONFIG-001 至 T-CONFIG-006）、T-TEXT-001 稳定模板、CS-001/CS-002 案例验证；创建 RELEASE_NOTES_v1.0.md；更新总体进度表 |
| v1.9.0 | 2026-05-19 | 新增 T-CONFIG-006 v0.1 正式版登记（Prompt-KB 长上下文输入规范）；修正 §18 与 §5.1 输入结构一致性（删除多余"待确认事项"区块）；标记 P1-7 已完成 |
| v1.8.0 | 2026-05-16 | 新增 T-CONFIG-005 v0.1 正式版登记（Prompt-KB 格式描述与占位符规范）；标记 P0-5 已完成 |
| v1.7.0 | 2026-05-16 | 新增 T-CONFIG-004 v0.1 正式版登记（Prompt-KB Few-shot 适用条件判断规范） |
| v1.6.0 | 2026-05-16 | 新增 T-CONFIG-003 v0.2 正式版登记（Prompt-KB 模型类型与提示策略判断规范） |
| v1.5.0 | 2026-05-16 | 新增 T-CONFIG-002 v0.2 正式版登记（Prompt-KB Few-shot 示例规范） |
| v1.4.0 | 2026-05-14 | 新增 T-CONFIG-001 v0.2 正式版登记（Prompt-KB 通用模板结构规范） |
| v1.3.0 | 2026-05-14 | 新增 CS-002 案例验证记录（T-TEXT-001 小红书内容创作计划实测 93.3% A 通过） |
| v1.2.0 | 2026-05-14 | 新增 T-TEXT-001 模糊需求转计划模板（v0.2 已验收）到已完成模块和导航入口 |
| v1.1.0 | 2026-05-14 | Phase 1 中期验收后导航更新：新增进度表、已完成模块详情、各入口链接、学习路径 |
| v1.0.0 | 2026-05-14 | 初始创建，包含目录结构和设计原则 |

---

*本知识库由 KB-Admin 维护，OpenClaw 辅助建立，持续迭代中。当前版本：Prompt-KB v1.1 已发布。*
