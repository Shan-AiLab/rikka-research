## 1. Agent design needs to start with the business

Enterprise resource planning (ERP), office automation (OA), customer relationship management (CRM), product lifecycle management (PLM), manufacturing execution systems (MES)… A company may already have deployed many systems, yet employees still need to create spreadsheets, ask colleagues, start group chats, cross-check information, and use experience to judge what to do next.

Some of this work is now being expressed as requirements for agents: automatically tracking orders, assessing material readiness, analyzing the impact of changes, and coordinating tasks across departments. Discussion quickly turns to “how to design the agent”: which tools it needs, how to divide tasks, and how to organize collaboration among several agents.

Setting aside projects that look for use cases simply to spend an AI budget, **the answer to “how to design the agent” needs to start with the business needs behind these requirements.** What does the business actually need? What do existing systems already support? Why are people still doing the rest? Clarifying these questions provides a basis for deciding which work agents should undertake and which requirements can be met in other ways.

## 2. What does the business itself involve?

A manufacturing company turns customer requirements into products it can deliver. Sales, engineering, procurement, production, and delivery perform different functions, supported by people, funding, equipment, and management arrangements. Order progress, material readiness, and the impact of changes arise from these activities and their interdependencies.

Consider an engineering change. A customer asks to replace type A components with type B in a batch of products. The old components may already have been purchased, and some products may already be assembled. Lead times for the new components and the capacity needed for rework may affect the original delivery schedule.

Handling this change requires the company to understand several aspects of the business.

First, **objects, relationships, and states**: which contracts and products are affected, which version of the technical design applies, how much material has been purchased and which orders or projects it has been allocated to, and how far production has progressed. Knowing “how much is in the warehouse” does not establish “how much this project can use.” Managing customer relationships likewise requires connecting customers, opportunities, contracts, and service records to judge whether a complaint affects a renewal in progress. Retail requires distinguishing stock on hand, in transit, and reserved at different stores to identify actual shortages. Business judgments depend on relationships between specific objects and their current states.

Second, **goals, responsibilities, and capabilities**: to what extent customer requirements must be met, whether delivery dates are negotiable, and who bears additional costs; what engineering, procurement, production, and sales are each responsible for, who is accountable for taking the change through to completion, and whether existing resources can handle the rework.

The company also needs to define **activities, rules, and decisions**: which assessments can run in parallel, which work must wait for confirmation, and when the old version stops being used; which technical constraints must not be violated and who can approve additional spending; how much each option costs, which deliveries it affects, and how to choose among them.

Together, these determine how the business operates. The same way of describing a business applies to the enterprise as a whole and to its departments, teams, and individual activities. Each has its own goals and responsibilities, connected through shared objects, resources, and handoffs.

## 3. What do existing systems cover, and what still depends on people?

ERP can manage procurement, inventory, and finance. PLM can manage product structures and technical versions. MES can record production execution, and OA can support approval workflows. These systems may also offer rule validation, planning calculations, and analysis. The company is not starting digitalization from zero.

The problem is that **having the individual parts in systems does not mean the business logic connecting them is fully supported.**

When the bill of materials (BOM) changes in the engineering system, do purchase orders need adjusting? Which projects are the old components in inventory allocated to? Which shop-floor tasks must stop? After a change is approved in OA, who confirms that every system and the shop floor have adopted the new version?

Transferring data through interfaces does not necessarily answer these questions. The meanings of “available for use,” “completed,” and “needs changing” depend on object relationships, business rules, and responsibilities.

People often fill in what systems do not support.

Someone maintains mappings across systems in Excel. Someone asks for the latest progress in a group chat. Someone remembers the conditions under which a material can be substituted. Someone knows whom to contact when a problem arises. And someone weighs costs, delivery dates, and customer relationships to decide how to respond.

**People fill in facts, connect information, and execute established rules; they also handle conflicts, uncertainty, and decisions that require real trade-offs.** These activities mix together in everyday work. They all look like “manual work outside the systems,” yet their nature differs.

This also explains why new requirements keep appearing despite the number of systems already in place. Gaps remain in how the digital world supports the business, while the business itself keeps changing. Product adjustments, reassigned responsibilities, revised rules, and new customer requirements can all make previously adequate coverage incomplete again.

## 4. Should all this manual work be handed to agents?

Once large language models can read documents, understand messages, and call tools, it is natural to ask whether an agent could take over this manual work.

That is worth exploring. But first, it helps to unpack the work.

For example, a sales team wants an agent to “automatically follow up with customers.” Breaking this down may reveal that the customer's current stage, the responsible person, and the conditions for follow-up have not been explicitly recorded. Once these definitions are in place, ordinary workflows can generate reminders and assign tasks. Understanding a customer's objections and choosing a communication strategy are further judgment problems.

A retailer wants an agent to “automatically replenish stock.” This requires complete relationships between products, stores, stock on hand, goods in transit, and promotional plans. With that foundation, routine replenishment can be calculated using rules and forecasting models. Allocating limited inventory across stores during an unexpected shortage involves choices under business goals and constraints.

A manufacturer facing delayed materials needs to decide whether to pay more for procurement, use substitutes, or adjust delivery dates. This involves generating options, checking constraints, and weighing value. Some judgments can be handled by explicit rules or optimization algorithms; others may benefit from agent-assisted analysis and may still require a person to make the final decision.

Decisions also need to be broken down further. Are the necessary facts complete? Are the constraints explicit? Do evaluation criteria exist? When these foundations are missing, what is called a “need for intelligent judgment” may still contain substantial work to fill information gaps and clarify business definitions.

Therefore, **work expressed as a requirement for an agent does not necessarily need to be implemented with an agent.** First identify what comes from objects, states, relationships, and rules missing from systems, what comes from insufficient computational capabilities, and what actually involves complex decisions. Then select the appropriate implementation methods.

## 5. Locate requirements in the gap between the business and its digital twin

This returns to the direction discussed in [“Enterprise digitalization should ultimately create a business digital twin”](https://rikkalab.com/en/digitalization/business-digital-twin/): the digital world should progressively support how the business operates, allowing people, agents, and traditional systems to continue one another's work around the same objects, facts, and rules.

What a digital twin needs to contain is determined by the business itself. It must support everyday records and workflows while providing a shared environment for computation, decisions, action, and feedback. Development can begin within a limited scope, gradually filling in missing content and connections.

**Whether the resulting requirement concerns digitalization, reporting, workflows, or agents, it can be understood through the same question: what is still missing between the capabilities the business needs and what its existing digital twin supports?**

The next article will explore how to identify these gaps and turn them into product requirements with a clear basis in the business.
