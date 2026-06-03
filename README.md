# Prompt Engineering 知识库 (Prompt-KB)

> **项目版本**: Prompt-KB v1.1
> **当前状态**: 已发布 / 可日常使用
> **README 修订号**: v2.20.0
> **创建日期**: 2026-05-14
> **最近更新**: 2026-05-28
> **维护者**: KB-Admin
> **用途**: AI 提示词学习、复用、复盘的长期知识积累系统

---

## 知识库目标

构建一个**以 DAIR.AI Prompt Engineering Guide 为主线**的提示词知识库，
覆盖文本/图像/视频三大媒介，支持单 Agent 和多 Agent (OpenClaw) 执行场景，
实现「学→练→复用→复盘」的闭环。

> **关于 OpenClaw**：OpenClaw 在本知识库中指代多 Agent 工作流执行环境，
> 可迁移理解为 Claude Code、OpenClaw 或其他 Agent 工作流工具。
> 本知识库的工作流规范和案例不绑定特定平台，可按需迁移到任意支持多步骤任务编排的 Agent 环境。

**当前聚焦**: Prompt-KB v1.1 已发布 / 进入使用阶段

---

## 5-Minute Quick Start

如果你是第一次接触 Prompt-KB，按以下顺序阅读：

1. **README.md**（本文件）— 了解知识库全貌
2. **[QUICKSTART.md](QUICKSTART.md)** — 按需求快速定位文件
3. **[RELEASE_NOTES_v1.1.md](RELEASE_NOTES_v1.1.md)** — 了解 v1.1 发布内容
4. **[FINAL_ACCEPTANCE_REPORT_v1.1.md](FINAL_ACCEPTANCE_REPORT_v1.1.md)** — 了解验收结论
5. **[HANDOFF_PROMPT-KB_v1.1.md](HANDOFF_PROMPT-KB_v1.1.md)** — 交接说明，用于迁移到新环境

---

## 总体进度

| 阶段 | 模块 | 状态 | 说明 |
|------|------|------|------|
| Phase 1 | Prompt Engineering 基础学习 | ✅ 已完成 | DAIR.AI / OpenAI / Anthropic 学习与校准 |
| Phase 2 | 配置规范层建设 | ✅ 已完成 | T-CONFIG-001 至 T-CONFIG-006 全部完成 |
| Phase 3 | 图像提示词模块 | ✅ 已完成阶段性闭环 | 7 个交付物；五层闭环；2 个平台适配测试通过 |
| Phase 4 | 视频提示词模块 | ✅ 已完成阶段性闭环 | 5 个交付物（A级）；四条子闭环成立 |
| Phase 5 | OpenClaw 多 Agent 工作流 | ✅ 已完成阶段性闭环 | 3/3 交付物（A级）；20/20 能力项覆盖 |

> **发布说明**: [RELEASE_NOTES_v1.0.md](RELEASE_NOTES_v1.0.md) · [RELEASE_NOTES_v1.1.md](RELEASE_NOTES_v1.1.md)
>
> **验收报告**: [FINAL_ACCEPTANCE_REPORT_v1.1.md](FINAL_ACCEPTANCE_REPORT_v1.1.md)
>
> **交接说明**: [HANDOFF_PROMPT-KB_v1.1.md](HANDOFF_PROMPT-KB_v1.1.md)

---

## What is Included

本知识库包含以下模块：

| 模块 | 目录 | 核心交付物 | 状态 |
|------|------|----------|------|
| 文本提示词基础 | `01-fundamentals/` | DAIR.AI 全系列 + 7 个高级技术卡片 | ✅ 已完成 |
| 文本提示词模板 | `02-text-prompts/` | T-TEXT-001 模糊需求转计划 Pipeline | ✅ v0.4 已验收 |
| 知识库配置规范 | `_config/` | T-CONFIG-001 至 T-CONFIG-006 | ✅ 全部正式版 |
| 图像提示词模块 | `03-image-prompts/` | T-IMG-001 + 速查卡 + T-IMG-002 + 2 案例 + 2 测试 | ✅ 已完成阶段性闭环 |
| 视频提示词模块 | `04-video-prompts/` | T-VIDEO-001 + 速查卡 + T-VIDEO-002 + 1 案例 + 1 测试 | ✅ 已完成阶段性闭环 |
| OpenClaw 工作流 | `05-openclaw-workflows/` | T-OPENCLAW-001 + 速查卡 + 1 案例 | ✅ 已完成阶段性闭环 |
| 案例库 | `06-case-studies/` | 10 个已完成案例 / 测试记录 | ✅ 已登记 |
| 学习资源 | `07-learning/` | 资源索引 + 学习计划 + 校准文档 | ✅ 已完成 |

