# 第一阶段学习计划

> **版本**: v1.0.0
> **创建日期**: 2026-05-14
> **阶段目标**: 建立 Prompt Engineering 基础能力，产出第一批可复用模板
> **预计时长**: 2-3 周（每天 1 个任务）

---

## 学习路径概览

```
DAIR.AI Introduction
       ↓
DAIR.AI Basic Prompting
       ↓
DAIR.AI Advanced Prompting
       ↓
OpenAI 官方指南
       ↓
Anthropic Prompt Engineering
```

---

## 任务 1: DAIR.AI Introduction — 建立概念框架

### 学习目标
- 理解 Prompt Engineering 是什么
- 了解为什么提示词设计重要
- 建立对 AI 能力的正确认知

### 输入资源
- DAIR.AI Prompt Engineering Guide → Introduction 章节
- 网址: https://github.com/dair-ai/Prompt-Engineering-Guide

### 输出文件
1. `07-learning/notes-dair-ai-intro.md` — 学习笔记
2. `01-fundamentals/concept-what-is-prompting.md` — 核心概念条目
3. `01-fundamentals/principles-why-matters.md` — 为什么重要条目

### OpenClaw 需要生成的内容
- 中文版"什么是 Prompt Engineering"概念说明
- 3-5 个可复用的基础中文提示词模板
- 适合单 Agent 使用的场景示例

### 验收标准
- [ ] 理解 Prompt Engineering 的定义
- [ ] 能用自己的话解释为什么提示词设计重要
- [ ] 有 3 个以上可复制的中文模板
- [ ] 知道什么场景适合单 Agent

---

## 任务 2: DAIR.AI Basic Prompting — 掌握基础技巧

### 学习目标
- 学会基本的提示词构建方法
- 掌握"清晰指令 + 具体描述"的核心技巧
- 能写出基本可用的提示词

### 输入资源
- DAIR.AI Prompt Engineering Guide → Basic Prompting 章节

### 输出文件
1. `07-learning/notes-dair-ai-basic.md` — 学习笔记
2. `02-text-prompts/basic-instruction-template.md` — 基础指令模板
3. `02-text-prompts/basic-description-template.md` — 基础描述模板

### OpenClaw 需要生成的内容
- "清晰指令"的中文模板
- "具体描述"的中文模板
- 两者的组合模板

### 验收标准
- [ ] 能区分"清晰指令"和"模糊指令"的区别
- [ ] 能写出清晰的指令提示词
- [ ] 知道如何使用例子（Few-shot）

---

## 任务 3: DAIR.AI Advanced Prompting — 提升技巧

### 学习目标
- 学会 Chain of Thought（思维链）技巧
- 理解如何让 AI 逐步推理
- 掌握复杂任务的分解方法

### 输入资源
- DAIR.AI Prompt Engineering Guide → Advanced Prompting 章节

### 输出文件
1. `07-learning/notes-dair-ai-advanced.md` — 学习笔记
2. `02-text-prompts/chain-of-thought-template.md` — 思维链模板
3. `02-text-prompts/task-decomposition-template.md` — 任务分解模板

### OpenClaw 需要生成的内容
- Chain of Thought 提示词模板（中文）
- 任务分解模板（中文）
- 多步骤任务的提示词示例

### 验收标准
- [ ] 能解释什么是 Chain of Thought
- [ ] 能写出引导 AI 逐步推理的提示词
- [ ] 能分解复杂任务为简单步骤
- [ ] 知道什么场景适合多步骤提示词

---

## 任务 4: OpenAI 官方指南 — 实战技巧

### 学习目标
- 学习 OpenAI 推荐的提示词技巧
- 掌握 OpenAI 官方最佳实践
- 了解 ChatGPT 特有的提示词方法

### 输入资源
- OpenAI Prompt Engineering Guide（官方文档）

### 输出文件
1. `07-learning/notes-openai-guide.md` — 学习笔记
2. `02-text-prompts/openai-best-practices-template.md` — OpenAI 最佳实践模板
3. `02-text-prompts/chatgpt-specific-template.md` — ChatGPT 专项模板

### OpenClaw 需要生成的内容
- 6 大策略的中文模板
- ChatGPT 特定场景的提示词
- 与 DAIR.AI 方法的对比总结

### 验收标准
- [ ] 了解 OpenAI 的 6 大策略
- [ ] 能对比 DAIR.AI 和 OpenAI 的方法差异
- [ ] 有针对 ChatGPT 的专项模板

---

## 任务 5: Anthropic Prompt Engineering — 可靠性提升

### 学习目标
- 学习 Claude 的提示词方法
- 提升提示词的可靠性和一致性
- 了解 Constitutional AI 相关概念

### 输入资源
- Anthropic Prompt Engineering Guide

### 输出文件
1. `07-learning/notes-anthropic-guide.md` — 学习笔记
2. `02-text-prompts/anthropic-reliable-template.md` — 可靠性模板
3. `02-text-prompts/role-definition-template.md` — 角色定义模板

### OpenClaw 需要生成的内容
- 提升输出一致性的提示词
- 角色定义的标准模板
- 避免常见失败的提示词技巧

### 验收标准
- [ ] 能定义清晰的 AI 角色
- [ ] 能写出一致性高的提示词
- [ ] 知道如何避免常见失败

---

## 阶段总结

### 完成后应具备的能力

| 能力 | 验收标准 |
|------|----------|
| 基础构建 | 能写出清晰、具体的提示词 |
| 进阶技巧 | 能使用思维链和任务分解 |
| 工具适配 | 了解不同工具的提示词差异 |
| 可靠性 | 能写出稳定、一致的提示词 |
| 复盘能力 | 能记录和优化自己的提示词 |

### 第一阶段产出清单

```
第一阶段完成时，应有：
□ 5 个学习笔记文件
□ 10+ 个可复用中文模板
□ 1 份资源索引文件
□ 1 份阶段总结文件
□ 若干案例复盘文件
```

---

## 下一步（第二阶段可选）

- 学习 DAIR.AI 的 Reliability 章节
- 开始图像生成提示词学习
- 在 OpenClaw 中实际应用模板
- 建立第一个完整的工作流

---

*本计划由 KB-Admin 制定，根据实际进度调整。*
