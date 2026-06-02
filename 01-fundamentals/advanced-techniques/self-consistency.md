# Self-Consistency (SC) — 自洽性验证

> 🟢 **立即掌握** | DAIR.AI Advanced Prompting #2 | [返回总览](../dair-ai-advanced-prompting.md)

---

## 1. 一句话解释

**同一个问题问模型多次，取多数投票的结果作为最终答案。**

```
问题：我 6 岁时妹妹是我年龄的一半。现在我 70 岁，妹妹多少岁？

❌ 标准 CoT（可能出错）：70 ÷ 2 = 35 → 答：35 岁

✅ Self-Consistency 问 5 次：
   第 1 次：6 岁时妹妹 3 岁，年龄差 3 岁。70 - 3 = 67 岁
   第 2 次：妹妹当时是一半即 3 岁，差 3 年。70 - 3 = 67 岁
   第 3 次：70 / 2 = 35 → 答：35 岁（❌ 掉入陷阱）
   第 4 次：年龄差不变 = 3 岁。70 - 3 = 67 岁
   第 5 次：70 减去 (6-3) = 67 岁
   → 投票结果：67 岁占 4 票，35 岁占 1 票
   → 最终答案：67 岁 ✅
```

---

## 2. 适合什么时候用

- ✅ **关键决策的高精度推理** — 不能容忍错误的场景（医疗/法律/金融）
- ✅ **CoT 已经用了但还不够准** — SC 是 CoT 的直接升级
- ✅ **数学/逻辑题的错误率偏高时** — 多票投票有效过滤掉随机错误路径
- ✅ **有 API 调用预算** — SC 需要多次调用，成本较高
- ✅ **对延迟不敏感的离线任务** — 批处理场景理想

---

## 3. 不适合什么时候用

- ❌ **API 成本敏感的场景** — 5-40 倍调用成本
- ❌ **实时交互/低延迟要求** — 需要等待多次调用完成
- ❌ **简单任务已经够准了** — 杀鸡焉用牛刀
- ❌ **Temperature 必须设为 0 的场景** — 无法产生多样化输出
- ❌ **只需要一个"差不多"的答案** — 一次 CoT 就够了

---

## 4. 核心原理

- 用**"多数投票"**替代**"贪心解码"**（只取最可能的单次输出）
- 正确的推理路径通常更稳定、更容易重复出现
- 错误路径往往是随机波动，不容易重复
- **前提条件：** 需要 `temperature > 0` 来获得多样化输出

**SC 本质上是 CoT 的增强层——它不替代 CoT，而是在 CoT 之上加一道保险。**

---

## 5. 中文提示词模板

Self-Consistency 不是单一 prompt 技术，而是一种**调用策略**。模板体现在配置层面：

```python
# 伪代码：Self-Consistency 调用策略
def self_consistency(question, num_samples=5):
    results = []
    for i in range(num_samples):
        # 每次 CoT 调用使用不同的 temperature
        response = call_llm(
            prompt=f"{question}\n\n请一步一步地思考，并给出最终答案。",
            temperature=0.7,  # 必须 > 0
            top_p=0.9
        )
        answer = extract_final_answer(response)
        results.append(answer)

    # 多数投票
    final_answer = majority_vote(results)
    return final_answer
```

**Prompt 层面（每次调用的 prompt）：**
```markdown
{问题描述}

请一步一步地思考，并给出最终答案。
```

> 注意：prompt 本身就是标准 CoT prompt。SC 的"魔法"在于**多次调用 + 投票聚合**，不在 prompt 措辞。

---

## 6. OpenClaw 使用方式

### 配置方案：SC 增强的 CoT Agent

```
┌───────────────────────────────────────────────────┐
│           SC-Enhanced CoT Agent                    │
├───────────────────────────────────────────────────┤
│ 调用策略（在代码层面控制）：                         │
│                                                   │
│  for i in range(num_samples):                     │
│      response = agent.run(prompt,                 │
│          temperature=0.7,                          │
│          top_p=0.9)                                │
│      answers.append(extract_answer(response))     │
│                                                   │
│  final_answer = majority_vote(answers)             │
│                                                   │
│ Agent 内部 System Prompt：同标准 CoT Agent          │
└───────────────────────────────────────────────────┘
```

**关键参数配置：**
```
- temperature: 0.7（必须 > 0 才能有多样性）
- top_p: 0.9（允许一定的随机性）
- num_samples: 5-40（根据任务难度和成本预算决定）
- aggregation: majority_vote（多数投票）
```

**⚠️ 注意：** 增加 sampling 会提高 API 成本和延迟。如果只是简单任务，1-2 次 CoT 通常就够了。

---

