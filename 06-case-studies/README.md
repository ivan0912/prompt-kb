# 案例复盘目录

> **版本**: v1.7.0
> **创建日期**: 2026-05-14
> **最近更新**: 2026-05-27（登记 CS-OPENCLAW-001 为 OpenClaw 工作流案例）
> **用途**: 记录实际使用中的成功和失败案例、模板验证测试，覆盖文本、图像、视频和 OpenClaw 工作流四大类别

---

## 内容说明

本目录存放所有案例复盘，用于：
- 记录成功的提示词和经验
- 分析失败的原因和教训
- 提炼可复用的模式

## 目录结构

```
06-case-studies/
├── README.md                    # 本文件
├── oral-request-to-learning-plan.md          # CS-001：学习计划案例（T-TEXT-001 原型）
├── t-text-001-xiaohongshu-content-plan-test.md # CS-002：小红书内容创作计划（T-TEXT-001 迁移验证）
├── cs-img-001-prompt-kb-cover-image.md       # CS-IMG-001：图像提示词案例（T-IMG-001 实战验证）
├── cs-img-002-product-hero-image.md          # CS-IMG-002：产品主视觉图案例（T-IMG-001 实战验证）
├── cs-img-003-fishing-gathering.md          # CS-IMG-003：多人物户外场景图案例（T-IMG-001 实战验证）
├── cs-img-001-platform-adaptation-test.md    # TEST-IMG-002-001：平台适配测试（T-IMG-002 实战验证）
├── cs-img-002-platform-adaptation-test.md    # TEST-IMG-002-002：产品图平台适配测试（T-IMG-002 实战验证）
├── cs-video-001-product-showcase-video.md    # CS-VIDEO-001：智能水壶产品展示视频提示词案例
├── cs-video-001-platform-adaptation-test.md  # TEST-VIDEO-002-001：视频平台适配测试（T-VIDEO-002 实战验证）
├── cs-openclaw-001-module-delivery-workflow.md # CS-OPENCLAW-001：OpenClaw 工作流案例（模块产物创建—验收—登记）
├── _success/                   # 成功案例
│   ├── 2026-05-14-weekly-report-automation.md
│   ├── 2026-05-10-market-analysis.md
│   └── [更多成功案例]
├── _failure/                    # 失败案例
│   ├── 2026-05-12-api-integration-fail.md
│   ├── 2026-05-08-misunderstanding-issue.md
│   └── [更多失败案例]
└── _lessons/                   # 教训总结
    ├── lesson-prompt-vagueness.md
    ├── lesson-context-missing.md
    └── [更多教训]
```

---

## 已有案例

### CS-001｜口语需求转学习计划

> **文件**: [oral-request-to-learning-plan.md](oral-request-to-learning-plan.md)
> **类型**: 模板来源案例（从真实需求中提炼出 T-TEXT-001 通用模板）
> **原始需求**: "我想让 AI 帮我整理一个学习计划，但是我不知道怎么说，也不知道应该让它输出什么格式"
> **关联模板**: T-TEXT-001 模糊需求转计划类任务 Pipeline（**当前稳定版：v0.4**）
> **模板兼容性**：✅ 案例逻辑兼容 v0.4，无需重写正文
> **状态**: v1.1，已归档

---

### CS-002｜T-TEXT-001 实测：30 天小红书内容创作计划

> **文件**: [t-text-001-xiaohongshu-content-plan-test.md](t-text-001-xiaohongshu-content-plan-test.md)
> **类型**: 模板迁移验证（验证 T-TEXT-001 能否处理非学习计划场景）
> **原始需求**: "我想做一个 30 天小红书内容创作计划，但不知道每天该发什么，也不知道怎么安排选题。"
> **关联模板**: T-TEXT-001（**当前稳定版：v0.4**）
> **模板兼容性**：✅ 案例逻辑兼容 v0.4，无需重写正文
> **执行范围**: Step 1 需求澄清 + Step 2 计划框架（未执行 Step 3，故意验证防跳步机制）
> **测试重点**:
- 模板跨领域迁移有效性（学习计划 → 小红书内容创作）
- 最小回答版在信息匮乏场景下的表现
- Step 1→Step 2 的衔接流畅度
- 假设比例管理是否有效
> **结论**: ✅ **A 通过，93.3%（28/30）**
> **是否修改模板**: ❌ 否（提出 3 条 P2/P3 优化建议，建议积累更多实测后统一判断）
> **状态**: v0.1，已归档

