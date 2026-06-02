# Prompt-KB 🚀

**A structured prompt engineering knowledge base for building reusable AI workflows across text, image, video, and agent-based tasks.**

**Prompt-KB** 不是简单的提示词合集，而是一套用于创建、验收、维护和复用 AI 提示词资产的结构化知识库。它覆盖文本提示词、图像提示词、视频提示词、平台适配和多步骤 Agent 工作流，帮助你把零散提示词变成可复用、可测试、可迭代的 AI 工作流资产。

> **Current Release**: Prompt-KB v1.1
> **Status**: ✅ Released / Ready for daily use
> **Maintainer**: KB-Admin
> **Last Updated**: 2026-05-28
> **Language**: 中文为主，部分英文说明
> **Use Case**: Prompt Engineering learning, reusable templates, AI workflow design, prompt evaluation, and knowledge base maintenance

---

## ✨ Why Prompt-KB?

Most prompt repositories only collect prompts.

Prompt-KB focuses on the full lifecycle of prompt assets:

```text
需求 → 模板 → 验收 → 小修 → 案例 → 平台适配 → 测试 → 发布 → 复盘
```

它适合你在以下场景中使用：

* 想系统学习 Prompt Engineering；
* 想把模糊需求转成可执行提示词；
* 想生成图像 / 视频提示词；
* 想把同一个提示词适配到不同平台；
* 想构建可维护的 AI 工作流；
* 想让 Claude Code / OpenClaw / Cursor / ChatGPT 执行复杂多步骤任务；
* 想把提示词沉淀成团队或个人知识资产。

---

## 🧭 5-Minute Quick Start

| I want to...                                  | Start here                                                                                                         |
| --------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Understand the whole project                  | [QUICKSTART.md](QUICKSTART.md)                                                                                     |
| See release status                            | [RELEASE_NOTES_v1.1.md](RELEASE_NOTES_v1.1.md)                                                                     |
| Check final acceptance result                 | [FINAL_ACCEPTANCE_REPORT_v1.1.md](FINAL_ACCEPTANCE_REPORT_v1.1.md)                                                 |
| Transfer this KB to another Agent environment | [HANDOFF_PROMPT-KB_v1.1.md](HANDOFF_PROMPT-KB_v1.1.md)                                                             |
| Write better text prompts                     | [T-TEXT-001](02-text-prompts/templates/fuzzy-request-to-plan-pipeline.md)                                          |
| Generate image prompts                        | [Image Prompt Quick Reference](03-image-prompts/image-prompt-quick-reference.md)                                   |
| Generate video prompts                        | [Video Prompt Quick Reference](04-video-prompts/video-prompt-quick-reference.md)                                   |
| Adapt image prompts to platforms              | [T-IMG-002 Image Platform Adaptation Template](03-image-prompts/templates/image-platform-adaptation-template.md)   |
| Adapt video prompts to platforms              | [T-VIDEO-002 Video Platform Adaptation Template](04-video-prompts/templates/video-platform-adaptation-template.md) |
| Run complex multi-step Agent tasks            | [OpenClaw Workflow Quick Reference](05-openclaw-workflows/openclaw-workflow-quick-reference.md)                    |
| Browse examples and tests                     | [Case Studies](06-case-studies/README.md)                                                                          |

---

## 🧪 Examples

### Example 1: Vague request → action plan

**Input**

```text
我想一个月内提高英语口语，但不知道怎么安排。
```

**Prompt-KB helps produce**

```text
结构化学习计划
阶段目标
每日任务
复盘方式
风险提醒
待确认问题
```

Recommended file:

```text
02-text-prompts/templates/fuzzy-request-to-plan-pipeline.md
```

---

### Example 2: Image request → image prompt

**Input**

```text
生成一张符合今天汕头天气和潮汕地区风格街景的图片。
```

**Prompt-KB helps produce**

```text
中文图像提示词
英文图像提示词
负面提示词
3 个变体
平台适配建议
风险与注意事项
```

Recommended file:

```text
03-image-prompts/image-prompt-quick-reference.md
```

---

### Example 3: Complex task → Agent workflow

**Input**

```text
帮我创建一个新模板，并完成验收、小修和导航登记。
```

**Prompt-KB helps produce**

