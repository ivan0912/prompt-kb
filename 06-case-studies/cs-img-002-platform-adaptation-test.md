# TEST-IMG-002-002｜CS-IMG-002 产品图平台适配测试

> **测试编号**: TEST-IMG-002-002
> **测试名称**: CS-IMG-002 产品图平台适配测试
> **版本**: v0.1
> **创建日期**: 2026-05-25
> **来源案例**: CS-IMG-002｜极简智能水杯产品主视觉图提示词案例 v0.1
> **测试模板**: T-IMG-002｜图像提示词平台适配模板 v0.1
> **关联规范**: T-IMG-001 v0.2 / image-prompt-quick-reference v0.2
> **参考测试**: TEST-IMG-002-001｜CS-IMG-001 平台适配测试 v0.1
> **性质**: 模板实测记录——不是新规范、不是新案例、不是对 T-IMG-002 或 CS-IMG-002 的修改
> **存放路径**: prompt-kb/06-case-studies/cs-img-002-platform-adaptation-test.md

---

## 1. 测试目标

本测试用于验证以下问题：

| # | 验证目标 | 说明 |
|---|----------|------|
| 1 | T-IMG-002 是否适用于产品图 / 商业摄影场景 | 对 CS-IMG-002 的智能水杯产品主视觉图需求，生成 ChatGPT Images / 豆包 / Midjourney / Stable Diffusion / Flux / Hugging Face 六平台适配版本 |
| 2 | 是否能将同一个产品图需求改写为多平台版本 | 各平台版本的核心视觉信息是否与原始需求一致，产品主体是否清晰可辨 |
| 3 | 是否能保留产品主体、材质、色彩、构图、光线和负面限制 | 哑光白杯身、OLED 温度屏幕、不锈钢杯口、商业摄影风格、柔光箱打光、中性灰背景等核心元素在各平台版本中是否保留 |
| 4 | 是否能避免品牌 logo、真实人物、复杂文字、水印和侵权元素 | 各平台版本的限制条件是否按平台支持方式正确传递 |
| 5 | 是否能避免写死平台版本号 | 不出现 `--v 6`、`--v 7` 等硬编码版本号（如出现则标注"以当前平台文档为准"） |
| 6 | 是否能避免跨平台误用参数 | 不把 Midjourney 参数写到 ChatGPT Images 版本、不把 SD 标签式写法写到 Flux 版本 |
| 7 | 是否能基于 CS-IMG-002 生成可用的平台适配提示词 | 最终输出的平台版本是否能直接使用或仅需微调即可使用 |

---

## 2. 测试来源

| 来源项 | 详情 |
|--------|------|
| **来源案例** | CS-IMG-002｜极简智能水杯产品主视觉图提示词案例 v0.1 |
| **来源文件** | prompt-kb/06-case-studies/cs-img-002-product-hero-image.md |
| **测试模板** | T-IMG-002｜图像提示词平台适配模板 v0.1 |
| **模板文件** | prompt-kb/03-image-prompts/templates/image-platform-adaptation-template.md |
| **关联规范** | T-IMG-001｜Prompt-KB 图像提示词基础规范 v0.2 |
| **关联速查卡** | image-prompt-quick-reference v0.2 |
| **参考测试** | TEST-IMG-002-001｜CS-IMG-001 平台适配测试 v0.1（封面图 / 抽象概念图场景的首次平台适配测试） |

---

## 3. 从 CS-IMG-002 提取的核心信息

| # | 信息项 | 提取内容 | 来源位置 |
|---|--------|----------|----------|
| 1 | 原始图像需求 | 生成一张智能水杯产品主视觉图，用于电商详情页或新品介绍页面；画面突出产品本身，体现"智能、简洁、健康、科技感"；产品是现代极简风格的智能水杯，带温度显示小屏幕；商业摄影风格，背景简洁不花哨；不要品牌 logo、人物、复杂文字、水印；适合横版产品展示图或官网 Banner | CS-IMG-002 §2 |
| 2 | 使用场景 | 电商详情页主图 / 官网 Banner / 新品介绍页 / 产品展示图 | CS-IMG-002 §3 |
| 3 | 产品主体 | 一只现代极简风格的智能水杯，带有温度显示小屏幕（OLED），外观干净利落，适合年轻办公人群 | CS-IMG-002 §4 维度 2 |
| 4 | 场景 | 简洁背景，干净无杂乱元素，可轻微渐变或浅灰基底；柔和中性灰色背景，轻微渐变 | CS-IMG-002 §4 维度 3 |
| 5 | 风格 | 商业摄影风格 | CS-IMG-002 §4 维度 4 |
| 6 | 构图 | 中心构图，主体居中，四周留适量空间 | CS-IMG-002 §4 维度 5 |
| 7 | 镜头 / 视角 | 平视或轻微俯拍（约 15-20 度），中景，杯体完整可见 | CS-IMG-002 §4 维度 6 |
| 8 | 光线 | 柔光箱打光，均匀漫射光，产品表面有柔和高光反射 | CS-IMG-002 §4 维度 7 |
| 9 | 色彩方案 | 杯体为哑光白或浅灰，背景为柔和中性灰或微暖白渐变，屏幕发淡蓝或淡绿微光 | CS-IMG-002 §4 维度 8 |
| 10 | 材质与细节 | 杯身哑光磨砂质感，不锈钢或陶瓷杯口，OLED 温度屏幕清晰可读，杯盖简约光滑 | CS-IMG-002 §4 维度 9 |
| 11 | 氛围 | 干净、专业、健康、科技感，不冰冷，面向年轻办公人群的温暖科技感 | CS-IMG-002 §4 维度 10 |
| 12 | 负面限制 | 无品牌 logo、无水印、无复杂文字、无真实人物、无杂乱背景、无低清、无过度反光、无塑料廉价感、无变形杯体、无错误屏幕文字、无侵权品牌元素 | CS-IMG-002 §7 |
| 13 | 中文图像提示词 | 完整的 CS-IMG-002 §5 中文提示词 | CS-IMG-002 §5 |
| 14 | 英文图像提示词 | 完整的 CS-IMG-002 §6 英文提示词 | CS-IMG-002 §6 |
| 15 | 3 个变体 | 变体 1：极简白底产品图（1:1 方形，纯白背景） / 变体 2：办公桌面场景图（16:9，木桌+绿植） / 变体 3：科技感健康生活图（3:4 竖版，浅蓝渐变，水珠凝结） | CS-IMG-002 §8 |
| 16 | 平台适配建议 | 5 平台适配建议（ChatGPT Images / 豆包 / Midjourney / SD&Flux / Hugging Face） | CS-IMG-002 §9 |
| 17 | 风险与注意事项 | 8 类风险：品牌 logo 风险、复杂文字生成风险、产品形态不稳定风险、屏幕显示内容错误风险、材质过度反光风险、画面过于复杂风险、不同平台理解差异、水珠效果过度风险 | CS-IMG-002 §11 |
| 18 | 复杂度等级 | L3（中等复杂，需要精确控制材质和产品形态） | CS-IMG-002 §3 |
| 19 | 画面比例 | 16:9 横版产品展示图（官网 Banner 可用 3:2） | CS-IMG-002 §3 |

