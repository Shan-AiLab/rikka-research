When an enterprise starts working with AI, the request often seems straightforward: build an AI agent that automatically identifies material shortages, finds suppliers, recommends purchases, and perhaps even creates procurement tasks directly.

Viewed from the agent layer, this seems sufficiently clear. The model needs to read project requirements, inventory, supplier information, and historical procurement records, make judgments according to certain rules, and then call systems to carry out actions.

But once implementation begins, the questions quickly lead further upstream.

What counts as a material shortage? Is it project demand minus current inventory, or must inventory already reserved for other projects also be considered? When substitute materials exist, under what conditions are they allowed? If an urgent project requirement and safety-stock replenishment arise together, how should they be prioritized? Who confirmed the procurement requirement, and who can change it? When a supplier changes its delivery date, who is responsible for reassessing project risk?

Further investigation may reveal that the system does not even have a stable procurement requirement object. Project demand, inventory shortfalls, safety stock, and manually added purchases are mixed in one table. Different people modify the data through different processes. Many rules that actually determine procurement actions exist only in employees’ heads.

Eventually, what first looked like a request to build a procurement agent is no longer just an agent problem.

It exposes a deeper chain of dependencies:

**Business → Organization → Systems → Agents.**

These four layers are not capabilities that can be freely assembled. Problems unresolved in one layer do not disappear when we move to the next. They continue in another form.

## 01 | Many problems exposed by agents originate outside the agent layer

For a one-off procurement analysis, an agent can read a few Excel spreadsheets and explanations, then produce a plausible result. Models are good at this kind of task: the source information has been prepared, the scope is limited, and a person will ultimately check the result.

But once an agent is expected to participate in everyday business, it faces a continuously changing environment rather than a static collection of information.

Inventory falls today, a customer changes a configuration tomorrow, and a supplier revises its delivery date the next day. A procurement action in turn changes inventory, project states, and the funds committed. The agent needs more than analytical ability: it needs to keep knowing what the current reality is.

At this point, ambiguities previously resolved through human experience become immediately apparent.

An enterprise may have long worked by the rule “buy what is missing.” Only when it prepares to automate that judgment does it discover that “missing” has no stable definition. Employees could work because they made judgments as needed by combining project progress, inventory reservations, substitute materials, delivery dates, and experience.

When these judgments are delegated to an agent, the business is forced to make the question explicit for the first time:

**How does this business actually operate?**

Enterprise AI projects that encounter data, process, permission, or organizational issues have therefore not necessarily lost their way. The agent is beginning to encounter ambiguities that people previously absorbed.

> **Many problems exposed by agents stem from how the business, responsibilities, and systems are defined in the preceding layers, rather than in the agent layer itself.** They cannot simply be summarized as poor enterprise data quality.

Even large amounts of high-quality structured data do not mean these problems have been solved.

Imagine a city with comprehensive records of residents, buildings, roads, and vehicles. The records may be detailed and their fields standardized, but whether the city can govern at a fine level of detail still depends on whether different records can refer to the same real-world object, relationships between objects are explicit, changes in state can be maintained over time, and incidents can be acted on according to rules and responsibilities.

The same applies to enterprise databases. Structured data can store records without necessarily including the object relationships, state constraints, rules governing responsibilities, and mechanisms for action that business operations require.

**Structured data does not necessarily constitute a structured world.**

Sometimes, then, the problem with putting AI to work in an enterprise is neither insufficient data nor even poor data quality. The data has yet to form a business environment that supports ongoing judgment and action.

## 02 | The four layers form a dependency chain, not four modules

Business comes first.

The business layer does not answer which features a system has. It answers what exists in the business world and how those things relate.

Returning to procurement, before discussing an agent we need at least to understand project demand, inventory, net requirements, and the conditions that create a procurement task. We need to know the relationship between standard and substitute materials, the states a requirement passes through, and the criteria for considering procurement complete.

These definitions form the basic structure of the business itself.

