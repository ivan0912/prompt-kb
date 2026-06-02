# TEST-VIDEO-002-001｜CS-VIDEO-001 视频平台适配测试

> **测试编号**: TEST-VIDEO-002-001
> **测试名称**: CS-VIDEO-001 视频平台适配测试
> **版本**: v0.1
> **创建日期**: 2026-05-27
> **来源案例**: CS-VIDEO-001｜极简智能水杯产品展示视频提示词案例 v0.2
> **测试模板**: T-VIDEO-002｜视频提示词平台适配模板 v0.1
> **关联规范**: T-VIDEO-001｜Prompt-KB 视频提示词基础规范 v0.1
> **关联速查卡**: video-prompt-quick-reference v0.2
> **性质**: 平台适配测试记录——不是新规范、不是新案例正文、不是视频平台适配模板本身
> **存放路径**: prompt-kb/06-case-studies/cs-video-001-platform-adaptation-test.md

---

## 1. 测试定位

本测试用于验证以下问题：

| # | 验证目标 | 说明 |
|---|----------|------|
| 1 | T-VIDEO-002 是否适用于真实视频案例 | 以 CS-VIDEO-001 作为真实 L4 产品展示视频输入，检验模板在真实案例中的可操作性 |
| 2 | T-VIDEO-002 是否能将通用视频提示词改写为多平台版本 | 对同一个来源案例，生成 Runway / Pika / Kling / Luma / Sora / 豆包 / 即梦 / 其他模型的适配版本 |
| 3 | 是否能保留核心视频信息 | 主体、场景、动作、镜头运动、时间顺序、节奏、风格、光线、色彩、材质、首帧、末帧、负面限制均不丢失 |
| 4 | 是否能避免写死平台版本号 | 各平台版本不硬编码具体版本号；如需提及，只作为示例并说明以当前平台文档为准 |
| 5 | 是否能避免写死实时平台参数 | 不硬编码时长上限、分辨率、运动强度等实时参数 |
| 6 | 是否能避免跨平台误用参数 | 不把 Sora 的长叙事直接套给 Pika，不把 Kling 的中文结构直接套给需要英文的平台 |
| 7 | 是否能支撑后续视频平台适配流程 | 本测试输出可作为后续导航登记、平台对比测试和模板可用性判定的基础记录 |

本文件明确为：

- 平台适配测试记录；
- 不是新规范；
- 不是视频案例正文；
- 不是视频平台适配模板；
- 不修改 `T-VIDEO-002`；
- 不修改 `CS-VIDEO-001`。

---

## 2. 测试来源

| 来源项 | 详情 |
|--------|------|
| **来源案例** | CS-VIDEO-001｜极简智能水杯产品展示视频提示词案例 v0.2 |
| **来源文件** | `prompt-kb/06-case-studies/cs-video-001-product-showcase-video.md` |
| **测试模板** | T-VIDEO-002｜视频提示词平台适配模板 v0.1 |
| **模板文件** | `prompt-kb/04-video-prompts/templates/video-platform-adaptation-template.md` |
| **关联规范** | T-VIDEO-001｜Prompt-KB 视频提示词基础规范 v0.1 |
| **关联速查卡** | `prompt-kb/04-video-prompts/video-prompt-quick-reference.md` |

---

## 3. 从 CS-VIDEO-001 提取的核心信息

