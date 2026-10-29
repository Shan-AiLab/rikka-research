Production is about to be scheduled, but not all the required materials are ready.

Procurement says the order has been placed and the supplier is late. The warehouse says the goods have not arrived and cannot be booked into inventory. Engineering says a substitute material is still awaiting confirmation. Each department has its own work to do, and each can explain why things remain unfinished.

But production still cannot start.

If we look at the system, we may find that someone is responsible for the purchase requisition, someone is following up on the purchase order, and someone handles incoming inspection and acceptance. Each task has an assignee, and the workflows are running normally.

**If someone is doing every piece of work, why is the final business outcome still not assured?**

This problem existed before agents arrived. Enterprise resource planning (ERP), office automation (OA), and customer relationship management (CRM) systems have been developed for many years. Why do enterprises still rely on Excel, group chats, and manual coordination to carry out everyday business?

Often, the problem is not a missing system feature. The system has failed to represent the business correctly from the outset.

## 1. Start with the Business Outcome, Not the Purchase Requisition

Material readiness for production means having materials of the right quantity, specification, and quality available when production needs them. Completing purchasing alone does not achieve that goal.

Procurement is only part of achieving it.

Ensuring material readiness may require calculating requirements, checking inventory and inbound shipments, making purchasing plans, following up on supplier delivery dates, coordinating substitute materials, and completing incoming inspection and acceptance. The division of work can differ between enterprises, but these activities serve a common business outcome: all materials required for production are ready.

Looking back at the opening example, procurement may be entirely correct in saying, “We have placed the order.” It has completed one part of procurement execution, but that does not necessarily mean the business goal of material readiness has been achieved.

Likewise, receiving goods and booking them into inventory does not mean that all materials required for production are ready.

**Completing individual pieces of work does not establish that the overall business outcome has been achieved.**

An enterprise needs to establish who is accountable for the relevant business outcome, then assign the work needed to achieve it to the appropriate departments and people. Procurement, warehousing, engineering, and planning can each take on different responsibilities. Dividing the work must not leave accountability for the final outcome undefined.

There is no fixed answer that suits every enterprise. In some, planning and material control coordinate material readiness; others may organize the work differently. The point is for the enterprise to establish who is responsible for ensuring which outcomes, based on its business goals and organizational design, rather than to prescribe a particular department in advance.

Without answering that question, discussing who should be responsible for purchase requisitions can easily remain at the level of execution.

We may know who raises a requirement and who places an order while still not knowing who ensures that the requirement is ultimately met.

## 2. Unresolved business problems become problems the system is expected to absorb

When an organization has not established accountability for the overall business outcome, system development faces an immediate problem: requirements need owners, workflows need to advance, and exceptions need to be handled.

The system begins adding fields.

Purchase requisition owner, buyer, coordinator, ultimately accountable person—each field seems to solve part of the problem.

But what do these fields actually mean?

Is the purchase requisition owner responsible for the accuracy of the requirement, or for ensuring it is ultimately met? Is the buyer responsible for placing the order, or also for ensuring supplier delivery? Does the coordinator merely move the workflow along, or bear responsibility for the outcome? How does the ultimately accountable person relate to these other roles?

If the business has not clarified these distinctions first, the system can only operate through field names, workflow conventions, and human interpretation.

New situations may lead to more fields, more permitted associations, and additional special rules. On the surface, the system can express more. In practice, the unresolved responsibilities have simply been broken into more pieces of information that require interpretation.

**A system can record that someone has been designated as responsible, but that field alone cannot create a clear and workable assignment of accountability.**

This does not mean a system should not support multiple roles. Businesses do need people who handle work, review it, and collaborate on it. But each additional role should have a clear business meaning and context of use, rather than serve as a generic remedy for unclear responsibilities.

If the enterprise still has not decided who is accountable for which outcomes, adding fields merely records the uncertainty in greater detail.

## 3. One foundational problem becomes a chain of downstream problems

Suppose the enterprise decides that a purchase requisition needs an explicit owner, but allows several departments to share accountability for the same requisition. The system therefore supports associations with multiple people and uses additional fields to distinguish their responsibilities.

The problem appears to be solved.

But the system then needs to determine who has authority to advance purchasing, who can handle exceptions, who should receive overdue reminders, who is accountable for unfinished tasks, and which department should receive attribution in reporting.

If shared responsibility has not been defined, the existing data alone cannot answer these questions.

Downstream modules have to add their own decision rules. One workflow treats the first associated person as the owner. Another module gives precedence to a designated primary-owner field. A report still requires a person to decide which department the result belongs to.

A single unresolved business definition has now spread into workflows, permissions, reporting, and automation.

In practice, allowing several parties to share responsibility is often a compromise recorded in the system when the organization cannot agree on accountability, rather than a carefully designed management choice. Neither department wants to be solely accountable, so both are entered into the owner field to get the workflow moving.

Recording that compromise does not resolve accountability. When something goes wrong, both parties can still show that they completed their own part. Without clear accountability, the system cannot determine who should coordinate the response next.

