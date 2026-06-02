# TEST-IMG-002-001｜CS-IMG-001 平台适配测试

> **测试编号**: TEST-IMG-002-001
> **测试名称**: CS-IMG-001 平台适配测试
> **版本**: v0.1
> **创建日期**: 2026-05-25
> **来源案例**: CS-IMG-001｜Prompt-KB 知识库封面图提示词案例 v0.2
> **测试模板**: T-IMG-002｜图像提示词平台适配模板 v0.1
> **关联规范**: T-IMG-001 v0.2 / image-prompt-quick-reference v0.2
> **性质**: 模板实测记录——不是新规范、不是新案例、不是对 T-IMG-002 或 CS-IMG-001 的修改
> **存放路径**: prompt-kb/06-case-studies/cs-img-001-platform-adaptation-test.md

---

## 1. 测试目标

本测试用于验证以下问题：

| # | 验证目标 | 说明 |
|---|----------|------|
| 1 | T-IMG-002 是否能将同一个图像需求改写为多平台版本 | 对 CS-IMG-001 的封面图需求，生成 ChatGPT Images / 豆包 / Midjourney / Stable Diffusion / Flux / Hugging Face 六平台适配版本 |
| 2 | 是否能保留主体、场景、风格、构图、光线、色彩和负面限制 | 各平台版本的核心视觉信息是否与原始需求一致 |
| 3 | 是否能避免写死平台版本号 | 不出现 `--v 6`、`--v 7` 等硬编码版本号（如出现则标注"以当前平台文档为准"） |
| 4 | 是否能避免跨平台误用参数 | 不把 Midjourney 参数写到 ChatGPT Images 版本、不把 SD 标签式写法写到 Flux 版本 |
| 5 | 是否能基于 CS-IMG-001 生成可用的平台适配提示词 | 最终输出的平台版本是否能直接使用或仅需微调即可使用 |

---

## 2. 测试来源

| 来源项 | 详情 |
|--------|------|
| **来源案例** | CS-IMG-001｜Prompt-KB 知识库封面图提示词案例 v0.2 |
| **来源文件** | prompt-kb/06-case-studies/cs-img-001-prompt-kb-cover-image.md |
| **测试模板** | T-IMG-002｜图像提示词平台适配模板 v0.1 |
| **模板文件** | prompt-kb/03-image-prompts/templates/image-platform-adaptation-template.md |
| **关联规范** | T-IMG-001｜Prompt-KB 图像提示词基础规范 v0.2 |
| **关联速查卡** | image-prompt-quick-reference v0.2 |

---

## 3. 从 CS-IMG-001 提取的核心信息

