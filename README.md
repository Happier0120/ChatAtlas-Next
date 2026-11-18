# ChatAtlas-Next

ChatAtlas-Next 是从零重新规划的 AI 对话应用，面向经常使用 AI 处理复杂或开放性问题的个人用户，支持更自主地展开、组织和利用与 AI 的讨论。

目标产品具有用户账户、Project 工作空间和用户自带模型 API Key（BYOK）能力。完整定位与开放事项见 [Product Vision](docs/product/product-vision.md)。

## 当前阶段

当前处于 **Feature Discovery + UX/UI Design：MVP 基础行为首轮发现与文档审核**。已逐项确认账户、BYOK、Project／Conversation 管理、生成与异常、输入草稿、Fork 及 Resume 的关键行为；本轮按授权整理发现记录、GLOSSARY 和必要 ADR。整理稿为 Draft，剩余功能行为、UX/UI 与技术可行性仍需细化和验证，不执行 Git Commit。

- 用户已审核并批准这五个基线文件，同时授权执行首次 Commit；批准依据见研究基线 S9。
- Product Vision v0.2 和 Idea Inventory v0.1 的仓库整理版均为 `Approved`。
- 构想库已获认可作为 Discovery 输入；MVP 范围现由方案 A 及补充边界确定，详细规则与功能有效性仍待发现和验证。
- A～E 高层级旅程结构已获正式批准，文档状态为 `Approved — High-level Journey Map`，作为后续 Feature Map 与 MVP Planning 的规划依据；此次批准不代表用户行为或功能价值已验证。
- 基础对话与可选增强解耦原则已获明确批准并写入 Product Vision 第 4 节；此前已放弃的逐题访谈不作为正式需求依据。
- Feature Map v0.1 状态为 `Approved — Product Capability Map`：原审核批准三 Epic + Foundation 的结构、能力领域与 A～E 映射；SC-01 保留为跨功能场景，GAP-01／02 在该次审核中仅为待探索缺口。原批准不代表功能价值、详细规则、MVP 或开发实施获批；后续 MVP 决定见下一项。Foundation 不表示低优先级或无需进入 MVP。
- 用户已正式选择方案 A：基础聊天、Project、BYOK、账户与数据隔离、Fork、地图与持久化接续形成首版闭环；GAP-01／02 中必要调用条件、失败和中断状态可辨认的基本要求纳入 MVP。首版按一家供应商、一个真实模型规划，对象待确认；历史检索、Prompt／Skill、多模型切换及高级管理能力延后。批准依据、六项补充边界及 Feature ID 见 [MVP Scope](docs/product/mvp-scope.md)。产品范围已批准，MVP Scope 整理稿状态为 `Draft`，详细业务规则、UX/UI、技术方案与价值验证保持待定。
- 本轮 Feature Discovery 的 FD-01～FD-34 已由用户逐项确认，含提供测试连接、普通输入手动保存与 Ctrl＋S 的明确纠正；完整行为、来源、开放事项及覆盖检查见 [MVP Feature Discovery](docs/product/mvp-feature-discovery.md)。用户已授权落档，全文整理稿保持 `Draft`，不等于完整验收基线或已验证实现；不回写历史产品批准范围。
- 首个文档基线已有阶段性提交，实际提交记录以 Git 历史为准。没有业务代码或已确定的工程架构。

## 文档入口

| 文档 | 用途与当前状态 |
| --- | --- |
| [Agent 约定](AGENTS.md) | 项目工作方式、导航、状态与审批规则、外部平台边界 |
| [Product Vision v0.2](docs/product/product-vision.md) | 产品定位、用户、问题域、价值与目标能力；Approved |
| [Product Idea Inventory v0.1](docs/product/idea-inventory.md) | 已明确要求、用户构想与待探索事项；Approved，不代表 MVP 或验证完成 |
| [User Journeys](docs/product/user-journeys.md) | Approved — High-level Journey Map；A～E 高层级结构获批，保留 As-Is 证据限制、To-Be 与方案假设的区别 |
| [Feature Map v0.1](docs/product/feature-map.md) | Approved — Product Capability Map；三 Epic + Foundation 的产品能力分类与规划基线，保留来源、条目性质、依赖及开放事项，不代表 MVP 或实施批准 |
| [MVP Scope v0.1](docs/product/mvp-scope.md) | 方案 A 及补充产品范围已批准；文档整理稿 Draft、待审核；包含首版深度、排除项、依赖风险、验收场景与后续问题，不批准详细规则或实施 |
| [MVP Feature Discovery v0.1](docs/product/mvp-feature-discovery.md) | Draft；覆盖检查、FD-01～FD-34 已确认行为、纠正、来源与开放事项；不是完整 Spec 或已执行验收 |
| [领域术语表](GLOSSARY.md) | Draft；已确认的 Project、Conversation、Turn、Fork、输入草稿等术语，定义与实现分离 |
| [ADR-0001](docs/adr/0001-conversations-share-turns-after-fork.md) | Draft 整理稿、领域决定已确认；Fork 创建独立 Conversation、历史 Turn 可共同归属、后续独立继续 |
| [ADR-0002](docs/adr/0002-map-nodes-represent-turns.md) | Draft 整理稿、领域决定已确认；地图节点代表 Turn，浏览位置与发送目标分开理解，具体 UX 待定 |
| [ADR-0003](docs/adr/0003-preserve-incomplete-turns-and-append-new-attempts.md) | Draft 整理稿、决定已确认；未完成 Turn 保留历史，再次提交追加新 Turn、不覆盖原记录 |
| [ADR-0004](docs/adr/0004-create-conversations-on-first-saved-prompt.md) | Draft 整理稿、决定已确认；首次 Prompt 确认保存时建立新 Conversation，准备输入独立作为草稿 |
| [Product Discovery Baseline](docs/research/product-discovery-baseline.md) | 原话摘录、访谈摘要、决策与推断、来源限制及审核记录；Approved，研究证据限制保留 |

