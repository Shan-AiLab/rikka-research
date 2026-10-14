## 1. The name “procurement agent” does not yet explain its work

When planning a procurement agent, it is easy to start discussing which systems to connect, what tools to provide, and whether to split it into agents for quotations, ordering, and delivery follow-up.

These designs first need a basis: which part of the work will it undertake, and why is that work needed?

The previous article, [What do we mean when we say “let AI help people complete tasks”?](https://rikkalab.com/en/digitalization/what-it-means-for-ai-to-complete-tasks/), discussed the goals behind tasks. This article takes the discussion into the enterprise: **if organizational functions, business objects, and operating rules can be explicitly represented, we have an opportunity to reason about where tasks come from and where their boundaries lie.**

Consider a retailer. A store needs certain goods ready by a specified time. Procurement is only one possible way to meet that need. Whether to buy, transfer stock between stores, or adjust sales plans depends on the circumstances. The name “procurement agent” has already selected part of the solution.

## 2. Find the source of work in the functions an organization performs

We can understand why an organization exists through the functions it performs in a value network. A retailer connects product supply with consumer demand. Stores provide local sales and service, while supply operations must make the right goods available when needed.

This is the organization's ecological niche expressed in concrete business terms: what value it provides and to whom, which upstream participants it depends on, and what commitments it makes downstream.

Further decomposition reveals demand forecasting, inventory management, procurement, and distribution. Together, they support product availability, subject to constraints such as capital tied up in stock, losses, and transport costs.

The unit of analysis here is **the function assigned to each part of the work**. Which department or position currently performs it can be arranged separately. A function may involve several people, or be shared by people, traditional systems, and agents.

“Ensuring supply” is an ongoing business function. “Replenishing a particular product for a particular store today” is a specific task. Connecting the two also requires the current business situation.

## 3. The gap between goals and current states makes tasks concrete

Suppose a store needs 100 units for a Friday promotion. It has 20 available, and another 50 are confirmed to arrive before the promotion. All of these can be used for it. The uncovered requirement is therefore 30 units.

This identifies a supply gap, but does not establish that 30 units must be purchased. Do nearby stores have stock available for transfer? Can a supplier deliver on time? Is the additional expense worthwhile? These conditions determine which approach to take.

Once a gap is identified, tasks can first be created to verify information, compare options, or request a decision. After an approach is agreed, it can be expanded into execution tasks such as initiating a transfer or making an additional purchase. The scope, deadline, and expected result of each task should be traceable to this business need.

Tasks may also change as circumstances change. If the 50 confirmed units are suddenly delayed, the gap must be recalculated. If the promotion is canceled, related tasks should be reviewed so that work whose basis has disappeared does not continue.

**Tasks result from business requirements, current states, and the chosen approach acting together.** They need to remain linked to the requirements, conditions, and decisions that gave rise to them so they can be updated as the business changes.

This gap differs from the gap in product requirements. A shortage generates business tasks such as replenishment; a system's inability to detect the shortage may generate product tasks to build inventory relationships and shortage calculation capabilities. Both require clear goals and current conditions, but they change different things.

## 4. Identifying the objects clarifies how far a task must go

“Follow up on this shipment” can easily be understood as sending a message. Once the message is sent, it may still be unclear whether the task is complete.

If the task is to confirm a delivery date, its expected result should be a traceable confirmation and an updated order record. If it is to resolve a supply gap, obtaining a date that misses the promotion does not complete the work. Other options still need to be considered.

The same situation can produce tasks with different boundaries:

| Task | Objects involved | Expected result |
| ---- | ---- | ---- |
| Confirm the delivery date | Purchase order and delivery commitment | Obtain a reliable arrival date and update the relevant records |
| Assess the impact of a delay | Arrival plans and store requirements | Identify affected requirements and the remaining gap |
| Execute a stock transfer | Transfer order and related inventory | Complete dispatch, transport, and receipt under the agreed plan |
| Decide whether to revise the promotion | Promotion plan | Reach an explicit decision within business constraints |

Some tasks change the state of the real business, some establish facts, and others produce judgments. Each needs to specify which objects it concerns, what result is expected, and what evidence establishes completion.

Boundaries also determine handoffs. Someone confirming a delivery date may discover a delay, complete the fact-finding task, and hand the supply exception to the person responsible for resolving it. Finishing the inquiry must not make the underlying supply problem disappear from view.

## 5. Responsibilities and authority determine who can undertake a task

Only after a task is clear can we determine what capabilities its assignee needs and what actions are permitted.

A buyer may be responsible for following up on orders without being authorized to increase the budget. A store manager may request a transfer without being allowed to use stock reserved by another store. Management responsibility and execution permissions need separate definitions.

The same applies when introducing agents. If an agent's authorization specifies only which tools or APIs a role may call, it is difficult to express which specific objects it may act on, under which states and conditions, and when a decision must be escalated. Role permissions need connections to tasks, objects, and business rules to establish an authorization boundary that can actually be enforced. An agent confirming delivery dates needs to read orders, contact suppliers, and record confirmations. If it also handles delays, it needs visibility into related requirements, the ability to compare options, and clarity about the scope within which it may act.

When a matter exceeds its authority—for example, increasing expenses or changing a customer commitment—it should reach the person responsible for that decision. After escalation, the task must retain its state and outcome so execution can resume.

Existing relationships between functions and objects can also provide a shared basis for system configuration. Those carrying out the work see their assigned objects and pending work; managers see summaries and exceptions within their responsibility scope. Object changes trigger relevant notifications, and actions beyond delegated authority enter decision workflows.

**An agent's work boundaries should be defined jointly by its assigned tasks, scope of responsibility, and authority.** The tools it is given should be selected to support that defined scope of work.

## 6. A digital twin makes ongoing task derivation more feasible

When these definitions are represented in a digital twin, ongoing functions can be connected to specific tasks.

Once store requirements are clear, the system checks available inventory and expected arrivals to identify gaps. When an arrival commitment changes, it reassesses the impact. Once an approach is agreed, it generates tasks and assigns them according to responsibilities and permissions. Execution results update business states for the next round of judgment.

Some steps can be calculated using explicit rules. Others require forecasting, optimization, or agent analysis, and some require human decisions. When facts or business definitions are missing, verification and clarification tasks can be created first.

This process also needs to manage the tasks themselves. Detecting the same exception repeatedly must not create duplicate work items every time. How much of a gap existing tasks cover needs to be visible. When goals change or problems are resolved, related tasks must be updated or closed. Once a gap is identified, its impact, the cost of addressing it, and available resources must inform the decision on whether to act.

The basis for this reasoning is the relationships among organizational functions, business requirements, object states, rules, and responsibilities. By maintaining them over time, a digital twin creates an opportunity to make task generation, assignment, and evaluation progressively computable.

Agent design then becomes more concrete: **within this ongoing business operation, which judgments and actions does the agent undertake, what environmental support does it need, and how does it know its work is complete?**