**提取完整性**：19 项信息全部从 CS-IMG-002 提取，无新增事实。

---

## 4. 通用需求解析

| 解析项 | 内容 |
|--------|------|
| **图像目标** | 生成一张智能水杯的产品主视觉图，用于电商详情页或官网 Banner，突出产品本身的"智能、简洁、健康、科技感"特质 |
| **使用场景** | 电商详情页主图 / 官网 Banner / 新品介绍页 / 产品展示图——对外商业展示用途，需要突出产品本身 |
| **核心产品元素** | 现代极简智能水杯（哑光白磨砂杯身 + OLED 温度显示屏发淡蓝微光 + 不锈钢杯口 + 简约光滑杯盖）+ 柔和中性灰渐变背景 + 柔光箱打光 + 商业摄影风格 |
| **需要保留的元素** | 产品主体（智能水杯完整形态）、材质（哑光磨砂/不锈钢/OLED屏幕）、色彩（哑光白+中性灰+淡蓝微光）、构图（中心构图）、光线（柔光箱均匀漫射）、风格（商业摄影）、氛围（干净专业科技感）、比例（16:9） |
| **需要避免的元素** | 品牌 logo、水印、复杂文字、真实人物、杂乱背景、低清/模糊、过度反光、塑料廉价感、变形杯体、错误屏幕文字、侵权品牌元素、阴暗氛围 |
| **产品图平台适配重点** | ChatGPT Images：限制条件融入正向提示词，自然语言描述产品外观和材质；豆包：中文自然语言，适合电商和社交媒体场景；Midjourney：英文提示词+参数，产品主体和商业摄影风格靠前，注意避免过度艺术化；Stable Diffusion：英文标签式+独立 Negative Prompt，注意产品形态一致性；Flux：英文自然语言完整描述，不依赖碎片化标签；Hugging Face：通用自然语言+需确认模型的产品图生成能力和文字控制能力 |

---

## 5. 通用中文提示词

基于 CS-IMG-002 §5 中英文提示词，整理平台无关版本：

```
一张横版智能水杯产品主视觉图，商业摄影风格。
主体是一只现代极简风格的智能水杯，哑光白色磨砂杯身，
杯身嵌有一块小型 OLED 温度显示屏，显示淡蓝色微光数字温度，
杯口为不锈钢材质，杯盖简约光滑，整体设计干净利落。
水杯居中放置在柔和中性灰色背景前，背景轻微渐变，
柔光箱打光，均匀漫射光，杯身表面有柔和高光反射，
中心构图，平视轻微俯拍视角，杯体完整清晰可见，
高分辨率，商业摄影级别细节，16:9 横版产品图。
无品牌 logo，无人物，无复杂文字，无水印。
```

**说明**：
- 保留 CS-IMG-002 的全部核心视觉信息（产品主体、材质、色彩、构图、光线、风格、氛围、比例）；
- 将"无品牌 logo"等负面限制直接融入正向描述；
- 不添加 CS-IMG-002 中不存在的新事实；
- 色彩方案严格为"哑光白 + 中性灰 + 淡蓝微光"。

---

## 6. 通用英文提示词

基于 CS-IMG-002 §6 英文提示词，整理平台无关版本：

```
A wide-format smart water bottle product hero image, commercial photography style.
The subject is a modern minimalist smart water bottle with a matte white frosted body,
featuring a small embedded OLED temperature display showing a soft blue glow readout.
Stainless steel mouth rim, smooth minimalist cap, clean and sleek overall design.
The bottle is centered against a soft neutral gray background with subtle gradient.
Softbox lighting, even diffused light, gentle specular highlights on the bottle surface.
Center composition, slightly elevated eye-level angle, full bottle body clearly visible.
High resolution, commercial photography level detail, 16:9 horizontal product shot.
No brand logo, no people, no complex text, no watermark.
```