| # | 信息项 | 提取内容 | 来源位置 |
|---|--------|----------|----------|
| 1 | 原始视频需求 | 生成一个极简风格的智能保温水壶展示视频，白色哑光机身，圆柱形瓶身配圆形瓶盖，瓶身中间有一个隐藏式 LED 触控显示屏，可以显示水温；背景干净简洁，突出科技感和高级感；视频大概 15 秒左右，适合发到抖音上 | CS-VIDEO-001 §2 |
| 2 | 视频用途 | 电商详情页首屏视频 / 抖音小红书种草视频 / 广告投流素材；本案适配对象偏向官网 Banner、产品展示、短视频广告素材 | CS-VIDEO-001 §3 |
| 3 | 视频目标 | 在 15 秒内完整呈现智能水壶外观、核心功能（水温显示）与使用体验，激发观众购买欲 | CS-VIDEO-001 §4 D1 |
| 4 | 产品主体 | 极简智能水壶：哑光白圆柱形瓶身（约 24cm 高，约 7cm 直径），一体化圆形平底瓶盖，瓶身中部嵌入式圆形 LED 触控显示屏，熄灭时几乎不可见，整体如鹅卵石般流畅 | CS-VIDEO-001 §4 D2 |
| 5 | 场景 | 纯净浅灰渐变背景（#F5F5F5 → #E8E8E8），左上方微弱暖色光晕，右下方极淡冷色反射面，零杂物 | CS-VIDEO-001 §4 D3 |
| 6 | 动作 | ① 瓶身从左侧缓速滑入并自转 180°；② LED 屏亮起显示“56°C”；③ 瓶身倾斜约 30° 倒出透明水流；④ 回正后微微晃动一次 | CS-VIDEO-001 §4 D4 |
| 7 | 镜头运动 | 开篇缓慢推镜（Dolly In）→ 旋转时切换为 45° 俯角环绕轨道（Orbit）→ LED 亮起时急推至特写（Crash Zoom）→ 倒水时跟拍倾斜（Tilt Down）→ 结尾缓慢拉远（Pull Back） | CS-VIDEO-001 §4 D5 |
| 8 | 时间顺序 | 0.0s-2.5s 入场旋转 → 2.5s-5.0s LED 亮起展示 → 5.0s-10.0s 倒水使用演示 → 10.0s-13.0s 回正定格 → 13.0s-15.0s 品牌信息浮现 | CS-VIDEO-001 §4 D6 |
| 9 | 节奏 | 慢（入场）→ 急停（LED 亮）→ 中速流畅（倒水）→ 静（定格）→ 渐隐（结尾） | CS-VIDEO-001 §4 D7 |
| 10 | 风格 | 极简科技感（Minimalist Tech），参考 Apple 产品视频和 Nothing 品牌视觉语言 | CS-VIDEO-001 §4 D8 |
| 11 | 构图 | 中心构图为主，三分法为辅，留白率≥40%，产品始终为视觉重心 | CS-VIDEO-001 §4 D9 |
| 12 | 镜头 / 景别 | 全景 → 中景 → 大特写（LED 屏幕）→ 中近景（倒水）→ 全景 | CS-VIDEO-001 §4 D10 |
| 13 | 光线 | 主光左前 45° 柔光箱（80%）；轮廓光右后 30° 窄光束（40%）；LED 屏幕自身发光；环境底光填充阴影（20%） | CS-VIDEO-001 §4 D11 |
| 14 | 色彩 | 哑光白 #F0F0F0（瓶身）；冷蓝 #00AFFF（LED 数字与品牌点缀）；背景中性灰阶 #F5F5F5 ~ #E0E0E0；整体偏冷、洁净、科技 | CS-VIDEO-001 §4 D12 |
| 15 | 材质与细节 | 哑光颗粒表面、瓶盖与瓶身接缝 ≤0.3mm、镜面玻璃镶嵌 LED 区、底座防滑硅胶圈微弱纹理 | CS-VIDEO-001 §4 D13 |
| 16 | 氛围 | 安静、专注、品质生活、仪式感，强调冷静克制和高级感 | CS-VIDEO-001 §4 D14 |
| 17 | 时长 | 约 15 秒（±1 秒） | CS-VIDEO-001 §4 D15 |
| 18 | 画面比例 | 9:16 竖屏（1080×1920） | CS-VIDEO-001 §4 D16 |
| 19 | 首帧 | 智能水壶位于画面左侧三分之一处，瓶身呈 15° 微倾角，背景纯净浅灰，左侧有微弱动态模糊残影，LED 屏未亮 | CS-VIDEO-001 §4 D17 |
| 20 | 末帧 | 水壶回正居中，画面底部渐现半透明白色横条，内含占位品牌文字“HYDRATE SMART / SINCE 2026”，背景亮度较首帧降低约 10% | CS-VIDEO-001 §4 D18 |
| 21 | 负面限制 | 无人物、无水印、无复杂文字、无 logo（除末帧指定内容）、无杂乱背景、无闪烁、无主体变形、无产品形变、无错误屏幕文字、无背景跳变、无过度运动模糊、无风格突变、无侵权品牌元素 | CS-VIDEO-001 §10 |
| 22 | 中文视频提示词 | CS-VIDEO-001 §6 主提示词（含产品外观、场景、视频动作与时间线、镜头运动、光影、色彩与质感、风格与构图、技术参数） | CS-VIDEO-001 §6 |
| 23 | 英文视频提示词 | CS-VIDEO-001 §7 英文主提示词（含 Product Appearance、Scene & Environment、Action & Timeline、Camera Movement、Lighting、Color & Texture、Style & Composition、Technical Specifications） | CS-VIDEO-001 §7 |
| 24 | 3 个视频变体 | A 晨间仪式（生活感）、B 功能对比（信息对比）、C ASMR 质感（感官细节） | CS-VIDEO-001 §11 |
| 25 | 风险与注意事项 | 高风险：LED 文字渲染、水流物理模拟；中风险：镜头数量过多、Crash Zoom 风格过强、纯灰背景吸引力、产品占比偏小；低风险：中英文差异、品牌占位、变体范围 | CS-VIDEO-001 §14 |

---

## 4. 通用需求解析

