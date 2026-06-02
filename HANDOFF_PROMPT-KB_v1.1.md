# HANDOFF_PROMPT-KB_v1.1｜Prompt-KB v1.1 交接说明

> **版本**: v1.1
> **创建日期**: 2026-06-02
> **用途**: 帮助新使用者或新的 Agent 环境接收 Prompt-KB v1.1 知识库

---

**本文件定位**：
- 本文件是 Prompt-KB v1.1 的交接说明；
- 用于帮助新使用者或新的 Claude Code / OpenClaw / Agent 环境接收知识库；
- 不替代 README.md（知识库总览与模块索引）；
- 不替代 QUICKSTART.md（按需求快速查找入口）；
- 不替代 RELEASE_NOTES_v1.1.md（发布内容与变更记录）；
- 不替代 FINAL_ACCEPTANCE_REPORT_v1.1.md（验收依据与质量证明）；
- 本文档专门说明如何导入、如何阅读、如何使用、如何扩展。

---

## 1. 知识库状态

Prompt-KB v1.1 当前状态：

| 项目 | 状态 |
|------|------|
| 发布状态 | ✅ 已发布 |
| 总体验收 | ✅ 已完成（A 级） |
| 发布说明 | ✅ RELEASE_NOTES_v1.1.md 已创建 |
| 总体验收报告 | ✅ FINAL_ACCEPTANCE_REPORT_v1.1.md 已创建 |
| 隐私脱敏 | ✅ 已完成（P0/P1/P2 全部修复） |
| 对外分享前安全审计 | ✅ 已完成 |
| 当前阶段 | 使用阶段 + 按需扩展阶段 |

**已完成的修复**：
- P0：cs-img-003 个人信息脱敏（人物外貌、年龄、身高、地理定位、口语化原文全部替换为虚构泛化数据）；
- P1：全库真实人名（Ivan）清理、内部项目代号（WorkBuddy / WorkRally）清理、OpenClaw 泛化说明；
- P2：状态一致性修复（"进行中/待验收"残留清理）、孤立文件补登记（cs-img-003、校准文档、_templates）。

---

## 2. 适用对象

### 适合使用本知识库的人

| 类型 | 说明 |
|------|------|
| 想系统管理提示词的人 | 不再散落各处，把提示词变成可维护、可复盘、可扩展的长期资产 |
| 使用 ChatGPT / Claude / Claude Code / OpenClaw / Cursor 等工具的人 | 覆盖单 Agent 和多 Agent 两种执行场景 |
| 需要文本、图像、视频提示词模板的人 | 三大媒介各有基础规范、速查卡、模板和案例 |
| 需要多平台适配提示词的人 | 图像覆盖 ChatGPT Images / 豆包 / Midjourney / Stable Diffusion / Flux / Hugging Face；视频覆盖 Runway / Pika / Kling / Luma / Sora / 豆包 / 即梦 |
| 需要构建 Agent 工作流的人 | 05-openclaw-workflows/ 提供多 Agent 任务编排规范和案例 |
| 想把提示词变成可维护资产的人 | _config/ 提供 6 份元规范，确保新增内容风格统一、质量可控 |

### 不适合使用本知识库的人

| 类型 | 说明 |
|------|------|
| 只想复制几条简单提示词的人 | 本知识库是结构化知识体系，不是提示词收藏夹 |
| 不想阅读结构化文档的人 | 需要理解规范 → 速查卡 → 案例的递进关系 |
| 需要现成业务私有数据的人 | 本知识库已完成脱敏，不含真实业务数据 |
| 想直接获取平台实时参数的人 | 平台参数会变化，本知识库提供适配框架而非实时参数 |

---

## 3. 目录结构概览

