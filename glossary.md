# Rikka Research 中英术语表

本文件用于统一公开站、研究文章、理论页面和 `rikka-research` 仓库中的中英文术语。中文内容是语义真相源；英文应优先保证概念清晰和上下文自然，不做机械逐字翻译。

## 核心术语

| 中文 | 首选英文 | 使用规则 |
| --- | --- | --- |
| 认知地图 | Cognito Atlas | 理论专名，固定使用 `Cognito Atlas`；不译为 `Cognitive Map`。 |
| 决策空间 | Decision Space | 理论专名，固定使用 `Decision Space`。 |
| 业务地图 | Business Atlas | 理论概念固定使用 `Business Atlas`；需要强调它表示完整业务世界时可写作 `Business World Atlas`。只有明确指现实中的交通地图、城市地图或导航地图时才使用 `map`。 |
| 业务建模 | Business Modeling | 指主动设计现实业务如何进入数字世界，并持续维护业务对象、关系、状态、规则等表征结构的建模活动。作为本文定义的概念时使用首字母大写。 |
| 表征 | Representation | 指现实经过选择和转换后进入认知、交流、计算与行动的表达；不要在同一语境中与 `presentation` 混用。 |
| 业务对象 | Business Object | 指企业业务中可被稳定识别和引用的对象。 |
| 数字世界 | Digital World | 指业务在数字环境中的结构化表达。 |
| 主体 | Actor / Agent | 一般复杂系统、人与组织等行动主体使用 `actor`；明确指 AI 时使用 `agent`。不要机械翻译为 `subject`。 |
| 治理 | Governance | 指对复杂系统的规则、责任、约束与行动进行组织和控制的能力。 |
| 状态 | State | 指对象在特定时间点的可判断情形。 |
| 规则 | Rule | 指稳定约束、判断条件或行动要求。 |
| 事件 | Event | 指引起状态变化或需要被记录的业务发生。 |
| 环境模型 | Environment Model | 指主体所处环境的结构化表示。 |
| 业务语义 | Business Semantics | 指业务对象、关系、状态、规则和事件所共同形成的意义系统。 |
| 可计算 | Computable | 表示信息或结构能够进入明确的计算与推演过程。 |
| 可治理 | Governable | 表示系统能够被观察、约束、协调和持续修正。 |

## Atlas 概念层级

### Cognito Atlas

一般性的复杂世界表示框架，用于讨论一个复杂世界如何被稳定地表示、理解和持续更新。它不限定具体领域，也不等同于企业场景中的某一种局部地图。

### Enterprise Atlas

`Cognito Atlas` 在企业复杂系统中的应用，用于表示企业中相互依赖的四个层面：

- `Business`：业务世界及其稳定结构。
- `Organization`：责任、分工、协作与决策权。
- `Systems`：承载业务世界的数字化系统与接口。
- `Agents`：使用环境、获取信息并执行行动的智能主体。

### Business Atlas

`Enterprise Atlas` 中对**业务世界**的表示。它描述业务中的对象、关系、任务、事件、状态与规则等稳定结构，是企业 Atlas 的组成部分，而不是 `Enterprise Atlas` 的同义词。

层级关系：`Cognito Atlas` → `Enterprise Atlas` → `Business Atlas`。

## “主体”的翻译规则

“主体”是本理论体系中的核心概念，必须根据语境选择英文：

- 讨论一般复杂系统、决策结构、人、组织或多种行动者时，使用 `actor`。
- 明确讨论 AI、Agent 系统或硅基智能时，使用 `agent`。
- 同时包含人和 AI 时，优先写作 `actors, including humans and AI agents`，之后可根据上下文简化为 `actors`。
- 不要将“主体”机械翻译为 `subject`。只有引用已经固定使用 `subject` 的学术概念或原文时才例外，并应保留上下文说明。

## 大小写与行文

- `Cognito Atlas`、`Decision Space` 是专名，始终使用首字母大写。
- `Business Atlas`、`Environment Model` 等作为概念名称或标题时使用首字母大写；现实地图或纯类比中的普通名词 `map` 按英文句法使用小写。
- 中文中的 `Agent` 在英文正文里通常写作 `agent`；只有产品名、标题或专名需要大写。
- 英文翻译以读者能够准确理解概念为优先，可调整句序、拆分长句和补充必要主语，但不能改变论证强度、概念边界或因果关系。

## 维护规则

- 新增核心概念或发现同一术语出现多种英文译法时，先更新本文件，再更新公开内容。
- 翻译公开文章与理论页面前必须检查本文件。
- 中文发生实质变化时，英文镜像必须在同一个 PR 或 commit 中更新。
- 如果某个术语确实需要多个译法，必须在本文件中写清使用条件，不能只列同义词。