| # | 信息项 | 提取内容 | 来源位置 |
|---|--------|----------|----------|
| 1 | 原始图像需求 | 生成 Prompt-KB 知识库封面图，用于 README 或项目介绍；体现"AI 提示词知识库""结构化思考""多模块协作""可复用模板"；风格现代、干净、科技感但不太夸张；不出现品牌 logo、真实人物、复杂文字；适合横版封面或 banner | CS-IMG-001 §2 |
| 2 | 使用场景 | 项目 README 封面图 / GitHub Banner / 文档顶部图；对外展示用途，需要简洁专业 | CS-IMG-001 §3 |
| 3 | 主体 | 抽象的知识节点网络 + 提示词模板卡片 + 模块化结构图形 + 简约几何图标 | CS-IMG-001 §4 维度 2 |
| 4 | 场景 | 简洁数字空间背景，轻微渐变底色，深蓝到紫蓝渐变，体现科技感但不拥挤 | CS-IMG-001 §4 维度 3 |
| 5 | 风格 | 现代扁平插画风格，微渐变 | CS-IMG-001 §4 维度 4 |
| 6 | 构图 | 三分法构图，核心元素集中在左侧三分之一，右侧留白（适合 README 文字排版） | CS-IMG-001 §4 维度 5 |
| 7 | 光线 | 柔和漫射光，局部有轻微发光点效果（节点发光），不刺眼，不写实灯光 | CS-IMG-001 §4 维度 7 |
| 8 | 色彩方案 | 蓝紫科技感：深蓝、紫蓝渐变背景，白色和浅灰色节点/卡片，少量青色高光点缀 | CS-IMG-001 §4 维度 8 |
| 9 | 细节 / 材质 | 细线网格连接节点，卡片有轻微阴影，图标为几何简约风格 | CS-IMG-001 §4 维度 9 |
| 10 | 负面限制 | 无文字、无水印、无 logo、无真实人物（无真实人脸）、无品牌标识、无侵权角色、无杂乱背景、无低清/模糊、无过度复杂细节、无强烈赛博朋克霓虹、无恐怖或阴暗氛围、无变形、无伪影 | CS-IMG-001 §7 |
| 11 | 中文图像提示词 | CS-IMG-001 §5 的完整中文提示词 | CS-IMG-001 §5 |
| 12 | 英文图像提示词 | CS-IMG-001 §6 的完整英文提示词 | CS-IMG-001 §6 |
| 13 | 平台适配建议 | 5 平台适配建议（ChatGPT Images / 豆包 / Midjourney / SD&Flux / Hugging Face） | CS-IMG-001 §9 |
| 14 | 风险与注意事项 | 6 类风险：文字生成风险、logo/商标风险、真实人物风险、风格过度堆砌风险、画面过于复杂风险、平台理解差异 | CS-IMG-001 §11 |
| 15 | 复杂度等级 | L3（中等复杂，多元素协调） | CS-IMG-001 §3 |
| 16 | 画面比例 | 16:9 横版封面（Banner 可用 3:1） | CS-IMG-001 §3 |
| 17 | 镜头 / 视角 | 正面俯视平视，无透视变形 | CS-IMG-001 §4 维度 6 |
| 18 | 氛围 | 专业、冷静、有序，带轻微未来感 | CS-IMG-001 §4 维度 10 |

**提取完整性**：18 项信息全部从 CS-IMG-001 提取，无新增事实。

---

## 4. 通用需求解析

| 解析项 | 内容 |
|--------|------|
| **图像目标** | 生成一张 Prompt-KB 知识库的横版封面图，用于 GitHub README 顶部或项目介绍页，传达 AI 提示词知识库的专业感、结构化、多模块协作和可复用模板概念 |
| **使用场景** | 项目 README 封面 / GitHub Banner / 文档顶部图；对外展示，需简洁专业 |
| **核心视觉元素** | 抽象知识节点网络（细线连接） + 浮动提示词模板卡片（简约几何图标） + 深蓝到紫蓝渐变数字空间背景 |
| **需要保留的元素** | 主体（节点网络+卡片）、场景（渐变数字空间）、风格（现代扁平插画）、构图（三分法+右侧留白）、光线（柔和漫射+节点发光）、色彩（蓝紫科技感+白色/浅灰+青色高光）、细节（细线网格+卡片阴影）、氛围（专业冷静）、比例（16:9） |
| **需要避免的元素** | 文字、水印、logo、真实人物、人脸、品牌标识、侵权角色、杂乱背景、低清、模糊、过度复杂细节、强烈赛博朋克霓虹、恐怖或阴暗氛围、变形、伪影 |
| **平台适配重点** | ChatGPT Images：限制条件融入正向提示词；豆包：使用中文自然语言；Midjourney：英文提示词+参数，主体和风格靠前；Stable Diffusion：英文标签式+独立 Negative Prompt；Flux：英文自然语言完整描述；Hugging Face：通用自然语言+需确认模型信息 |

---

## 5. 通用中文提示词

基于 CS-IMG-001 §5 中英文提示词，整理平台无关版本：

```
一张横版知识库封面图，主体是多个抽象的知识节点，用细线连接成网络结构，
节点旁浮动着几张提示词模板卡片，卡片上有简约几何图标（方块和线条代替真实文字），
背景是深蓝到紫蓝的渐变数字空间，左侧三分之一区域集中主要元素，右侧留白可供文字排版，
柔和漫射光，节点有轻微发光效果，卡片有淡淡阴影，
整体蓝紫科技感配色，白色和浅灰色节点/卡片，少量青色高光点缀，
现代扁平插画风格，正面平视，无透视变形，
专业、冷静、有序，带轻微未来感，高分辨率，16:9 横版封面。
不含任何文字、水印、logo、真实人物或品牌标识，背景干净不杂乱。
```