| 目录 | 作用 | 新用户优先级 |
|------|------|:---:|
| `_config/` | 知识库元规范层：模板结构、Few-shot 规范、模型策略、格式描述、长上下文输入等 6 份规范 | ⭐⭐ 需要新增内容时阅读 |
| `01-fundamentals/` | 文本提示词基础理论：DAIR.AI 全系列（入门/基础/高级）+ 7 个高级技术独立卡片 + 2 份校准笔记 | ⭐⭐⭐ 学习基础时阅读 |
| `02-text-prompts/` | 文本提示词模板库：T-TEXT-001 模糊需求转计划 Pipeline（v0.4 稳定版） | ⭐⭐⭐⭐ 文本任务首选 |
| `03-image-prompts/` | 图像提示词模块：T-IMG-001 基础规范 + 速查卡 + T-IMG-002 平台适配模板 | ⭐⭐⭐⭐ 图像任务首选 |
| `04-video-prompts/` | 视频提示词模块：T-VIDEO-001 基础规范 + 速查卡 + T-VIDEO-002 平台适配模板 | ⭐⭐⭐⭐ 视频任务首选 |
| `05-openclaw-workflows/` | 多 Agent 工作流模块：T-OPENCLAW-001 基础规范 + 速查卡 + CS-OPENCLAW-001 案例 | ⭐⭐⭐ 复杂任务时阅读 |
| `06-case-studies/` | 案例库：10 个已完成案例（2 文本 + 3 图像 + 2 图像测试 + 1 视频 + 1 视频测试 + 1 工作流） | ⭐⭐⭐ 参考实际用法 |
| `07-learning/` | 学习资源与校准笔记：资源索引、学习计划、校准文档 | ⭐ 了解背景时阅读 |

---

## 4. 新环境接收顺序

新的 Claude Code / OpenClaw / Agent 环境应按以下顺序读取：

| 步骤 | 文件 | 目的 |
|------|------|------|
| 1 | `README.md` | 理解知识库全貌：目标、模块、进度、入口 |
| 2 | `QUICKSTART.md` | 按需求快速定位：30 秒找到需要的文件 |
| 3 | `RELEASE_NOTES_v1.1.md` | 了解 v1.1 发布内容和能力范围 |
| 4 | `FINAL_ACCEPTANCE_REPORT_v1.1.md` | 了解验收结论和质量证明 |
| 5 | `HANDOFF_PROMPT-KB_v1.1.md` | 本文件：理解如何使用和扩展 |
| 6 | `05-openclaw-workflows/openclaw-workflow-quick-reference.md` | 了解多 Agent 工作流速查卡 |
| 7 | 根据任务类型读取对应模块 | 见下一节"模块选择指南" |

**关键原则**：不要一上来全量读取所有文件。应先理解入口和任务类型，再按需深入对应模块。本知识库的设计理念是"按需查阅"，而非"全量记忆"。

---

## 5. 模块选择指南

| 任务类型 | 优先查看文件 | 说明 |
|----------|-------------|------|
| **文本提示词任务** | `02-text-prompts/templates/fuzzy-request-to-plan-pipeline.md` | T-TEXT-001 模糊需求转计划 Pipeline（v0.4），适用于学习计划、健身计划、写作计划、项目计划等 |
| **图像提示词任务（日常）** | `03-image-prompts/image-prompt-quick-reference.md` | T-IMG-001 速查卡，15 维度速查表 + 可复制模板 + 验收清单 |
| **图像提示词任务（完整）** | `03-image-prompts/image-prompt-foundation.md` | T-IMG-001 基础规范，完整规则和深度说明 |
| **视频提示词任务（日常）** | `04-video-prompts/video-prompt-quick-reference.md` | T-VIDEO-001 速查卡，20 维度速查表 + 可复制模板 + 验收清单 |
| **视频提示词任务（完整）** | `04-video-prompts/video-prompt-foundation.md` | T-VIDEO-001 基础规范，完整规则和深度说明 |
| **图像平台适配** | `03-image-prompts/templates/image-platform-adaptation-template.md` | T-IMG-002，将通用图像提示词改写为 ChatGPT Images / 豆包 / Midjourney / SD / Flux / HF 适配版本 |
| **视频平台适配** | `04-video-prompts/templates/video-platform-adaptation-template.md` | T-VIDEO-002，将通用视频提示词改写为 Runway / Pika / Kling / Luma / Sora / 豆包 / 即梦 适配版本 |
| **复杂多步骤任务** | `05-openclaw-workflows/openclaw-workflow-quick-reference.md` | 多 Agent 工作流速查卡，适用于需要拆分、协调、验收的复杂任务 |
| **案例参考** | `06-case-studies/README.md` | 案例索引，10 个案例按类型查找 |
| **知识库维护 / 新增内容** | `_config/README.md` | 6 份元规范索引，新增模板/案例前必读 |
| **发布说明** | `RELEASE_NOTES_v1.1.md` | v1.1 完整发布内容 |
| **验收依据** | `FINAL_ACCEPTANCE_REPORT_v1.1.md` | Phase 1-5 验收结论和质量证明 |
| **提示词基础学习** | `01-fundamentals/dair-ai-introduction.md` | DAIR.AI 入门，从零开始理解 Prompt Engineering |

