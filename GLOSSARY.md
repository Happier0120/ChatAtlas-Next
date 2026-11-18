# ChatAtlas-Next

本术语表定义 MVP 多方向讨论中的 Project、Conversation、Turn、Fork 与输入草稿等概念，作为领域建模与 UX 设计的共同语言。

- **Document status:** Draft — 已确认术语的整理稿，待审核本文表述。
- **Last updated:** 2026-11-18（Asia/Shanghai）
- **Decision basis:** 本会话逐项确认，记录见 [ADR-0001](docs/adr/0001-conversations-share-turns-after-fork.md)、[ADR-0002](docs/adr/0002-map-nodes-represent-turns.md) 及 [MVP Feature Discovery](docs/product/mvp-feature-discovery.md)；未完成 Turn 与草稿边界的取舍另见 [ADR-0003](docs/adr/0003-preserve-incomplete-turns-and-append-new-attempts.md)、[ADR-0004](docs/adr/0004-create-conversations-on-first-saved-prompt.md)。

## Language

**Project**：
个人工作空间中按主题或任务组织讨论的单位，可以容纳多条独立 Conversation 及多棵对话树。
_Avoid_：用 Project 代指一条 Conversation、一棵树或默认共享全部上下文的讨论集合。

**Conversation**：
固定属于一个 Project、可独立继续的一条讨论，包含按讨论顺序组织的 Turn；New Chat 与 Fork 都会创建新的 Conversation。
_Avoid_：用 Project、Turn 或整棵分叉讨论树代指 Conversation。

**Turn**：
一次已提交的用户 Prompt 及其对应 AI 回复所构成的问答单元，回复可以尚未收到或未完成；同一个 Turn 可以同时属于多个 Conversation，其身份不因共同归属而改变。
_Avoid_：将用户消息和 AI 回复各算一个 Turn；将未提交输入称为 Turn，或因回复未完成就否认该已提交问答的 Turn 身份。

**New Chat**：
创建独立起点 Conversation 的操作。
_Avoid_：用 New Chat 代指 Continue 或 Fork。

**Continue**：
在发送目标 Conversation 的当前末尾追加新 Turn 的操作；新 Turn 不自动加入其他 Conversation。
_Avoid_：将历史位置另开方向称为普通继续。

**Fork**：
从历史 Turn 的 AI 回复位置展开新方向、创建新 Conversation 的操作；新 Conversation 保留与来源 Conversation 及来源 Turn 的关联。
_Avoid_：将浏览历史或普通 Continue 称为 Fork；将 Fork 结果理解为仍属于同一 Conversation 的内部讨论方向。

**共同历史**：
多个 Conversation 共同包含的相同历史 Turn；共同历史不表示这些 Conversation 后续新增的 Turn 会自动相互加入。
_Avoid_：将共同历史理解为各自身份不同的重复问答，或后续讨论自动同步。

**地图节点**：
讨论地图中代表 Turn 本身的节点；它所指向的 Turn 可以关联多个 Conversation，因此仅定位节点不足以唯一确定发送目标。
_Avoid_：将地图节点等同于 Conversation，或等同于某个 Conversation 内的 Turn 位置。

**浏览位置**：
用户当前查看的 Turn 位置；单纯浏览不会改变发送目标或 Continue 的接续位置，也不会触发 Fork。
_Avoid_：将正在查看的历史 Turn 视为下一轮问答的自动接续位置。

**发送目标**：
下一条 Prompt 将继续的目标 Conversation；普通 Continue 在其当前末尾追加新 Turn。
_Avoid_：仅凭当前查看的 Turn 或地图节点推定发送目标。

**输入草稿**：
尚未提交的 Prompt 输入，与已提交 Turn 及讨论历史区分；可以归属于一条已有 Conversation，或作为 Project 的新讨论输入草稿。
_Avoid_：将草稿已保存理解为 Prompt 已发送、已有 Turn 或已形成新的 Conversation。

**新讨论输入草稿**：
归属于 Project、用于准备一条新 Conversation 的输入草稿；可准备独立起点的 New Chat，或带有所选来源 Conversation／Turn 的 Fork。
_Avoid_：用 New Chat 统称 Fork 准备；将保存该草稿等同于已创建新 Conversation，或视为讨论历史与模型上下文。