**说明**：
- 保留 CS-IMG-001 的全部核心视觉信息（主体、场景、风格、构图、光线、色彩、细节、氛围、比例）；
- 将"无文字"等负面限制直接融入正向描述；
- 不添加 CS-IMG-001 中不存在的新事实；
- 色彩方案严格为"蓝紫科技感 + 白色/浅灰背景 + 少量青色高光"。

---

## 6. 通用英文提示词

基于 CS-IMG-001 §6 英文提示词，整理平台无关版本：

```
A wide-format knowledge base cover image, featuring multiple abstract knowledge nodes
connected by fine lines forming a network structure, with floating prompt template
cards displaying simplified geometric icons (rectangles and lines instead of real text).
Background is a deep blue to purple-blue gradient digital space. Main elements are
arranged in the left third of the frame, with the right side left open for text placement.
Soft diffused lighting, nodes have a subtle glowing effect, cards cast soft shadows.
Overall blue-purple tech color palette, with white and light gray nodes/cards,
accented by a small amount of cyan highlights. Modern flat illustration style.
Straight-on flat view, no perspective distortion. Professional, calm, structured,
with a slight futuristic feel. High resolution, 16:9 horizontal format.
No text, no watermark, no logo, no real people, no brand identity, clean background.
```

**说明**：
- 与通用中文提示词语义完全一致；
- 保留色彩方案"blue-purple tech color palette, white/light gray + cyan highlights"；
- 未添加中文提示词中没有的新事实；
- 负面限制已融入正向描述（如"no text, no watermark, no logo..."）。

---

## 7. 负面提示词 / 限制条件

### 通用英文负面提示词

供支持独立 Negative Prompt 字段的平台使用（Stable Diffusion / Flux 等）：

```
no text, no letters, no watermark, no logo, no real human faces, no portraits,
no people, no brand identity, no copyright characters, no trademark, no cluttered
background, no low resolution, no blur, no overly complex details, no strong
cyberpunk neon, no dark or horror atmosphere, no distortion, no ugly artifacts,
no bad anatomy, no extra limbs
```

### 中文自然语言限制版本

供需要中文负面表达的平台使用（豆包等）：

```
不要文字、不要字母、不要水印、不要 logo、不要真实人脸、不要肖像、
不要人物、不要品牌标识、不要侵权角色、不要商标、不要杂乱背景、
不要低分辨率、不要模糊、不要过度复杂细节、不要强烈赛博朋克霓虹、
不要恐怖或阴暗氛围、不要变形、不要伪影、不要畸形、不要多余肢体
```

### 来源说明

以上负面提示词基于 CS-IMG-001 §7 整理，扩展了常见图像质量相关负面词（如 `bad anatomy`, `extra limbs`），属于通用最佳实践补充，未超出 T-IMG-001 定义的负面提示词范围。

---

## 8. ChatGPT Images 适配版本

### ChatGPT Images 提示词

使用自然语言英文描述，适合直接复制到 ChatGPT 对话框：

```
I need a wide-format cover image for a knowledge base project called "Prompt-KB".
It should serve as a GitHub README header or project introduction banner.

The image features abstract knowledge nodes connected by fine glowing lines forming
a network structure. Several floating prompt template cards hover near the nodes,
each with simple geometric icons — use rectangles and lines as placeholder blocks
instead of real text. The background is a deep blue to purple-blue gradient digital
space, clean and uncluttered.

Composition: core elements are arranged in the left third of the frame (three-part
composition), with the right side kept open as clean breathing space suitable for
overlaying text later. Straight-on flat view, no perspective distortion.

Lighting: soft diffused ambient light, with the nodes emitting a subtle glow —
not harsh or neon-like. Cards cast soft understated shadows.

Color palette: rich blue-purple tech feel — deep blue base transitioning to
purple-blue gradient, with white and light gray for nodes and cards. Small cyan
accent highlights for key connection points or glowing edges. No strong cyberpunk
neon, no dark or horror mood.

Style: modern flat illustration style with subtle gradients. Professional, calm,
structured, with a slight futuristic feel. High resolution, 16:9 horizontal format.

Important: absolutely no visible text, no letters, no watermarks, no logos,
no brand identity, no real people or faces, no copyrighted characters. The
background should remain clean and not cluttered. No low resolution or blur.
```