---

## 6. 新 Agent 接收提示词

将以下提示词复制给新的 Claude Code / OpenClaw / Agent 环境，用于完成知识库接收：

```
你现在接收了一个名为 Prompt-KB v1.1 的提示词知识库。这是一个已发布、已验收、已完成隐私脱敏的知识库系统。

请你按以下步骤完成接收：

第一步：不要修改任何文件。先只读。

第二步：按顺序读取以下入口文件，每个文件读完后给出一句话总结：
1. README.md → 总结知识库目标和模块结构
2. QUICKSTART.md → 总结按需求查找的入口逻辑
3. RELEASE_NOTES_v1.1.md → 总结 v1.1 发布内容
4. FINAL_ACCEPTANCE_REPORT_v1.1.md → 总结验收结论
5. HANDOFF_PROMPT-KB_v1.1.md → 总结使用和扩展规则

第三步：读取完入口文件后，输出一份结构化摘要，包含：
- 知识库包含哪些模块
- 每个模块的核心文件是什么
- 哪些文件是只读的（不应随意修改）
- 遇到不同任务时应该查哪个模块

第四步：确认你已理解以下规则：
- 遇到任务先判断属于哪个模块（文本/图像/视频/工作流）
- 只读文件包括：RELEASE_NOTES、FINAL_ACCEPTANCE_REPORT、T-CONFIG 系列、已验收的规范和案例
- 新增内容需遵循：创建 → 验收 → 小修 → 登记 → 下一步
- 不要全量读取所有文件，按需查阅

第五步：确认你已准备好基于 Prompt-KB v1.1 处理真实任务。
```

---

## 7. 使用模式提示词

Agent 完成接收后，将以下提示词用于日常任务执行：

```
你现在基于 Prompt-KB v1.1 工作。遇到任何提示词相关任务，请按以下流程处理：

1. 判断任务类型：文本提示词 / 图像提示词 / 视频提示词 / 多 Agent 工作流 / 知识库维护
2. 判断复杂度：简单任务（直接用速查卡）/ 中等任务（参考规范 + 案例）/ 复杂任务（多步骤编排）
3. 判断执行方式：单 Agent 顺序执行 / 多 Agent 协作
4. 明确参考文件：列出本次任务需要参考的规范、速查卡、模板、案例
5. 给出执行方案：说明将按什么步骤完成任务
6. 如需生成内容：直接输出可复制的提示词或结果
7. 如需修改知识库：先声明修改范围和保护文件清单，获得确认后再执行

知识库维护规则：
- 新增任何内容都遵循：创建 → 验收 → 小修 → 轻量复核 → 登记导航 → 更新状态 → 给出下一步建议
- 只读文件：RELEASE_NOTES_v1.1.md、FINAL_ACCEPTANCE_REPORT_v1.1.md、T-CONFIG 系列、已验收规范、已验收案例、已验收速查卡
- 修改前声明范围，修改后更新索引
```

---

## 8. 只读文件与保护规则

### 默认只读文件

以下文件在正常使用中不应随意修改，只有在明确执行"小修任务"时才修改目标文件：