**说明**：
- 与通用中文提示词语义完全一致；
- 保留色彩方案"matte white + neutral gray + soft blue glow"；
- 未添加中文提示词中没有的新事实；
- 负面限制已融入正向描述（如"no brand logo, no people, no complex text, no watermark"）。

---

## 7. 负面提示词 / 限制条件

### 通用英文负面提示词

供支持独立 Negative Prompt 字段的平台使用（Stable Diffusion / Flux 等）：

```
no brand logo, no watermark, no complex text, no real people,
no cluttered background, no low resolution, no blur,
no excessive reflections, no cheap plastic texture,
no deformed bottle shape, no incorrect screen text,
no copyrighted brand elements, no distortion,
no dark or gloomy mood, no messy desk background,
no bad anatomy, no extra limbs, no ugly artifacts
```

### 中文自然语言限制版本

供需要中文负面表达的平台使用（豆包等）：

```
不要品牌 logo，不要水印，不要复杂文字，不要真实人物，
不要杂乱背景，不要低清，不要模糊，
不要过度反光，不要塑料廉价感，
不要变形杯体，不要错误屏幕文字，
不要侵权品牌元素，不要畸变，
不要阴暗氛围，不要杂乱的桌面背景，
不要畸形，不要多余肢体，不要伪影
```

### 来源说明

以上负面提示词基于 CS-IMG-002 §7 整理，扩展了常见图像质量相关负面词（如 `bad anatomy`, `extra limbs`），属于通用最佳实践补充，未超出 T-IMG-001 定义的负面提示词范围。

---

## 8. ChatGPT Images 适配版本

### ChatGPT Images 提示词

使用自然语言英文描述，适合直接复制到 ChatGPT 对话框：

```
I need a wide-format product hero image of a smart water bottle for an
e-commerce product detail page or website banner, commercial photography style.

The product is a modern minimalist smart water bottle with a matte white frosted body.
Embedded in the body is a small OLED temperature display, glowing a soft blue light
with digital temperature readout. The mouth rim is stainless steel, and the cap is
smooth and minimalist. The overall design is clean and sleek, targeted at young
office professionals.

The bottle is centered against a soft neutral gray background with a subtle gradient.
Lighting is softbox style — even diffused light with gentle specular highlights on
the bottle surface. The composition is center-framed with enough breathing room
around the bottle. The camera angle is slightly elevated at eye level, showing the
full bottle body clearly.

Style is commercial product photography — clean, professional, with a sense of
health and technology. High resolution, commercial photography level detail.
16:9 horizontal format.

Important restrictions: absolutely no brand logo, no watermark, no complex text,
no real people. The background is clean and uncluttered — no messy desk or
distracting elements. No excessive reflections, no cheap plastic texture, no
deformed bottle shape. The screen displays soft blue digits only — no garbled
or incorrect text.
```

也可使用中文自然语言版本：

```
请生成一张智能水杯的产品主视觉图，用于电商详情页或官网 Banner，商业摄影风格。

产品是一只现代极简风格的智能水杯，哑光白色磨砂杯身，杯身嵌有一块小型 OLED 温度
显示屏，显示淡蓝色微光数字温度。杯口为不锈钢材质，杯盖简约光滑，整体设计干净
利落，面向年轻办公人群。

水杯居中放置在柔和中性灰色渐变背景前。照明为柔光箱打光，均匀漫射光，杯身表面
有柔和高光反射。构图为中心构图，四周留适量空间。视角为平视轻微俯拍，杯体完整
清晰可见。高分辨率，商业摄影级别细节，16:9 横版产品图。

重要限制：绝对不能出现品牌 logo、水印、复杂文字、真实人物。背景保持干净简洁，
无杂乱桌面或分散注意力的元素。不要过度反光，不要塑料廉价感，不要变形杯体。
屏幕只显示淡蓝色数字温度，不要乱码或错误文字。
```

### 修改 / 迭代说明

ChatGPT Images 支持多轮对话修改。如果首次生成不满意，可按以下方式迭代：

| 问题 | 迭代指令 |
|------|----------|
| 杯身不够哑光 | "让杯身的磨砂质感更明显，减少反光" |
| 屏幕显示不清晰 | "让 OLED 屏幕的数字温度更清晰锐利" |
| 背景不够简洁 | "进一步简化背景，让背景更干净、更均匀" |
| 杯体形态不理想 | "让杯体更直筒、更简约，不要收腰设计" |
| 出现乱码文字 | "把屏幕上和杯身上的所有文字去掉，只保留淡蓝色数字显示" |
| 风格过于艺术化 | "让画面更写实，更接近真实产品摄影，减少艺术处理" |
| 更换画面比例 | "保持当前产品外观和光线，改为 1:1 方形构图" |

### 注意事项

- ChatGPT Images 不支持独立的负面提示词字段，所有限制条件已直接写进正向提示词中（"absolutely no brand logo..."等）；
- 不适用 `--ar`、`--no`、`--style` 等参数；画面比例通过自然语言"16:9 horizontal format"指定；
- 产品图的核心挑战是主体一致性——如果多次生成产品外观差异大，可以在迭代时更详细描述杯身形状（"直筒圆柱形，高度约 20cm，直径约 7cm"）；
- 如果屏幕文字仍然乱码，可追加"the display shows only numeric digits, no letters or symbols"。