| 解析项 | 内容 |
|--------|------|
| **视频目标** | 生成一个产品展示视频，在短时长内呈现智能水壶外观、LED 水温显示、使用演示和品牌收束感，适配官网 Banner / 产品展示 / 短视频广告场景 |
| **使用场景** | 产品官网、电商详情页、社交媒体广告、短视频信息流、新品介绍页 |
| **核心产品元素** | 哑光白圆柱形瓶身、圆形瓶盖、嵌入式 LED 触控屏、水温显示、细腻哑光材质、极简无 logo 外观 |
| **需要保留的视觉元素** | 浅灰渐变背景、冷暖光混合、冷蓝功能光、中心构图、40% 留白、商业产品摄影质感 |
| **需要保留的动作** | 产品旋转展示、LED 亮起、倒水使用、回正定格、品牌收束 |
| **需要保留的镜头运动** | 推镜、环绕、急推特写、跟拍倾斜、拉远 |
| **需要保留的时间顺序** | 开场建立主体 → 中段展示功能与使用 → 结尾收束品牌信息 |
| **需要避免的元素** | 人物、logo、复杂文字、杂乱背景、闪烁、变形、产品形态漂移、风格突变 |
| **平台适配重点** | 保持视频核心信息一致；根据平台特性调整语言、结构、动作复杂度、负面提示词写法和镜头描述方式；避免写死平台版本号和实时参数 |

---

## 5. 通用中文视频提示词

```
一段产品展示视频，竖屏比例，用于官网 Banner、产品展示或短视频广告。

产品是一个白色哑光智能保温水壶，圆柱形瓶身，圆形瓶盖，瓶身中部有一块嵌入式圆形 LED 触控显示屏。材质细腻哑光，整体造型极简，没有多余按键、logo 或装饰。

背景为纯净浅灰色渐变，左上方有微弱暖色光晕，右下方有极淡冷色反射面，画面干净无杂物。

视频动作按时间顺序展开：产品从左侧缓速滑入并轻微旋转展示外观；随后 LED 屏亮起，显示柔和冷蓝色温度数字；接着瓶身缓慢倾斜倒出透明水流，再回正静止；最后画面收束，底部浮现简洁品牌占位文字。

镜头运动包括：开场缓慢推镜，旋转阶段轻微环绕，屏幕亮起时快速推向特写，倒水时跟随倾斜拍摄，最后缓慢拉远回到全身构图。

整体风格为极简科技感，参考商业产品摄影和高级品牌视频。光线柔和，主光来自左前方，轮廓光勾勒产品边缘，LED 屏幕亮起时带出冷蓝色功能光。主色为哑光白，背景为中性灰阶，点缀色为冷蓝。画面稳定，节奏从舒缓过渡到功能强调，再回到宁静收束。

首帧为产品刚刚滑入左侧画面，屏幕未亮；末帧为产品回正居中，底部出现简洁品牌占位信息，画面亮度略微收束。

限制条件：画面稳定，不出现真实人物，不出现 logo，不出现复杂文字，不出现杂乱背景，不出现闪烁，不出现产品变形，不出现屏幕乱码，不出现风格突变。
```

**说明**：
- 保留 CS-VIDEO-001 的核心视频信息；
- 保留主体、动作、镜头运动、时间顺序、节奏、风格、光线、色彩、材质、首帧、末帧和负面限制；
- 不新增来源案例中没有的新事实；
- 不写具体平台版本号，不写实时平台参数。

---

## 6. 通用英文视频提示词

```
A vertical product showcase video for website banner, product display, or short-form advertising.

The product is a white matte smart insulated water bottle with a cylindrical body and a circular cap. A circular LED touchscreen display is embedded at the middle of the body. The surface is finely matte, and the overall design is minimalist with no extra buttons, logos, or decorative elements.

The scene is a clean light gray gradient background with a faint warm glow in the upper left and a very subtle cool-toned reflection area in the lower right. The frame is clean and uncluttered.

The video follows a clear temporal sequence: the bottle gently slides in from the left and slowly rotates to reveal its form; the embedded LED screen illuminates with a soft cold-blue temperature reading; the bottle tilts to pour a transparent water stream, then returns upright and settles; finally the frame closes with a simple brand placeholder near the bottom.

Camera movement includes a slow opening dolly-in, a subtle orbit during the rotation, a quick push toward the LED screen when it lights up, a downward tilt following the pour, and a slow pull-back to restore the full product composition.

The style is minimalist tech, referencing commercial product photography and premium brand films. Lighting is soft and controlled: a key light from the front-left, a rim light outlining the product edge, and a practical cold-blue glow from the LED display. The primary color is matte white, the background is neutral gray, and the accent color is cold blue. The video should be stable, with a rhythm that moves from calm to functional emphasis and then back to a composed ending.

The first frame shows the product just entering the left side of the frame with the screen off. The final frame shows the bottle centered and upright, with a simple brand placeholder appearing at the bottom and a slight overall dimming for closure.

Restrictions: stable footage; no real people; no logos; no complex text; no cluttered background; no flickering; no product deformation; no garbled screen text; no sudden style change.
```

**说明**：
- 与中文提示词语义一致；
- 不加入中文提示词中没有的新事实；
- 不写具体平台版本号，不写实时平台参数。

---

## 7. 通用负面提示词 / 限制条件

### 7.1 通用英文负面提示词

