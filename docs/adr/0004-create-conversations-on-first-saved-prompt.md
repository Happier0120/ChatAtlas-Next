# ADR-0004：新 Conversation 在首次 Prompt 确认保存时建立，准备输入独立作为草稿

- **Document status:** Draft — 已确认决定的整理稿，待审核本文表述。
- **Decision status:** Accepted — 用户已逐项确认本决定涉及的行为。
- **Recorded:** 2026-11-18（Asia/Shanghai）
- **Basis:** [本轮 Feature Discovery](../product/mvp-feature-discovery.md) FD-24、FD-26～30、FD-33；Q24、Q26、调整后的 Q27、Q28、Q29、Q30、Q33 分别回复“同意”“采用”“同意”“采用”“同意”“同意”“同意”。

MVP 暂无删除或归档讨论的能力，点击 New Chat 或准备 Fork 时立即保留新 Conversation，会积累尚未开展讨论的记录。用户选择首次 Prompt 发送成功并确认保存时，才建立并保存新 Conversation；未提交输入可独立手动保存为输入草稿，保存草稿不创建 Conversation 或 Turn，也不进入地图或模型上下文。已有 Conversation 各有一份输入草稿，每个 Project 一份新讨论输入草稿，后者可准备独立 New Chat 或 Fork；Fork 草稿同时保留所选来源 Conversation／Turn，首次发送成功后新 Conversation 保留共同历史与来源关联。

这是在“打开准备界面即保留讨论”与“首次提交成功才保留讨论”之间选择后者，避免空讨论积累，同时以独立草稿支持跨页面恢复；代价是准备态与已建立讨论必须在 UX 中清楚区分，且每 Project 只能保存一份新讨论输入草稿。取舍理由来自 Agent 提案及用户确认，不额外推断用户动机；草稿与讨论历史的边界一旦被身份、列表、地图、来源及保存流程依赖，再合并或更改建立时点有实质成本，因此独立记录。

本决定细化 [ADR-0001](0001-conversations-share-turns-after-fork.md) 留给后续的保存与 UX 边界，不改变 New Chat／Fork 创建独立 Conversation 或共同 Turn 的身份语义，不指定数据库事务、API 顺序或草稿存储方案。草稿清除与未保存修改保护见 Feature Discovery FD-29／30，术语以 [GLOSSARY](../../GLOSSARY.md) 为准。文档保持 Draft，未获 Git Commit 授权。
