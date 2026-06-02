# DAIR.AI Introduction 学习 — 执行提示词

> **版本**: v1.0.0
> **创建日期**: 2026-05-14
> **用途**: 开始学习 DAIR.AI Prompt Engineering Guide 的 Introduction 章节
> **限制**: 只处理此章节，不扩展到其他内容

---

## 🎯 任务说明

你现在的任务是帮助学习者学习 DAIR.AI Prompt Engineering Guide 的 **Introduction** 章节。

**限制条件**:
- ❌ 不要处理 Basic Prompting 章节
- ❌ 不要处理 Advanced Prompting 章节
- ❌ 不要处理其他章节
- ✅ 只处理 Introduction

---

## 📋 执行步骤

### Step 1: 获取 Introduction 内容

请先获取 DAIR.AI Prompt Engineering Guide 的 Introduction 章节内容。

资源地址: https://github.com/dair-ai/Prompt-Engineering-Guide
相关路径: Introduction / 简介 部分

---

### Step 2: 提炼核心概念

在阅读内容后，提炼出：

1. **什么是 Prompt Engineering**
   - 用 2-3 句话定义
   - 为什么它重要

2. **Prompt 的基本定义**
   - 什么是 prompt（提示词）
   - prompt 在人机交互中的作用

3. **AI 模型对 prompt 的敏感性**
   - 为什么小小的改动会导致不同的输出
   - "Prompting" 作为一种能力的重要性

4. **本章节的核心知识点**
   - 列出 3-5 个关键概念
   - 每个概念用一句话解释

---

### Step 3: 生成中文提示词模板

为以下场景生成可复制的中文提示词模板：

#### 模板 1: 基础问答模板
适用于简单的 Q&A 场景

#### 模板 2: 角色扮演模板
适用于需要 AI 扮演特定角色的场景

#### 模板 3: 简单指令模板
适用于让 AI 执行明确任务的场景

每个模板都要包含：
- 角色定义（如果适用）
- 任务描述
- 约束条件
- 输出格式要求

---

### Step 4: 生成知识库条目

按标准模板生成以下知识库条目：

#### 条目 1: `01-fundamentals/concept-what-is-prompting.md`
- 标题: "什么是 Prompt Engineering"
- 主题类型: 基础理论
- 核心概念: Prompt Engineering 的定义和重要性

#### 条目 2: `01-fundamentals/principles-why-matters.md`
- 标题: "为什么 Prompt Engineering 很重要"
- 主题类型: 基础理论
- 核心概念: AI 对提示词的敏感性，提示词设计的影响

#### 条目 3: `02-text-prompts/basic-qa-template.md`
- 标题: "基础问答提示词模板"
- 主题类型: 提示词模板
- 核心概念: 如何写一个有效的问答提示词

---

### Step 5: OpenClaw 使用建议

#### 适合单 Agent 的场景

| 场景 | 说明 | 推荐模板 |
|------|------|----------|
| 简单问答 | 问题明确，答案直接 | 基础问答模板 |
| 快速翻译 | 短文本翻译 | 简单指令模板 |
| 格式转换 | JSON 转 Markdown | 简单指令模板 |

#### 适合多 Agent 的场景

Introduction 章节内容暂不涉及多 Agent 场景，此部分留空，待后续高级章节补充。

---

### Step 6: 安全注意事项

> ⚠️ **重要**: 基础问答和简单任务通常不需要外部操作

以下场景可能需要人工确认（本次任务中暂不涉及，但需要了解）：

- [ ] 如果提示词涉及文件读取 → 确认文件路径
- [ ] 如果提示词涉及命令执行 → 确认命令内容
- [ ] 如果提示词涉及邮件发送 → 确认收件人和内容
- [ ] 如果提示词涉及日历修改 → 确认时间和事件

---

## 📁 输出文件清单

本次任务完成后，应生成以下文件：

```
prompt-kb/
├── 01-fundamentals/
│   ├── concept-what-is-prompting.md      ← 新建
│   └── principles-why-matters.md         ← 新建
├── 02-text-prompts/
│   └── basic-qa-template.md              ← 新建
└── 07-learning/
    └── notes-dair-ai-intro.md            ← 新建
```

---

## ✅ 验收标准

在回复中，请确认以下验收标准：

| 标准 | 状态 | 说明 |
|------|------|------|
| 提炼了 3-5 个核心概念 | ☐ | |
| 生成了 3 个中文提示词模板 | ☐ | |
| 创建了 4 个知识库条目文件 | ☐ | |
| 给出了单 Agent 使用建议 | ☐ | |
| 没有扩展到其他章节 | ☐ | |

---

## 📝 注意事项

1. **不要全文翻译**: 只提炼核心概念，不要逐段翻译
2. **不要泛泛而谈**: 每个概念都要有实际可用的模板
3. **中文优先**: 所有输出使用中文
4. **单 Agent 为主**: Introduction 章节内容适合单 Agent 处理
5. **保存到指定路径**: 按照文件清单的路径创建文件

---

## 🚀 开始执行

当学习者发送以下内容时，请按此提示词执行：

> "开始学习 DAIR.AI Introduction"

或者发送此文件内容给 AI 开始执行。

---

*此提示词用于指导 AI 助手完成 DAIR.AI Introduction 章节的学习任务。*