```
no brand logo
no watermark
no complex text
no real people
no cluttered background
no low resolution
no flickering
no camera shake
no subject deformation
no product shape change
no incorrect screen text
no background jumping
no excessive motion blur
no sudden style change
no copyrighted brand elements
```

### 7.2 中文自然语言限制版本

```
画面稳定，不出现真实人物；
不出现 logo、商标或品牌标识（除末帧指定占位信息外）；
不出现复杂文字、价格标签、促销信息或网页界面；
不出现杂乱背景或其他干扰物体；
不出现低清、模糊、闪烁、跳帧或压缩伪影；
不出现主体变形、产品形状改变或屏幕乱码；
不出现背景跳变、过度运动模糊或风格突变；
保持产品外观一致，保持材质、瓶盖和屏幕位置稳定。
```

---

## 8. Runway 适配版本

### Runway 提示词

```
A vertical minimalist tech product showcase video featuring a white matte smart insulated water bottle on a clean neutral gray gradient background. The cylindrical bottle has a circular cap and an embedded circular LED touchscreen at the center of the body. The product gently slides in from the left and slowly rotates to show its full exterior, then the LED screen lights up with a soft cold-blue glow. The bottle tilts slightly to pour a transparent water stream, returns upright, and the frame closes with a simple brand placeholder at the bottom. Camera starts with a slow dolly-in, shifts to a subtle orbit around the bottle, quickly pushes toward the screen when it illuminates, tilts down to follow the pour, and ends with a slow pull-back. The style is calm, clean, and commercial, with soft key light, rim light, and a cold-blue practical glow from the screen. The video should look stable and premium, with no people, no logos, no complex text, and no cluttered background. If the platform supports a negative or constraint field, exclude logos, watermarks, flickering, background jumps, subject deformation, garbled screen text, and sudden style changes.
```

### 镜头与动作说明

- **起始画面**：产品刚刚进入画面左侧，屏幕未亮，背景干净。
- **主体动作**：产品缓速滑入、轻微旋转、LED 屏亮起、轻微倾斜倒水、回正静止。
- **镜头运动**：慢推镜 → 轻微环绕 → 快速推向屏幕特写 → 跟随倾斜拍摄 → 缓慢拉远。
- **结束画面**：产品居中，底部出现简洁品牌占位文字，画面略微收束。
- **是否需要稳定镜头**：需要；全程保持画面稳定，避免抖动和背景跳变。

### 负面限制

如果平台提供负面字段，可填写：无人物、无 logo、无水印、无复杂文字、无杂乱背景、无闪烁、无主体变形、无产品形状改变、无屏幕乱码、无背景跳变、无运动模糊过度、无风格突变。

如果没有负面字段，将限制融入正向提示词中，强调“画面干净、稳定、商业产品摄影风格、产品形态保持一致”。

### 注意事项

- 具体版本和功能以当前平台文档为准；
- 如果使用参考图或首帧图，需要明确是作为起始画面输入、风格参考还是构图参考；
- LED 屏幕文字、水流物理效果和主体一致性是本案例的重点风险，需要优先检查；
- 不建议直接使用多镜头高强度运镜描述，必要时可拆分片段生成后拼接。

---

## 9. Pika 适配版本

### Pika 提示词

```
A short vertical product video of a white matte smart water bottle on a clean light gray background. The bottle slowly rotates to show its form, the embedded LED screen glows with a soft cold-blue light, and the camera gently pushes closer. The shot should be stable, clean, and minimal, with no people, no logos, and no clutter.
```

### 动作重点

1. **产品轻微旋转展示** — 用于呈现外观和材质；
2. **LED 屏幕微光亮起** — 用于传递功能亮点；
3. **镜头缓慢推近** — 用于增强产品聚焦，但保持画面稳定。

### 负面限制

画面保持干净稳定，不出现人物、logo、水印、复杂文字、杂乱背景、闪烁、主体变形或产品形状改变。如果平台支持负面字段，可单独列出；否则将限制融入正向描述中。

### 注意事项

- Pika 更适合轻量、简洁的产品动态展示；
- 不建议写入太多连续动作或复杂分镜；
- 本案例原始 5 个镜头属于较高复杂度，用于 Pika 时应优先保留“旋转、亮屏、推镜”等最核心信息；
- 具体时长、分辨率和功能支持以当前平台说明为准。

---

## 10. Kling / 可灵适配版本

### Kling / 可灵提示词

```
一段竖屏产品展示视频，白色哑光智能保温水壶放在干净的浅灰色渐变背景前。
产品是圆柱形瓶身、圆形瓶盖、中间有一块嵌入式圆形 LED 触控显示屏。
视频按时间顺序展开：产品从左侧缓速滑入并缓慢旋转，展示完整外观；随后 LED 屏亮起，显示冷蓝色温度数字；接着瓶身轻微倾斜倒出透明水流；最后产品回正静止，画面底部浮现简洁品牌占位文字。
镜头运动依次为：开场推镜，旋转时轻微环绕，屏幕亮起时快速推向特写，倒水时跟随拍摄，最后缓慢拉远。
整体风格为极简科技感，画面稳定，背景干净，材质细腻，不出现人物、logo、复杂文字或杂乱背景。
如果平台支持负面提示词，排除闪烁、主体变形、产品形状变化、屏幕乱码、背景跳变和风格突变。
```