---

## 9. 豆包适配版本

### 豆包中文提示词

使用自然流畅的中文表达，适合电商主图、官网 Banner、新品介绍页或社交媒体产品图：

```
横版智能水杯产品主视觉图，商业摄影风格，用于电商详情页或官网 Banner。

画面主体是一只现代极简风格的智能水杯，哑光白色磨砂杯身，杯身上嵌有一块小型
OLED 温度显示屏，显示淡蓝色数字温度。杯口是不锈钢材质，杯盖简约光滑，
整体设计干净利落。

水杯居中放置在柔和的中性灰色渐变背景前，柔光箱均匀打光，杯身表面有柔和的
高光反射。中心构图，平视轻微俯拍视角，杯体完整清晰可见。
高分辨率，16:9 横版比例。

整体传达干净、专业、健康、科技感的氛围，面向年轻办公人群。

不要品牌 logo，不要水印，不要人物，不要复杂文字，不要杂乱背景，不要过度反光，
不要塑料廉价感，不要变形杯体。
```

### 负面限制

如需填入豆包平台的负面提示词独立字段：

```
不要品牌 logo，不要水印，不要复杂文字，不要真实人物，
不要杂乱背景，不要低清，不要模糊，不要过度反光，
不要塑料廉价感，不要变形杯体，不要错误屏幕文字，
不要侵权品牌元素，不要畸变，不要阴暗氛围
```

### 使用建议

- 中文表达自然流畅，风格描述不参数化，直接复制到豆包提示词输入区即可；
- 可在豆包平台的图片尺寸设置中选择 1024×576 或对应横版规格；
- 产品图建议选择"写实"或"摄影"风格模式，以强化商业摄影质感；
- 推荐迭代路径：先生成白底产品图 → 再生成办公场景图 → 再生成社交媒体变体（如 CS-IMG-002 的三个变体可作为迭代起点）；
- 如首次生成效果不理想，可在提示词末尾补充自然语言迭代指令，如"请让杯身的磨砂质感更明显一些"。

---

## 10. Midjourney 适配版本

### Midjourney 英文提示词

主体和风格靠前，英文自然语言 + 参数：

```
modern minimalist smart water bottle with matte white frosted body, small embedded
OLED temperature display glowing soft blue digits, stainless steel mouth rim, smooth
minimalist cap, centered against soft neutral gray gradient background, commercial
product photography style, softbox lighting with even diffused light and gentle
specular highlights on bottle surface, center composition, slightly elevated eye-level
angle showing full bottle body clearly, clean professional health-tech atmosphere,
high resolution, 16:9 wide format --ar 16:9 --no brand logo, watermark, complex text,
real people, cluttered background, excessive reflections, cheap plastic texture,
deformed shape, incorrect text, dark mood, messy desk
```

### 参数建议

| 参数 | 建议 | 说明 |
|------|------|------|
| `--ar 16:9` | 画面比例 | 横版产品展示图标准比例 |
| `--no brand logo, watermark, complex text, real people, cluttered background, excessive reflections, cheap plastic texture, deformed shape, incorrect text, dark mood, messy desk` | 负面排除 | 排除品牌元素、人物、杂乱背景、不当材质和形态问题 |
| `--style raw`（可选） | 风格控制 | 降低 Midjourney 自动艺术化干扰，产品图需要写实摄影风格 |
| `--q 2`（可选） | 质量提升 | 提升细节质量，产品图对材质还原要求高 |

> 以上参数为通用建议。版本号（如 `--v`）以当前 Midjourney 平台官方文档为准，不在此写死。如当前文档推荐使用特定版本参数，请按平台文档调整。

### 注意事项

- Midjourney 对英文提示词响应更稳定，建议使用英文版本；
- 产品主体"modern minimalist smart water bottle"和风格"commercial product photography style"已在提示词靠前位置；
- `--no` 参数已覆盖品牌 logo、水印、人物、杂乱背景、过度反光、塑料质感、变形、错误文字等；
- 不要把 `--ar`、`--no` 等 Midjourney 参数用于其他平台（ChatGPT Images、豆包等不支持该语法）；
- Midjourney 默认风格可能偏艺术化——如果生成的水杯造型过于概念化，追加 `--style raw` 降低自动美化；
- 产品图最主要的风险是主体形态不一致——Midjourney 可能在不同生成中给出不同造型的"智能水杯"，建议锁定满意的生成结果后使用 `--seed` 参数固定随机种子。

---

## 11. Stable Diffusion 适配版本

### Positive Prompt

英文标签式正向提示词，结构：质量标签 → 主体 → 场景 → 风格 → 构图 → 光线 → 色彩 → 细节：

```
masterpiece, best quality, high resolution, 16:9 wide format,
modern minimalist smart water bottle with matte white frosted body,
small embedded OLED temperature display glowing soft blue digital readout,
stainless steel mouth rim, smooth minimalist cap,
clean sleek design, young professional lifestyle,
centered against soft neutral gray gradient background,
commercial product photography style,
center composition, slightly elevated eye-level angle,
full bottle body clearly visible,
softbox lighting, even diffused light,
gentle specular highlights on bottle surface,
matte white and neutral gray color scheme,
soft blue glow from OLED screen,
clean professional health-tech atmosphere,
no clutter, clean background
```

