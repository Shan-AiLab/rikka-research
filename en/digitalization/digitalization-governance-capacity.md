The most common way to describe digitalization is “reducing costs and improving efficiency.” That is certainly valid, but it gives us too narrow a view of what digitalization does.

Many digitalization efforts do not even reduce costs in the short term. Recording more of the work process, filling gaps in traceability, unifying object definitions, clarifying responsibilities, and capturing more states can initially give an organization more work to do. These investments still have value because digitalization changes more than efficiency. It changes **the range and complexity of reality an organization can perceive, understand, and govern**.

From this perspective, the more fundamental meaning of digitalization is **improving governance capacity**.

## 01 | Governance begins with visibility

What an organization can govern depends first on what it can see.

An ancient state needed to know its population, land, and output before it could levy taxes. A city needs to know its roads, vehicles, locations, traffic flows, and incidents to manage traffic. An enterprise managing delivery likewise needs to know how many orders it has, where each stands, which tasks are overdue, which materials affect production, and who is responsible for what.

If these aspects of reality cannot be made consistently visible, management must rely largely on experience, manual reporting, and ad hoc coordination.

The need for managers to ask “What is happening now?” in meetings every day is itself a sign of limited organizational visibility. Information may exist in employees’ heads, group chats, Excel spreadsheets, or disconnected systems. But without stable, ongoing, shared representations, the organization struggles to use it as a basis for further judgment.

Governance therefore does not always begin with a clever decision-maker who then requests data. Often, governance first becomes possible because reality has finally become visible.

> **How finely an organization can govern depends first on how much detail it can observe.**

## 02 | Digitalization first expands what the organization can perceive

Without digitalization, many inherent limits constrain how much reality an organization can perceive. Managers see only what they encounter personally and depend on reports passed up through layers of subordinates. Information is repeatedly compressed and distorted along the way. Many states are known only to people on site, many rules live only in an experienced employee’s head, and many exceptions are discovered only after something goes wrong.

Paper records, Excel, enterprise resource planning (ERP), manufacturing execution systems (MES), and customer relationship management (CRM) all help overcome these limits. They gradually bring aspects of reality that once depended on human memory, spoken communication, and on-site observation into a digital environment that can be shared, continually accessed, and checked repeatedly.

This is the relationship between representation and digitalization. Representation addresses **how reality is represented**. Digitalization further enables those representations to become an ongoing part of organizational operations at scale.

An order is no longer merely an agreement between a salesperson and a customer: it becomes an object in a system, with a state, an owner, milestones, and related tasks. Equipment no longer exists only on the factory floor: it has a digital identity, an operating state, and maintenance history. A procurement requirement is no longer merely something someone says: it can be linked to inventory, projects, suppliers, procurement tasks, and delivery outcomes.

As more of reality enters the Digital World, the organization gains more than additional data. It gains an expanding **space of observable business reality**.

The first improvement digitalization brings is therefore not faster operations, but a greater ability to perceive the organization’s own operational state.

## 03 | An agent’s action-and-feedback cycle depends on a governable business world

Many agent architectures describe a similar cycle: perceive the environment, obtain information, form judgments, take action, and use the results to update subsequent behavior. From the agent’s perspective, this is usually described as a set of capabilities: **perception, measurement, judgment, decision-making, action, and feedback**.

Shift the perspective from the agent to its business environment, however, and a more fundamental set of prerequisites becomes visible.

Perception first requires reality to be **visible**. Key objects, states, and changes must enter the digital environment accessible to the agent. If actual order states are never recorded, equipment states are updated manually only once every three days, and responsibilities exist only in temporary group chats, even a model with strong perceptual capabilities can perceive only an incomplete representation of the world.

Measurement requires business reality to be **quantifiable**. An organization needs to know more than that a project is behind schedule. It needs to know by how much, against which target, and for how long. If goals, times, quantities, and states are not clearly defined, reasoning alone cannot supply reliable measurements.

Judgment further requires an environment in which **causes can be traced**. If the system shows only that a project is delayed, without showing task dependencies, resource use, requirement changes, material shortages, and the chain of responsibilities, an agent may generate a plausible explanation but still struggle to distinguish actual causes from plausible guesses expressed in text.