```text
任务类型判断
复杂度判断
单 Agent / 多 Agent 判断
执行流程
保护文件清单
验收报告
下一步建议
```

Recommended file:

```text
05-openclaw-workflows/openclaw-workflow-quick-reference.md
```

---

## 📦 What is included?

| Area                | Content                                                                          |
| ------------------- | -------------------------------------------------------------------------------- |
| 🧠 Fundamentals     | Prompt Engineering basics, DAIR.AI learning notes, advanced prompting techniques |
| 📝 Text Prompts     | Reusable text prompt templates, especially vague request → plan pipeline         |
| 🎨 Image Prompts    | Image prompt foundation, quick reference, platform adaptation, image cases       |
| 🎬 Video Prompts    | Video prompt foundation, quick reference, platform adaptation, video cases       |
| 🤖 Agent Workflows  | OpenClaw / Claude Code / Agent workflow rules, multi-step task execution         |
| 🧪 Case Studies     | Text, image, video, and workflow examples with validation records                |
| ✅ Quality Checks    | Acceptance reports, checklists, release notes, handoff guide                     |
| 🔁 Maintenance Flow | Create → review → refine → register → test → release                             |

---

## 🗂 Repository Structure

```text
prompt-kb/
├── README.md
├── QUICKSTART.md
├── RELEASE_NOTES_v1.1.md
├── FINAL_ACCEPTANCE_REPORT_v1.1.md
├── HANDOFF_PROMPT-KB_v1.1.md
├── _config/
├── 01-fundamentals/
├── 02-text-prompts/
├── 03-image-prompts/
├── 04-video-prompts/
├── 05-openclaw-workflows/
├── 06-case-studies/
└── 07-learning/
```

| Directory                | Purpose                                                           |
| ------------------------ | ----------------------------------------------------------------- |
| `_config/`               | Core configuration and prompt template standards                  |
| `01-fundamentals/`       | Prompt Engineering learning notes and advanced techniques         |
| `02-text-prompts/`       | Text prompt templates                                             |
| `03-image-prompts/`      | Image prompt foundation, quick reference, and platform adaptation |
| `04-video-prompts/`      | Video prompt foundation, quick reference, and platform adaptation |
| `05-openclaw-workflows/` | Agent workflow rules and OpenClaw-style task orchestration        |
| `06-case-studies/`       | Case studies and test records                                     |
| `07-learning/`           | Learning resources, plans, and calibration records                |

---

## ✅ Current Status

Prompt-KB v1.1 has been released and is ready for daily use.

| Phase   | Module                           | Status      | Summary                                                            |
| ------- | -------------------------------- | ----------- | ------------------------------------------------------------------ |
| Phase 1 | Prompt Engineering Fundamentals  | ✅ Completed | DAIR.AI / OpenAI / Anthropic learning and calibration completed    |
| Phase 2 | Configuration Standards          | ✅ Completed | T-CONFIG-001 to T-CONFIG-006 completed                             |
| Phase 3 | Image Prompt Module              | ✅ Completed | Foundation → quick reference → cases → platform adaptation → tests |
| Phase 4 | Video Prompt Module              | ✅ Completed | Foundation → quick reference → case → platform adaptation → test   |
| Phase 5 | OpenClaw / Agent Workflow Module | ✅ Completed | Foundation → quick reference → workflow case → registration        |

Release documents:

* [RELEASE_NOTES_v1.1.md](RELEASE_NOTES_v1.1.md)
* [FINAL_ACCEPTANCE_REPORT_v1.1.md](FINAL_ACCEPTANCE_REPORT_v1.1.md)
* [HANDOFF_PROMPT-KB_v1.1.md](HANDOFF_PROMPT-KB_v1.1.md)

---

## 🧩 Core Standards

### Configuration Standards