---

### CS-IMG-001｜Prompt-KB 知识库封面图提示词案例

> **文件**: [cs-img-001-prompt-kb-cover-image.md](cs-img-001-prompt-kb-cover-image.md)
> **版本**: v0.2
> **状态**: 已通过轻量验收
> **类型**: 图像提示词案例
> **关联规范**: T-IMG-001｜Prompt-KB 图像提示词基础规范
> **关联速查卡**: image-prompt-quick-reference.md
> **用途**: 验证「口语化图像需求 → 图像提示词 → 验收清单 → 复盘结论」的完整流程
> **场景**: README 封面图、项目介绍 Banner、知识库配图、AI 项目视觉封面
> **核心内容**:
> - 原始需求分析
> - 按 T-IMG-001 的 15 维度拆解
> - 中文图像提示词
> - 英文图像提示词
> - 负面提示词
> - 3 个变体
> - 平台适配建议
> - 验收清单
> - 风险与注意事项
> - 案例结论与可复用价值
>
> 这是 Prompt-KB 的第一个图像提示词案例，可作为后续图像案例、平台适配模板和实测验证的参考样例。

---

### CS-IMG-002｜极简智能水杯产品主视觉图提示词案例

> **文件**: [cs-img-002-product-hero-image.md](cs-img-002-product-hero-image.md)
> **版本**: v0.1
> **状态**: 已通过轻量验收
> **类型**: 图像提示词案例 / 产品主视觉图案例
> **关联规范**: T-IMG-001｜Prompt-KB 图像提示词基础规范
> **关联速查卡**: image-prompt-quick-reference.md
> **关联平台适配模板**: T-IMG-002｜图像提示词平台适配模板（[../03-image-prompts/templates/image-platform-adaptation-template.md](../03-image-prompts/templates/image-platform-adaptation-template.md)）
> **用途**: 验证 T-IMG-001、quick-reference 和 T-IMG-002 在产品图 / 商业摄影 / 智能硬件展示图场景下的可用性
> **场景**: 电商详情页主图、官网 Banner、新品介绍图、智能硬件产品图、社交媒体产品宣传图
> **核心内容**:
> - 原始需求分析
> - 按 T-IMG-001 的 15 维度拆解（15/15 全部明确）
> - 中文图像提示词
> - 英文图像提示词
> - 中英文负面提示词
> - 3 个产品图变体（极简白底 / 办公桌面场景 / 科技感健康生活）
> - 平台适配建议（ChatGPT Images / 豆包 / Midjourney / Stable Diffusion & Flux / Hugging Face）
> - quick-reference 验收清单（17/17 全部通过）
> - 产品图风险与注意事项（8 项）
> - 案例结论与可复用价值
>
> 这是 Prompt-KB 的第二个图像提示词案例，与 CS-IMG-001 形成「抽象概念图 + 实体产品图」的互补覆盖，可作为后续产品图、商业摄影图和智能硬件视觉案例的参考样例。

---
### CS-IMG-003｜多人物户外场景图（野钓聚会）提示词案例

> **文件**: [cs-img-003-fishing-gathering.md](cs-img-003-fishing-gathering.md)
> **版本**: v0.1
> **状态**: 已完成脱敏整理（原始需求来自真实口语化输入，已全面脱敏）
> **类型**: 图像提示词案例 / 多人物户外场景图案例
> **关联规范**: T-IMG-001｜Prompt-KB 图像提示词基础规范
> **关联速查卡**: image-prompt-quick-reference.md
> **用途**: 验证 T-IMG-001 和 quick-reference 在多人物、特定地域、复杂场景下的可用性
> **场景**: 家庭聚会记录、朋友聚会记录、户外活动场景、多人物协调构图
> **核心内容**:
> - 口语化需求分析与改写
> - 按 T-IMG-001 的 15 维度拆解（15/15 全部明确）
> - 中文图像提示词 + 英文图像提示词
> - 中英文负面提示词
> - 3 个变体（温馨家庭时光 / 老同学叙旧 / 野钓全景）
> - 平台适配建议（ChatGPT Images / 豆包 / Midjourney / Stable Diffusion & Flux / Hugging Face）
> - quick-reference 验收清单（17/17 全部通过）
> - 风险与注意事项（6 项）
> - 案例结论与可复用价值
>
> 这是 Prompt-KB 的第三个图像提示词案例，重点验证多人物场景和复杂构图能力。与 CS-IMG-001（抽象概念图）和 CS-IMG-002（产品图）形成三种不同图像类型的互补覆盖。