Decision-making and collaboration then require a business world that **supports coordination**: clear responsibilities, tasks that can be broken down, resources that can be allocated, and explicit boundaries for action. Taking action also requires **the ability to intervene**: clear points at which particular actions can be taken, an understanding of which object and state they will change, and a way to feed the results back into the system.

These two perspectives describe two sides of the same cycle:

| Actor / agent capability | Conditions the business world must provide |
| --- | --- |
| Perception | **Visibility:** objects, states, and changes can be observed |
| Measurement | **Quantifiability:** scale, time, goals, and deviations can be measured |
| Judgment | **Traceable causes:** relationships, dependencies, constraints, and causes can be traced |
| Decision-making / collaboration | **Coordination:** responsibilities, tasks, resources, and actions can be organized |
| Action | **Intervention:** explicit interfaces for action exist, with feedback on results |

> **The agent loop describes how an actor operates. Governance through digitalization concerns whether the world has been developed enough to support that loop.**

This is why model capability alone cannot determine the upper limit of an agent’s capabilities inside an enterprise. If the business world is not visible or quantifiable, and its causes cannot be traced, even a highly capable model can only work in an environment represented at a low level of detail.

In this sense, digitalization maturity can be understood as **the extent to which real business has moved from merely existing to being governable**.

## 04 | The granularity of digitalization sets the ceiling for governance capacity

Governance capacity depends not only on whether data exists, but also on the granularity at which reality has been modeled.

Suppose an enterprise’s systems show only “project on track” or “project delayed.” Its ability to govern remains largely at the project level. Managers know that a project has a problem, but not where in the work it arose. They must keep holding meetings, asking people, and chasing progress.

Break the project down further, and distinct objects appear: contracts, orders, technical proposals, material requirements, procurement tasks, production tasks, and delivery milestones. Each has its own state, owner, relationships, rules, and metrics. “Project delayed” is no longer just an outcome label. It becomes possible to trace which batch is missing required materials, which procurement task is incomplete, whether the cause is a supplier delay or a requirement change, and which production tasks are affected.

The organization has not suddenly become smarter because a system went live. What has changed is its ability to observe reality: where it could previously see only projects, it can now see tasks, resources, and dependencies. Governance can move from broad requests to hurry up to more precise diagnosis and intervention.

> **The level at which you can govern depends on the level at which reality has been modeled.**

The same applies to city governance.

With statistics available only at the administrative-district level, a city can identify and address problems only at a broad level. When roads, buildings, and land parcels have stable identifiers, spatial relationships are established, and geographic management zones are mapped to clearly defined responsibilities, the city gains the foundations to locate specific incidents, identify their impact, and arrange a response.

Cameras can expand a city’s ability to perceive what is happening, but cameras alone are insufficient. If detected incidents cannot be linked to specific roads, buildings, rules, and responsible actors, observations are difficult to translate into precise governance action.

This is why seemingly basic digitalization work on objects, tasks, and responsibilities matters so much. Without defined objects, states cannot be tracked consistently. Without defined tasks, execution progress cannot be identified accurately. Without defined responsibilities, it is difficult to say who should handle a problem.

Digitalization maturity therefore does not equal the number of systems implemented, let alone the number of features in use. What matters more is whether, within a particular business domain, key objects have been identified, states are trustworthy, tasks are traceable, responsibilities are clear, and relationships and dependencies can be understood.

This governance resolution can be examined further through the digital maturity of different business objects and tasks.

Object maturity concerns whether an object has a stable identity, explicit relationships with other objects, and states and changes that can be tracked over time.

Task maturity concerns whether a piece of work has clear triggers, actors responsible for execution, inputs and outputs, states, and completion criteria, and whether its results can feed back into the relevant business objects.

The two do not necessarily develop together. An enterprise may have comprehensive material records yet still rely on procurement staff to coordinate shortages in group chats. It may also have well-developed approval and task systems that process only vaguely defined request forms.

Digitalization maturity should therefore be assessed beyond an enterprise’s overall stage. It also requires examining specific business domains to understand the maturity of different objects and tasks, and whether they connect to one another.

Together, these capabilities determine the level of detail at which an organization can govern itself.