---

## Repository Structure

```
prompt-kb/
├── README.md                          # 本文件：知识库总览
├── QUICKSTART.md                      # 快速启动指南
├── RELEASE_NOTES_v1.0.md              # v1.0 发布说明
├── RELEASE_NOTES_v1.1.md              # v1.1 发布说明
├── FINAL_ACCEPTANCE_REPORT_v1.1.md    # v1.1 验收报告
├── HANDOFF_PROMPT-KB_v1.1.md          # 交接说明
│
├── _config/                           # 知识库配置与规范（6 份元规范）
│   ├── README.md
│   ├── prompt-template-style-guide.md       # T-CONFIG-001
│   ├── few-shot-example-guide.md            # T-CONFIG-002
│   ├── model-strategy-selection-guide.md    # T-CONFIG-003
│   ├── few-shot-usage-decision-guide.md     # T-CONFIG-004
│   ├── format-and-placeholder-guide.md      # T-CONFIG-005
│   ├── long-context-input-guide.md          # T-CONFIG-006
│   └── resource-processing.md
│
├── 01-fundamentals/                   # 文本提示词基础
│   ├── README.md
│   ├── dair-ai-introduction.md
│   ├── dair-ai-basic-prompting.md
│   ├── dair-ai-advanced-prompting.md
│   ├── openai-prompt-guidance-calibration.md
│   ├── anthropic-structured-prompting-calibration.md
│   ├── advanced-techniques/           # 7 个高级技术卡片
│   └── _templates/
│
├── 02-text-prompts/                   # 文本提示词模板
│   ├── README.md
│   └── templates/
│       └── fuzzy-request-to-plan-pipeline.md  # T-TEXT-001
│
├── 03-image-prompts/                  # 图像提示词模块
│   ├── README.md
│   ├── image-prompt-foundation.md           # T-IMG-001
│   ├── image-prompt-quick-reference.md      # T-IMG-001 速查卡
│   ├── templates/
│   │   └── image-platform-adaptation-template.md  # T-IMG-002
│   └── _templates/
│
├── 04-video-prompts/                  # 视频提示词模块
│   ├── README.md
│   ├── video-prompt-foundation.md           # T-VIDEO-001
│   ├── video-prompt-quick-reference.md      # T-VIDEO-001 速查卡
│   ├── templates/
│   │   └── video-platform-adaptation-template.md  # T-VIDEO-002
│   └── _templates/
│
├── 05-openclaw-workflows/             # OpenClaw 工作流模块
│   ├── README.md
│   ├── openclaw-workflow-foundation.md      # T-OPENCLAW-001
│   └── openclaw-workflow-quick-reference.md # T-OPENCLAW-001 速查卡
│
├── 06-case-studies/                   # 案例库（10 个）
│   ├── README.md
│   ├── cs-img-001-prompt-kb-cover-image.md
│   ├── cs-img-002-product-hero-image.md
│   ├── cs-img-003-fishing-gathering.md
│   ├── cs-video-001-product-showcase-video.md
│   ├── cs-openclaw-001-module-delivery-workflow.md
│   ├── cs-img-001-platform-adaptation-test.md
│   ├── cs-img-002-platform-adaptation-test.md
│   ├── cs-video-001-platform-adaptation-test.md
│   ├── oral-request-to-learning-plan.md
│   └── t-text-001-xiaohongshu-content-plan-test.md
│
└── 07-learning/                       # 学习资源与校准笔记
    ├── README.md
    ├── _plans/
    └── _resources/
```

---

## Current Status

| 项目 | 状态 |
|------|------|
| 发布状态 | ✅ Prompt-KB v1.1 已发布 |
| 总体验收 | ✅ A 级通过 |
| 隐私脱敏 | ✅ 已完成 |
| 当前阶段 | 使用阶段 + 按需扩展 |

---

## Core Standards

### 文本提示词规范