也可使用中文自然语言版本：

```
请生成一张 Prompt-KB 知识库的横版封面图，用于 GitHub README 顶部。

画面主体是多个抽象的知识节点由发光的细线连接成知识网络，节点旁浮动着几张提示词
模板卡片，卡片上有简约几何图标（用方块和线条代替真实文字，不要出现可读文字）。
背景是深蓝到紫蓝渐变数字空间，干净不杂乱。

构图采用三分法：核心元素集中在画面左侧三分之一，右侧留出干净的空白区域，
适合后续叠加文字标题。正面平视角度，无透视变形。

光线为柔和漫射光，节点发出轻微柔和的光晕（不是刺眼的霓虹），卡片有淡淡的阴影。

色彩方案：蓝紫科技感——深蓝底色向紫蓝过渡，节点和卡片为白色和浅灰色，
少量青色高光点缀在关键连接点或发光边缘。不要强烈赛博朋克霓虹，不要恐怖或阴暗氛围。

风格：现代扁平插画风格，带微渐变。整体专业、冷静、有序，有轻微未来感。
高分辨率，16:9 横版。

重要限制：画面中绝对不能出现任何文字、字母、水印、logo、品牌标识、真实人物、
真实人脸、侵权角色。背景保持干净，不拥挤。不要低清或模糊。
```

### 修改 / 迭代说明

ChatGPT Images 支持多轮对话修改。如果首次生成不满意，可按以下方式迭代：

| 问题 | 迭代指令 |
|------|----------|
| 色彩太鲜艳 | "把色彩饱和度降低一些，让蓝紫色更柔和" |
| 节点网络太密集 | "减少节点数量，让知识网络更简洁宽敞" |
| 右侧留白不够 | "把画面元素进一步往左移，右侧留出更多空白区域" |
| 风格不够扁平 | "强化扁平插画风格，减少立体感和阴影深度" |
| 出现了乱码文字 | "把卡片上的所有文字改成纯几何图形（方块和线条），不要任何字母" |
| 整体构图调整 | "保留当前的色彩和风格，把构图改成中心对称" |

### 注意事项

- ChatGPT Images 不支持独立的负面提示词字段，所有限制条件已直接写进正向提示词中（"absolutely no visible text..."等）；
- 不适用 `--ar`、`--no`、`--style` 等参数；画面比例通过自然语言"16:9 horizontal format"指定；
- 如首次生成结果中卡片出现文字，可追加"replace all text on cards with abstract geometric shapes"进行修正。

---

## 9. 豆包适配版本

### 豆包中文提示词

使用自然流畅的中文表达，适合封面图 / README Banner / 社交媒体配图：

```
横版知识库封面图，用于项目介绍页顶部 Banner。

画面主体是一组抽象的知识节点，节点之间由细线连接成知识网络结构。
节点周围悬浮着几张提示词模板卡片，卡片上是用几何图形（方块和线条）
代替的文字占位符——不要出现真实的可读文字。

背景是深蓝到紫蓝的渐变空间，干净简洁。画面左侧集中主要元素，
右侧留出约三分之一的空白区域，方便后续放标题文字。

光线柔和，节点有轻微发光感，卡片带淡淡阴影。
配色是蓝紫科技风：深蓝、紫蓝渐变背景，节点和卡片为白色和浅灰色，
用少量青色点缀关键位置。

整体风格是现代扁平插画，专业、冷静、有序，有轻微的科技未来感，
但不夸张。16:9 横版比例，高清晰度。

不要文字、不要水印、不要 logo、不要真人、不要人脸、不要品牌标识、
不要杂乱背景、不要赛博朋克霓虹、不要阴暗恐怖氛围。
```

### 负面限制

如需填入豆包平台的负面提示词独立字段：

```
不要文字、不要字母、不要水印、不要 logo、不要真人、不要人脸、
不要肖像、不要品牌标识、不要商标、不要侵权角色、不要杂乱背景、
不要低清、不要模糊、不要过度复杂细节、不要强烈霓虹灯光、
不要恐怖或阴暗氛围、不要变形
```

### 使用建议

