# ADR-0001：Fork 创建独立 Conversation，历史 Turn 可共同归属

- **Document status:** Draft — 已确认决策的整理稿，待审核本文表述。
- **Decision status:** Accepted — 下列基本领域语义已由用户逐项选择或确认。
- **Recorded:** 2026-11-18（Asia/Shanghai）

[MVP Scope](../product/mvp-scope.md) 的 MP02 要求原讨论与 Fork 新方向能够独立继续，但当时保留了 Conversation 与 Fork 的身份关系。[Product Vision](../product/product-vision.md) 要求 Project、Conversation、Turn 保持概念区分。

本次决定：New Chat 创建独立起点的 Conversation；Fork 从历史 Turn 的 AI 回复位置创建新的 Conversation，并保留与来源 Conversation、来源 Turn 的关联。同一个历史 Turn 可以同时属于多个 Conversation，仍是同一次问答。Turn 表示一次用户 Prompt 与对应 AI 回复；Continue 仅在明确的目标 Conversation 当前末尾追加新 Turn，新增 Turn 不自动加入其他 Conversation。

## 考虑过的选择与取舍

| 问题 | 采用的选择 | 未采用的选择 | 取舍分析 |
| --- | --- | --- | --- |
| Fork 后的讨论身份 | 新方向拥有独立 Conversation 身份 | 同一 Conversation 内创建分支，Conversation 包含整棵分叉讨论树 | 将可独立继续的讨论方向作为 Conversation；不再用一个 Conversation 同时指代多个发送方向 |
| 历史 Turn 的归属 | 相同历史 Turn 可同时属于多个 Conversation | Turn 只属于原 Conversation，新 Conversation 通过来源关系回溯 | 共同历史直接属于相关 Conversation；代价是不能由一个 Turn 唯一推定其所属 Conversation |

表中取舍是 Agent 对所讨论方案的整理，不额外推断用户未表达的选择动机。Conversation 身份与历史 Turn 归属会影响后续领域语言、历史解释和导航；形成依赖后再改动会有实质成本，因此将这组相关决定保留为一份 ADR。

## 已确认场景与后果

| 阶段 | Conversation A | Conversation B |
| --- | --- | --- |
| 原讨论已进行三轮 | T1 → T2 → T3 | 尚未创建 |
| 从 T2 的 AI 回复 Fork，在 B 中形成 T4 | T1 → T2 → T3 | T1 → T2 → T4 |
| A Continue 产生 T5，B Continue 产生 T6 | T1 → T2 → T3 → T5 | T1 → T2 → T4 → T6 |

T1、T2 在 A、B 中保持相同的 Turn 身份。查看历史 T2 时，如果发送目标是 A，Continue 仍接在 A 的当前末尾；不会因为浏览位置而改成从 T2 另开方向、切换发送目标或替换后续内容。

共同归属使单一 Turn 不能唯一标识当前讨论方向；这一后果与 [ADR-0002](0002-map-nodes-represent-turns.md) 的地图节点语义共同约束后续 UX 设计。

## 确认依据与范围

以下为本会话的可独立阅读记录；记录日期为本文日期，不虚构各轮时间戳。

| 用户原话 | 当时选择或确认的内容 |
| --- | --- |
| “我选择A” | Fork 创建新的 Conversation，而非在同一 Conversation 内创建分支 |
| “采用A” | 一个 Turn 是一次用户 Prompt 与对应 AI 回复组成的问答单元 |
| “选择B” | T1、T2 同时属于原 Conversation A 与 Fork 后的 Conversation B，而非只归属于 A |
| “确认” | Continue 始终在目标 Conversation 的当前末尾追加新 Turn |
| “确认” | Fork 后，各 Conversation 新增的 Turn 不自动加入另一条 Conversation |

用户随后授权编写 GLOSSARY 并评估、记录必要 ADR；该写入授权不自动批准本文全文，也不包含 Git Commit。

本决定限定基本身份、归属和 Continue 语义。它不决定历史存储、模型上下文构造、已有 Turn 的修改或同步规则，也不决定未完成问答、保存时点、恢复机制及具体 UX；示例不代表已完成可用性或实现验证。旧 ChatAtlas 的领域文档未作为本决定依据。

术语定义以根目录 [GLOSSARY](../../GLOSSARY.md) 为准。