The system may then add coordinators, escalation contacts, ultimately accountable people, and other roles, accumulating further complexity.

This complexity also spreads to modules further downstream. Each module seems to add only a little decision logic, but as modules multiply, they may develop different interpretations that become difficult to keep consistent.

The problem grows further when AI agents begin making judgments and executing tasks autonomously using this data.

For example, a procurement agent discovers that an order is overdue and production scheduling is approaching. The system shows that the buyer has placed the order, a coordinator is following up, and engineering still has an unfinished task to confirm a substitute material.

What should the agent do next?

It could remind the buyer to expedite delivery, but reminders may not help if the supplier has confirmed that on-time delivery is impossible. It could suggest using a substitute material, but whether substitution is permitted and who must confirm it depend on another set of business rules. It could also notify production planning to reschedule. Yet without clear accountability for material readiness, the agent cannot determine from these fields alone who should coordinate the response to the exception.

If the system records multiple participants without clearly expressing business goals, responsibility boundaries, and the relevant decision rules, the agent can only guess, ask repeatedly, or act according to a local rule. Even successful tool calls and state updates do not establish that it made the right business decision.

**If every downstream module has to reinterpret business semantics, the system loses the value of reducing complexity through a shared model.**

## 4. Resolve a problem at the level where it arises

When a business situation cannot be represented properly in a system, adding fields or relaxing relationships should not be the immediate response to every difficulty. Investigate from the top down:

1. **Business outcomes and accountability:** What outcome must be achieved? Who is accountable for it? If this is unclear, first resolve the business goals and accountability arrangements.
2. **Responsibility boundaries:** What is each party responsible for? If responsibilities overlap or people pass the blame, first clarify their scopes and handoffs.
3. **Decomposition of responsibilities:** Are existing responsibilities too broad, or is the division of work unreasonable? Where necessary, break responsibilities down and adjust organizational arrangements.
4. **System representation:** Once business definitions are clear, if the existing model still cannot represent them, examine the design of objects, relationships, states, and rules.

For example, the goal of medical equipment maintenance is to restore the equipment’s availability for use. If maintenance, procurement, and warehousing have all completed their tasks but the equipment remains out of service, first examine accountability for the overall outcome and the boundaries between responsibilities, rather than immediately adding an “equipment restoration owner” field.

**Complexity should be resolved at its own level or above, rather than passed downstream by changing the meaning of lower-level concepts, relaxing constraints on foundational relationships, or continually adding exceptions.**

## 5. Starting with the business means understanding it, rather than copying the status quo

Starting with the business does not mean requiring a system to reproduce an enterprise’s existing organizational structure and working methods faithfully.

The business itself may have problems. Departmental responsibilities may overlap, some work may have no one responsible for it, and existing workflows may fail to ensure that business goals are met. Moving these arrangements into a system unchanged can entrench the original problems.

Business analysis therefore needs to establish business goals, responsibility arrangements, and operating rules before deciding what the system should represent.

For example, when an enterprise asks to “add a purchasing workflow,” design cannot begin solely with request forms and approval steps. First establish why purchase requisitions arise, how purchasing quantities are determined, how inventory and inbound shipments enter the calculation, who is responsible for the accuracy of requirements, who has authority to approve purchases, and what business outcome must be ensured once purchasing is complete.

Only then can we determine which business objects, relationships, states, and rules are needed, and how the system should represent and support them.

If the existing model cannot express a reasonable business arrangement, examine the model itself. If the problem is an unresolved business definition, resolve the corresponding business issue first.

Business definitions determine what the system needs to represent. The system model then turns those definitions into stable, executable structures. The two require ongoing collaboration, but neither can substitute for the other.

## 6. Why so many systems are difficult to use

Many enterprises have ERP, procurement, and production management systems but still rely on Excel to schedule production, reconcile inventory, and calculate shortages.

For example, the ERP system records inventory, the procurement system records orders, and the production system records production schedules. Yet the systems have not organized production requirements, bills of materials, inventory, inbound shipments, and supplier delivery dates into a business model that directly supports material-readiness decisions.

Planners therefore have to export data from multiple systems, combine spreadsheets, calculate shortages, adjust priorities, and send the results to the relevant departments.

**When systems do not reflect how the business operates, people have to reorganize the business outside them.** More systems do not necessarily mean greater management capability. If key business relationships and responsibilities are not represented correctly, Excel and manual coordination still have to make up for the gaps.

## Conclusion

When business definitions are unclear, the system keeps adding fields. When business relationships remain unresolved, downstream modules keep adding logic. The system ends up recording large amounts of data and many workflows while still failing to support management effectively.

Return to the opening scenario: production is about to be scheduled, but not all the required materials are ready. A useful system should make shortages visible in advance, with their impacts and accountability clearly traceable, rather than leave people to piece together an answer from several systems and Excel only after scheduling is blocked.

**System development should identify the root of a problem and resolve it at the right level, rather than reserve a field for every business ambiguity. That is why system development must start with the business.**