- 中文表达自然流畅，风格描述不参数化，直接复制到豆包提示词输入区即可；
- 可在豆包平台的图片尺寸设置中选择 1024×576 或对应横版规格；
- 如首次生成效果不理想，可在提示词末尾补充"请把节点间的连线画得更清晰一些"等自然语言迭代；
- 如需国风或东方美学风格的变体，可在"现代扁平插画风格"前后补充风格方向，但须保持蓝紫科技感色彩方案。

---

## 10. Midjourney 适配版本

### Midjourney 英文提示词

主体和风格靠前，英文自然语言 + 参数：

```
abstract knowledge nodes connected by glowing fine lines forming a network structure,
floating prompt template cards with simple geometric placeholder icons, deep blue to
purple-blue gradient digital space background, soft diffused lighting with subtle node
glow, modern flat illustration style, three-part composition with main elements in left
third and right side open for breathing room, white and light gray nodes and cards,
cyan accent highlights, professional calm structured atmosphere, slight futuristic feel,
high resolution, straight-on flat view --ar 16:9 --no text, letters, watermark, logo,
real people, faces, brand identity, cluttered background, cyberpunk neon, dark mood
```

### 参数建议

| 参数 | 建议 | 说明 |
|------|------|------|
| `--ar 16:9` | 画面比例 | 横版封面/Banner 标准比例 |
| `--no text, letters, watermark, logo, real people, faces, brand identity, cluttered background, cyberpunk neon, dark mood` | 负面排除 | 排除文字、人物、品牌、混乱背景、不当风格 |
| `--style raw`（可选） | 风格控制 | 降低 Midjourney 自动美化干扰，更贴合"现代扁平插画"意图 |

> 以上参数为通用建议。版本号（如 `--v`）以当前 Midjourney 平台官方文档为准，不在此写死。如当前文档推荐使用特定版本参数，请按平台文档调整。

### 注意事项

- Midjourney 对英文提示词响应更稳定，建议使用英文版本；
- 主体"abstract knowledge nodes"和风格"modern flat illustration style"已在提示词靠前位置；
- `--no` 参数可排除不需要的内容，已覆盖文字、水印、logo、人物、品牌、赛博朋克等；
- 不要把 `--ar`、`--no` 等 Midjourney 参数用于其他平台（ChatGPT Images、豆包等不支持该语法）；
- 如果 Midjourney 默认风格过于写实或立体，可追加 `--style raw` 降低自动美化。

---

## 11. Stable Diffusion 适配版本

### Positive Prompt

英文标签式正向提示词，结构：质量标签 → 主体 → 场景 → 风格 → 构图 → 光线 → 色彩 → 细节：

```
masterpiece, best quality, high resolution, 16:9 wide format,
abstract knowledge nodes connected by fine glowing lines forming a knowledge network,
floating prompt template cards with simple geometric placeholder icons,
deep blue to purple-blue gradient digital space background,
modern flat illustration style, subtle gradients,
three-part composition with main elements in left third, right side open for text placement,
straight-on flat view, no perspective distortion,
soft diffused lighting, subtle node glow effect, soft card shadows,
blue-purple tech color palette, white and light gray nodes and cards, cyan accent highlights,
professional, calm, structured atmosphere, slight futuristic feel,
clean background, no clutter
```

### Negative Prompt

```
text, letters, watermark, logo, signature, artist name,
realistic human, human face, portrait, person, people,
brand identity, trademark, copyright character,
cluttered background, messy composition,
low resolution, low quality, blur, blurry,
overly complex details, cyberpunk, neon, dark atmosphere, horror,
distortion, ugly, deformed, bad anatomy, extra limbs, artifacts,
photorealistic, 3D render, realistic shading
```

### Optional Settings

| 字段 | 建议 | 说明 |
|------|------|------|
| 分辨率 | 1920×1080（16:9） | 横版封面标准分辨率 |
| 采样器 | — | 以当前使用的模型和界面推荐为准 |
| Steps | — | 以当前使用的模型推荐为准（通常 20-40） |
| CFG Scale | — | 以当前使用的模型推荐为准（通常 5-9） |
| Seed | — | 如需可复现结果，固定一个 seed 值 |
| 模型类型建议 | 插画风格模型 | 不写死具体模型文件名；SDXL 类模型对自然语言支持更好，或搭配扁平插画 LoRA |

