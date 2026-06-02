# _config/ — 知识库配置与规范

> **版本**: v1.5.0
> **创建日期**: 2026-05-14
> **维护者**: KB-Admin
> **用途**: 存放 Prompt-KB 的元规范、写作规则和质量标准

---

## 规范索引

### T-CONFIG-001｜Prompt-KB 通用模板结构规范

| 属性 | 内容 |
|------|------|
| **文件** | `prompt-template-style-guide.md` |
| **版本** | v0.2 |
| **状态** | 正式版 |
| **类型** | 模板写作规范 |
| **用途** | 约束和指导后续 Prompt-KB 模板创建 |
| **依据来源** | DAIR.AI + OpenAI + Anthropic 三方校准 |

**适用对象**：
- 文本提示词模板
- OpenClaw 工作流模板
- Prompt Chaining 模板
- 带参考资料输入的模板
- 后续图像 / 视频提示词模板的结构参考

**覆盖内容**：模板元数据 · 适用/不适用场景 · 标准输入区 · 参考资料机制 · 分隔符规范 · Few-shot 示例边界 · Thinking/CoT 使用边界 · 简化版/标准版/进阶版选择 · OpenClaw 执行规范 · 版本记录 · 质量验收清单

**快速跳转**：
- [prompt-template-style-guide.md](prompt-template-style-guide.md)

---

### T-CONFIG-002｜Prompt-KB Few-shot 示例规范

| 属性 | 内容 |
|------|------|
| **文件** | `few-shot-example-guide.md` |
| **版本** | v0.2 |
| **状态** | 正式版 |
| **类型** | 示例写作规范 |
| **用途** | 指导后续 Prompt-KB 模板如何设计 Few-shot 示例 |
| **依据来源** | DAIR.AI + OpenAI + Anthropic 三方校准 + T-CONFIG-001 §8.3 |

**适用对象**：
- 文本提示词模板
- Prompt Chaining 模板
- 带参考资料输入的模板
- 图像 / 视频提示词模板的示例设计（通用原则适用，具体格式由各模块定义）
- OpenClaw 工作流模板的示例设计

**覆盖内容**：是否需要 Few-shot · 示例数量规则 · 三类标准示例（正常/信息不足/边界）· 带参考资料输入示例格式 · 图像/视频示例边界 · 示例污染风险 · 示例验收标准 · 可复制模板（最小骨架 + 完整版）

**快速跳转**：
- [few-shot-example-guide.md](few-shot-example-guide.md)

---

### T-CONFIG-003｜Prompt-KB 模型类型与提示策略判断规范

| 属性 | 内容 |
|------|------|
| **文件** | `model-strategy-selection-guide.md` |
| **版本** | v0.2 |
| **状态** | 正式版 |
| **类型** | 策略判断规范 |
| **用途** | 指导不同任务选择 Zero-Shot、Few-shot、Prompt Chaining、CoT、工具调用、单 Agent / 多 Agent |
| **依据来源** | DAIR.AI + OpenAI + Anthropic 三方校准 + T-CONFIG-001 / T-CONFIG-002 |

**适用对象**：
- 文本提示词模板
- Prompt Chaining 模板
- 带参考资料输入的模板
- OpenClaw 工作流模板
- 多 Agent 协作模板
- 图像 / 视频提示词模块的策略判断

**覆盖内容**：L1-L5 任务复杂度分级 · Zero-Shot/Few-Shot/Prompt Chaining/Thinking·CoT/工具调用/单多 Agent 选择标准 · 7 类模型类型判断 · 图像/视频任务策略边界 · 决策树 · 可复制策略判断提示词 · 常见误判

**快速跳转**：
- [model-strategy-selection-guide.md](model-strategy-selection-guide.md)

---

### T-CONFIG-004｜Prompt-KB Few-shot 适用条件判断规范

| 属性 | 内容 |
|------|------|
| **文件** | `few-shot-usage-decision-guide.md` |
| **版本** | v0.1 |
| **状态** | 正式版 |
| **类型** | Few-shot 启用判断规范 |
| **用途** | 判断模板是否需要 Few-shot，以及何时迁移到案例库 |
| **依据来源** | DAIR.AI + OpenAI + Anthropic 三方校准 + T-CONFIG-002 / T-CONFIG-003 |