Organization then answers another question: **who is responsible for what within that structure?**

Who confirms engineering requirements? Who is responsible for procurement shortfalls? Who can approve substitute materials? Who handles exceptions to supplier delivery commitments? Does the project manager merely need to be informed, or do they have decision-making authority? Organization is more than a department hierarchy. It defines responsibilities connecting actors with business objects, tasks, and decisions.

Once the business is reasonably clear, systems have something they can consistently represent and maintain. Once responsibilities are explicit, we can discuss an agent’s boundaries. Workflows, permissions, and pages express the underlying business structure digitally. System configuration should not become a way to guess how the business ought to operate.

Agents come later in this chain. They enter an existing business environment to perceive changes, read states, form judgments, and take action.

Therefore:

> **Business defines the world. Organization defines responsibilities. Systems represent and maintain the world. Agents act within it.**

These layers form a dependency relationship, rather than merely a hierarchy.

## 03 | Gaps between layers are sources of entropy in enterprise operations

For many enterprises, the real problem is not that any layer is entirely absent. It is that adjacent layers are misaligned.

**When a gap exists between business and organization**, responsibilities may sound clear but become ambiguous in specific situations.

“Procurement is responsible for ensuring all required materials are available” appears to assign responsibility. But available for what: a project, a production task, or a delivery milestone? When engineering requirements change, who is responsible for invalidating the original procurement task? Is a shortage procurement’s responsibility or the responsibility of whoever confirmed the requirement? If substitute materials exist, who has the final say?

Without definitions for these questions, responsibility for material availability can only be interpreted through experience.

**When a gap exists between organization and systems**, ambiguity passes into the system. Unclear responsibilities lead to excessive approvals as a fallback. Uncertainty about who can modify data leads to permissions that are either too broad or entirely locked down. Numerous exceptions in real work lead to ever more workflow branches. People eventually conclude that the system is rigid, approvals are excessive, and workflows are difficult to use. Yet the system has merely built unresolved organizational problems into its design.

Further along, **a gap between systems and agents** leaves the agent to deal with complexity unresolved in the preceding layer.

Without stable object identities, it must infer from text whether records refer to the same thing. Without reliably maintained states, it must guess the latest situation from chats and documents. Without rules implemented in systems, it must reread policies each time. When sources conflict, the model is left to decide which to trust.

These approaches can work to some extent, but they turn structural problems in the environment into reasoning costs and uncertainty.

> **Problems unresolved in one layer do not disappear. They pass to the next in more expensive and less reliable forms.**

This is what I mean by gaps between layers being sources of entropy.

Many apparent difficulties in enterprise AI implementation arise because organizations previously relied on people to absorb this entropy and are now trying to make machines take it on.

## 04 | Moving from content to action changes the requirements for the environment

This does not mean enterprises should avoid AI until their business, organization, and systems have all been redesigned.

On the contrary, many AI applications are already valuable. Organizing procurement records, summarizing meetings, generating PowerPoint presentations, and helping analyze exceptions can create value quickly.

These use cases share one feature: **AI mainly produces content.**

Content can tolerate some ambiguity. A meeting summary can be worded in different ways without causing a serious problem, and different wording in an analysis report is normal. Even if a model misses some information, people usually still read, interpret, and judge the output before deciding whether to act.

At the content level, context and human oversight can therefore compensate for many problems.

But as AI moves beyond generating content, the requirements change.

The first step is **decision-making**.

The model no longer merely says, “I think there may be a material shortage.” It must identify which materials need purchasing, which option takes priority, and whether risk has reached a threshold. Its output begins to affect subsequent system behavior directly. Objects, metrics, rules, and constraints therefore need to be clearer than for content generation.

The next step is **action**.

If an agent creates procurement tasks, modifies orders, reserves inventory, or notifies suppliers directly, rather than merely offering advice, it is changing the business world instead of just generating information.

An answer that is approximately right is no longer enough.