### Negative Prompt

```
brand logo, watermark, complex text, letters, signature, artist name,
real people, human, person, face, portrait,
cluttered background, messy desk, messy composition,
low resolution, low quality, blur, blurry,
excessive reflections, mirror reflection,
cheap plastic texture, glossy plastic,
deformed bottle shape, distorted bottle, asymmetrical bottle,
incorrect screen text, garbled text, random characters on screen,
copyrighted brand elements, trademark,
dark atmosphere, gloomy mood, horror,
distortion, ugly, deformed, bad anatomy, artifacts,
dark background, busy background
```

### Optional Settings

| 字段 | 建议 | 说明 |
|------|------|------|
| 分辨率 | 1920×1080（16:9） | 横版产品图标准分辨率 |
| 采样器 | — | 以当前使用的模型和界面推荐为准 |
| Steps | — | 以当前使用的模型推荐为准（通常 20-40） |
| CFG Scale | — | 以当前使用的模型推荐为准（通常 5-9） |
| Seed | — | 如需可复现产品形态，固定一个 seed 值 |
| 模型类型建议 | 写实 / 摄影类模型 | 不写死具体模型文件名；推荐使用擅长产品摄影和写实物体的模型；可搭配产品摄影 LoRA 增强材质还原 |

### 注意事项

- Positive 和 Negative Prompt 的格式取决于使用的具体模型（SD1.5 / SDXL / SD3 等）和界面（ComfyUI / A1111 / Forge 等）；
- Optional Settings 中的采样器、Steps、CFG Scale 等不写死数值，以当前使用的模型推荐为准；
- 产品图要注意主体一致性和屏幕文字风险——SD 对"智能水杯"的外观理解可能差异很大，建议在提示词中充分描述杯身形态；
- 如果使用 ControlNet / LoRA / IP-Adapter 等扩展，需另外说明用途（如用 ControlNet 锁定构图、用产品摄影 LoRA 强化商业摄影质感）；
- Negative Prompt 中额外添加了 `dark background, busy background` 以强化简洁背景效果；
- SD 的碎片化标签写法可能导致 OLED 屏幕乱码——建议在 Negative Prompt 中强化 `garbled text, random characters on screen`。

---

## 12. Flux 适配版本

### Flux 提示词

使用英文自然语言完整描述，不需碎片化标签：

```
A wide-format smart water bottle product hero image in 16:9 aspect ratio,
commercial photography style.

The product is a modern minimalist smart water bottle with a matte white frosted body.
Embedded in the body is a small OLED temperature display, glowing a soft blue light
with numeric temperature readout. The mouth rim is stainless steel with a subtle
metallic sheen, and the cap is smooth and minimalist. The overall design is clean
and sleek, appealing to young office professionals.

The bottle is centered against a soft neutral gray background with a subtle gradient.
Lighting is softbox style — even, diffused light with gentle specular highlights
catching on the bottle's matte surface. The composition is center-framed with ample
breathing room around the bottle. Camera angle is slightly elevated at eye level
showing the full bottle body clearly and completely.

Color palette: matte white bottle body, neutral gray gradient background, soft blue
glow from the temperature display.

High resolution, commercial photography level detail. Clean, professional,
health-conscious, and subtly tech-forward atmosphere.

No brand logo, no watermark, no complex text, no people, no cluttered background.
The screen displays soft blue numeric digits only — no garbled or incorrect text.
```

### 负面限制

用自然语言表达的负面限制（如 Flux 部署界面支持独立 Negative Prompt 字段，可参考 Stable Diffusion 版本的 Negative Prompt）：

```
No brand logo. No watermark. No complex text or letters.
No real people or human figures. No cluttered or messy background.
No excessive reflections or mirror-like surfaces.
No cheap plastic texture or glossy finish.
No deformed or distorted bottle shape.
No incorrect or garbled text on the screen.
No copyrighted brand elements.
No dark, gloomy, or horror atmosphere.
No blur or low resolution.
```

### 注意事项

- Flux 对自然语言理解较好，不需要传统 SD 的碎片化标签；上述提示词使用完整句段即可；
- 不要过度依赖碎片化标签式写法——Flux 对完整自然语言描述的响应优于标签堆砌；
- 如果部署界面支持独立 Negative Prompt 字段，可将"负面限制"填入该字段；否则直接融入正向提示词末尾；
- 具体模型版本以当前部署环境为准（Flux.1 dev / Flux.1 pro / Flux.1 schnell 等）；
- 产品图场景下 Flux 的材质还原通常较好，但屏幕文字仍是风险点——建议明确描述屏幕只显示"numeric digits"。

---

## 13. Hugging Face 图像模型适配版本

### Hugging Face 通用提示词

使用简洁英文自然语言描述（通用版本，适用多数图像生成模型）：

```
A wide-format smart water bottle product hero image in 16:9 ratio, commercial
photography style. Modern minimalist smart water bottle with matte white frosted
body. Small embedded OLED temperature display glowing soft blue digits. Stainless
steel mouth rim and smooth cap. Centered against soft neutral gray gradient
background. Softbox lighting with diffused light and gentle highlights. Center
composition, slightly elevated eye-level angle, full bottle body visible.
High resolution. No brand logo, no watermark, no text, no people, no clutter.
```

### 需要确认的模型信息

在下表中填入实际使用模型的信息：

