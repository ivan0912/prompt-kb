# 图像生成提示词知识库

> **版本**: v1.9.0
> **创建日期**: 2026-05-14
> **最近更新**: 2026-05-27（修正 Phase 4 状态，确保图像模块 README 与项目总状态一致）
> **用途**: 统一管理所有图像生成提示词模板和技巧

---

## 模块索引

| 规范 | 编号 | 文件 | 类型 | 状态 |
|------|------|------|------|------|
| **Prompt-KB 图像提示词基础规范** | T-IMG-001 | [image-prompt-foundation.md](image-prompt-foundation.md) | 图像提示词基础规范 | ✅ v0.2 正式版 |
| **T-IMG-001 图像提示词速查卡** | — | [image-prompt-quick-reference.md](image-prompt-quick-reference.md) | 速查卡 / quick-reference | ✅ v0.2 已通过轻量验收 |
| **T-IMG-002 图像提示词平台适配模板** | T-IMG-002 | [templates/image-platform-adaptation-template.md](templates/image-platform-adaptation-template.md) | 平台适配模板 | ✅ v0.1 已通过质量验收 |

> **Phase 3 状态**: ✅ 已完成阶段性闭环（7 个交付物完成） → Phase 4 视频提示词模块 ✅ 已完成阶段性闭环

---

### T-IMG-001 图像提示词基础规范

**关联规范**：T-IMG-001｜Prompt-KB 图像提示词基础规范

**文件**：image-prompt-foundation.md

**版本**：v0.2 正式版

**用途**：作为 Phase 3 图像提示词模块的底层规范，统一图像生成提示词的完整结构和规则

**适用场景**：
- 文生图提示词
- 封面图
- 海报图
- 产品图
- 插画图
- 头像 / 角色图
- 场景概念图
- 社交媒体配图
- 带参考图的图像生成任务

**不适用场景**：
- 视频生成
- 严格工程制图
- 需要精确文字排版的设计稿
- 需要真实人物身份还原的任务
- 高风险或侵权图像生成任务

---

### T-IMG-001 图像提示词速查卡

**关联规范**：T-IMG-001｜Prompt-KB 图像提示词基础规范

**文件**：image-prompt-quick-reference.md

**版本**：v0.2

**状态**：已通过轻量验收（结论 A：通过）

**类型**：速查卡 / quick-reference

**用途**：作为日常快速写图像提示词、优化提示词和检查提示词完整性的入口

**覆盖内容**：
- 图像提示词核心公式
- 15 维度速查表
- 标准输入区（6 块）
- 标准输出区（10 项）
- L1-L5 图像任务复杂度速查
- 常用描述词速查
- 负面提示词速查
- 口语需求转图像提示词模板（10 项输出结构）
- 优化已有图像提示词模板（8 项输出结构）
- 图像提示词验收清单（18 项）
- 常见错误速查
- 推荐使用流程

**适用场景**：
- 快速把口语需求转成图像提示词
- 快速优化已有图像提示词
- 快速检查提示词是否缺主体、场景、风格、构图、光线、色彩、负面提示词等
- 快速查找常用描述词
- 快速查看负面提示词
- 快速判断图像任务复杂度

**与完整规范的关系**：
- image-prompt-quick-reference.md 是日常使用入口
- image-prompt-foundation.md 是完整基础规范
- quick-reference 不替代完整规范
- 平台参数以后续平台适配模板为准

---

### T-IMG-002 图像提示词平台适配模板

**关联规范**：T-IMG-002｜图像提示词平台适配模板

**文件**：templates/image-platform-adaptation-template.md

**版本**：v0.1

**状态**：已通过质量验收（结论 A：通过）

**类型**：平台适配模板

**关联基础规范**：T-IMG-001｜image-prompt-foundation.md

**关联速查卡**：image-prompt-quick-reference.md

**关联案例**：CS-IMG-001｜../06-case-studies/cs-img-001-prompt-kb-cover-image.md

**用途**：将通用图像提示词改写为不同平台适配版本

**覆盖平台**：
- ChatGPT Images
- 豆包
- Midjourney
- Stable Diffusion
- Flux
- Hugging Face 图像模型