| ID           | Name               | File                                                                                   | Status   |
| ------------ | ------------------ | -------------------------------------------------------------------------------------- | -------- |
| T-CONFIG-001 | Prompt-KB 通用模板结构规范 | [_config/prompt-template-style-guide.md](_config/prompt-template-style-guide.md)       | ✅ Stable |
| T-CONFIG-002 | Few-shot 示例规范      | [_config/few-shot-example-guide.md](_config/few-shot-example-guide.md)                 | ✅ Stable |
| T-CONFIG-003 | 模型类型与提示策略判断规范      | [_config/model-strategy-selection-guide.md](_config/model-strategy-selection-guide.md) | ✅ Stable |
| T-CONFIG-004 | Few-shot 适用条件判断规范  | [_config/few-shot-usage-decision-guide.md](_config/few-shot-usage-decision-guide.md)   | ✅ Stable |
| T-CONFIG-005 | 格式描述与占位符规范         | [_config/format-and-placeholder-guide.md](_config/format-and-placeholder-guide.md)     | ✅ Stable |
| T-CONFIG-006 | 长上下文输入规范           | [_config/long-context-input-guide.md](_config/long-context-input-guide.md)             | ✅ Stable |

---

### Text Prompt Standard

| ID         | Name                | File                                                                                             | Status   |
| ---------- | ------------------- | ------------------------------------------------------------------------------------------------ | -------- |
| T-TEXT-001 | 模糊需求转计划类任务 Pipeline | [fuzzy-request-to-plan-pipeline.md](02-text-prompts/templates/fuzzy-request-to-plan-pipeline.md) | ✅ Stable |

---

### Image Prompt Standards

| ID           | Name      | File                                                                                                      | Status   |
| ------------ | --------- | --------------------------------------------------------------------------------------------------------- | -------- |
| T-IMG-001    | 图像提示词基础规范 | [image-prompt-foundation.md](03-image-prompts/image-prompt-foundation.md)                                 | ✅ Stable |
| T-IMG-001 QR | 图像提示词速查卡  | [image-prompt-quick-reference.md](03-image-prompts/image-prompt-quick-reference.md)                       | ✅ Stable |
| T-IMG-002    | 图像平台适配模板  | [image-platform-adaptation-template.md](03-image-prompts/templates/image-platform-adaptation-template.md) | ✅ Stable |

---

### Video Prompt Standards

| ID             | Name      | File                                                                                                      | Status   |
| -------------- | --------- | --------------------------------------------------------------------------------------------------------- | -------- |
| T-VIDEO-001    | 视频提示词基础规范 | [video-prompt-foundation.md](04-video-prompts/video-prompt-foundation.md)                                 | ✅ Stable |
| T-VIDEO-001 QR | 视频提示词速查卡  | [video-prompt-quick-reference.md](04-video-prompts/video-prompt-quick-reference.md)                       | ✅ Stable |
| T-VIDEO-002    | 视频平台适配模板  | [video-platform-adaptation-template.md](04-video-prompts/templates/video-platform-adaptation-template.md) | ✅ Stable |

---

### Agent Workflow Standards

| ID                | Name                     | File                                                                                               | Status   |
| ----------------- | ------------------------ | -------------------------------------------------------------------------------------------------- | -------- |
| T-OPENCLAW-001    | OpenClaw 多 Agent 工作流基础规范 | [openclaw-workflow-foundation.md](05-openclaw-workflows/openclaw-workflow-foundation.md)           | ✅ Stable |
| T-OPENCLAW-001 QR | OpenClaw 工作流速查卡          | [openclaw-workflow-quick-reference.md](05-openclaw-workflows/openclaw-workflow-quick-reference.md) | ✅ Stable |

> **About OpenClaw**
> In this repository, OpenClaw refers to a multi-agent workflow execution environment. The workflow rules can also be adapted to Claude Code, Cursor, ChatGPT, or other Agent-based tools.

---

## 🧪 Case Studies and Tests