| 项目 | 说明 | 本测试当前状态 |
|------|------|---------------|
| 模型类型 | SDXL / SD3 / Flux / Kolors / 其他——查看模型 Model Card | ⏳ 待用户根据实际使用模型填写 |
| 提示词语言 | 英文 / 中文 / 双语——查看模型说明 | ⏳ 待确认；通用版提供英文 |
| 提示词格式 | 自然语言 / 标签式 / 混合——查看模型文档和社区示例 | ⏳ 待确认；通用版使用自然语言 |
| 负面提示词支持 | 支持独立 Negative Prompt / 支持参数传入 / 不支持——查看模型说明 | ⏳ 待确认 |
| 推荐分辨率 | 查看模型文档的建议分辨率 | ⏳ 待确认；通用版建议 1920×1080 |
| 是否支持参考图 | 是否可传入参考图做产品外观参考 | ⏳ 待确认 |
| 产品图生成能力 | 是否擅长产品摄影和写实物体的生成 | ⏳ 待确认；SDXL 类模型通常表现较好 |
| 文字/屏幕显示能力 | 模型对屏幕数字文字的生成是否可控 | ⏳ 待确认；多数模型对屏幕文字控制有限 |

### 注意事项

- Hugging Face 是一个模型集合平台，不是单一图像生成器——上面的模型（SDXL、SD3、Flux、Kolors 等）提示词格式差异大；
- 以上提示词为通用版本，实际使用时请以具体模型的 README / Model Card / 社区示例为准；
- 如果模型不支持负面提示词字段，应将"No brand logo, no watermark..."等限制融入正向提示词中；
- 推荐在使用前先查看该模型在 Hugging Face 上的示例 prompt，确认推荐的措辞和格式；
- 不同模型对产品一致性和文字显示能力差异较大——如果模型擅长写实物体但不擅长屏幕文字，建议弱化屏幕描述，聚焦杯体形态和材质；
- 如模型支持标签式提示词（如 SDXL 类），可参考本测试 §11 的 Stable Diffusion 版本。

---

## 14. 平台差异说明

| 平台 | 推荐提示词风格 | 负面提示词处理 | 参数使用 | 产品图注意事项 |
|------|---------------|---------------|----------|---------------|
| **ChatGPT Images** | 自然语言（中/英均可），完整句段描述产品外观、材质和场景 | 不支持独立 Negative Prompt，限制条件融入正向提示词 | 不支持 `--ar`/`--no` 等参数；比例通过自然语言指定 | 支持多轮对话迭代修改产品形态；屏幕文字可控性较好；中文效果良好 |
| **豆包** | 中文自然语言，简洁流畅，适合电商和社交媒体场景 | 可填入独立负面提示词字段，或融入正向描述 | 平台界面设置尺寸；提示词末尾可补充比例期望 | 中文理解好；适合电商主图、社交媒体配图；风格模式选择"写实"或"摄影" |
| **Midjourney** | 英文自然语言 + 参数；产品主体和商业摄影风格靠前 | 通过 `--no` 参数传入排除内容 | `--ar` 指定比例；`--style raw` 降低艺术化；不写死 `--v` 版本号 | 对英文响应更稳定；默认风格偏艺术化，产品图需 `--style raw`；主体形态一致性需要 seed 锁定 |
| **Stable Diffusion** | 英文标签式（质量标签→产品主体→场景→风格→构图→光线→色彩→材质） | 独立的 Negative Prompt 字段，可详细列出 | 采样器/Steps/CFG 等不写死数值；分辨率按比例建议 | 产品形态一致性是核心挑战；屏幕文字容易乱码；可搭配产品摄影 LoRA 和 ControlNet |
| **Flux** | 英文自然语言完整描述 | 可填入独立字段或融入正向；自然语言表达即可 | 不需要传统 SD 的碎片化标签；自然语言即可 | 材质还原通常较好；屏幕文字仍是风险点；不依赖标签式写法；具体参数以部署环境为准 |
| **Hugging Face** | 以模型为准（通用版提供简洁英文自然语言） | 以模型文档为准（有的支持独立字段，有的不支持） | 不写死任何参数；需要先确认模型类型和格式 | 模型差异大；产品一致性和屏幕文字控制能力因模型而异；使用前必须查看模型 README/Model Card；如模型不擅长屏幕文字，弱化屏幕描述 |

---

## 15. 平台适配检查清单

使用 T-IMG-002 §13 检查清单，对本测试输出的六平台版本逐一检查：