**覆盖内容**：
- 标准输入区（7 字段）
- 平台适配总原则（8 条）
- 6 平台适配规则及输出结构
- 多平台输出模板（12 区块）
- 平台适配检查清单（12 项）
- 常见错误（10 项）
- 与现有文件关系（6 项）

**适用场景**：
- 同一个图像需求要在多个平台测试
- 已有通用提示词，需要改写为平台版本
- 需要比较不同平台输出差异
- 需要为图像案例生成平台适配版本
- 需要避免跨平台误用参数

---

## 目录结构

```
03-image-prompts/
├── README.md                         # 本文件
├── image-prompt-foundation.md        # T-IMG-001 v0.2 正式版（图像提示词基础规范）
├── image-prompt-quick-reference.md   # T-IMG-001 速查卡 v0.2（已通过轻量验收）
├── templates/
│   ├── image-platform-adaptation-template.md  # T-IMG-002 v0.1（已通过质量验收）
│   ├── 00-image-template.md          # 标准图像提示词模板
│   ├── portrait-photorealistic.md
│   ├── landscape-nature.md
│   ├── product-commercial.md
│   
├── _templates/
│   └── 00-image-template.md          # 图像提示词内部参考模板（非正式产物）
│   └── character-design.md
├── _style-guides/
│   ├── photography-styles.md         # 摄影风格指南
│   ├── art-styles.md                 # 艺术风格指南
│   ├── illustration-styles.md        # 插画风格指南
│   └── anime-styles.md              # 动漫风格指南
├── _case-studies/
│   └── [按工具或主题分类存放]
└── _tools/
    ├── chatgpt-images.md             # ChatGPT Images 专项
    ├── midjourney.md                 # Midjourney 专项
    ├── stable-diffusion.md           # Stable Diffusion 专项
    ├── flux.md                       # Flux 专项
    ├── huggingface.md                # Hugging Face 专项
    └── doubao.md                     # 豆包图像专项
```

---

## 支持的工具

| 工具 | 类型 | 特点 | 推荐模板风格 |
|------|------|------|--------------|
| ChatGPT Images (DALL-E 3) | 多模态生成 | 文字理解强，构图精准 | 写实、插画、概念艺术 |
| Midjourney | AI 生图 | 艺术感强，风格多样 | 油画、水彩、概念设计 |
| Stable Diffusion | 开源模型 | 可本地部署，定制性强 | 所有风格 |
| Flux | 新兴模型 | 细节丰富，写实强 | 写实、摄影 |
| Hugging Face | 模型集合 | 社区资源丰富 | 各类型 |
| 豆包图像 | 国产工具 | 中文理解好 | 国风、东方美学 |

---

## 图像提示词核心维度

### 1. 主体 (Subject)
- 人物/角色
- 动物
- 物体/产品
- 场景/环境
- 抽象概念

### 2. 场景 (Scene/Environment)
- 室内/室外
- 具体地点（咖啡馆、办公室、森林）
- 时间（白天、夜晚、日落）
- 天气（晴天、雨天、雪天）

### 3. 风格 (Style)
| 类别 | 风格示例 |
|------|----------|
| 摄影 | 写实、纪实、风光、人像 |
| 艺术 | 油画、水彩、素描、版画 |
| 设计 | 扁平化、极简、孟菲斯 |
| 插画 | 商业插画、儿童插画、国风 |
| 动漫 | 日系、美系、写实系 |
| 概念 | Sci-Fi、Fantasy、Cyberpunk |

### 4. 构图 (Composition)
- 三分法 (Rule of Thirds)
- 中心构图
- 对角线构图
- 框架构图
- 引导线构图

### 5. 光线 (Lighting)
- 自然光（阳光、阴天、光晕）
- 人造光（柔光箱、霓虹、烛光）
- 戏剧光（伦勃朗光、蝴蝶光）
- 氛围光（边缘光、轮廓光）

### 6. 色彩 (Color)
- 色调（暖色调、冷色调）
- 配色方案（单色、互补、邻近）
- 饱和度（高饱和、低饱和）
- 色彩情绪（活力、忧郁、神秘）