---

### TEST-IMG-002-001｜CS-IMG-001 平台适配测试

> **文件**: [cs-img-001-platform-adaptation-test.md](cs-img-001-platform-adaptation-test.md)
> **版本**: v0.1
> **状态**: 已完成 / 已通过平台适配检查
> **类型**: 图像平台适配测试记录
> **关联模板**: T-IMG-002｜图像提示词平台适配模板（[../03-image-prompts/templates/image-platform-adaptation-template.md](../03-image-prompts/templates/image-platform-adaptation-template.md)）
> **关联案例**: CS-IMG-001｜Prompt-KB 知识库封面图提示词案例（[cs-img-001-prompt-kb-cover-image.md](cs-img-001-prompt-kb-cover-image.md)）
> **用途**: 验证 T-IMG-002 是否能将同一个图像需求改写为多个平台适配版本
> **覆盖平台**:
> - ChatGPT Images
> - 豆包
> - Midjourney
> - Stable Diffusion
> - Flux
> - Hugging Face 图像模型
> **核心内容**:
> - 从 CS-IMG-001 提取 18 项核心信息
> - 通用需求解析（6 项）
> - 通用中英文提示词（平台无关）
> - 负面提示词 / 限制条件（英文 + 中文版本）
> - 6 个平台适配版本（各含提示词 + 注意事项）
> - 平台差异说明（6 平台 × 5 维度表格）
> - 平台适配检查清单（12 项，全部通过）
> - 测试结论与后续建议
> **测试结论**:
> - 成功从 CS-IMG-001 提取核心信息；
> - 成功生成 6 个平台适配版本；
> - 未写死平台版本号；
> - 未跨平台误用参数；
> - 12 项平台适配检查全部通过；
> - T-IMG-002 暂不需要修改。
>
> 这是 Prompt-KB 第一个图像平台适配测试记录，可作为后续平台适配模板测试和多平台提示词改写的参考样例。

---

### TEST-IMG-002-002｜CS-IMG-002 产品图平台适配测试

> **文件**: [cs-img-002-platform-adaptation-test.md](cs-img-002-platform-adaptation-test.md)
> **版本**: v0.1
> **状态**: 已完成 / 已通过平台适配检查
> **类型**: 图像平台适配测试记录 / 产品图平台适配测试
> **关联模板**: T-IMG-002｜图像提示词平台适配模板（[../03-image-prompts/templates/image-platform-adaptation-template.md](../03-image-prompts/templates/image-platform-adaptation-template.md)）
> **关联案例**: CS-IMG-002｜极简智能水杯产品主视觉图提示词案例（[cs-img-002-product-hero-image.md](cs-img-002-product-hero-image.md)）
> **参考测试**: TEST-IMG-002-001｜CS-IMG-001 平台适配测试（[cs-img-001-platform-adaptation-test.md](cs-img-001-platform-adaptation-test.md)）
> **用途**: 验证 T-IMG-002 是否能将产品主视觉图需求改写为多个平台适配版本
> **覆盖平台**:
> - ChatGPT Images
> - 豆包
> - Midjourney
> - Stable Diffusion
> - Flux
> - Hugging Face 图像模型
> **核心内容**:
> - 从 CS-IMG-002 提取 19 项核心信息
> - 通用需求解析（6 项）
> - 通用中英文提示词（平台无关）
> - 负面提示词 / 限制条件（英文 13 项 + 中文 13 项）
> - 6 个平台适配版本（各含提示词 + 注意事项，含产品图专项提醒）
> - 平台差异说明（6 平台 × 5 维度 + 产品图注意事项列）
> - 平台适配检查清单（扩展至 15 项，全部通过，N/A 1 项）
> - 与 TEST-IMG-002-001 的互补性对比
> - 测试结论与后续建议
> **测试结论**:
> - 成功从 CS-IMG-002 提取核心信息；
> - 成功生成 6 个平台适配版本；
> - 未写死平台版本号；
> - 未跨平台误用参数；
> - 保留产品主体、材质、色彩、构图、光线和负面限制；
> - 强化了产品主体一致性和屏幕文字风险提醒；
> - T-IMG-002 暂不需要修改。
>
> 这是 Prompt-KB 的第二个图像平台适配测试记录，与 TEST-IMG-002-001 形成「抽象概念图 + 实体产品图」的平台适配验证组合。

---

### CS-VIDEO-001｜智能水壶产品展示视频提示词案例