Is it acting on the correct object? Does the recorded state reflect reality? Is this actor authorized to take this action? Which rules permit it? Which other objects and tasks will it affect? If execution goes wrong, can it be traced, reversed, and recovered from?

Improving model reasoning alone cannot answer these questions.

Moving from content to decisions and then to action therefore follows a path of increasing requirements for the environment:

**Content can tolerate ambiguity. Decisions need explicit boundaries. Action requires a stable environment.**

This helps explain why AI can appear so impressive yet seem unreliable when put to work, and why enterprise implementations so often remain chat interfaces. The difference lies in the level of work AI is expected to perform, rather than simply in how intelligent it is.

If people still supply the missing context, check the results, and decide whether to execute, AI remains primarily an assistance tool. Once an agent continuously participates in business operations and gains more authority to judge and act, it becomes an actor within the business system.

It will then inevitably encounter the business, organization, and system layers again.

The real question is therefore not:

**Can we build the agent first?**

It is:

> **Is this AI producing content, participating in decisions, or preparing to change the business world directly?**

The closer it moves to action, the harder it becomes to bypass business definitions, responsibilities, and the systems that maintain those structures.

## 05 | Start with a limited scope, but still start with the business

“Business → Organization → Systems → Agents” is not a waterfall model requiring years of digitalization before AI can begin. Enterprises do not need to redefine every business activity, restructure the entire organization, and rebuild every system before finally starting AI. That would rarely be feasible in practice.

A more reasonable approach is to start with a sufficiently small business problem that has clear value.

For example, focus only on procuring critical materials for a particular category of projects.

Once the scope is limited, the problem becomes manageable. First clarify where requirements originate, how inventory is calculated, how substitutions are assessed, and what triggers procurement. Then establish who confirms requirements, executes procurement, and approves substitutions. Next, check whether existing systems can reliably represent and maintain these objects and states.

Only then decide what the agent should do: continuously check shortfalls, identify exceptions, generate recommendations, or create procurement tasks directly when certain conditions are met.

This may cover only a small part of the enterprise, but within that scope it still follows the full chain:

**Business → Organization → Systems → Agents.**

> **You can start with a limited scope, but you cannot skip layers.**

Starting with the business therefore does not mean a comprehensive redesign. What matters is establishing a sufficiently clear small world within the scope being prepared for automation.

**Enterprise-wide completeness is not a prerequisite. A functioning end-to-end loop within the chosen scope is.**

Rather than adding an increasingly capable agent to a large, disorderly environment, find a problem domain with sufficient value, clarify that part of the business, and let the agent work there.

## 06 | AI changes the actors, but does not remove the business world

In traditional enterprises, people and systems jointly perform most work. Agents introduce a new kind of actor into that environment.

People previously read reports, judged exceptions, and initiated tasks. Agents may perform some of that work in the future. Systems traditionally focused on storage, workflows, and rule execution. Agents can take on more interpretation, judgment, and action on top of those stable structures.

What changes is the capability and composition of the actors. The business world still needs structure.

Customers remain customers, orders still have states, procurement tasks still need clear responsibilities, and rules still determine what is permitted. Indeed, as machines begin to participate in business operations, many structures previously hidden in people’s heads, meetings, and experience need to become more explicit for the first time.

In this sense, an AI-native enterprise need not have less structure.

It may instead have **more explicit structure, with more flexible interaction and execution**. Business objects, relationships, states, rules, and responsibilities form a shared environment in which people, traditional systems, and agents participate according to their capabilities and permissions.

“Business → Organization → Systems → Agents” is therefore not a traditional digitalization method dressed in AI language.

It expresses a simpler fact about dependencies:

> **Business defines the world. Organization defines who is responsible for it. Systems keep that world operating reliably. Agents can then understand and act within it reliably.**

AI implementation can begin in any limited scope. But every part of the business that is genuinely ready to operate this way must first answer the same question:

> **How does the business here actually operate?**