**适用对象**：
- 文本提示词模板
- Prompt Chaining 模板
- 带参考资料输入的模板
- OpenClaw 工作流模板
- 多 Agent 协作模板
- 图像 / 视频提示词模板的示例判断

**覆盖内容**：Few-shot 决策总表（16 场景）· 应该使用 Few-shot 的场景 · 不应该使用 Few-shot 的场景 · Zero-Shot / Few-shot / 案例库边界 · 示例数量判断 · Prompt Chaining 中的 Few-shot 判断 · 图像/视频提示词中的 Few-shot 判断 · OpenClaw 工作流中的 Few-shot 判断 · Few-shot 启用决策树 · 可复制判断提示词 · 常见误判

**快速跳转**：
- [few-shot-usage-decision-guide.md](few-shot-usage-decision-guide.md)

---

### T-CONFIG-005｜Prompt-KB 格式描述与占位符规范

| 属性 | 内容 |
|------|------|
| **文件** | `format-and-placeholder-guide.md` |
| **版本** | v0.1 |
| **状态** | 正式版 |
| **类型** | 格式与占位符规范 |
| **用途** | 统一模板中的输入区、输出格式、占位符、JSON / YAML / Markdown / 表格写法 |
| **依据来源** | DAIR.AI + OpenAI + Anthropic 三方校准 + T-CONFIG-001~004 |

**适用对象**：
- 文本提示词模板
- 图像提示词模板
- 视频提示词模板
- Prompt Chaining 模板
- OpenClaw 工作流模板
- 多 Agent 协作模板
- 带参考资料输入的模板
- Few-shot 示例中的输入 / 输出格式

**覆盖内容**：占位符基础规范 · 占位符命名规则 · 标准输入区 · Markdown 输出格式 · 表格输出格式 · JSON 输出格式 · YAML 输出格式 · 图像提示词格式描述 · 视频提示词格式描述 · OpenClaw 工作流格式 · 占位符示例库 · 常见格式错误 · 可复制格式判断提示词

**快速跳转**：
- [format-and-placeholder-guide.md](format-and-placeholder-guide.md)

---

### T-CONFIG-006｜Prompt-KB 长上下文输入规范

| 属性 | 内容 |
|------|------|
| **文件** | `long-context-input-guide.md` |
| **版本** | v0.1 |
| **状态** | 正式版 |
| **类型** | 长上下文输入规范 |
| **用途** | 指导长文档、多来源资料、参考资料、资料冲突、资料不足和 OpenClaw 长流程任务的输入组织 |
| **依据来源** | DAIR.AI + OpenAI（S2 Provide Reference Text / S3 Split Complex Tasks）+ Anthropic（文档靠前问题靠后 / XML 结构化）+ T-CONFIG-001~005 |

**适用对象**：
- 长文档分析
- 多来源资料整理
- 会议纪要总结
- 网页 / 论文 / 报告摘要
- 用户笔记整理
- 带参考资料的写作任务
- OpenClaw 长流程任务
- 多 Agent 协作中的资料交接
- 图像 / 视频模块中的参考资料或参考图说明

**覆盖内容**：长上下文任务判断（8 条标准 + 判断表）· 长上下文输入总结构（7 区块）· 多来源资料组织 · 资料来源标注（10 种类型）· 资料可信度和时效性（14 种资料类型可信度表）· 资料冲突处理（5 种冲突类型 + 模板）· 资料不足处理（4 级风险等级 + 模板）· 长资料摘要规范 · 分块处理规范 · 引用和依据说明规范 · 长上下文输出格式 · OpenClaw 长上下文工作流（6 步）· 多 Agent 协作边界（判断表）· 图像 / 视频参考资料处理 · 可复制输入模板 · 可复制处理提示词 · 常见错误（12 项）

**快速跳转**：
- [long-context-input-guide.md](long-context-input-guide.md)

---

## 规则索引

| 规则文件 | 用途 |
|----------|------|
| [kb-rules.md](kb-rules.md) | 知识库运作规则、模板创建规范、安全操作要求 |

---

*本目录为 Prompt-KB 的配置层，所有规范经 T-CONFIG-001 正式验收后方可登记入本索引。*