> **文件**: [cs-video-001-product-showcase-video.md](cs-video-001-product-showcase-video.md)
> **版本**: v0.2
> **状态**: A级 / 20/20 验收通过，待正式验收
> **类型**: 视频提示词案例 / 产品展示视频案例
> **关联规范**: T-VIDEO-001｜Prompt-KB 视频提示词基础规范
> **关联速查卡**: video-prompt-quick-reference.md（v0.2）
> **关联图像案例**: CS-IMG-002｜极简智能水杯产品主视觉图提示词案例（[cs-img-002-product-hero-image.md](cs-img-002-product-hero-image.md)）
> **用途**: 验证 T-VIDEO-001 基础规范和速查卡 v0.2 在 L4 产品广告/多镜头视频场景下的完整可用性
> **场景**: 电商产品展示视频、官网产品介绍视频、社交媒体短视频广告、智能硬件功能演示视频
> **核心内容**:
> - 原始需求分析（43 字口语需求）
> - 按 T-VIDEO-001 的 20 维度拆解（20/20 全部明确）
> - L4 复杂度判断及理由
> - 中文视频提示词（结构化 + 自然语言双版本）
> - 英文视频提示词（结构化 + 自然语言双版本）
> - 动作-镜头同步矩阵（7 时间段 × 6 列）
> - 3 个变体（A 短版抖音 / B 中版小红书 / C 长版 B站）
> - 7 平台适配版本（Sora/Runway/Pika/Kling/Luma/豆包/Midjourney）
> - 负面提示词（四源法：通用排除 + 质量防守 + 产品保真 + 风格边界）
> - AI 工具能力边界参考表（7 类能力/限制）
> - 验收清单（20/20 全部通过）
> - 风险与注意事项（8 项，含 Top 3 高风险项）
> - 与 CS-IMG-002 的继承对比表（15 继承 / 8 新增维度）
> - 案例结论与可复用价值
>
> 这是 Prompt-KB 的第一个视频提示词案例，与 CS-IMG-002 形成「图像 → 视频」的案例继承链，可作为后续产品展示视频、广告视频和智能硬件演示视频案例的参考样例。

---

### TEST-VIDEO-002-001｜CS-VIDEO-001 视频平台适配测试

> **文件**: [cs-video-001-platform-adaptation-test.md](cs-video-001-platform-adaptation-test.md)
> **版本**: v0.1
> **状态**: 已完成 / 已通过视频平台适配检查
> **类型**: 视频平台适配测试记录
> **关联模板**: T-VIDEO-002｜视频提示词平台适配模板（[../04-video-prompts/templates/video-platform-adaptation-template.md](../04-video-prompts/templates/video-platform-adaptation-template.md)）
> **关联案例**: CS-VIDEO-001｜智能水壶产品展示视频提示词案例（[cs-video-001-product-showcase-video.md](cs-video-001-product-showcase-video.md)）
> **关联规范**: T-VIDEO-001｜Prompt-KB 视频提示词基础规范（[../04-video-prompts/video-prompt-foundation.md](../04-video-prompts/video-prompt-foundation.md)）
> **关联速查卡**: [../04-video-prompts/video-prompt-quick-reference.md](../04-video-prompts/video-prompt-quick-reference.md)
> **用途**: 验证 T-VIDEO-002 是否能将通用视频提示词改写为多个视频生成平台适配版本
> **覆盖平台**:
> - Runway
> - Pika
> - Kling / 可灵
> - Luma
> - Sora
> - 豆包 / 即梦
> - 其他视频生成模型
> **核心内容**:
> - 从 CS-VIDEO-001 提取 25 项核心信息
> - 通用中英文视频提示词与通用负面提示词
> - 7 类平台适配版本
> - 平台差异说明、推荐优先测试平台、人工确认项
> - T-VIDEO-002 视频平台适配检查清单（20 项）
> - 测试结论与后续建议
> **测试结论**:
> - 成功从 CS-VIDEO-001 提取核心信息；
> - 成功生成 7 类平台适配版本；
> - 未写死平台版本号；
> - 未写死实时平台参数；
> - 未跨平台误用参数；
> - T-VIDEO-002 检查清单 20/20 通过；
> - 当前不需要修改 T-VIDEO-002。
>
> 这是 Prompt-KB 第一个视频平台适配测试记录，用于验证从产品展示视频案例到多平台视频提示词版本的完整改写流程。

---

