# 学习资源目录

> **版本**: v1.0.0
> **创建日期**: 2026-05-14
> **用途**: 管理学习资源和个人笔记

---

## 目录结构

```
07-learning/
├── README.md                    # 本文件
├── _resources/                  # 资源索引
│   ├── resource-index.md        # 资源总索引
│   ├── resource-dair-ai.md      # DAIR.AI 资源详情
│   ├── resource-openai.md       # OpenAI 资源详情
│   ├── resource-anthropic.md    # Anthropic 资源详情
│   └── resource-courses.md      # 课程资源
├── _notes/                      # 学习笔记
│   ├── notes-dair-ai-intro.md   # DAIR.AI Introduction 笔记
│   ├── notes-dair-ai-basic.md   # DAIR.AI Basic 笔记
│   └── [按章节命名的笔记]
├── _plans/                      # 学习计划
│   ├── plan-phase-1.md          # 第一阶段计划
│   ├── plan-phase-2.md          # 第二阶段计划（预留）
│   └── execution-prompt-*.md    # 执行提示词
└── _progress/                   # 学习进度
    └── progress-tracking.md     # 进度追踪表
```

---

## 资源索引

### 官方文档

| 资源名称 | 网址 | 优先级 | 状态 |
|----------|------|--------|------|
| DAIR.AI PE Guide | GitHub | ⭐⭐⭐⭐⭐ | ✅ 已完成 |
| OpenAI PE Guide | openai.com | ⭐⭐⭐⭐⭐ | ✅ 已完成校准 |
| Anthropic PE Guide | anthropic.com | ⭐⭐⭐⭐ | ✅ 已完成校准 |
| Google AI PE | developers.google.com | ⭐⭐⭐ | 📋 待学 |

### 在线课程

| 课程名称 | 平台 | 优先级 | 状态 |
|----------|------|--------|------|
| DeepLearning.AI PE | deeplearning.ai | ⭐⭐⭐⭐ | 📋 待学 |
| Learn Prompting | learnprompting.org | ⭐⭐⭐⭐ | 📋 待学 |

### 视频教程

| 教程名称 | 平台 | 优先级 | 状态 |
|----------|------|--------|------|
| B站 AI 提示词教程 | B站 | ⭐⭐⭐ | 📋 待学 |

---

## 学习进度追踪

### 第一阶段

| 任务 | 资源 | 状态 | 完成日期 |
|------|------|------|----------|
| 1. Introduction | DAIR.AI | ✅ 已完成 | 2026-05-14~05-20 |
| 2. Basic Prompting | DAIR.AI | ✅ 已完成 | 2026-05-14~05-20 |
| 3. Advanced Prompting | DAIR.AI | ✅ 已完成 | 2026-05-14~05-20 |
| 4. OpenAI Guide | OpenAI | ✅ 已完成校准 | 2026-05-20~05-25 |
| 5. Anthropic Guide | Anthropic | ✅ 已完成校准 | 2026-05-20~05-25 |

---
## 校准文档

以下校准文档是 Phase 1 学习阶段的产出，用于支撑 T-CONFIG 系列规范的制定，不属于正式规范或模板：

| 文件 | 类型 | 说明 |
|------|------|------|
| [openai-prompt-guidance-calibration.md](../01-fundamentals/openai-prompt-guidance-calibration.md) | 学习校准笔记 | OpenAI Prompt Engineering Guide 校准成果，含 Phase 2 任务优先级表，用于支撑 T-CONFIG 系列规范制定 |
| [anthropic-structured-prompting-calibration.md](../01-fundamentals/anthropic-structured-prompting-calibration.md) | 学习校准笔记 | Anthropic 结构化提示方法论校准成果，含方法论提炼和 Phase 2 Backlog，用于支撑 T-CONFIG 系列规范制定 |

> 这两份文件存放于 `01-fundamentals/` 目录下，是学习过程中的方法论沉淀，不是正式规范产物。

## 学习笔记命名规范

```
notes-[来源简称]-[章节名].md

示例:
- notes-dair-ai-intro.md        → DAIR.AI Introduction 笔记
- notes-dair-ai-basic.md       → DAIR.AI Basic 笔记
- notes-openai-strategies.md   → OpenAI 策略笔记
- notes-anthropic-reliable.md  → Anthropic 可靠性笔记
```

---

## 笔记格式

每份笔记应包含：

1. **学习日期**: YYYY-MM-DD
2. **资源来源**: 名称 + 章节
3. **核心收获**: 3-5 个关键点
4. **疑问点**: 学习中发现的问题
5. **实践计划**: 如何在 OpenClaw 中应用

---

*持续学习，渐进积累。*