### 7. 细节 (Details)
- 纹理/材质
- 景深（浅景深、深景深）
- 清晰度
- 颗粒感

### 8. 负面提示词 (Negative Prompt)
- 不想要的内容
- 画质问题（模糊、噪点）
- 风格问题（变形、失真）

---

## 工具专项说明

### ChatGPT Images
- **优势**: 文字理解准确，复杂场景描述效果好
- **劣势**: 不支持负面提示词
- **技巧**: 使用自然语言精确描述场景

### Midjourney
- **优势**: 艺术感强，风格多样
- **劣势**: 随机性较大
- **技巧**: 善用 `--ar` 参数控制比例，用 `--style` 控制风格

### Stable Diffusion
- **优势**: 可本地部署，定制性强
- **劣势**: 需要调参
- **技巧**: 配合 ControlNet、LoRA 使用

### Flux
- **优势**: 细节丰富，人体结构好
- **劣势**: 资源消耗大
- **技巧**: 提示词要详细具体

### 豆包图像
- **优势**: 中文理解好，国风/东方美学
- **劣势**: 国际风格支持相对弱
- **技巧**: 中文提示词效果更好

---

## 标准化流程

### 1. 需求分析
- 明确用途（商业/个人/项目）
- 确定目标受众
- 选择合适工具

### 2. 提示词构建
- 主体 → 场景 → 风格 → 构图 → 光线 → 色彩 → 细节
- 添加负面提示词（如支持）

### 3. 参数设置
- 尺寸比例
- 质量参数
- 风格参数

### 4. 生成与迭代
- 首轮生成评估
- 根据结果调整
- 迭代优化

### 5. 结果归档
- 保存成功提示词
- 记录失败教训
- 归入对应分类

---

*此目录专门存放图像生成提示词，与文本提示词完全分离。*

---

## 相关案例

### CS-IMG-001｜Prompt-KB 知识库封面图提示词案例

- **文件**: [../06-case-studies/cs-img-001-prompt-kb-cover-image.md](../06-case-studies/cs-img-001-prompt-kb-cover-image.md)
- **版本**: v0.2
- **状态**: 已通过轻量验收
- **类型**: 图像提示词实战案例
- **关联规范**: T-IMG-001
- **关联速查卡**: image-prompt-quick-reference.md
- **说明**: 使用 T-IMG-001 和 quick-reference，完成从原始需求到最终提示词和验收结论的完整闭环。覆盖 15 维度拆解、中英文提示词、负面提示词、3 个变体、平台适配建议。

> 建议先阅读 T-IMG-001 和 quick-reference，再查看 CS-IMG-001，理解完整使用流程。

### CS-IMG-002｜极简智能水杯产品主视觉图提示词案例

- **文件**: [../06-case-studies/cs-img-002-product-hero-image.md](../06-case-studies/cs-img-002-product-hero-image.md)
- **版本**: v0.1
- **状态**: 已通过轻量验收
- **类型**: 图像提示词实战案例 / 产品图案例
- **关联规范**: T-IMG-001
- **关联速查卡**: image-prompt-quick-reference.md
- **关联平台适配模板**: T-IMG-002
- **说明**: 使用 T-IMG-001、quick-reference 和 T-IMG-002，完成从产品图原始需求到中英文提示词、负面提示词、3 个变体（极简白底 / 办公桌面场景 / 科技感健康生活）、平台适配建议和验收结论的完整流程。15 维度拆解 15/15 全部明确，quick-reference 验收清单 17/17 全部通过。

> CS-IMG-001 适合参考「抽象概念图 / 知识库封面图」，CS-IMG-002 适合参考「实体产品图 / 商业摄影图」。

### CS-IMG-003｜多人物户外场景图（野钓聚会）提示词案例

- **文件**: [../06-case-studies/cs-img-003-fishing-gathering.md](../06-case-studies/cs-img-003-fishing-gathering.md)
- **版本**: v0.1
- **状态**: 已完成脱敏整理
- **类型**: 图像提示词实战案例 / 多人物户外场景图案例
- **关联规范**: T-IMG-001
- **关联速查卡**: image-prompt-quick-reference.md
- **说明**: 验证 T-IMG-001 和 quick-reference 在多人物、特定地域、复杂场景下的可用性。15 维度拆解 15/15 全部明确，quick-reference 验收清单 17/17 全部通过。含 3 个变体（温馨家庭时光 / 老同学叙旧 / 野钓全景）。

