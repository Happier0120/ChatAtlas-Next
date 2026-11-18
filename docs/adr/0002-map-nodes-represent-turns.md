# ADR-0002：地图节点代表 Turn，浏览位置与发送目标分开理解

- **Document status:** Draft — 已确认决策的整理稿，待审核本文表述。
- **Decision status:** Accepted — 地图节点的领域指代与浏览不改变发送目标的原则已获用户确认。
- **Recorded:** 2026-11-18（Asia/Shanghai）

[Feature Map](../product/feature-map.md) 的 MAP-01～03 要求查看 Turn 对应内容、理解关系并导航，[MVP Scope](../product/mvp-scope.md) 的 MP03 要求地图表达真实关系并支持接续。[ADR-0001](0001-conversations-share-turns-after-fork.md) 已确定同一个历史 Turn 可以同时属于多个 Conversation，因此必须明确节点究竟指代 Turn，还是某个 Conversation 内的 Turn 位置。

本次决定：地图中的讨论节点代表 Turn 本身，其所指向的 Turn 可以关联多个 Conversation。用户当前浏览的 Turn 与下一条 Prompt 的发送目标 Conversation 分开理解，单纯浏览历史不会改变发送目标或 Continue 的接续位置，也不会触发 Fork。

## 考虑过的选择与取舍

| 选择 | 节点的领域含义 | 后果 |
| --- | --- | --- |
| 采用：节点代表 Turn 本身 | 指向一次问答，不限定其所属的某一个 Conversation | 与 Turn 的共同身份一致；仅定位节点不能唯一确定发送目标 |
| 未采用：节点代表某个 Conversation 中的 Turn 位置 | 同时限定 Conversation 与 Turn | A 中的 T2 与 B 中的 T2 是不同导航位置，尽管指向同一个 Turn |

上述比较为 Agent 对方案的整理。选择 Turn 本身作为节点的领域指代，保留共同历史的身份含义，也将“确定正在查看什么”和“确定继续哪条讨论”之间的区别留给后续领域与 UX 协同设计；改变该选择会影响导航语义，因此保留此 ADR。

## 具体后果与待决边界

当 A 包含 T1 → T2 → T3、B 包含 T1 → T2 → T4 时，定位 T2 只确定用户查看的问答，不能据此判断下一条 Prompt 发往 A 还是 B。用户必须能理解和控制发送目标；目标如何表达、选择及切换，仍是领域建模与 UX 的共同待决问题。

此决定不规定一个 Turn 在画面中出现几次，不规定节点外观、布局、地图入口或具体点击行为，也不决定浏览、切换与 Fork 需要几次操作。尚未开展 UX 原型或可用性验证。

## 确认依据与范围

以下记录来自本会话，日期同本文，不虚构各轮时间戳。

- 用户明确认可“查看历史节点、切换讨论方向、Fork 是不同操作意图”，并补充：“单纯浏览历史不能自动触发 Fork 或改变发送目标。”
- 在“节点代表 Turn 本身”与“节点代表某个 Conversation 中的 Turn 位置”两个方案之间，用户回复“选择A”，确认前者。
- 用户另行确认 Continue 始终在目标 Conversation 当前末尾追加新 Turn，见 ADR-0001。
- 本轮仅授权编写术语表与必要 ADR，未批准本文全文、具体 UX 或 Git Commit。

术语定义以根目录 [GLOSSARY](../../GLOSSARY.md) 为准；本决定未继承旧 ChatAtlas 的地图或 Fork 设计。
