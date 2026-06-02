# 05-openclaw-workflows｜OpenClaw 工作流模块

> **版本**: v1.4.0
> **创建日期**: 2026-05-14
> **最近更新**: 2026-05-27（Phase 5 OpenClaw 工作流模块阶段性收尾，3/3 交付物完成，四条闭环成立）
> **关于 OpenClaw**：OpenClaw 在本知识库中指代多 Agent 工作流执行环境，可迁移理解为 Claude Code、OpenClaw 或其他 Agent 工作流工具。本模块的规范和案例不绑定特定平台，核心方法论（多步骤任务编排、产物创建—验收—登记闭环）适用于任意支持多 Agent 协作的环境。
---

## 模块状态

✅ Phase 5 已完成阶段性闭环 — 3/3 交付物完成，四条闭环全部成立

### Phase 5 收尾说明

Phase 5 已完成：

- T-OPENCLAW-001 OpenClaw 多 Agent 工作流基础规范（v0.1，A级 / 120/120）
- T-OPENCLAW-001 OpenClaw 工作流速查卡（v0.1，A级 / 120/120）
- CS-OPENCLAW-001 模块产物创建—验收—登记工作流案例（v0.1，A级 / 110/110）

四条闭环全部成立：OpenClaw 基础工作流闭环、复杂任务执行闭环、Prompt-KB 模块交付闭环、案例验证闭环。

后续可按需扩展（不阻塞 Prompt-KB 总体验收 / 发布整理）：

- 多 Agent 协作模板
- 第二个 OpenClaw 工作流案例
- 复杂失败恢复案例
- 跨模块重构案例
- 长上下文资料整理案例
- 团队协作 / 人工确认流程案例
- 自动化任务追踪机制

## 当前已完成

### T-OPENCLAW-001｜OpenClaw 多 Agent 工作流基础规范

| 属性 | 内容 |
|------|------|
| **文件** | [openclaw-workflow-foundation.md](openclaw-workflow-foundation.md) |
| **版本** | v0.1 |
| **状态** | ✅ 已通过质量验收 |
| **验收等级** | A级 |
| **验收评分** | 120/120 |
| **类型** | OpenClaw 工作流基础规范 |
| **用途** | 作为 Phase 5 OpenClaw 工作流模块的底层规范 |

**核心能力**：
- 任务识别与范围界定
- 资料定位与参考文件管理
- 单 Agent / 多 Agent 判断
- 执行计划与产物生成
- 验收检查与小修处理
- 导航登记与下一步决策

**18 个核心维度**：任务目标、任务类型、输入资料、参考文件、目标文件、产物类型、复杂度等级、单/多 Agent 判断、执行顺序、验收标准、保护文件、是否需要小修、是否需要导航登记、是否需要案例验证、是否需要平台适配、是否需要人工确认、输出报告、下一步建议

**标准工作流**：创建类、验收类、小修类、导航登记类、测试记录类、阶段性验收类

**覆盖内容**：
- OpenClaw 工作流核心公式（10 环节）
- 16 种任务类型分类
- L1-L5 复杂度分级
- 8 个多 Agent 角色设计（Planner/Builder/Reviewer/Refiner/Librarian/Tester/Risk/Summarizer）
- 保护文件与范围控制规范
- 失败与返工处理规范（10 种失败类型）
- 输出报告规范与工作流验收清单

### T-OPENCLAW-001 OpenClaw 工作流速查卡

| 属性 | 内容 |
|------|------|
| **文件** | [openclaw-workflow-quick-reference.md](openclaw-workflow-quick-reference.md) |
| **版本** | v0.1 |
| **状态** | ✅ 已通过质量验收 |
| **验收等级** | A级 |
| **验收评分** | 120/120 |
| **类型** | 速查卡 |
| **关联完整规范** | [openclaw-workflow-foundation.md](openclaw-workflow-foundation.md)（T-OPENCLAW-001） |
| **用途** | 日常快速判断任务类型、复杂度、单 Agent / 多 Agent、执行流程、验收方式和下一步行动 |

**核心内容**：
- 18 维度速查表
- 16 种任务类型速查
- L1-L5 复杂度速查
- 单 Agent / 多 Agent 判断速查
- 8 个多 Agent 角色速查
- 创建 / 验收 / 小修 / 登记 / 测试 / 阶段性验收流程
- 保护文件速查
- 失败与返工速查
- 输出报告模板
- 工作流验收清单
- 推荐使用流程

> 日常使用时优先查阅 openclaw-workflow-quick-reference.md；需要完整规则、边界和设计依据时再查阅 openclaw-workflow-foundation.md。

---

## 目录结构

```
05-openclaw-workflows/
├── README.md                              # 本文件
├── openclaw-workflow-foundation.md        # T-OPENCLAW-001 工作流基础规范 ✅
├── openclaw-workflow-quick-reference.md   # T-OPENCLAW-001 工作流速查卡 ✅
├── _single-agent/                         # 单 Agent 模板（规划中）
├── _multi-agent/                          # 多 Agent 协作模板（规划中）
├── _collaboration/                        # 协作模式库（规划中）
└── _patterns/                             # 通用模式（规划中）
```