| 编号 | 名称 | 文件 | 状态 |
|------|------|------|------|
| T-TEXT-001 | 模糊需求转计划 Pipeline | `02-text-prompts/templates/fuzzy-request-to-plan-pipeline.md` | ✅ v0.4 |

### 图像提示词规范

| 编号 | 名称 | 文件 | 状态 |
|------|------|------|------|
| T-IMG-001 | 图像提示词基础规范 | `03-image-prompts/image-prompt-foundation.md` | ✅ v0.2 |
| T-IMG-001 QR | 图像提示词速查卡 | `03-image-prompts/image-prompt-quick-reference.md` | ✅ v0.2 |
| T-IMG-002 | 图像平台适配模板 | `03-image-prompts/templates/image-platform-adaptation-template.md` | ✅ v0.1 |

### 视频提示词规范

| 编号 | 名称 | 文件 | 状态 |
|------|------|------|------|
| T-VIDEO-001 | 视频提示词基础规范 | `04-video-prompts/video-prompt-foundation.md` | ✅ v0.1（A级） |
| T-VIDEO-001 QR | 视频提示词速查卡 | `04-video-prompts/video-prompt-quick-reference.md` | ✅ v0.2（A级） |
| T-VIDEO-002 | 视频平台适配模板 | `04-video-prompts/templates/video-platform-adaptation-template.md` | ✅ v0.1（A级） |

### OpenClaw 工作流规范

| 编号 | 名称 | 文件 | 状态 |
|------|------|------|------|
| T-OPENCLAW-001 | 多 Agent 工作流基础规范 | `05-openclaw-workflows/openclaw-workflow-foundation.md` | ✅ v0.1（A级） |
| T-OPENCLAW-001 QR | 工作流速查卡 | `05-openclaw-workflows/openclaw-workflow-quick-reference.md` | ✅ v0.1（A级） |

### 配置规范（_config/）

| 编号 | 名称 | 文件 | 状态 |
|------|------|------|------|
| T-CONFIG-001 | 通用模板结构规范 | `_config/prompt-template-style-guide.md` | ✅ v0.2 |
| T-CONFIG-002 | Few-shot 示例规范 | `_config/few-shot-example-guide.md` | ✅ v0.2 |
| T-CONFIG-003 | 模型策略判断规范 | `_config/model-strategy-selection-guide.md` | ✅ v0.2 |
| T-CONFIG-004 | Few-shot 适用条件规范 | `_config/few-shot-usage-decision-guide.md` | ✅ v0.1 |
| T-CONFIG-005 | 格式描述与占位符规范 | `_config/format-and-placeholder-guide.md` | ✅ v0.1 |
| T-CONFIG-006 | 长上下文输入规范 | `_config/long-context-input-guide.md` | ✅ v0.1 |

---

## Case Studies and Tests

### 文本案例

| 编号 | 名称 | 文件 | 场景 | 状态 |
|------|------|------|------|------|
| CS-001 | 学习计划原型 | `06-case-studies/oral-request-to-learning-plan.md` | 学习计划 | 来源案例 |
| CS-002 | 小红书内容计划 | `06-case-studies/t-text-001-xiaohongshu-content-plan-test.md` | 内容创作 | ✅ 93.3% A级 |

### 图像案例与测试

| 编号 | 名称 | 文件 | 状态 |
|------|------|------|------|
| CS-IMG-001 | 知识库封面图 | `06-case-studies/cs-img-001-prompt-kb-cover-image.md` | ✅ v0.2 |
| CS-IMG-002 | 产品主视觉图 | `06-case-studies/cs-img-002-product-hero-image.md` | ✅ v0.1 |
| CS-IMG-003 | 多人物户外场景图 | `06-case-studies/cs-img-003-fishing-gathering.md` | ✅ 已脱敏 |
| TEST-IMG-002-001 | CS-IMG-001 平台适配测试 | `06-case-studies/cs-img-001-platform-adaptation-test.md` | ✅ 12/12 |
| TEST-IMG-002-002 | CS-IMG-002 平台适配测试 | `06-case-studies/cs-img-002-platform-adaptation-test.md` | ✅ 15/15 |

### 视频案例与测试

| 编号 | 名称 | 文件 | 状态 |
|------|------|------|------|
| CS-VIDEO-001 | 产品展示视频 | `06-case-studies/cs-video-001-product-showcase-video.md` | ✅ A级 20/20 |
| TEST-VIDEO-002-001 | 视频平台适配测试 | `06-case-studies/cs-video-001-platform-adaptation-test.md` | ✅ 20/20 |