### 时间顺序

| 阶段 | 时间 | 画面 | 动作 | 镜头运动 |
|------|------|------|------|----------|
| 开头 | 0.0s - 2.5s | 产品刚进入画面，屏幕未亮 | 缓速滑入并开始轻微旋转 | 推镜（Dolly In） |
| 中段 | 2.5s - 10.0s | LED 亮起，屏幕显示温度，产品倾倒出水 | 旋转展示、屏幕亮起、倒水、回正 | 环绕 → 急推特写 → 跟拍倾斜 |
| 结尾 | 10.0s - 15.0s | 产品居中静止，底部出现品牌占位文字 | 主体静止，画面收束 | 缓慢拉远（Pull Back） |

### 主体一致性要求

- 瓶身形态保持一致，不从圆柱形变为方形或不规则形状；
- 瓶盖与瓶身比例保持一致；
- LED 屏幕位置保持在瓶身中部，不漂移；
- 哑光白材质保持稳定，不突变为金属镜面或塑料感；
- 不出现人物、logo 或非指定文字；
- 不出现品牌变化或产品颜色偏移。

### 负面限制

如果平台支持独立负面字段，可填写：无人物、无 logo、无水印、无复杂文字、无杂乱背景、无闪烁、无主体变形、无产品形状变化、无屏幕乱码、无背景跳变、无风格突变。

如果没有独立字段，则将限制融入正向描述，强调产品外观稳定、画面干净、材质一致。

---

## 11. Luma 适配版本

### Luma 提示词

```
A vertical minimalist tech product showcase video focusing on a white matte smart insulated water bottle placed against a clean neutral gray gradient background. The cylindrical bottle has a circular cap and an embedded circular LED display at the center of the body. The camera begins slightly left of the product, slowly dollies in, then performs a gentle partial orbit while the bottle rotates to reveal its matte surface and cap detail. When the LED screen emits a soft cold-blue glow, the camera eases closer to emphasize the display. The composition maintains stable movement, balanced negative space, and smooth spatial transitions. Soft key light comes from the front-left, rim light outlines the bottle edge, and the LED provides a subtle practical light source. The overall tone is cool, clean, and premium. Exclude people, logos, complex text, background clutter, flickering, product deformation, garbled screen content, and sudden style changes.
```

### 镜头运动说明

- **起始位置**：产品偏左，屏幕未亮；
- **运动方式**：先慢推镜，再轻微环绕，然后在屏幕亮起时缓慢靠近；
- **运动速度**：全程低速稳定，避免突然加速；
- **结束位置**：镜头回到略远的全景/中全景，产品居中；
- **是否稳定**：需要保持稳定，避免漂移和抖动。

### 场景与空间关系

- 产品位于画面中景偏前，是唯一视觉主体；
- 背景为浅灰渐变，空间干净，没有复杂层次；
- 产品与背景之间保持清晰分离，避免前景干扰；
- 构图保持留白，避免产品充满画面；
- 主体运动路径保持自然、平稳，避免出现不合理的漂移。

### 注意事项

- 避免场景跳变，更适合平稳过渡；
- 避免主体漂移和产品形态变化；
- 避免过强的风格化处理，保持商业产品摄影质感；
- 具体功能和参数以当前平台官方说明为准。

---

## 12. Sora 适配版本

### Sora 视频提示词

```
A vertical commercial product video opens on a clean light gray gradient background. A white matte smart insulated water bottle slides gently into the left side of the frame and begins a slow rotation, revealing its cylindrical body, circular cap, and finely matte surface. The camera moves in slowly, then shifts into a subtle high-angle orbit to show the bottle from multiple perspectives. When the embedded circular LED touchscreen at the center of the bottle lights up, the camera quickly pushes closer to display a soft cold-blue temperature readout. The bottle then tilts slightly and releases a transparent water stream, after which it returns upright and settles. In the final moments, the camera pulls back gently, the product stays centered, and a minimal brand placeholder appears at the bottom while the overall frame dims slightly for closure.

The style should remain consistent throughout: minimalist tech, clean commercial product photography, soft key light from the front-left, rim light along the bottle edge, and a subtle cold-blue practical glow from the screen. The background stays clean and neutral, the bottle's matte white finish remains consistent, and the rhythm moves from calm to focused emphasis to quiet ending. Avoid real people, logos, complex text, cluttered backgrounds, flickering, shape distortion, garbled display text, and sudden stylistic changes.
```

### 时间顺序 / 分镜