---

### CS-OPENCLAW-001｜模块产物创建—验收—登记工作流案例

| 属性 | 内容 |
|------|------|
| **文件** | [../06-case-studies/cs-openclaw-001-module-delivery-workflow.md](../06-case-studies/cs-openclaw-001-module-delivery-workflow.md) |
| **版本** | v0.1 |
| **状态** | ✅ 已通过质量验收 |
| **验收等级** | A级 |
| **验收评分** | 110/110 |
| **类型** | OpenClaw 工作流实战案例 / 模块交付流程案例 |
| **关联规范** | [openclaw-workflow-foundation.md](openclaw-workflow-foundation.md)（T-OPENCLAW-001） |
| **关联速查卡** | [openclaw-workflow-quick-reference.md](openclaw-workflow-quick-reference.md) |
| **用途** | 验证 T-OPENCLAW-001 和工作流速查卡在"创建 → 验收 → 小修 → 复核 → 登记 → 下一步"复杂任务链路中的可用性 |

**核心内容**：原始任务场景、18 维度拆解、任务类型判断、L3 复杂度判断、单/多 Agent 判断、可选 8 角色分工、推荐执行流程、4 个可复制指令模板（创建/验收/小修/登记）、保护文件与范围控制、失败与返工处理、输出报告模板、工作流验收清单（13/13 通过）、可复用价值（10 种场景）

> CS-OPENCLAW-001 适合参考"模块产物从创建到登记"的完整交付链路，是后续多 Agent 协作模板的重要输入案例。

---

## 后续建议

1. ~~创建 OpenClaw 工作流速查卡~~ → ✅ **已完成（v0.1，A级 / 120/120）**
2. ~~创建第一个 OpenClaw 工作流案例~~ → ✅ **已完成（CS-OPENCLAW-001 v0.1，A级 / 110/110）**
3. ~~Phase 5 阶段性验收~~ → ✅ **已完成（A级，四条闭环成立）**
4. **下一步推荐**：执行 Prompt-KB 总体验收 / 发布整理
5. 根据实际使用反馈决定是否小修 T-OPENCLAW-001 到 v0.2
6. 根据实际使用反馈决定是否小修 OpenClaw 工作流速查卡到 v0.2

---

## 单 Agent vs 多 Agent

### 单 Agent 适用场景

| 场景 | 特点 | 示例 |
|------|------|------|
| 简单任务 | 输入明确，输出直接 | 翻译、格式转换 |
| 单一技能 | 不需要多角度 | 代码审查、文案撰写 |
| 快速执行 | 需要即时结果 | 临时查询、简单问答 |

### 多 Agent 适用场景

| 场景 | 特点 | 示例 |
|------|------|------|
| 复杂任务 | 需要分解为多个子任务 | 年度报告生成 |
| 多角度分析 | 需要不同视角 | 竞品分析、市场调研 |
| 并行处理 | 有独立的并行分支 | 多产品同时调研 |
| 质量把控 | 需要审核和修订 | 重要文档发布 |

---

## 协作模式

### 1. 规划-执行模式 (Planner-Executor)

```
Planner Agent
    ↓ 分解任务
Executor Agent 1 ──┐
Executor Agent 2 ──┼──→ 结果汇总
Executor Agent 3 ──┘
```

**适用**: 复杂任务分解

### 2. 研究-写作模式 (Researcher-Writer)

```
Researcher Agent
    ↓ 提供素材
Writer Agent
    ↓ 输出草稿
Reviewer Agent
    ↓ 反馈修改
Writer Agent (修订)
```

**适用**: 需要准确信息的写作任务

### 3. 并行-汇总模式 (Parallel-Aggregate)

```
Agent A (分支1) ──┐
Agent B (分支2) ──┼──→ Aggregator Agent ──→ 最终输出
Agent C (分支3) ──┘
```

**适用**: 需要多来源信息的综合任务

### 4. 审核循环模式 (Review Loop)

```
Writer Agent ──→ Reviewer Agent ──→ 反馈
                    ↑               ↓
                    └───── 修改 ←───┘
```

**适用**: 需要高质量输出的迭代任务

---

## 使用指南

### 如何选择工作流

1. **评估任务复杂度**: 简单任务用单 Agent
2. **判断是否需要多视角**: 是 → 多 Agent
3. **识别任务阶段**: 规划/执行/审核/修订
4. **选择合适的协作模式**

### 工作流文件格式

每个工作流文件应包含：
1. 任务概述
2. Agent 角色定义
3. 输入输出规范
4. 协作流程说明
5. 提示词模板
6. 验收标准

---

*本目录专门服务于 OpenClaw 系统的工作流设计。*