### 工作流案例

| 编号 | 名称 | 文件 | 状态 |
|------|------|------|------|
| CS-OPENCLAW-001 | 模块产物交付工作流 | `06-case-studies/cs-openclaw-001-module-delivery-workflow.md` | ✅ A级 110/110 |

---

## Release and Acceptance

| 文档 | 说明 |
|------|------|
| [RELEASE_NOTES_v1.0.md](RELEASE_NOTES_v1.0.md) | v1.0 基础可用版发布说明 |
| [RELEASE_NOTES_v1.1.md](RELEASE_NOTES_v1.1.md) | v1.1 完整能力扩展版发布说明 |
| [FINAL_ACCEPTANCE_REPORT_v1.1.md](FINAL_ACCEPTANCE_REPORT_v1.1.md) | v1.1 总体验收报告（A 级通过） |
| [HANDOFF_PROMPT-KB_v1.1.md](HANDOFF_PROMPT-KB_v1.1.md) | 交接说明，用于迁移到新 Agent 环境 |

---

## 按场景速查

### 文本提示词

- 「想做一个 XX 计划」→ [T-TEXT-001](02-text-prompts/templates/fuzzy-request-to-plan-pipeline.md)
- 「从零开始学提示词」→ [Introduction](01-fundamentals/dair-ai-introduction.md)
- 「学会 Zero-Shot / Few-Shot」→ [Basic Prompting](01-fundamentals/dair-ai-basic-prompting.md)
- 「学习高级技术」→ [Advanced Prompting](01-fundamentals/dair-ai-advanced-prompting.md)

### 图像提示词

- 「想生成图片」→ 日常：[T-IMG-001 速查卡](03-image-prompts/image-prompt-quick-reference.md)；完整：[T-IMG-001](03-image-prompts/image-prompt-foundation.md)
- 「想看图像实战样例」→ [CS-IMG-001](06-case-studies/cs-img-001-prompt-kb-cover-image.md)（封面图）
- 「想看产品图样例」→ [CS-IMG-002](06-case-studies/cs-img-002-product-hero-image.md)（产品图）
- 「想看多人物场景样例」→ [CS-IMG-003](06-case-studies/cs-img-003-fishing-gathering.md)（户外场景）
- 「想适配不同图像平台」→ [T-IMG-002](03-image-prompts/templates/image-platform-adaptation-template.md)

### 视频提示词

- 「想生成视频」→ 日常：[T-VIDEO-001 速查卡](04-video-prompts/video-prompt-quick-reference.md)；完整：[T-VIDEO-001](04-video-prompts/video-prompt-foundation.md)
- 「想看视频实战样例」→ [CS-VIDEO-001](06-case-studies/cs-video-001-product-showcase-video.md)
- 「想适配不同视频平台」→ [T-VIDEO-002](04-video-prompts/templates/video-platform-adaptation-template.md)

### OpenClaw 工作流

- 「想执行复杂多步骤任务」→ 日常：[工作流速查卡](05-openclaw-workflows/openclaw-workflow-quick-reference.md)；完整：[T-OPENCLAW-001](05-openclaw-workflows/openclaw-workflow-foundation.md)
- 「想看工作流实战样例」→ [CS-OPENCLAW-001](06-case-studies/cs-openclaw-001-module-delivery-workflow.md)

---

## 推荐学习路径

```
新手路径（推荐）：
  ① Introduction        → 了解"提示词能做什么"
  ② Basic Prompting     → 学会 Zero-Shot / Few-Shot
  ③ CoT                 → 掌握思维链（最实用）
  ④ Prompt Chaining     → 学会分步拆解复杂任务
  ⑤ ReAct               → 理解 Agent 循环模式

进阶路径（可选）：
  ⑥ Self-Consistency    → 多数投票提升准确率
  ⑦ Generated Knowledge → 外部知识增强推理
  ⑧ Tree of Thoughts    → 分支探索复杂决策
  ⑨ PAL                 → 代码辅助推理
```

---

## Roadmap