| 类别 | 文件 | 说明 |
|------|------|------|
| 发布记录 | `RELEASE_NOTES_v1.1.md` | 发布内容快照，修改会破坏发布记录完整性 |
| 验收报告 | `FINAL_ACCEPTANCE_REPORT_v1.1.md` | 验收结论快照，修改会破坏质量证明 |
| 元规范 | `_config/prompt-template-style-guide.md`（T-CONFIG-001） | 模板结构标准 |
| 元规范 | `_config/few-shot-example-guide.md`（T-CONFIG-002） | Few-shot 示例规范 |
| 元规范 | `_config/model-strategy-selection-guide.md`（T-CONFIG-003） | 模型策略判断规范 |
| 元规范 | `_config/few-shot-usage-decision-guide.md`（T-CONFIG-004） | Few-shot 适用条件规范 |
| 元规范 | `_config/format-and-placeholder-guide.md`（T-CONFIG-005） | 格式描述与占位符规范 |
| 元规范 | `_config/long-context-input-guide.md`（T-CONFIG-006） | 长上下文输入规范 |
| 文本规范 | `02-text-prompts/templates/fuzzy-request-to-plan-pipeline.md`（T-TEXT-001） | 已验收的文本模板 |
| 图像规范 | `03-image-prompts/image-prompt-foundation.md`（T-IMG-001） | 已验收的图像规范 |
| 图像速查 | `03-image-prompts/image-prompt-quick-reference.md` | 已验收的图像速查卡 |
| 图像适配 | `03-image-prompts/templates/image-platform-adaptation-template.md`（T-IMG-002） | 已验收的图像平台适配模板 |
| 视频规范 | `04-video-prompts/video-prompt-foundation.md`（T-VIDEO-001） | 已验收的视频规范 |
| 视频速查 | `04-video-prompts/video-prompt-quick-reference.md` | 已验收的视频速查卡 |
| 视频适配 | `04-video-prompts/templates/video-platform-adaptation-template.md`（T-VIDEO-002） | 已验收的视频平台适配模板 |
| 工作流规范 | `05-openclaw-workflows/openclaw-workflow-foundation.md`（T-OPENCLAW-001） | 已验收的工作流规范 |
| 工作流速查 | `05-openclaw-workflows/openclaw-workflow-quick-reference.md` | 已验收的工作流速查卡 |
| 已验收案例 | `06-case-studies/` 下状态为"已验收"或"已通过"的案例文件 | 已验收的案例内容 |

### 保护规则

| 场景 | 规则 |
|------|------|
| 验收任务 | 不应修改任何文件，只做检查和评分 |
| 登记任务 | 只修改 README 索引和状态字段，不修改规范/案例正文 |
| 小修任务 | 只修改明确声明的目标文件，保护其他文件不受影响 |
| 新增任务 | 创建新文件，不修改已有文件 |

---

## 9. 新增内容流程

新增任何内容（新模板、新案例、新规范）都应遵循以下流程：

```
创建 → 验收 → 小修 → 轻量复核 → 登记导航 → 更新状态 → 下一步建议
```

| 步骤 | 说明 | 产出 |
|------|------|------|
| 1. 创建 | 按对应模板和规范创建新文件 | 新的 .md 文件 |
| 2. 验收 | 按对应验收清单逐项检查 | 验收结果（通过/待修改） |
| 3. 小修 | 如验收发现问题，修复后重新验收 | 修复后的文件 |
| 4. 轻量复核 | 检查文件头、版本号、关联引用是否正确 | 确认无误 |
| 5. 登记导航 | 在对应 README 中添加索引条目 | README 更新 |
| 6. 更新状态 | 更新文件状态标记和 README 状态 | 状态同步 |
| 7. 下一步建议 | 给出后续可以做什么 | 行动建议 |

**命名规范**：
- 模板/规范：`T-{模块}-{编号}`（如 T-IMG-001、T-VIDEO-002）
- 案例：`CS-{模块}-{编号}` 或 `cs-{模块}-{编号}-{描述}.md`
- 测试：`TEST-{模块}-{编号}-{序号}`

---

## 10. 打包与迁移建议

### 推荐压缩包名称

```
prompt-kb-v1.1-release.zip
```

### 推荐包含内容

```
prompt-kb/
├── README.md
├── QUICKSTART.md
├── RELEASE_NOTES_v1.0.md
├── RELEASE_NOTES_v1.1.md
├── FINAL_ACCEPTANCE_REPORT_v1.1.md
├── HANDOFF_PROMPT-KB_v1.1.md          ← 本文件
├── _config/
├── 01-fundamentals/
├── 02-text-prompts/
├── 03-image-prompts/
├── 04-video-prompts/
├── 05-openclaw-workflows/
├── 06-case-studies/
└── 07-learning/
```

### 迁移注意事项

