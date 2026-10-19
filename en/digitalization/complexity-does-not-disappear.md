“Complexity doesn’t disappear; it only shifts.” The claim sounds persuasive. In enterprise digitalization, we often see business issues left undefined for product managers to resolve; issues left unclear in product design passed to developers or implementation teams; and gaps in systems left for business staff to handle through manual work, communication, and coordination.

Complexity has not disappeared because we chose not to address it. It has moved elsewhere.

Following this argument further, however, raises a question: **is complexity really conserved?**

If the business world is inherently complex, can we only quietly hope that someone else will deal with it? Or can changing how a system is organized actually reduce complexity across the whole system?

## 1. The business world is already complex

Consider two practical situations.

### Adjusting a production schedule

A production planner at a manufacturer is using Excel to reprioritize several orders. The planner must consider customer importance, contractual delivery dates and liability for delays, whether all critical materials are available, procurement progress and supplier delivery commitments, current production progress, and the available capacity of equipment and staff.

These factors also interact. A material delay for one order may free some capacity, but assigning it to another order depends on that order's material availability and process requirements. Giving one customer priority may delay another.

**The planner may appear to be rearranging a few rows in Excel, but is actually searching for a feasible plan among interdependent facts, resources, rules, and goals.**

### Purchasing medical equipment

In a hospital's information system, equipment procurement may appear as an application form followed by a chain of approvals. The applicant enters the equipment name, quantity, budget, and reason for purchase, and the relevant departments approve it in turn.

How many judgments must actually be made behind that single application?

First comes the need for the purchase. Why is the equipment needed? Will it add clinical capability or replace aging equipment? How is existing equipment being used? Would continued maintenance be more economical?

Clinical and technical assessment follows. Which diagnostic or treatment needs must the equipment meet? How do the technical approaches differ? How should key performance requirements be determined?

Economic considerations also matter. Beyond the purchase price, what consumables, maintenance, and staffing costs will arise over the equipment's lifetime? Where will the budget come from, and what benefits are expected? Are the premises, power supply, information systems, and personnel ready for implementation?

Only after assessing needs and feasibility does the work proceed to procurement itself. Market research, technical requirements, product comparison, review, and contract negotiation are still needed, followed by acceptance checks and delivery.

These activities depend on one another. Clinical needs determine technical requirements, which affect the range of suppliers. Budget limits constrain configuration choices, while implementation conditions may in turn affect equipment selection.

**What appears to be one procurement application is actually a series of decisions involving clinical, technical, economic, resource, and compliance constraints.**

The situations differ, but share one feature: real business already involves many objects, relationships, states, rules, resources, and goals. A local decision often needs information from several dimensions and consideration of its effects on other business activities.

**Business complexity does not depend on whether we have written it down or how many forms appear on screen. Not modeling it does not make it cease to exist.**

## 2. Complexity left unresolved upstream moves downstream

If an enterprise does not clearly maintain relationships among orders, material requirements, procurement progress, and production tasks, planners must consult multiple spreadsheets, ask the responsible people, and use experience to reconstruct the current situation.

Medical equipment procurement presents a similar problem. If initial needs have not been adequately defined and expressed, approvers lack necessary information, making the process lengthy and repetitive. Without stable relationships among equipment configurations, budgets, and technical requirements, each change may require reorganizing materials and explaining the background again.

**Facts, relationships, and rules that could have been clarified upstream become repeated judgment, communication, and coordination downstream.**

Enterprise software has two particularly common ways of transferring complexity.

The first is custom configuration.

Fields, forms, workflows, and permissions can all be customized. But which business matters need independent objects, which are only state changes, and how should the objects relate? Configuration tools do not answer these questions automatically. Without a stable business model in the product, implementation staff must make these judgments afresh for each customer.