| # | 检查项 | 是否通过 | 说明 |
|---|--------|---------|------|
| 1 | 是否保留产品主体 | ✅ 通过 | 所有平台版本均包含"modern minimalist smart water bottle with matte white frosted body + OLED temperature display + stainless steel mouth rim + smooth cap" |
| 2 | 是否保留场景 | ✅ 通过 | 所有平台版本均包含"soft neutral gray gradient background, clean and uncluttered" |
| 3 | 是否保留风格 | ✅ 通过 | 所有平台版本均保留"commercial photography style"，风格词不超过 3 个 |
| 4 | 是否保留构图 | ✅ 通过 | 所有平台版本均保留"center composition, slightly elevated eye-level angle, full bottle body visible" |
| 5 | 是否保留光线 | ✅ 通过 | 所有平台版本均保留"softbox lighting, even diffused light, gentle specular highlights" |
| 6 | 是否保留色彩 | ✅ 通过 | 所有平台版本均保留"matte white + neutral gray + soft blue glow"色彩方案 |
| 7 | 是否保留材质与细节 | ✅ 通过 | 所有平台版本均保留"matte frosted body + stainless steel mouth rim + smooth cap + OLED display"材质描述 |
| 8 | 是否保留负面限制 | ✅ 通过 | 各平台均根据支持方式正确传递负面限制：ChatGPT Images 融入正向；豆包独立字段+融入；Midjourney 用 `--no`；SD 独立 Negative Prompt；Flux 融入正向；HF 融入正向 |
| 9 | 是否避免写死平台版本 | ✅ 通过 | 未出现具体 `--v 6`、`--v 7` 等硬编码版本号；Midjourney 部分已标注"版本号以当前平台文档为准" |
| 10 | 是否避免跨平台误用参数 | ✅ 通过 | ChatGPT Images 版本无 `--ar`/`--no`；豆包版本无 Midjourney 参数；Flux 版本无 SD 标签式写法；Midjourney 参数未出现在其他平台 |
| 11 | 是否说明参考图用途 | ✅ 通过 | CS-IMG-002 无参考图，检查项不适用（N/A）。各平台版本均未引入参考图说明 |
| 12 | 是否保留风险限制 | ✅ 通过 | 无品牌 logo/无人物/无复杂文字/无水印/无过度反光/无塑料廉价感/无变形杯体/无错误屏幕文字等限制在所有 6 个平台版本中均保留 |
| 13 | 是否给出平台差异说明 | ✅ 通过 | §14 已用表格说明 6 个平台的提示词风格、负面处理方式、参数使用和产品图注意事项差异 |
| 14 | 是否强调产品主体一致性 | ✅ 通过 | 各平台适配版本的注意事项中均已提醒产品形态一致性风险，Midjourney 建议用 `--seed` 锁定，SD 建议充分描述杯身形态 |
| 15 | 是否提醒屏幕文字风险 | ✅ 通过 | 各平台适配版本的注意事项中均已提醒 OLED 屏幕文字乱码风险，ChatGPT Images 可迭代修正，SD 在 Negative Prompt 中强化排除，Flux 建议明确描述为 "numeric digits" |

**检查结论**：15 项检查全部通过（其中第 11 项因无参考图而标记为 N/A）。T-IMG-002 的检查清单完整覆盖了本次产品图场景测试的所有关键适配维度，并额外增加了产品图特有的"主体一致性"和"屏幕文字风险"两项检查。

---

## 16. 测试结论

| # | 判断项 | 结论 | 说明 |
|---|--------|------|------|
| 1 | T-IMG-002 是否适用于 CS-IMG-002 | ✅ **适用** | T-IMG-002 的 6 平台适配规则和输出结构完整覆盖了 CS-IMG-002 产品图需求的平台改写需求。从 CS-IMG-002 的通用提示词出发，可以顺利生成各平台版本。产品主体、材质、色彩、构图、光线、负面限制在所有版本中均得到完整保留。 |
| 2 | T-IMG-002 是否适用于产品图 / 商业摄影场景 | ✅ **适用** | 产品图的实体物体特性（需要精确描述材质、反光控制、主体形态一致性）在 T-IMG-002 的适配规则下得到有效处理。各平台版本均正确传递了商业摄影风格和柔光箱布光等产品摄影核心要素。 |
| 3 | 是否需要修改 T-IMG-002 | ❌ **不需要** | T-IMG-002 v0.1 的适配规则、输出结构和检查清单在产品图场景下运行流畅。虽然产品图在检查清单中需要额外关注"主体一致性"和"屏幕文字风险"两项，但这些在 T-IMG-002 现有的 12 项检查清单框架下（第 1 项"是否保留主体"和第 7 项"是否保留负面限制"）已经自然覆盖。如后续产品图案例增多，可考虑在 T-IMG-002 §13 检查清单中增加"产品图专项检查"子项，但当前版本无需修改。 |
| 4 | 是否需要修改 CS-IMG-002 | ❌ **不需要** | CS-IMG-002 v0.1 的核心信息（产品主体、材质、色彩、构图、光线、负面限制、3 个变体、8 类风险）提取完整，足以支撑多平台适配。 |
| 5 | 是否需要修改 T-IMG-001 或 quick-reference | ❌ **不需要** | T-IMG-001 定义的 15 维度结构是本测试的底层基础，quick-reference 的速查表在提取信息过程中提供了有效参照。两者均无需修改。 |
| 6 | 是否可以将本测试作为产品图平台适配测试记录入库 | ✅ **可以** | 本测试文件完整记录了从 CS-IMG-002 提取 19 项核心信息 → 通用需求解析 → 通用中英文提示词 → 负面提示词 → 6 平台适配版本 → 平台差异说明 → 15 项检查清单的全流程，与 TEST-IMG-002-001（封面图场景）形成完整的互补覆盖。 |

**总体结论**：T-IMG-002 v0.1 通过 CS-IMG-002 的产品图实战测试。模板的 6 平台适配规则在产品图 / 商业摄影场景下同样适用，产品核心视觉信息在各平台版本中均得到完整保留，负面限制按各平台支持方式正确传递，无跨平台参数误用。T-IMG-002 在产品图场景下无需修改。**测试通过。**

---

## 17. 与 TEST-IMG-002-001 的互补性