| 阶段 | 目标 | 状态 |
|------|------|------|
| Phase 3 | 图像提示词模块 | ✅ 已完成阶段性闭环 |
| Phase 4 | 视频提示词模块 | ✅ 已完成阶段性闭环 |
| Phase 5 | OpenClaw 工作流 | ✅ 已完成阶段性闭环 |
| v1.1 发布 | 总体验收与发布 | ✅ 已发布 |

### 后续按需扩展

1. 日常使用 Prompt-KB
2. 根据真实使用反馈小修具体模块
3. 按需扩展多 Agent 协作模板
4. 按需补充第二个视频案例
5. 按需补充参考图 / 首帧 / 末帧案例
6. 按需补充真实生成结果复盘
7. 按需扩展音频 / 字幕 / 口播规范

---

---

## License

**License**: MIT

See [LICENSE](LICENSE) for details.

## README Revision History

> 本节记录 README 与知识库索引文件的修订历史；Prompt-KB 的对外发布版本以 [RELEASE_NOTES_v1.1.md](RELEASE_NOTES_v1.1.md) 和 GitHub Release `v1.1` 为准。

| 版本 | 日期 | 变更内容 |
|------|------|----------|
| v2.20.0 | 2026-05-28 | v1.1 正式发布；Phase 1-5 全部完成；验收报告归档 |
| v2.19.0 | 2026-05-27 | v1.1 发布整理；创建 RELEASE_NOTES_v1.1.md |
| v2.18.0 | 2026-05-27 | Phase 5 OpenClaw 工作流模块收尾 |
| v2.17.0 | 2026-05-27 | 登记 CS-OPENCLAW-001 v0.1（A级 110/110） |
| v2.16.0 | 2026-05-27 | 登记 OpenClaw 工作流速查卡 v0.1（A级 120/120） |
| v2.15.0 | 2026-05-27 | 登记 T-OPENCLAW-001 v0.1（A级 120/120） |
| v2.14.0 | 2026-05-27 | Phase 4 收尾 + Phase 5 启动 |
| v2.13.0 | 2026-05-27 | 登记 TEST-VIDEO-002-001 视频平台适配测试 |
| v2.12.0 | 2026-05-26 | 登记 T-VIDEO-002 v0.1（A级 110/110） |
| v2.11.0 | 2026-05-26 | 登记 CS-VIDEO-001 v0.2（A级 20/20） |
| v2.9.0 | 2026-05-26 | 登记 T-VIDEO-001 v0.1（A级 91/100） |
| v2.8.0 | 2026-05-25 | Phase 3 图像提示词模块收尾 |
| v2.6.0 | 2026-05-25 | 登记 CS-IMG-002 v0.1 产品图案例 |
| v2.5.0 | 2026-05-25 | 登记 TEST-IMG-002-001 平台适配测试 |
| v2.4.0 | 2026-05-25 | 登记 T-IMG-002 v0.1 平台适配模板 |
| v2.3.0 | 2026-05-25 | 登记 CS-IMG-001 v0.2 封面图案例 |
| v2.2.0 | 2026-05-25 | 登记 T-IMG-001 速查卡 v0.2 |
| v2.1.0 | 2026-05-19 | 登记 T-IMG-001 v0.2 图像基础规范 |
| v2.0.0 | 2026-05-19 | v1.0 可用版发布 |
| v1.9.0 | 2026-05-19 | 登记 T-CONFIG-006 长上下文输入规范 |
| v1.8.0 | 2026-05-16 | 登记 T-CONFIG-005 格式描述规范 |
| v1.7.0 | 2026-05-16 | 登记 T-CONFIG-004 Few-shot 适用条件规范 |
| v1.6.0 | 2026-05-16 | 登记 T-CONFIG-003 模型策略判断规范 |
| v1.5.0 | 2026-05-16 | 登记 T-CONFIG-002 Few-shot 示例规范 |
| v1.4.0 | 2026-05-14 | 登记 T-CONFIG-001 模板结构规范 |
| v1.3.0 | 2026-05-14 | 登记 CS-002 小红书内容计划案例 |
| v1.2.0 | 2026-05-14 | 登记 T-TEXT-001 模糊需求转计划模板 |
| v1.1.0 | 2026-05-14 | Phase 1 中期验收后导航更新 |
| v1.0.0 | 2026-05-14 | 初始创建 |

---

*本知识库由 KB-Admin 维护，OpenClaw 辅助建立，持续迭代中。当前版本：Prompt-KB v1.1 已发布。*