- 不要只复制单个模板文件，应保留完整目录结构；
- 不要删除 `_config/` 目录，它是新增内容的质量保障层；
- 不要删除 `06-case-studies/`，案例是规范的实际验证；
- 不要删除 `07-learning/`，校准笔记支撑了 T-CONFIG 系列的制定依据；
- 迁移后建议先按本文件第 4 节顺序读取入口文件，再开始使用。

---

## 11. 对外分享前检查清单

分享前请逐项确认：

- [ ] 是否已完成 P0 隐私脱敏（cs-img-003 个人信息已替换为虚构数据）
- [ ] 是否已清理真实人名（Ivan 已全库替换为 KB-Admin 或维护者）
- [ ] 是否已清理内部项目代号（WorkBuddy / WorkRally 已清理，OpenClaw 已添加泛化说明）
- [ ] 是否无 API key / token / secret
- [ ] 是否无本地路径（C:\、/Users/、/home/ 等）
- [ ] 是否无精确个人地理定位
- [ ] 是否无未脱敏真实案例
- [ ] 是否 README / QUICKSTART 状态一致
- [ ] 是否 RELEASE_NOTES_v1.1.md 存在
- [ ] 是否 FINAL_ACCEPTANCE_REPORT_v1.1.md 存在
- [ ] 是否 HANDOFF_PROMPT-KB_v1.1.md 存在
- [ ] 是否建议在分享前重新审计一次

---

## 12. GitHub 分享建议

如果计划发布到 GitHub，建议补充以下内容（非 v1.1 必需项，但有助于外部用户理解和获得 star）：

| 补充项 | 说明 |
|--------|------|
| `LICENSE` | 推荐 MIT 或 CC-BY-4.0，明确使用权限 |
| `CONTRIBUTING.md` | 说明如何贡献新模板、新案例、新规范 |
| `SECURITY.md` | 说明安全问题反馈方式 |
| 英文摘要 | 在 README 顶部增加英文简介，扩大受众 |
| 5 分钟快速开始 | 基于 QUICKSTART.md 精简为一页 GitHub README |
| 示例 demo | 提供 1-2 个可直接运行的示例（如 T-TEXT-001 的完整输入输出） |
| GitHub 项目描述 | 简洁说明 Prompt-KB 是什么、覆盖什么、适合谁 |
| Topics 标签 | `prompt-engineering`、`ai`、`llm`、`image-generation`、`video-generation`、`multi-agent` |

---

## 13. 后续按需扩展方向

以下方向可根据实际需要按需扩展，不需要一次性全部完成：

| 方向 | 说明 | 优先级 |
|------|------|--------|
| 多 Agent 协作模板 | 第二个 OpenClaw 工作流案例，验证更复杂的多 Agent 协作场景 | ⭐⭐⭐ |
| 第二个视频案例 | 扩展视频提示词案例覆盖范围（如广告视频、教程视频） | ⭐⭐⭐ |
| 真实生成结果复盘 | 将实际生成的图像/视频结果回填到案例中，形成"提示词 → 生成结果 → 复盘"闭环 | ⭐⭐⭐ |
| 参考图 / 首帧 / 末帧案例 | 补充视频提示词中参考图、首帧、末帧控制的实战案例 | ⭐⭐ |
| 音频 / 字幕 / 口播规范 | 扩展视频模块到包含音频和字幕的完整视频制作流程 | ⭐⭐ |
| 跨模块重构案例 | 验证从文本需求到图像到视频的端到端工作流 | ⭐⭐ |
| 自动化任务追踪 | 通过 OpenClaw 实现知识库任务的自动追踪和状态更新 | ⭐ |
| GitHub 包装优化 | LICENSE、CONTRIBUTING、英文摘要、5 分钟快速开始 | ⭐ |

---

## 14. 版本记录

| 版本 | 日期 | 说明 |
|------|------|------|
| v1.1 | 2026-06-02 | 创建 Prompt-KB v1.1 交接说明。用于对外分享、迁移到新 Claude Code / OpenClaw 环境、指导新 Agent 接收、使用和扩展知识库。覆盖：知识库状态、适用对象、目录结构、接收顺序、模块选择指南、Agent 提示词、只读保护规则、新增内容流程、打包迁移建议、分享前检查清单、GitHub 建议、扩展方向。 |