> CS-IMG-001 覆盖「抽象概念图」，CS-IMG-002 覆盖「实体产品图」，CS-IMG-003 覆盖「多人物户外场景图」，三者形成完整的图像类型互补。

### TEST-IMG-002-001｜CS-IMG-001 平台适配测试

- **文件**: [../06-case-studies/cs-img-001-platform-adaptation-test.md](../06-case-studies/cs-img-001-platform-adaptation-test.md)
- **版本**: v0.1
- **状态**: 已完成 / 已通过平台适配检查
- **类型**: 平台适配测试记录
- **关联模板**: T-IMG-002｜[templates/image-platform-adaptation-template.md](templates/image-platform-adaptation-template.md)
- **关联案例**: CS-IMG-001｜[../06-case-studies/cs-img-001-prompt-kb-cover-image.md](../06-case-studies/cs-img-001-prompt-kb-cover-image.md)
- **说明**: 使用 CS-IMG-001 测试 T-IMG-002，生成 ChatGPT Images、豆包、Midjourney、Stable Diffusion、Flux 和 Hugging Face 六个平台适配版本，12 项平台适配检查全部通过。

> 建议先阅读 T-IMG-001 和 quick-reference，再查看 CS-IMG-001，最后查看 TEST-IMG-002-001，理解「通用图像提示词 → 平台适配版本」的完整流程。

### TEST-IMG-002-002｜CS-IMG-002 产品图平台适配测试

- **文件**: [../06-case-studies/cs-img-002-platform-adaptation-test.md](../06-case-studies/cs-img-002-platform-adaptation-test.md)
- **版本**: v0.1
- **状态**: 已完成 / 已通过平台适配检查
- **类型**: 平台适配测试记录 / 产品图平台适配测试
- **关联模板**: T-IMG-002｜[templates/image-platform-adaptation-template.md](templates/image-platform-adaptation-template.md)
- **关联案例**: CS-IMG-002｜[../06-case-studies/cs-img-002-product-hero-image.md](../06-case-studies/cs-img-002-product-hero-image.md)
- **参考测试**: TEST-IMG-002-001｜[../06-case-studies/cs-img-001-platform-adaptation-test.md](../06-case-studies/cs-img-001-platform-adaptation-test.md)
- **说明**: 使用 CS-IMG-002 测试 T-IMG-002，生成 ChatGPT Images、豆包、Midjourney、Stable Diffusion、Flux 和 Hugging Face 六个平台适配版本，并通过扩展后的平台适配检查清单（15 项全部通过，N/A 1 项）。

> TEST-IMG-002-001 验证抽象概念图的平台适配，TEST-IMG-002-002 验证产品主视觉图的平台适配，两者共同证明 T-IMG-002 具备跨图像类型迁移能力。

---

## 后续建议

### 已完成（Phase 3 收尾）

1. ✅ T-IMG-001 图像提示词基础规范 v0.2；
2. ✅ image-prompt-quick-reference 图像提示词速查卡 v0.2；
3. ✅ CS-IMG-001 知识库封面图案例 v0.2；
4. ✅ T-IMG-002 图像提示词平台适配模板 v0.1；
5. ✅ TEST-IMG-002-001 封面图平台适配测试；
6. ✅ CS-IMG-002 产品主视觉图案例 v0.1；
7. ✅ TEST-IMG-002-002 产品图平台适配测试。

Phase 3 已形成「规范 → 速查 → 案例 → 平台适配 → 测试」的完整闭环，三条子闭环（基础图像提示词闭环、平台适配闭环、案例验证闭环）全部成立。

### 后续可按需扩展（不阻塞 Phase 4）

- 人物 / 角色图案例；
- 场景概念图案例；
- 社交媒体配图案例；
- 参考图输入案例；
- 图像编辑 / 局部重绘案例；
- 平台专项模板。

### 当前焦点

**Prompt-KB v1.1 正式发布整理**（Phase 3-5 全部完成阶段性闭环）