| ID                 | Category   | File                                                                                                       | Purpose                                               |
| ------------------ | ---------- | ---------------------------------------------------------------------------------------------------------- | ----------------------------------------------------- |
| CS-001             | Text       | [oral-request-to-learning-plan.md](06-case-studies/oral-request-to-learning-plan.md)                       | Learning plan prototype case                          |
| CS-002             | Text       | [t-text-001-xiaohongshu-content-plan-test.md](06-case-studies/t-text-001-xiaohongshu-content-plan-test.md) | Xiaohongshu content plan validation                   |
| CS-IMG-001         | Image      | [cs-img-001-prompt-kb-cover-image.md](06-case-studies/cs-img-001-prompt-kb-cover-image.md)                 | Prompt-KB cover image case                            |
| CS-IMG-002         | Image      | [cs-img-002-product-hero-image.md](06-case-studies/cs-img-002-product-hero-image.md)                       | Product hero image case                               |
| CS-IMG-003         | Image      | [cs-img-003-fishing-gathering.md](06-case-studies/cs-img-003-fishing-gathering.md)                         | Desensitized multi-person scene image case            |
| TEST-IMG-002-001   | Image Test | [cs-img-001-platform-adaptation-test.md](06-case-studies/cs-img-001-platform-adaptation-test.md)           | Image platform adaptation test                        |
| TEST-IMG-002-002   | Image Test | [cs-img-002-platform-adaptation-test.md](06-case-studies/cs-img-002-platform-adaptation-test.md)           | Product image platform adaptation test                |
| CS-VIDEO-001       | Video      | [cs-video-001-product-showcase-video.md](06-case-studies/cs-video-001-product-showcase-video.md)           | Product showcase video case                           |
| TEST-VIDEO-002-001 | Video Test | [cs-video-001-platform-adaptation-test.md](06-case-studies/cs-video-001-platform-adaptation-test.md)       | Video platform adaptation test                        |
| CS-OPENCLAW-001    | Workflow   | [cs-openclaw-001-module-delivery-workflow.md](06-case-studies/cs-openclaw-001-module-delivery-workflow.md) | Module creation → review → registration workflow case |

See full index:

```text
06-case-studies/README.md
```

---

## 🛠 Platform Adaptation

Prompt-KB includes reusable platform adaptation templates for both image and video generation.

### Image Platforms

Supported by T-IMG-002:

* ChatGPT Images
* 豆包
* Midjourney
* Stable Diffusion
* Flux
* Hugging Face

### Video Platforms

Supported by T-VIDEO-002:

* Runway
* Pika
* Kling / 可灵
* Luma
* Sora
* 豆包 / 即梦
* Other video generation models

> Platform capabilities and parameters change over time. Prompt-KB avoids hardcoding real-time platform parameters and recommends checking current official documentation when needed.

---

## 🔁 Prompt-KB Workflow

Prompt-KB follows a repeatable maintenance workflow:

```text
Create → Review → Refine → Re-check → Register → Test → Release
```

For complex tasks, use:

```text
05-openclaw-workflows/openclaw-workflow-quick-reference.md
```

Typical workflow abilities include:

* Task type identification
* Complexity classification
* Single Agent / Multi Agent decision
* Execution planning
* Quality review
* Small-scope refinement
* Navigation registration
* Failure and rollback handling
* Final report generation
* Next-step recommendation

---

## 🧭 Recommended Learning Path

### Beginner Path

```text
1. Introduction
2. Basic Prompting
3. Chain-of-Thought
4. Prompt Chaining
5. ReAct
```

Recommended files:

* [dair-ai-introduction.md](01-fundamentals/dair-ai-introduction.md)
* [dair-ai-basic-prompting.md](01-fundamentals/dair-ai-basic-prompting.md)
* [cot.md](01-fundamentals/advanced-techniques/cot.md)
* [prompt-chaining.md](01-fundamentals/advanced-techniques/prompt-chaining.md)
* [react.md](01-fundamentals/advanced-techniques/react.md)

---

### Advanced Path

```text
1. Self-Consistency
2. Generated Knowledge
3. Tree of Thoughts
4. Program-Aided Language Models
5. Agent Workflow Design
```

Recommended files:

* [self-consistency.md](01-fundamentals/advanced-techniques/self-consistency.md)
* [generated-knowledge.md](01-fundamentals/advanced-techniques/generated-knowledge.md)
* [tree-of-thoughts.md](01-fundamentals/advanced-techniques/tree-of-thoughts.md)
* [program-aided-language-models.md](01-fundamentals/advanced-techniques/program-aided-language-models.md)
* [openclaw-workflow-quick-reference.md](05-openclaw-workflows/openclaw-workflow-quick-reference.md)

---

## 👥 Who is this for?

Prompt-KB is useful for:

* Prompt Engineering learners;
* AI content creators;
* Claude Code / Cursor / ChatGPT users;
* Agent workflow builders;
* Image and video generation users;
* Knowledge base maintainers;
* Teams that want reusable AI workflows.

It may not be ideal for:

* Users who only want a few copy-paste prompts;
* Users who do not want to read structured documentation;
* Users looking for private business data or platform-specific real-time parameters.