## 仓库知识与审核规则

本仓库是正式产品与工程文档的唯一权威来源。所有阶段的持久化成果保存在项目内；聊天辅助当前工作，重要信息须落到文件。Notion 等外部知识管理平台不属于默认工作流，历史链接不构成依赖。

文档 `Draft` / `Approved` 表示全文审核状态；条目是否已明确、是否经过验证须单独说明。已批准写入或已提交 Git，都不会自动将文档提升为 `Approved`。

工作节奏为：讨论 → 整理仓库草案 → 用户审核 → 修订与检查 → 按授权形成阶段性 Git Commit → 核对进入下一阶段的条件。草案可以持续保存，不要求每轮访谈提交。新的用户请求可以调整工作范围，需同步记录其影响。

## 后续文档与 Skills 路径约定

下表说明文档职责与后续路径。研究基线和旅程草案已有入口；其余后续文件和目录按阶段授权产生：

| 阶段或材料 | 预期位置与边界 |
| --- | --- |
| 产品全景、MVP | `docs/product/feature-map.md` 为能力规划基线；`docs/product/mvp-scope.md` 记录已批准方案 A 的 MVP 范围与边界，整理稿待审核 |
| 研究与决策依据 | `docs/research/`，保留来源、原话/摘要/推断的区别及证据限制 |
| 领域模型 | `docs/domain/`，按实际需要保存模型说明与图 |
| 术语与架构决策 | Matt Pocock Skills 默认读取根目录 `GLOSSARY.md` 与 `docs/adr/`；按实际领域工作产生，不预建或维护第二份术语权威来源 |
| UX/UI | `docs/design/`，保存设计说明、必要原型源文件和验证反馈 |
| Feature Spec | 本地 Markdown tracker 约定：`.scratch/<feature-slug>/spec.md` |
| Tickets | `.scratch/<feature-slug>/issues/<NN>-<slug>.md`，每个 Ticket 一个文件 |
| Skills 工程配置 | 进入相应工程阶段时再配置 `docs/agents/issue-tracker.md` 等所需文件；本轮未执行完整初始化 |

正式 Spec、Tickets 及其审核记录属于仓库成果，不因位于 `.scratch/` 而整体忽略。将来使用相关 Skills 时应明确本地 tracker，外部发布需单独获得用户授权。

采用“产品构想驱动、用户场景验证、功能渐进细化”的发现方式。后续旅程需同时检查遗漏的能力与遗漏的构想场景；产品全景和 MVP 切片后，再细化优先 Feature。Feature Discovery 与 UX/UI 可交叉迭代。

## 下一步

1. 审核 MVP Feature Discovery、GLOSSARY 与 ADR-0001～0004 的整理表述；已确认决定、文档全文审核及验证状态分别记录。
2. 按用户授权交替推进剩余功能行为与 UX/UI，基于已确认要求形成信息架构及局部交互，并通过原型验证；浏览位置、发送目标与新讨论准备来源须清楚区分。
3. 依发现记录第 5 节处理开放事项，包括验证／重设流程、草稿替换、保存未知状态与准备态恢复；供应商、上下文、持久化等技术问题另行调查，不自动进入 Spec、Tickets 或实施。

本轮仅落地并检查需求发现记录、领域术语、必要 ADR 与导航，不执行 Git Commit 或 Push，不设计数据库、API、上下文窗口算法或失败恢复状态机，不编写业务代码或制作原型。产品文档中历史阶段边界保留；当前阶段按最新用户授权理解，未修改其他已批准产品文档。