## 05 | Why “reducing costs and improving efficiency” is too narrow

Traditional digitalization projects often measure how much an investment reduces staffing needs, how many forms no longer need filling out, or how many days it removes from a process. These metrics matter because digitalization must ultimately create business value. But treating those outcomes as its essence can obscure more fundamental and longer-term value.

Taxation offers a clear example. In ancient times, taxation relied on household and land registers, manual land surveys, and reporting through successive administrative levels. The range of objects that could be identified and verified, the frequency of information updates, and statistical accuracy were all constrained by the governance infrastructure of the time.

As identity registries, cadastral records, real estate registries, transaction records, and tax information systems gradually developed, governing authorities could identify taxpayers and verify relevant facts more reliably, and administer taxation at a finer level of detail.

The value of this infrastructure clearly cannot be measured only by how many statistical staff it saves. More fundamentally, it expands the scope of reality that governing authorities can identify, perform calculations on, and address.

The same holds for enterprise digitalization.

Unifying product definitions may not reduce staffing needs at all in the short term, and may require considerable time organizing historical material. Establishing end-to-end quality traceability may add recording work on site. Clarifying previously ambiguous responsibilities may temporarily make processes that relied on tacit understanding and personal relationships seem more cumbersome. Such work may not immediately produce an impressive return on investment (ROI), but it establishes new foundations for governance.

An organization that could not reliably know what happened can now do so. Problems once discovered only in final outcomes can be detected in intermediate states. Where issues previously required finding people to coordinate a response, they can now be traced to specific objects, tasks, and responsibilities. Growth that once required more people to keep things running may now be managed through more stable structures capable of handling greater complexity.

The deeper value of digitalization is therefore more than making existing work faster:

> **It enables an organization to manage complexity it could not manage before.**

As an enterprise grows, change accelerates, business activities extend across more stages, and more roles become involved, this capability often matters more than isolated efficiency gains.

Cost reduction and efficiency improvement are among the possible outcomes of greater governance capacity. Better risk control, more reliable delivery, a greater ability to replicate organizational capabilities, and a stronger capacity to handle complex business are also outcomes.

## 06 | Agents raise the requirements for digitalization

With the arrival of agents, a natural thought is that large language models can read documents, understand natural language, and call tools across systems. Perhaps the complex work of data governance, system development, and business modeling can now be bypassed.

For short-term, limited tasks, some work can indeed be bypassed. Agents can gather information from multiple sources and use natural language to make possible operations that previously required fixed interfaces and workflows.

But if the goal is for agents to participate in real business over time and continually take responsibility for judgment and action, the conclusion is the opposite.

People previously compensated for many ambiguities. When a field was poorly defined, an experienced employee knew what it meant. When a process did not match reality, the person doing the work knew when to adapt. When two systems contained conflicting data, business staff could use experience to judge which was more trustworthy.

As more judgments and actions are delegated to agents, ambiguities once hidden in human experience become uncertainty in machine action.

Without clear object definitions, an agent cannot reliably identify what it is acting on. Without trustworthy states, it cannot know the current reality. Without clear responsibilities, it does not know who should receive a task. With conflicting rules, it must guess between competing statements. If real changes have not entered the system, it may not even realize that the environment has changed.

Agents have therefore not made the foundations of digitalization less important.

On the contrary, they expose much of the organizational entropy that people previously absorbed without drawing attention to it.

This is why I understand enterprise AI implementation as a chain of dependencies:

**Business → Organization → Systems → Agents**

This does not require every enterprise to finish a long, comprehensive digital transformation before it starts using AI. Development can proceed in parallel, with repeated iteration in both directions.

**An agent’s ability to work reliably ultimately depends on a business environment where relevant states are visible, quantities can be measured, causes can be traced, work can be coordinated, and actions can be taken with feedback on their results.**

Digitalization has never been merely a change in the software an enterprise uses. As more objects, relationships, states, rules, and tasks enter continuously maintained digital representations, the organization gains governance capacity at a finer level of detail.

AI then extends the range of actors that can understand, judge, and act on that foundation.

Before discussing which agents an enterprise could build, perhaps we should first ask a more fundamental question:

> **How much of its own business can this organization actually see today?**