| 镜头 | 时长 | 画面 | 动作 | 镜头运动 | 说明 |
|------|------|------|------|----------|------|
| 1 | 0.0s - 2.5s | 产品刚进入左侧画面，屏幕未亮 | 缓速滑入并开始旋转 | 慢推镜 | 建立主体第一印象 |
| 2 | 2.5s - 5.0s | 产品正面朝向观众，LED 屏亮起 | 屏幕显示冷蓝色温度数字 | 轻环绕 → 快推特写 | 功能亮点展示 |
| 3 | 5.0s - 10.0s | 瓶身倾斜，水流出现 | 使用演示和产品回正 | 跟拍倾斜 | 使用场景代入 |
| 4 | 10.0s - 15.0s | 产品居中静止，底部出现品牌信息 | 画面收束，整体略暗 | 缓慢拉远 | 稳定收尾与品牌记忆 |

### 风格连续性说明

- 风格始终为极简商业产品摄影；
- 光线保持柔和、可控，不出现强烈硬阴影；
- 色彩保持哑光白产品、中性灰背景、冷蓝功能光；
- 产品外观保持一致，不出现材质或形态突变；
- 背景保持简洁，不出现杂乱元素或场景跳变。

### 负面限制

以自然语言融入描述：无人物、无 logo、无水印、无复杂文字、无杂乱背景、无闪烁、无主体变形、无产品形状变化、无屏幕乱码、无背景跳变、无风格突变。

---

## 13. 豆包 / 即梦适配版本

### 豆包 / 即梦中文提示词

```
一段竖屏产品展示视频，白色哑光智能保温水壶放在干净的浅灰色渐变背景前，画面简洁高级。
产品是圆柱形瓶身、圆形瓶盖，瓶身中间有一块隐藏式 LED 触控显示屏。
镜头慢慢推近，产品轻微旋转展示外观，随后屏幕亮起显示冷蓝色温度数字，产品再缓慢倾斜倒出一点清水，最后回正静止。
整体风格是极简科技感，光线柔和，背景干净，画面稳定。
不要出现人物、logo、复杂文字、杂乱背景、闪烁、产品变形或屏幕乱码。
```

### 动作和镜头说明

- 产品轻微旋转，用于展示外观；
- 镜头慢慢推近，用于突出细节和材质；
- 屏幕微光显现，用于呈现智能功能；
- 画面保持稳定，用于维持商业产品摄影质感。

### 负面限制

- 不出现真实人物；
- 不出现 logo、商标或品牌标识；
- 不出现复杂文字、价格标签或促销信息；
- 不出现杂乱背景或干扰物体；
- 不出现闪烁、主体变形、产品形状变化或屏幕乱码；
- 不出现风格突变或画面抖动。

### 使用建议

- 先生成一个短版本，检查主体是否稳定；
- 确认 LED 屏幕、材质和背景表现后再迭代细节；
- 如果平台支持负面字段，可直接填入限制条件；
- 具体时长、分辨率和功能支持以当前平台版本为准。

---

## 14. 其他视频生成模型通用版本

### 通用视频模型提示词

```
A vertical minimalist product showcase video of a white matte smart insulated water bottle with a circular cap and an embedded LED screen, placed on a clean light gray gradient background. The bottle slowly rotates, the screen emits a soft cold-blue glow, the camera gently pushes closer, and the frame remains stable and clean. The style should be minimal, modern, and commercial. Avoid people, logos, complex text, cluttered backgrounds, flickering, shape distortion, and garbled screen text.
```

### 需要确认的模型信息

| 项目 | 确认内容 | 影响 |
|------|----------|------|
| 是否支持文生视频 | 是 / 否 | 决定能否从零开始生成 |
| 是否支持图生视频 | 是 / 否 | 决定能否使用首帧或参考图 |
| 是否支持首帧控制 | 是 / 否 | 决定能否固定起始画面 |
| 是否支持末帧控制 | 是 / 否 | 决定能否固定结束画面 |
| 是否支持负面提示词 | 是 / 否（或何种形式） | 决定限制条件写法 |
| 是否支持分镜 / 多镜头 | 是 / 否 | 决定能否使用复杂分镜 |
| 推荐输入语言 | 中文 / 英文 / 其他 | 决定提示词语言 |
| 时长限制 | 以平台文档为准 | 决定时间跨度 |
| 比例 / 分辨率限制 | 以平台文档为准 | 决定构图方式 |
| 运动强度控制 | 支持 / 不支持 / 方式 | 决定动作幅度写法 |

### 注意事项

- 先用最简单的单动作版本进行测试；
- 不确定平台能力时，不要写复杂分镜或长时间镜头链；
- 如果平台不支持负面提示词，应把限制直接写入正向提示词；
- 具体能力以当前模型说明为准。

---

## 15. 平台差异说明