## 7. 单 Agent 适配度

# ★★★★☆ (4/5)

**原因：**
- SC 通过对同一 Agent 的多次调用即可实现，不需要改变 Agent 架构
- 但增加了调用成本和延迟，不是所有场景都值得用
- **最佳实践：先用纯 CoT，发现错误率不可接受时再加 SC**

---

## 8. 多 Agent 适配度

# ★★★★★ (5/5)

**原因：**
- SC 可以用**多 Agent 并行推理 + 投票**来实现——天然并行化
- 每个 Agent 独立跑 CoT，最后汇总投票
- 这是多 Agent 场景下利用并行性降低延迟的理想模式

```
┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐
│ Agent 1 │  │ Agent 2 │  │ Agent 3 │  │ Agent 4 │  │ Agent 5 │
│ CoT → A │  │ CoT → A │  │ CoT → B │  │ CoT → A │  │ CoT → A │
└────┬─────┘  └────┬─────┘  └────┬─────┘  └────┬─────┘  └────┬─────┘
     │             │             │             │             │
     └─────────────┴─────────────┴─────────────┴─────────────┘
                           ↓
                   Majority Vote → 最终答案
```

---

## 9. 常见失败

| # | 失败模式 | 典型表现 | 根本原因 |
|---|----------|----------|----------|
| 1 | **Temperature 设为 0** | 调了 5 次结果完全一样，投票毫无意义 | temperature=0 导致输出确定性强，无法产生多样性 |
| 2 | **采样次数不够** | 3 次里有 2 次错误，投票反而选中错的 | 简单任务 5 次、复杂任务 20-40 次为宜 |
| 3 | **答案抽取规则模糊** | "67 岁" 和 "她今年 67 岁" 被当作不同答案 | 需要先做答案标准化（extract/normalize）再做投票 |
| 4 | **成本失控** | num_samples=40 + 长 prompt = 单题 token 消耗爆炸 | 必须根据预算和精度需求平衡采样次数 |

---

## 10. 修正提示

### 修正：Self-Consistency 无效 → 检查 Temperature 设置

**❌ 错误：** 调了 5 次结果一模一样

**✅ 修正——配置正确的采样参数：**
```
self_consistency 配置：
- temperature: 0.7（必须 > 0 才能有多样性）
- top_p: 0.9（允许一定的随机性）
- num_samples: 5-40（根据任务难度和成本预算决定）
- aggregation: majority_vote（多数投票）

⚠️ 注意：增加 sampling 会提高 API 成本和延迟
   如果只是简单任务，1-2 次 CoT 通常就够了
```

**答案标准化要点：**
```python
def normalize_answer(raw_text):
    """抽取并标准化答案，避免格式差异影响投票"""
    import re
    # 提取数字/关键词
    match = re.search(r'(\d+)\s*(岁|元|%|件)?', raw_text)
    if match:
        return match.group(0).strip()
    return raw_text.strip()
```

---

## 11. 示例

### 场景：周报增长率核算的高精度验证

**需求：** 周报中的环比增长率数据不能出错——这是给管理层看的报告。

**实现方式：**
```python
# 对每个品类的增长率做 Self-Consistency 验证
question = f"""
品类：{category_name}
本周销量：{this_week_qty} 件
上周销量：{last_week_qty} 件
报告中显示环比变化：{reported_wow}%

请一步一步地重新计算环比增长率，并给出你的计算结果。
"""

answers = self_consistency(question, num_samples=5)
# 5 次中有 4 次得出 "+15.2%"，1 次算错 → 采用 15.2%
```

**何时用：** 关键数值（Top5 品类的增长率、总销售额等）；非关键数据用单次 CoT 即可。

---

## 12. 与其他技术的组合方式

| 组合 | 方式 | 效果 |
|------|------|------|
| **SC + CoT** | 基础组合——CoT 推理 + SC 投票 | SC 的默认用法，降低 CoT 错误率 |
| **SC + 多 Agent 并行** | N 个 Agent 并行跑 CoT，汇总投票 | 利用并行性降低延迟 |
| **SC + Prompt Chaining** | Chaining 中的关键步骤用 SC 增强 | 仅对容易出错的步骤加 SC，控制成本 |

**SC 不适用的组合：** SC 依赖随机多样性，与需要确定性输出的场景（如代码生成、格式转换）不太搭配。

---

## 13. 推荐存放路径

```
prompt-kb/01-fundamentals/advanced-techniques/self-consistency.md
```

---

## 14. 版本记录

| 版本 | 日期 | 变更说明 |
|------|------|----------|
| v0.1 | 2026-05-14 | 从 dair-ai-advanced-prompting.md v0.1 拆分独立为技术卡片 |