### 注意事项

- Positive 和 Negative Prompt 的格式取决于使用的具体模型（SD1.5 / SDXL / SD3 等）和界面（ComfyUI / A1111 / Forge 等）；
- Optional Settings 中的采样器、Steps、CFG Scale 等不写死数值，以当前使用的模型推荐为准；
- 如果使用 ControlNet / LoRA / IP-Adapter 等扩展，需另外说明用途（如用 LoRA 强化扁平插画风格）；
- Negative Prompt 中额外添加了 `photorealistic, 3D render, realistic shading` 以强化扁平风格效果，避免模型输出过于写实。

---

## 12. Flux 适配版本

### Flux 提示词

使用英文自然语言完整描述，不需碎片化标签：

```
A wide-format knowledge base cover image in 16:9 aspect ratio.

Multiple abstract knowledge nodes are connected by fine glowing lines forming a
network structure. Several floating prompt template cards hover near the nodes,
each displaying simple geometric icons — use rectangles and lines as placeholder
shapes, never real readable text.

The background is a deep blue to purple-blue gradient digital space, clean and
uncluttered. The composition uses a three-part layout: main visual elements are
concentrated in the left third of the frame, with the right side kept open as
clean breathing room suitable for text overlay. Straight-on flat view with no
perspective distortion.

Lighting is soft and diffused throughout, with the knowledge nodes emitting a
gentle subtle glow — not harsh or neon. Cards cast soft understated shadows.

Color palette is blue-purple tech: deep blue base transitioning to purple-blue
gradient, white and light gray nodes and cards, with small cyan accent highlights
on key connection points or glowing edges.

Style is modern flat illustration with subtle gradients. The overall atmosphere
is professional, calm, and structured, with a slight futuristic feel.

High resolution, clean execution, no visual noise.
```

### 负面限制

用自然语言表达的负面限制（如 Flux 部署界面支持独立 Negative Prompt 字段，可参考 Stable Diffusion 版本的 Negative Prompt）：

```
No text, no letters, no watermark, no logo. No real people or human faces.
No brand identity or trademark. No cluttered or messy background.
No strong cyberpunk neon. No dark, horror, or gloomy atmosphere.
No distortion or artifacts. Clean, minimal, organized composition.
```

### 注意事项

- Flux 对自然语言理解较好，不需要传统 SD 的碎片化标签；上述提示词使用完整句段即可；
- 不要过度依赖碎片化标签式写法——Flux 对完整自然语言描述的响应优于标签堆砌；
- 如果部署界面支持独立 Negative Prompt 字段，可将"负面限制"填入该字段；否则直接融入正向提示词末尾；
- 具体模型版本以当前部署环境为准（Flux.1 dev / Flux.1 pro / Flux.1 schnell 等）。

---

## 13. Hugging Face 图像模型适配版本

### Hugging Face 通用提示词

使用简洁英文自然语言描述（通用版本，适用多数图像生成模型）：