---

## 📤 Handoff and Migration

If you want to move this knowledge base to another Agent environment, start here:

```text
HANDOFF_PROMPT-KB_v1.1.md
```

Recommended receiving order:

```text
1. README.md
2. QUICKSTART.md
3. RELEASE_NOTES_v1.1.md
4. FINAL_ACCEPTANCE_REPORT_v1.1.md
5. HANDOFF_PROMPT-KB_v1.1.md
6. 05-openclaw-workflows/openclaw-workflow-quick-reference.md
7. Then read task-specific modules as needed
```

---

## 📌 Current Limitations and Future Extensions

Current limitations do not block v1.1 usage.

Future extensions may include:

* More text prompt templates;
* More video cases;
* More OpenClaw workflow cases;
* Multi-Agent collaboration template;
* Real generation result reviews;
* Reference image / first-frame / last-frame cases;
* Audio / subtitle / voice-over prompt module;
* GitHub-specific packaging improvements;
* More English documentation.

---

## 📜 Release and Acceptance

| Document                                                           | Purpose                                  |
| ------------------------------------------------------------------ | ---------------------------------------- |
| [RELEASE_NOTES_v1.0.md](RELEASE_NOTES_v1.0.md)                     | v1.0 base release notes                  |
| [RELEASE_NOTES_v1.1.md](RELEASE_NOTES_v1.1.md)                     | v1.1 full capability release notes       |
| [FINAL_ACCEPTANCE_REPORT_v1.1.md](FINAL_ACCEPTANCE_REPORT_v1.1.md) | Final acceptance report                  |
| [HANDOFF_PROMPT-KB_v1.1.md](HANDOFF_PROMPT-KB_v1.1.md)             | Handoff guide for new Agent environments |

---

## ⭐ If this project helps you

If Prompt-KB helps you organize, evaluate, or reuse AI prompts, feel free to star the repository.

A star helps more people discover structured prompt engineering workflows.

---

## 🪪 License

License is not specified yet.

Recommended options:

* MIT License: simple and open for broad reuse;
* CC BY 4.0: suitable for knowledge documents with attribution;
* CC BY-NC 4.0: suitable if you want to restrict commercial use.

Before making this repository public, it is recommended to add a `LICENSE` file.

---

## 🛣 Roadmap

| Area                       | Status        |
| -------------------------- | ------------- |
| Text prompt foundation     | ✅ Completed   |
| Config standards           | ✅ Completed   |
| Image prompt module        | ✅ Completed   |
| Video prompt module        | ✅ Completed   |
| Agent workflow module      | ✅ Completed   |
| Release notes              | ✅ Completed   |
| Final acceptance report    | ✅ Completed   |
| Handoff guide              | ✅ Completed   |
| GitHub README optimization | ✅ In progress |
| License                    | ⏳ Recommended |
| CONTRIBUTING.md            | ⏳ Optional    |
| SECURITY.md                | ⏳ Optional    |
| More examples              | ⏳ Optional    |

---

## 🧾 Version History

This README keeps a short version summary. For release-level details, see:

* [RELEASE_NOTES_v1.0.md](RELEASE_NOTES_v1.0.md)
* [RELEASE_NOTES_v1.1.md](RELEASE_NOTES_v1.1.md)
* [FINAL_ACCEPTANCE_REPORT_v1.1.md](FINAL_ACCEPTANCE_REPORT_v1.1.md)

| Version             | Date       | Summary                                                                                                                                 |
| ------------------- | ---------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| v2.21.0             | 2026-06-02 | Optimized README for GitHub public release, added external-facing introduction, quick start, examples, module map, and sharing guidance |
| v2.20.0             | 2026-05-28 | Prompt-KB v1.1 officially released; Phase 1-5 completed; project entered daily use and on-demand extension stage                        |
| v2.19.0             | 2026-05-27 | Created v1.1 release notes and finalized release preparation                                                                            |
| v2.18.0             | 2026-05-27 | Completed Phase 5 stage closure and entered final acceptance / release preparation                                                      |
| v2.17.0 and earlier | 2026-05    | See release notes and repository history for full details                                                                               |

---

## Maintainer

Maintained by **KB-Admin**.

Prompt-KB v1.1 is released and ready for daily use.
