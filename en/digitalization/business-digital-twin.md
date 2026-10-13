## 01 | With so many systems in place, why do we still need a group chat?

Ask a manufacturing enterprise, “Can this order be delivered on time?” and the answer often has to be assembled from a series of conversations. Sales knows what was promised to the customer. Procurement knows the supplier’s latest expected arrival date. The warehouse knows how much has actually arrived. The shop floor knows which operations are complete. Everyone joins a group chat to check the details, and someone familiar with the business assesses the remaining risks.

Not all this information is missing from systems. Purchase orders, goods receipt records, and production orders may already exist. But moving from those records to a judgment about delivery still requires people to supply many relationships: which order needs the purchased materials, whether received quantities are already reserved for other projects, which operation a missing component will block, and how long the remaining work will take.

Each system keeps some records, while the full operating logic is distributed across people’s experience, communication, and temporary spreadsheets. Whenever a problem arises, people must organize these pieces again. If we gradually make the relationships explicit and keep them aligned with actual business, what form will digitalization take?

**I believe the ultimate outcome of enterprise digitalization is a business digital twin: a digital environment where people and AI agents work together.** “Ultimate outcome” here describes a direction for development. The Digital World progressively represents how the business operates, allowing participants to continue one another’s work and keep changing reality through action.

## 02 | What needs a twin is how the business operates

Digital twins readily bring to mind 3D equipment models, factory dashboards, and sensor data. Yet even with an accurate reconstruction of a machine’s shape and real-time operating measurements, we may still not know which order it is working on, which delivery a failure will affect, or whether another machine can take over. Its physical state needs to be understood through its relationships with orders, tasks, and resources to support these judgments.

An order has no physical shape to scan. Neither do delivery commitments, material allocations, or operating permissions, yet all affect enterprise operations. One hundred units of material in the warehouse do not mean one hundred units are available for this production run: sixty may already be allocated to other orders, and twenty may not have passed inspection. If a system records only total inventory, it does not represent the reality needed for this business judgment.

That reality also includes organizational relationships. When a material shortage arises, who fills it, who confirms a substitution, and who can change the schedule all affect whether work can proceed. If these relationships exist only in people’s habits, the Digital World still depends on people to fill the gaps.

**A business digital twin continuously maps the relevant objects, states, rules, and relationships in business operations.** Its level of detail depends on the judgments and actions it must support. Assessing delivery risk requires representing dependencies between materials and production tasks, but may not require locating every screw on the shop floor.

## 03 | Keeping the Digital World aligned with business changes

A complete business architecture diagram is still only an understanding of the business at one moment. When a customer changes a configuration, a supplier revises a delivery date, or production requires rework, those changes must enter the corresponding digital objects and relationships for the twin to remain useful.

Suppose a batch of components is now expected on Thursday rather than Monday. If the system merely stores another supplier email, the change has been recorded without updating the business state. Schedulers may still plan production using the old date, while the delivery assessment seen by sales remains unchanged.

Only when the delay is linked to a specific procurement item and, through material requirements, to production tasks and customer orders can the system identify which plans need review. Whether delivery remains feasible also depends on available inventory, substitution options, and remaining production capacity. Uncertainties should be retained as information gaps for the appropriate people to confirm.

Two kinds of change need to be maintained together. One concerns instance states, such as a delayed batch or a completed task. The other concerns business definitions, such as revised substitution rules or reassigned approval authority. The first updates what is happening now; the second changes how future judgments and operations work.

The mappings should also retain their sources and timestamps. “The supplier promises arrival on Thursday” and “The warehouse confirms receipt” have different meanings and different grounds for trust. Making these distinctions explicit lets participants know which conclusions can be used directly and which still need verification.

## 04 | People and agents work in the same Digital World

When objects, states, and dependencies are continuously maintained, “What if we produce another order first?” becomes a question with objects and constraints that can be analyzed. Business operations also require turning plans into action, with people, agents, and traditional systems participating together.

Faced with a component delay, an agent can mark affected production tasks on the corresponding order, query approved substitutes, and propose adjustments. An engineer accesses the same business object, reviews the engineering basis, and confirms the substitution conditions. Procurement secures supply, the scheduling system recalculates the plan, and an authorized actor confirms the change. Subsequent arrivals and production progress update those objects, allowing everyone to continue from the results already established.

People and agents can use different interfaces. People understand the situation through object pages, tables, or conversations; agents participate through structured queries and action interfaces. Both refer to the same business facts, and the results of their operations enter the same continuously updated environment. At handoff, the next participant can directly find the objects being handled, the judgments already formed, and unfinished work.

Whether the components actually arrive, whether the shop floor starts work in the revised sequence, and whether actual labor time matches the estimate must also feed back into the digital representation as a basis for the next judgment. **Observation, simulation, action, and feedback thus revolve around the same business representation, and the digital twin becomes a working environment for actual organizational operations.**

Which work people perform and which is assigned to agents or traditional systems can change with capabilities and business needs. The shared objects, rules, and results remain available over time.

## 05 | Building a business digital twin across software boundaries

A business digital twin can span several systems. Enterprise resource planning (ERP) systems maintain procurement and inventory, production systems record execution, and project systems maintain delivery plans. The question is whether the same business activity remains connected across those software boundaries.

If orders cannot be matched across three systems, and “procurement complete” means an order has been placed in one, goods have arrived in another, and payment has been made in the third, subsequent judgments may rest on different premises even when the interfaces are connected. Beyond connectivity, **business object identities, state meanings, responsibility for rules, and authority boundaries need to be aligned.**

This is the role of a shared Business Atlas. It connects local structures scattered across applications and departments, allowing a change to be understood in its full set of business relationships. As the map’s structures are linked to instances, continuously updated states, and executable operations, a running digital twin gradually takes shape.

Development can begin within a limited scope. For example, first connect the relationships from material requirements through procurement, production, and delivery for one category of orders. Actual operations then reveal missing relationships and rules, which can be addressed before expanding further.

Return to the original question: “Can this order be delivered on time?” People may still need to discuss it, but the discussion can start with identified gaps, conflicts, and options. Decisions change the states of relevant objects and enter subsequent execution. Next time, facts need not be assembled from scratch.

If every business change requires people to create a group chat, find spreadsheets, and ask around to reconstruct relationships between objects, key parts of business operations remain outside the systems, however many applications are in use. Adding an agent may merely introduce another participant busy piecing information together.

**What enterprise digitalization truly needs to deliver is a Digital World in which the business can operate continuously and people and agents can continue one another’s work.**