```
A wide-format cover image in 16:9 ratio. Abstract knowledge nodes connected by
fine glowing lines forming a network. Floating cards with simple geometric icons.
Deep blue to purple-blue gradient background. Modern flat illustration style.
Soft diffused light, subtle node glow. Main elements in left third, right side
open. White and light gray nodes with cyan highlights. Professional, calm,
structured feel. High resolution. No text, no watermark, no logo, no people.
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
| 是否支持参考图 | 是否可传入参考图做风格/构图引导 | ⏳ 待确认 |

### 注意事项

- Hugging Face 是一个模型集合平台，不是单一图像生成器——上面的模型（SDXL、SD3、Flux、Kolors 等）提示词格式差异大；
- 以上提示词为通用版本，实际使用时请以具体模型的 README / Model Card / 社区示例为准；
- 如果模型不支持负面提示词字段，应将"No text, no watermark..."等限制融入正向提示词中；
- 推荐在使用前先查看该模型在 Hugging Face 上的示例 prompt，确认推荐的措辞和格式；
- 如模型支持标签式提示词（如 SDXL 类），可参考本测试 §11 的 Stable Diffusion 版本。

---

## 14. 平台差异说明

| 平台 | 推荐提示词风格 | 负面提示词处理 | 参数使用 | 注意事项 |
|------|---------------|---------------|----------|----------|
| **ChatGPT Images** | 自然语言（中/英均可），完整句段描述 | 不支持独立 Negative Prompt，限制条件融入正向提示词 | 不支持 `--ar`/`--no` 等参数；比例通过自然语言指定 | 支持多轮对话迭代修改；中文效果良好 |
| **豆包** | 中文自然语言，简洁流畅 | 可填入独立负面提示词字段，或融入正向描述 | 平台界面设置尺寸；提示词末尾可补充比例期望 | 中文理解好；适合社交媒体配图、短视频封面 |
| **Midjourney** | 英文自然语言 + 参数；主体和风格靠前 | 通过 `--no` 参数传入排除内容 | `--ar` 指定比例；`--style raw` 降低自动美化；不写死 `--v` 版本号 | 对英文响应更稳定；艺术感强；随机性大 |
| **Stable Diffusion** | 英文标签式（质量标签→主体→场景→风格→构图→光线→色彩→细节） | 独立的 Negative Prompt 字段，可详细列出 | 采样器/Steps/CFG 等不写死数值；分辨率按比例建议 | 具体格式取决于模型（SD1.5/SDXL/SD3）；可搭配 LoRA/ControlNet |
| **Flux** | 英文自然语言完整描述 | 可填入独立字段或融入正向；自然语言表达即可 | 不需要传统 SD 的碎片化标签；自然语言即可 | 不依赖标签式写法；具体参数以部署环境为准 |
| **Hugging Face** | 以模型为准（通用版提供简洁英文自然语言） | 以模型文档为准（有的支持独立字段，有的不支持） | 不写死任何参数；需要先确认模型类型和格式 | 模型差异大；使用前必须查看模型 README/Model Card |

---

## 15. 平台适配检查清单

使用 T-IMG-002 §13 检查清单，对本测试输出的六平台版本逐一检查：

| # | 检查项 | 是否通过 | 说明 |
|---|--------|---------|------|
| 1 | 是否保留主体 | ✅ 通过 | 所有平台版本均包含"abstract knowledge nodes connected by lines forming a network + floating prompt template cards with geometric icons" |
| 2 | 是否保留场景 | ✅ 通过 | 所有平台版本均包含"deep blue to purple-blue gradient digital space" |
| 3 | 是否保留风格 | ✅ 通过 | 所有平台版本均保留"modern flat illustration style"，风格词不超过 3 个 |
| 4 | 是否保留构图 | ✅ 通过 | 所有平台版本均保留"three-part composition, left third main elements, right side open" |
| 5 | 是否保留光线 | ✅ 通过 | 所有平台版本均保留"soft diffused light + subtle node glow" |
| 6 | 是否保留色彩 | ✅ 通过 | 所有平台版本均保留"blue-purple tech palette, white/light gray nodes, cyan highlights" |
| 7 | 是否保留负面限制 | ✅ 通过 | 各平台均根据支持方式正确传递负面限制：ChatGPT Images 融入正向；豆包独立字段+融入；Midjourney 用 `--no`；SD 独立 Negative Prompt；Flux 融入正向；HF 融入正向 |
| 8 | 是否避免写死平台版本 | ✅ 通过 | 未出现具体 `--v 6`、`--v 7` 等硬编码版本号；Midjourney 部分已标注"版本号以当前平台文档为准" |
| 9 | 是否避免跨平台误用参数 | ✅ 通过 | ChatGPT Images 版本无 `--ar`/`--no`；豆包版本无 Midjourney 参数；Flux 版本无 SD 标签式写法；Midjourney 参数未出现在其他平台 |
| 10 | 是否说明参考图用途 | ✅ 通过 | CS-IMG-001 无参考图，检查项不适用（N/A）。各平台版本均未引入参考图说明 |
| 11 | 是否保留风险限制 | ✅ 通过 | 无文字/无 logo/无真实人物等限制在所有 6 个平台版本中均保留，未因平台切换丢失 |
| 12 | 是否给出平台差异说明 | ✅ 通过 | §14 已用表格说明 6 个平台的提示词风格、负面处理方式、参数使用和注意事项差异 |

**检查结论**：12 项检查全部通过（其中第 10 项因无参考图而标记为 N/A）。T-IMG-002 的检查清单完整覆盖了本次测试的所有关键适配维度。

---

## 16. 测试结论

| # | 判断项 | 结论 | 说明 |
|---|--------|------|------|
| 1 | T-IMG-002 是否适用于 CS-IMG-001 | ✅ **适用** | T-IMG-002 的 6 平台适配规则和输出结构完整覆盖了 CS-IMG-001 封面图需求的平台改写需求。从 CS-IMG-001 的通用提示词出发，可以顺利生成各平台版本。 |
| 2 | 是否需要修改 T-IMG-002 | ❌ **不需要** | T-IMG-002 v0.1 的适配规则、输出结构和检查清单在本次测试中运行流畅，未发现缺失或矛盾。 |
| 3 | 是否需要修改 CS-IMG-001 | ❌ **不需要** | CS-IMG-001 v0.2 的核心信息（主体、场景、风格、构图、光线、色彩、负面限制）提取完整，足以支撑多平台适配。 |
| 4 | 是否需要修改 T-IMG-001 或 quick-reference | ❌ **不需要** | T-IMG-001 定义的 15 维度结构是本测试的底层基础，quick-reference 的速查表在提取信息过程中提供了有效参照。两者均无需修改。 |
| 5 | 是否可以将本测试作为平台适配测试记录入库 | ✅ **可以** | 本测试文件完整记录了从 CS-IMG-001 提取核心信息 → 通用需求解析 → 6 平台适配版本 → 平台差异说明 → 检查清单的全流程，可作为 T-IMG-002 的首个正式测试记录。 |

**总体结论**：T-IMG-002 v0.1 通过 CS-IMG-001 的实战测试。模板的 6 平台适配规则设计合理，多平台输出模板可用，检查清单覆盖完整。CS-IMG-001 的核心视觉信息在 6 个平台版本中均得到完整保留，负面限制按各平台支持方式正确传递，无跨平台参数误用。**测试通过。**

---

## 17. 后续建议

按优先级排序：

| 优先级 | 建议 | 说明 |
|--------|------|------|
| **A** | 登记 TEST-IMG-002-001 到案例索引 | 将本测试记录登记到 `06-case-studies/README.md` 和 `03-image-prompts/README.md`，作为 T-IMG-002 的首个正式测试记录 |
| **B** | 不修改，直接推进 | T-IMG-002 和 CS-IMG-001 均无需修改，本次测试验证通过 |
| **C** | 创建第二个图像提示词案例 | 如人物图像、产品图等不同场景，进一步验证 T-IMG-001 + T-IMG-002 在不同图像类型下的适用性 |
| **D** | 创建更细的平台专项模板 | 如单独为 Midjourney、Stable Diffusion 创建更细致的平台专项模板（如参数速查卡） |
| **E** | 开始视频提示词模块 | 启动 Phase 4，创建 T-VIDEO-001 视频提示词基础规范 |

**推荐路径**：A（登记测试记录）→ C（创建第二个图像案例，如人物/产品图场景）→ E（启动视频模块）。

---

## 18. 版本记录

| 版本 | 日期 | 说明 |
|------|------|------|
| v0.1 | 2026-05-25 | 使用 CS-IMG-001（Prompt-KB 知识库封面图提示词案例 v0.2）测试 T-IMG-002（图像提示词平台适配模板 v0.1）。从 CS-IMG-001 提取 18 项核心信息，生成通用需求解析、通用中英文提示词、通用负面提示词，并输出 ChatGPT Images、豆包、Midjourney、Stable Diffusion、Flux 和 Hugging Face 六个平台适配版本。使用 T-IMG-002 §13 检查清单逐项验证，12 项检查全部通过。测试结论：T-IMG-002 适用于 CS-IMG-001，无需修改 T-IMG-002、CS-IMG-001、T-IMG-001 或 quick-reference。未修改任何受保护文件。 |

---

*本测试仅创建测试记录文件，未修改 T-IMG-002、CS-IMG-001、T-IMG-001、quick-reference、导航文件或其他案例。*