| 平台 | 推荐提示词风格 | 负面提示词处理 | 动作复杂度 | 镜头运动复杂度 | 首帧 / 末帧处理 | 产品视频注意事项 |
|------|----------------|----------------|------------|----------------|------------------|------------------|
| Runway | 自然语言段落，结构清晰 | 视平台界面而定；无独立字段时融入正向描述 | 中等，适合 2-4 个关键动作 | 中高，适合明确运镜描述 | 可支持图生视频，需说明首帧用途 | 重点检查主体一致性和屏幕文字 |
| Pika | 简洁短句，1-3 句优先 | 通常融入正向描述 | 低，建议 1-3 个重点动作 | 低，适合简单推镜或缩放 | 以平台当前能力为准 | 避免复杂分镜，优先保稳定 |
| Kling / 可灵 | 中文或英文均可，按时间顺序分段 | 通常可填写限制内容 | 中高，适合较完整动作链 | 中高，适合推镜、环绕等 | 支持首尾帧能力时可用于稳定起止画面 | 强调产品一致性、材质和光影 |
| Luma | 强调空间、光线、镜头流畅性 | 视平台界面而定 | 中等，适合平稳动作 | 中高，适合平滑运镜 | 可说明起止画面的空间关系 | 避免场景跳变和主体漂移 |
| Sora | 完整自然语言叙事，可更详细 | 通常以自然语言排除 | 中高，适合多镜头故事化描述 | 高，可串联多种运镜 | 以平台功能为准 | 保持风格连续性和逻辑自洽 |
| 豆包 / 即梦 | 自然中文，口语化但克制 | 中文限制条件通常表达直接 | 中低，优先 2-3 个直观动作 | 中低，适合缓推、轻环绕 | 以平台当前能力为准 | 先测试短版本，避免信息过载 |
| 其他视频生成模型 | 最简洁自然语言，保守描述 | 不确定时以正向替代 | 低，建议最少动作 | 低，建议最基础运镜 | 不假设高级能力 | 先确认模型能力再扩展复杂度 |

---

## 16. 推荐优先测试平台

| 平台 | 推荐优先级 | 理由 | 注意事项 |
|------|------------|------|----------|
| Kling / 可灵 | 第一优先 | 产品展示、主体一致性、中文能力和时间结构支持较匹配 | 重点检查 LED 文字、水流物理和产品外观稳定性 |
| Runway | 第二优先 | 自然语言理解、镜头运动表达和商业风格控制能力较好 | 注意运镜复杂度与生成稳定性之间的平衡 |
| Luma | 备选平台 | 画面稳定、空间感和光影质感适合产品展示 | 注意避免主体漂移和场景跳变 |
| Sora | 备选平台 | 适合更完整的时间描述和多镜头结构 | 注意不要过度复杂化，并核验平台当前可用能力 |
| 豆包 / 即梦 | 中文场景备选 | 中文自然语言表达顺手，适合快速迭代 | 先做短版本测试，再逐步增加细节 |
| Pika | 不确定 / 轻量测试平台 | 适合轻量展示，但对复杂多镜头支持较弱 | 需显著简化原始动作和镜头数量 |
| 其他视频生成模型 | 不确定平台 | 能力差异大，需先确认 Model Card 或文档 | 从最保守的单动作版本开始测试 |

---

## 17. 需要人工确认的问题

| # | 确认项 | 说明 |
|---|--------|------|
| 1 | 是否有参考图或首帧图 | 如果有，需要确认是作为风格参考、构图参考还是 I2V 首帧输入 |
| 2 | 是否需要固定产品外观 | 如需严格一致，应加强产品形态、材质和屏幕位置一致性描述 |
| 3 | 是否需要精确屏幕数字 | “56°C”属于高风险文字渲染项，如需精确显示建议后期叠加 |
| 4 | 是否需要真实品牌元素 | 如需真实 logo 或品牌名，需要额外处理侵权、字体与风格一致性 |
| 5 | 是否需要无人物 | 当前版本默认无人物；若允许人物入镜，需要修改提示词结构 |
| 6 | 是否需要固定时长 | 如平台时长限制较短，需要删减镜头数量或保留核心动作 |
| 7 | 是否需要适配某个具体平台 | 如已确定目标平台，可进一步压缩为单平台优化版本 |

---

## 18. 视频平台适配检查清单