### CS-OPENCLAW-001｜模块产物创建—验收—登记工作流案例

> **文件**: [cs-openclaw-001-module-delivery-workflow.md](cs-openclaw-001-module-delivery-workflow.md)
> **版本**: v0.1
> **状态**: 已完成 / 已通过质量验收
> **验收等级**: A级
> **验收评分**: 110/110
> **类型**: OpenClaw 工作流案例 / 模块交付流程案例
> **关联规范**: T-OPENCLAW-001｜OpenClaw 多 Agent 工作流基础规范（[../05-openclaw-workflows/openclaw-workflow-foundation.md](../05-openclaw-workflows/openclaw-workflow-foundation.md)）
> **关联速查卡**: [../05-openclaw-workflows/openclaw-workflow-quick-reference.md](../05-openclaw-workflows/openclaw-workflow-quick-reference.md)
> **用途**: 验证 T-OPENCLAW-001 和 OpenClaw 工作流速查卡在"创建 → 验收 → 小修 → 复核 → 登记 → 下一步"复杂任务链路中的可用性
> **适用场景**:
> - 新规范创建流程
> - 新模板创建流程
> - 新速查卡创建流程
> - 案例创建流程
> - 平台适配模板创建流程
> - 测试记录创建流程
> - 导航登记流程
> - 阶段性验收流程
> - 新模块从 0 到 1 的交付流程
> - OpenClaw 多 Agent 协作模板输入案例
> **核心内容**:
> - 原始任务场景
> - T-OPENCLAW-001 的 18 维度拆解
> - 任务类型判断（9 种类型）
> - L3 复杂度判断
> - 单 Agent / 多 Agent 判断
> - 可选 8 个多 Agent 角色分工
> - 推荐执行流程（9 步）
> - 创建类任务指令模板
> - 验收类任务指令模板
> - 小修类任务指令模板
> - 导航登记类任务指令模板
> - 保护文件与范围控制（7 场景规则）
> - 失败与返工处理（9 种失败类型）
> - 输出报告模板（9 项）
> - 工作流验收清单（13/13 通过）
> - 可复用价值说明（10 种场景）
>
> 这是 Prompt-KB 第一个 OpenClaw 工作流案例，用于验证从复杂任务到可执行闭环的完整流程。

---

## 案例格式

### 成功案例

```markdown
# [成功] 任务名称 — YYYY-MM-DD

## 任务背景
[为什么需要完成这个任务]

## 使用的提示词
```markdown
[完整提示词]
```

## 执行过程
[关键步骤]

## 最终结果
[结果描述，效果评估]

## 成功要素
1. [要素1]
2. [要素2]

## 可复用点
[提炼出可以用于其他场景的方法]
```

### 失败案例

```markdown
# [失败] 任务名称 — YYYY-MM-DD

## 任务背景
[任务描述]

## 尝试的提示词
```markdown
[提示词]
```

## 问题描述
[具体出现了什么问题]

## 失败原因
1. [原因1]
2. [原因2]

## 教训
[从失败中学到的教训]

## 改进方案
[下次如何改进]
```

---

## 教训总结

从多个案例中提炼出的通用教训：

### 1. 关于提示词清晰度
- 模糊的指令 → 模糊的结果
- 明确的约束 → 可控的输出

### 2. 关于上下文
- 上下文不足 → 幻觉和错误
- 适度上下文 → 准确理解

### 3. 关于任务分解
- 复杂任务硬做 → 质量不稳定
- 分解后逐步 → 质量可控

### 4. 关于迭代
- 一次到位 → 通常失望
- 迭代优化 → 逐步接近

---

## 复盘频率

| 类型 | 频率 | 说明 |
|------|------|------|
| 成功案例 | 每次成功使用后 | 记录成功要素 |
| 失败案例 | 每次失败后 | 分析原因，记录教训 |
| 教训总结 | 积累 3-5 个同类案例后 | 提炼通用模式 |

---

*案例是最好的老师，复盘是最快的成长。当前已有 10 个记录（CS-001 文本原型 + CS-002 文本迁移验证 + CS-IMG-001 图像实战验证 + CS-IMG-002 产品主视觉图案例 + TEST-IMG-002-001 平台适配测试 + TEST-IMG-002-002 产品图平台适配测试 + CS-VIDEO-001 产品展示视频案例 + TEST-VIDEO-002-001 视频平台适配测试 + CS-OPENCLAW-001 OpenClaw 工作流案例 + CS-IMG-003 多人物户外场景图案例）。*