**Business modeling left unfinished in the product is transferred to implementation staff.** This is also the problem discussed in [Why has system implementation become configuration hell?](https://rikkalab.com/en/digitalization/system-implementation-configuration-hell/).

The second is adding approvals.

To manage order changes, an enterprise adds a change request form. To inform relevant departments, it adds notification steps. To avoid missing someone responsible, it adds more approvers.

But which business object's state changes when approval is granted? Which subsequent tasks are affected? Who needs to decide, who needs to act, and who only needs to be informed?

If the system does not define these relationships, each recipient of the form must work out how it relates to other business matters—and whether to click “approve” now.

**Routing approvals is not the same as managing business states. Object states, rules, responsibilities, and authority that systems have not adequately represented become human judgments and operations.**

A more fundamental question remains: who defines these business structures?

In [The hidden gap in traditional enterprise digitalization: Who defines how business enters the digital world?](https://rikkalab.com/en/digitalization/business-modeling-defines-representation/), I discuss this longstanding gap in organizational functions. Business teams know operational reality but may not be able to abstract it into stable digital models. Software teams are skilled at implementing requirements but generally do not continuously define the enterprise's business world as a whole.

When no one undertakes this work, complexity keeps moving among business teams, product design, implementation, and day-to-day execution.

## 3. Complexity can be duplicated and amplified as well as transferred

When a business rule lacks a shared definition, several departments may each maintain their own version. Without reliable sources for an order's status at different stages, procurement, production, and sales must confirm it separately. Different systems defining the same business object differently require additional data conversion and coordination.

Business changes then require all these distributed definitions to be updated. One omission can create further inconsistencies and rework.

Three changes are taking place:

- **Transfer of complexity:** definitions and judgments left unresolved upstream are passed downstream.
- **Duplication of complexity:** the same fact, rule, or relationship is processed repeatedly in different parts of the work.
- **Amplification of complexity:** inconsistencies and additional dependencies created by repeated definitions introduce further coordination costs.

The complexity we have to handle therefore comes partly from the business itself and partly from how systems are organized.

**A system that looks simple in isolation is not necessarily simple as a whole.** Measuring only the efficiency of one product or activity can hide work transferred elsewhere or created in addition.

## 4. Is complexity really conserved?

“Complexity does not disappear; it only moves” carries an implicit assumption: **the overall structure of the system cannot change.**

With a fixed structure, work removed from one part may indeed move elsewhere. Allowing the system to be redesigned can produce a different result.

Good product managers and architects have long done this work: identifying duplicated business concepts, redrawing object boundaries, abstracting shared capabilities, reducing coupling between modules, and enabling rules and capabilities to be reused across contexts.

**Viewed through complexity, this work changes system structure to reduce the unnecessary complexity the whole system must handle.**

For example, several applications may each maintain the same business rules. Establishing the rules in a shared model requires an initial modeling investment, but may reduce repeated configuration, validation, and subsequent changes across those applications.

An upstream adjustment to an object boundary or clarification of a rule may go further, eliminating decision branches, configuration options, and exception handling across multiple downstream processes. **In principle, one modeling improvement can reduce a broad area of downstream complexity.**

This is an important contribution of good product and architecture design, though it has been difficult to measure.

We routinely count features built and efficiency gained. It is harder to calculate how much configuration, communication, and rework never happened because an earlier design choice was sound.

Yet the work that never occurs may constitute a substantial benefit of system architecture.

Complexity therefore need not be conserved. Design should be evaluated not only by work reduced locally, but by the costs of building, operating, and evolving the whole system.

Building the environment may require more upfront investment while reducing repeated definition, judgment, and coordination work across later tasks. Assessing whether it is worthwhile requires a long enough time horizon and a sufficiently complete scope of business operations, rather than comparing only the cost of one task.

## 5. How upstream modeling reduces downstream complexity

Return to the manufacturer.

A customer asks for an order to be delivered earlier. Traditionally, sales might initiate change approval, planners review the schedule, procurement checks material progress, and departments repeatedly confirm the scope of impact through forms and messages.

If the relationships among contractual deliverables, delivery batches, material requirements, procurement tasks, and production tasks have already been defined upstream, with corresponding states and rules, a delivery-date change can be linked directly to the affected business objects.

The system can use these relationships to identify procurement and production tasks needing reassessment, calculate constraints that can be determined, and send tasks or notifications to the responsible people. People still make real decisions about conflicting commitments and resource trade-offs. They need not start over each time to find objects, reconstruct relationships, and determine who should participate.

**An investment in structured modeling upstream can eliminate substantial repeated information collection, relationship analysis, and coordination downstream.**

This does more than move work earlier. It prevents some work from having to recur.

In [Business Modeling is fundamentally about defining how business is represented](https://rikkalab.com/en/digitalization/business-modeling/), I describe modeling as purposeful compression. For its benefits to reach operations, business requirements, product capabilities, and technical implementation also need explicit connections—the approach discussed in [From business to code: Reasoning across three architecture models](https://rikkalab.com/en/digitalization/business-product-technical-architecture/).

When these structures can be reused over time, adding a business scenario or application need not require defining the entire business world again.

**Leaving the business unmodeled lets complexity recur downstream; good modeling progressively reduces complexity upstream.**

**Good system design does not hide complexity or pass it to someone else. It changes system structure to reduce the unnecessary complexity the whole system must handle.**