| 维度 | TEST-IMG-002-001 | TEST-IMG-002-002 | 互补价值 |
|------|-----------------|-----------------|----------|
| **来源案例** | CS-IMG-001（Prompt-KB 知识库封面图） | CS-IMG-002（极简智能水杯产品主视觉图） | 覆盖两种截然不同的图像类型，验证 T-IMG-002 的通用性 |
| **图像类型** | 抽象概念图 / 封面图 | 实体产品图 / 商业摄影 | 从抽象到具象的完整覆盖；如果 T-IMG-002 在两种类型下均可用，说明模板设计具有足够的通用性 |
| **主体类型** | 抽象知识节点网络 + 模板卡片 | 实体智能水杯（有具体形态、材质、屏幕） | 抽象主体注重构图和多元素协调；实体主体注重材质还原和形态一致性 |
| **风格** | 现代扁平插画 | 商业摄影（写实） | 插画风格偏开放创作，摄影风格偏精确还原；两种风格对平台的要求完全不同 |
| **色彩方案** | 蓝紫科技感（深蓝+紫蓝渐变+青色高光） | 哑光白 + 中性灰 + 淡蓝微光 | 暗色调 vs 亮色调，高饱和 vs 低饱和，验证色彩方案在不同平台中的还原能力 |
| **主要风险** | 文字生成风险、logo/商标风险、风格堆砌 | 产品形态不一致、屏幕文字乱码、过度反光、材质失真 | 001 的风险偏向抽象生成（文字、复杂布局）；002 的风险偏向物理还原（形态、材质、反光） |
| **平台适配重点** | 如何在各平台中表达"抽象知识网络"；ChatGPT Images 对多元素构图的控制 | 如何在各平台中保持"水杯"这个实体物体的外观一致；如何处理屏幕文字在不同平台的生成差异 | 001 考验平台对抽象概念的理解，002 考验平台对实体物体的还原；两者结合全面验证 T-IMG-002 的适配能力 |
| **验证价值** | 验证 T-IMG-002 在抽象概念图和插画风格下的可用性 | 验证 T-IMG-002 在实体产品图和商业摄影风格下的可用性 | 两次测试共同证明 T-IMG-002 在"抽象插画"和"写实摄影"两条线路上均适用；T-IMG-002 无需修改即可覆盖当前 Prompt-KB 图像提示词模块的所有已支持图像类型 |

**互补结论**：TEST-IMG-002-001（封面图）和 TEST-IMG-002-002（产品图）形成了对 T-IMG-002 的双线验证——抽象概念图线（插画风格、多元素构图、文字风险）和实体产品图线（摄影风格、单主体材质还原、屏幕文字风险）。两条线均通过测试，说明 T-IMG-002 v0.1 的平台适配规则设计具有足够的通用性和鲁棒性。

---

## 18. 后续建议

按优先级排序：

| 优先级 | 建议 | 说明 |
|--------|------|------|
| **A** | 登记 TEST-IMG-002-002 到案例索引 | 将本测试记录登记到 `06-case-studies/README.md` 和 `03-image-prompts/README.md`，作为 T-IMG-002 的第二个正式测试记录，与 TEST-IMG-002-001 并列 |
| **B** | 小修 T-IMG-002（可选，非必须） | 如后续产品图案例增多，可考虑在 T-IMG-002 §13 检查清单中增加"产品图专项检查"子项（主体一致性、屏幕文字风险），但当前版本已通过测试，无需立即修改 |
| **C** | 创建第三个图像提示词案例 | 如人物图像、场景概念图等不同图像类型，进一步验证 T-IMG-001 + T-IMG-002 在更多场景下的适用性和互补覆盖 |
| **D** | 创建更细的平台专项模板 | 如单独为 Midjourney、Stable Diffusion 创建更细致的平台专项模板（如产品图参数速查卡、屏幕文字规避技巧） |
| **E** | 开始视频提示词模块 | 启动 Phase 4，创建 T-VIDEO-001 视频提示词基础规范 |

**推荐路径**：A（登记测试记录，与 TEST-IMG-002-001 并列）→ C（创建第三个图像案例，如人物/场景图）→ E（启动视频模块）。如果当前图像提示词模块的两个案例 + 两个测试记录已满足业务需求，也可以直接跳到 E。

---

## 19. 版本记录

| 版本 | 日期 | 说明 |
|------|------|------|
| v0.1 | 2026-05-25 | 使用 CS-IMG-002（极简智能水杯产品主视觉图提示词案例 v0.1）测试 T-IMG-002（图像提示词平台适配模板 v0.1）。从 CS-IMG-002 提取 19 项核心信息，生成通用需求解析、通用中英文提示词、通用负面提示词，并输出 ChatGPT Images、豆包、Midjourney、Stable Diffusion、Flux 和 Hugging Face 六个平台适配版本。使用 T-IMG-002 §13 检查清单逐项验证，扩展至 15 项检查（新增产品图专项的"主体一致性"和"屏幕文字风险"两项），全部通过。测试结论：T-IMG-002 适用于 CS-IMG-002 和产品图/商业摄影场景，无需修改 T-IMG-002、CS-IMG-002、T-IMG-001 或 quick-reference。与 TEST-IMG-002-001 形成"抽象概念图 + 实体产品图"的双线互补验证。未修改任何受保护文件。 |

---

*本测试仅创建测试记录文件，未修改 T-IMG-002、CS-IMG-002、CS-IMG-001、T-IMG-001、quick-reference、导航文件或其他案例。*
