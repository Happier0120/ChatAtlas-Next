# ADR-0003：未完成 Turn 保留历史，再次提交追加新 Turn

- **Document status:** Draft — 已确认决定的整理稿，待审核本文表述。
- **Decision status:** Accepted — 用户已逐项确认本决定涉及的行为。
- **Recorded:** 2026-11-18（Asia/Shanghai）
- **Basis:** [本轮 Feature Discovery](../product/mvp-feature-discovery.md) FD-17～20、FD-31；Q17～Q20、Q31 分别回复“支持”“允许”“同意”“同意”“允许”。

Turn 可以在回复尚无内容或未完成时留在讨论历史中；停止、失败、中断保留已提交 Prompt、已收到部分和真实状态。用户继续或重新提交原 Prompt 时追加新 Turn，原异常记录不被覆盖或补全，新请求按当前 Conversation 历史继续，而不保证复现原请求上下文；这是在“覆盖原异常回复”与“保留原记录、另行追加”之间选择后者，以保留尝试过程，代价是可能出现重复 Prompt。后续必要历史应能表达保留内容及其未完成状态；已结束且有 AI 内容的异常 Turn 也可以成为 Fork 的共同历史。

上述取舍理由是 Agent 在提案中的说明，用户确认了相应方案，不额外推断用户未陈述的动机。与 [ADR-0001](0001-conversations-share-turns-after-fork.md) 的共同 Turn 身份结合后，覆盖旧异常记录可能改变多条讨论所理解的同一段历史；历史身份、地图和上下文形成依赖后，再改为原位替换将有实质迁移成本，因此独立保留此决定。

本决定不引入回复版本或生成尝试实体，不决定历史存储及上下文算法，也不泛化决定所有既有 Turn 的编辑／同步规则。术语以 [GLOSSARY](../../GLOSSARY.md) 为准；具体产品边界及来源以 Feature Discovery 为准。写入授权不等于本文全文 Approved 或 Git Commit 授权。
