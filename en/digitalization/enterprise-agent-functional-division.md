Designing an enterprise agent first raises questions about boundaries. We may quickly name it a “procurement agent,” “sales agent,” or “project management agent,” but those names do not yet explain which business functions it performs, whose work it depends on, who receives its outputs, or the scope within which it can make decisions.

In “Intelligent systems, ecological niches, and agent networks,” I approach these questions through ecological niches. In an enterprise, defining a niche requires a closer understanding of the organization's division of work.

From a transaction-cost perspective, one important reason companies exist is to bring activities that would otherwise require repeated searches for counterparties, negotiation, and coordination into relatively stable organizational relationships. Once inside a company, these activities still need to be divided and connected: who provides what, who takes over the results, who makes judgments, and who is accountable for outcomes. Through division of work and collaboration, an organization combines the capabilities of different participants.

An agent joining an enterprise also joins these working relationships. A “procurement role” may include verifying requirements, selecting suppliers, executing orders, and following up on delivery dates. Each part connects with engineering, production, finance, and other work. Simply reusing a job title does not establish which parts an agent should take on.

The organization's existing descriptions of these boundaries may also be insufficiently clear. Companies generally have departmental responsibilities and job descriptions. Yet when something happens, several departments may claim involvement while no one is accountable for the final outcome. Or each department may finish its own work while a step between them remains unassigned.

Clarifying these relationships requires identifying the functions the business needs, the objects involved, and then who takes them on within what scope. **Functions are the intermediate layer connecting business needs with the actors that carry them out.**

## 1. Functions already exist, scattered across text

Departmental responsibilities, job descriptions, and recruitment postings already contain many descriptions of functions: maintaining customer relationships, managing sales contracts, confirming technical solutions, ensuring material supply, and calculating costs.

These can be broken down into a basic structure:

**What responsibility is undertaken, and for which business objects?**

For example, “responsible for sales contract management” identifies sales contracts as the objects, but remains broad. A contract includes payment arrangements, deliverables, and service-level agreements (SLAs). These are fundamentally different business objects, handled by different teams: finance tracks receivables and payments received, the delivery team handles completion and acceptance of deliverables, and the service team fulfills SLAs. Their relationships through the contract allow “contract management” to be divided into specific responsibilities that can be assigned and checked.

Function modeling can therefore begin with existing departmental responsibilities and job descriptions, extracting their objects, responsibilities, and scope, then checking them against the actual business.

Historically, these definitions have mainly existed as text. Different documents may use different names for the same responsibility. The same word, “responsible,” may mean execution, coordination, or final confirmation. Each document may look complete on its own, yet reading them together may still leave it unclear how the responsibilities fit together.

A shared structure makes it possible to identify overlaps: are several actors responsible for the same thing, or for different parts of it?

Finding gaps in responsibility also requires examining the business process. Work absent from every department's documents will not emerge automatically merely by organizing the text.

**Existing responsibilities provide the starting point for modeling; whether the business can operate from end to end provides the basis for validation.**

## 2. Precise responsibilities require stable business objects

Structuring job descriptions alone is insufficient. The objects to which responsibilities refer may themselves be poorly defined.

Traditional systems are often divided according to their product modules and implementation scope. Software boundaries do not necessarily match real business boundaries. A sales contract may be approved in an office automation (OA) system, produce an order in an enterprise resource planning (ERP) system, and have delivery organized in a project system, while subsequent amendments remain in chat histories and attachments.

A continuous business activity is split into several pieces when it enters systems. People familiar with the business often have to fill in how these pieces correspond, which information is valid, and what a particular change affects.

When two departments both say they are “responsible for the contract,” they may mean different stages or partial records in different systems. Comparing their responsibility descriptions directly makes it difficult to determine where they overlap or what they omit.

**Stable business objects provide a shared reference point for responsibilities.**

Stability here means an object has an explicit business meaning and can be consistently identified over time. The same contract remains identifiable across system boundaries, with its state, versions, and related business traceable. Contracts, orders, deliverables, and receivables each have their own boundaries and are connected through explicit relationships.

Once objects are clear, responsibilities can be assigned precisely: who maintains the contract terms in force, who tracks receivables, who confirms that deliverables meet acceptance conditions, and how these responsibilities connect when changes occur.

Object modeling and function modeling therefore need to validate each other. Object boundaries help locate responsibilities precisely; ambiguities discovered while breaking down responsibilities can, in turn, reveal gaps in the business model.

## 3. Separate the capability the business needs from who currently provides it

Once a function can be described independently, its definition can be maintained separately from its assignment to departments, roles, and people.

For example, a company needs to assess whether an order can be delivered on time. This function has explicit objects, inputs, and results: for a customer order, combine material arrivals, production progress, and available capacity to estimate the delivery date and assess risks.

Today, a particular planner may perform this work. As the company grows, different teams may take it on for different product lines. Systems may also contribute to the parts where data and rules are sufficiently developed. The way it is performed changes, but the company still needs the capability to assess delivery dates.

Conversely, one role often contains several functions. A planning lead may assess delivery dates, schedule production, and help coordinate major exceptions. Treating the role as an indivisible unit makes it difficult to discuss how to redistribute this work.

Functions and their assignment can be maintained at two levels:

| Level | What needs to be defined | Example |
| ---- | ---- | ---- |
| Function definition | Which objects it concerns, what function it continuously performs, and what results it produces | Responsibility for material procurement |
| Responsibility assignment | Who takes on the corresponding responsibility, and within what scope | The procurement department handles material procurement; Zhang San handles electronic components, and Li Si handles sheet-metal parts |

Departments and roles can take on and combine these functions. People assume responsibilities through their appointments and specific allocations of business work. The scope must also be made concrete, from “responsible for a product line” to “responsible for this particular order.”

Organizational changes then have an explicit place in the model. A personnel change adjusts the assignment; business expansion adjusts its scope; a change in working methods reorganizes the participants. A change in the business itself calls for revising the function definition.

## 4. Make the division of work a business structure that can be checked

Bringing these relationships together allows the organization to be examined from two directions.

Starting from a business object, we can check which responsibilities are needed as it is created, changed, fulfilled, and closed; whether someone has taken on each responsibility; and whether handoffs are complete.

Starting from departments, roles, and people, we can check which functions they perform, the scope they cover, and their collaborative relationships with other actors.

The division of work previously scattered across responsibility documents and personal experience becomes a business structure that people can jointly identify and adjust. AI can help extract candidate definitions from existing materials and compare differences. Boundaries and assignments still need to be confirmed against the actual business.

Only on this foundation can we further discuss how responsibilities map to permissions, which judgments approval steps make, how specific tasks arise, and which work is suitable for agents.

**The function model must first answer who needs to be responsible for what in this business. Clarifying this layer gives the organization a foundation for continuously adjusting its division of work and incorporating new actors to carry it out.**