| # | 检查项 | 是否通过 | 说明 |
|---|--------|----------|------|
| 1 | 是否保留主体 | ✅ | 智能水壶主体、外观特征和核心功能均保留 |
| 2 | 是否保留场景 | ✅ | 浅灰渐变背景、干净画面和光影关系保留 |
| 3 | 是否保留动作 | ✅ | 旋转、LED 亮起、倒水、回正、收束等核心动作保留 |
| 4 | 是否保留镜头运动 | ✅ | 推镜、环绕、急推特写、跟拍倾斜、拉远均保留 |
| 5 | 是否保留时间顺序 | ✅ | 开场 → 中段展示 → 结尾收束的顺序保留 |
| 6 | 是否保留节奏 | ✅ | 保留“舒缓 → 功能强调 → 平静收束”的节奏方向 |
| 7 | 是否保留风格 | ✅ | 极简科技感、商业产品摄影风格保留 |
| 8 | 是否保留光线 | ✅ | 主光、轮廓光、环境光和 LED 功能光均保留 |
| 9 | 是否保留色彩 | ✅ | 哑光白、中性灰背景、冷蓝功能色保留 |
| 10 | 是否保留材质 | ✅ | 哑光材质、细腻表面、产品细节保留 |
| 11 | 是否保留首帧 / 末帧 | ✅ | 产品刚进入画面的首帧和品牌收束的末帧均保留 |
| 12 | 是否保留负面限制 | ✅ | 无人物、无 logo、无复杂文字、无杂乱背景等限制保留 |
| 13 | 是否避免写死平台版本 | ✅ | 未硬编码具体平台版本号 |
| 14 | 是否避免写死实时参数 | ✅ | 未硬编码时长、分辨率、运动强度等实时参数 |
| 15 | 是否避免跨平台误用参数 | ✅ | 各平台按其风格和能力分别适配 |
| 16 | 是否说明参考图用途 | ✅ | 如使用参考图或首帧图，已在注意事项中要求明确用途 |
| 17 | 是否说明首帧 / 末帧用途 | ✅ | 首帧用于起始画面，末帧用于品牌收束 |
| 18 | 是否保留风险限制 | ✅ | LED 文字、水流物理、主体一致性等风险已保留 |
| 19 | 是否给出平台差异说明 | ✅ | 已提供平台差异对照表 |
| 20 | 是否有人工确认项 | ✅ | 已列出 7 项人工确认问题 |

---

## 19. 测试结论

| # | 判断项 | 结论 |
|---|--------|------|
| 1 | T-VIDEO-002 是否适用于 CS-VIDEO-001 | ✅ 适用 |
| 2 | T-VIDEO-002 是否适用于产品展示视频 / 官网 Banner 视频场景 | ✅ 适用 |
| 3 | 是否需要修改 T-VIDEO-002 | ❌ 当前不需要 |
| 4 | 是否需要修改 CS-VIDEO-001 | ❌ 当前不需要 |
| 5 | 是否需要修改 T-VIDEO-001 | ❌ 当前不需要 |
| 6 | 是否需要修改 video-prompt-quick-reference | ❌ 当前不需要 |
| 7 | 是否可以将本测试作为 TEST-VIDEO-002-001 入库 | ✅ 可以 |

**总判断**：T-VIDEO-002 在 CS-VIDEO-001 这一产品展示视频场景中可用，能够把同一个通用视频提示词改写为多平台版本，且在改写过程中保留了核心视频信息。

---

## 20. 与图像平台适配测试的关系

本测试是 Prompt-KB 从**静态图像平台适配**进入**动态视频平台适配**的延伸验证。

- `TEST-IMG-002-001` 验证封面图平台适配；
- `TEST-IMG-002-002` 验证产品图平台适配；
- `TEST-VIDEO-002-001` 验证产品展示视频平台适配；
- 本测试扩展了从静态图像平台适配到动态视频平台适配的能力。

| 维度 | TEST-IMG-002-001 | TEST-IMG-002-002 | TEST-VIDEO-002-001 | 变化 |
|------|------------------|------------------|--------------------|------|
| 被测模板 | T-IMG-002 | T-IMG-002 | T-VIDEO-002 | 从图像适配模板扩展到视频适配模板 |
| 来源案例 | CS-IMG-001 | CS-IMG-002 | CS-VIDEO-001 | 从抽象封面图 / 产品主图扩展到产品展示视频 |
| 核心保留维度 | 主体、场景、风格、构图、光线、色彩、负面限制 | 主体、场景、风格、构图、光线、色彩、材质、负面限制 | 主体、场景、动作、镜头运动、时间顺序、节奏、风格、光线、色彩、材质、首帧、末帧、负面限制 | 新增运动层与帧控制层保留要求 |
| 适配重点 | 平台语言、参数风格和限制写法差异 | 商业产品图的材质、光影与限制表达差异 | 视频时序、动作复杂度、镜头运动与平台能力差异 | 从静态结构适配扩展为动态结构适配 |
| 风险重心 | 文字、logo、风格过度堆砌 | 材质失真、颜色偏移、产品形态漂移 | LED 文字渲染、水流物理、主体一致性、镜头复杂度 | 风险从画面层扩展到时间层和物理层 |

---

## 21. 后续建议

建议选择：

- **A. 登记 TEST-VIDEO-002-001 到案例索引** ✅ **推荐下一步**
- B. 小修 T-VIDEO-002 — 当前测试未发现必须修改的问题
- C. 创建第二个视频案例 — 可在登记完成后按需扩展
- D. 小修 T-VIDEO-001 或速查卡 — 暂不必要
- E. 创建视频模块阶段性验收报告 — 可作为后续汇总动作

---

## 22. 版本记录

| 版本 | 日期 | 说明 |
|------|------|------|
| v0.1 | 2026-05-27 | 使用 CS-VIDEO-001 测试 T-VIDEO-002 视频平台适配模板，生成 Runway、Pika、Kling / 可灵、Luma、Sora、豆包 / 即梦和其他视频生成模型的多平台适配版本，用于验证产品展示视频场景下的视频平台适配能力。 |
