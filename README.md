# ChatAtlas-Next

ChatAtlas-Next 是从零重新规划的 AI 对话应用，面向经常使用 AI 处理复杂或开放性问题的个人用户，支持更自主地展开、组织和利用与 AI 的讨论。

目标产品具有用户账户、Project 工作空间和用户自带模型 API Key（BYOK）能力。完整定位与开放事项见 [Product Vision](docs/product/product-vision.md)。

## 当前阶段

当前已完成 **User Journey Mapping 高层级结构审核**；下一阶段为 Feature Map，当前仅提出工作方案，等待用户确认后开展。

- 用户已审核并批准这五个基线文件，同时授权执行首次 Commit；批准依据见研究基线 S9。
- Product Vision v0.2 和 Idea Inventory v0.1 的仓库整理版均为 `Approved`。
- 构想库已获认可作为 Discovery 输入；详细规则、MVP 范围与功能有效性尚未确定。
- A～E 高层级旅程结构已获正式批准，文档状态为 `Approved — High-level Journey Map`，作为后续 Feature Map 与 MVP Planning 的规划依据；此次批准不代表用户行为或功能价值已验证。
- 基础对话与可选增强解耦原则已获明确批准并写入 Product Vision 第 4 节；此前已放弃的逐题访谈不作为正式需求依据。
- 首个文档基线已有阶段性提交，实际提交记录以 Git 历史为准。没有业务代码或已确定的工程架构。

## 文档入口

| 文档 | 用途与当前状态 |
| --- | --- |
| [Agent 约定](AGENTS.md) | 项目工作方式、导航、状态与审批规则、外部平台边界 |
| [Product Vision v0.2](docs/product/product-vision.md) | 产品定位、用户、问题域、价值与目标能力；Approved |
| [Product Idea Inventory v0.1](docs/product/idea-inventory.md) | 已明确要求、用户构想与待探索事项；Approved，不代表 MVP 或验证完成 |
| [User Journeys](docs/product/user-journeys.md) | Approved — High-level Journey Map；A～E 高层级结构获批，保留 As-Is 证据限制、To-Be 与方案假设的区别 |
| [Product Discovery Baseline](docs/research/product-discovery-baseline.md) | 原话摘录、访谈摘要、决策与推断、来源限制及审核记录；Approved，研究证据限制保留 |

## 仓库知识与审核规则

本仓库是正式产品与工程文档的唯一权威来源。所有阶段的持久化成果保存在项目内；聊天辅助当前工作，重要信息须落到文件。Notion 等外部知识管理平台不属于默认工作流，历史链接不构成依赖。

文档 `Draft` / `Approved` 表示全文审核状态；条目是否已明确、是否经过验证须单独说明。已批准写入或已提交 Git，都不会自动将文档提升为 `Approved`。

工作节奏为：讨论 → 整理仓库草案 → 用户审核 → 修订与检查 → 按授权形成阶段性 Git Commit → 核对进入下一阶段的条件。草案可以持续保存，不要求每轮访谈提交。新的用户请求可以调整工作范围，需同步记录其影响。

## 后续文档与 Skills 路径约定

下表说明文档职责与后续路径。研究基线和旅程草案已有入口；其余后续文件和目录按阶段授权产生：

| 阶段或材料 | 预期位置与边界 |
| --- | --- |
| 产品全景、MVP | 后续在 `docs/product/` 创建 `feature-map.md`、`mvp-scope.md`；旅程草案已有入口，不代表这些阶段已启动 |
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

1. 按用户授权提交 README、Product Vision、User Journeys 三份文档，形成高层级旅程基线；不自动 Push。
2. 提出以 Product Vision、Idea Inventory、User Journey Map 为输入的 Feature Map 工作方案，按“用户价值 → Epic／产品能力领域 → Feature”组织；等待确认后再开展。
3. 保留全部产品构想及其状态，区分基础对话与可选增强，检查关联、依赖和遗漏，不提前确定 MVP 范围。

当前仅收尾已批准旅程并提出 Feature Map 方案，不生成实际功能地图，不进入 MVP Planning、详细 Feature Discovery、UX/UI、Spec、Tickets 或业务代码开发，也不提前创建 GLOSSARY 或 ADR。产品文档中历史阶段边界保留；当前阶段以本入口及最新用户授权为准。
