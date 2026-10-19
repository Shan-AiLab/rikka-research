Many digitalization projects assume that business requirements already exist and simply have not yet been collected in full. Projects therefore tend to begin with requirements gathering: business teams describe how work is done today, what gets in the way, and what they want the system to do; product managers organize the requirements, and software teams design and implement the solution.

In complex businesses, however, what this process uncovers is often only **the business’s current description of a problem**, not necessarily the problem that actually needs to be solved.

For example, a business team may ask for “a few more fields on the equipment page.” Further investigation may show that the problem is not a lack of fields, but that maintenance, asset management, quality control, and other activities are all adding information to the same equipment object. Looking more closely, the business may need to distinguish domains, perspectives, and the purpose for which the information is being used. At that point, “add fields” is no longer the original requirement.

Or consider an equipment purchase request where a new purchase and a replacement use the same fields and approval workflow because both look like “a request to buy a piece of equipment.” Follow the questions further and it becomes clear that the two cases need to answer very different things. A new purchase raises questions about why additional equipment is needed, why existing capacity is insufficient, and whether space and budget allow it. A replacement requires first understanding why the existing equipment should be replaced, whether continued repairs are worthwhile, and what should happen to the old equipment. **They look like the same kind of purchase request, but in fact require different information, grounds for judgment, and decision paths.**

These answers do not necessarily emerge after a few more rounds of asking, “What else do you need?” Many distinctions become visible only as the business is re-examined and modeled, as system design begins, or once the system is in operation.

Business modeling is therefore not just about turning stated requirements into process diagrams, fields, and data dictionaries. Its more important role is to keep deciding **which distinctions in real business should be preserved when it enters the digital world, and how those distinctions should be separated, related, and represented.**

**In this sense, business modeling defines how business is represented in the digital world.**

When these definitions change, systems, permissions, metrics, agents, and ways of working change with them. Modeling is therefore not a one-time preparation step before implementation. It is an ongoing foundational function that develops as the business is better understood and is revised through actual operation.

## The client cannot do it; the vendor does not own it: why business modeling remains unclaimed

In the traditional division of work between clients and vendors, modeling often falls into an awkward gap. Put bluntly:

**The client does not know how; the vendor does not take responsibility.**

The client knows the business reality best: what customers truly care about, which processes are merely historical habits, and which pieces of information are used every day despite never being recorded in a system. But knowing the business does not automatically mean being able to abstract that reality into a stable digital model. Business staff can say “this field matters,” “we need an approval here,” or “this is how we have always done it.” Deciding which object a field belongs to, how many distinct judgments are hidden inside an approval, or whether new purchases and replacements should share a workflow goes beyond simple requirements gathering.

Software vendors, meanwhile, are usually better at turning confirmed requirements into systems. When a client asks whether something can be implemented, the vendor often answers, “Anything is possible if the requirements are clear.” Whether those requirements make sense, why the system should be structured that way, and whether it can keep evolving as the business changes often fall outside the vendor’s delivery responsibility.

This leaves a large area with no clear owner:

**Business teams know the reality but may not be able to define it consistently; system teams can implement a digital world but usually take responsibility only for requirements that have already been articulated.**

Yet the question of how real business should enter the digital world sits precisely between them.

When systems end up with ever more fields, configurations, and workflows, the root cause is not necessarily that a particular product manager or implementation team made a mistake. More fundamentally, **business modeling itself has not become an ongoing function with clear ownership.**

The cost of leaving this function unfilled is not limited to repeated requirements discussions and system rework. Complexity may also be shifted, copied, and amplified across multiple stages. See [“Complexity doesn’t disappear—it only shifts. Or does it?”](https://rikkalab.com/en/digitalization/complexity-does-not-disappear/).

## AI makes this gap harder to work around

In the era of traditional systems, people could compensate for this problem.

When a field was poorly defined, someone could interpret it from experience. When objects in two systems did not line up, someone could convert them manually in Excel. When a workflow lacked a clear state, someone could ask in a group chat. When permissions were poorly designed, someone familiar with the organization could make a quick judgment about whom to contact.

People have long acted as the interpreters and glue between systems.

But as agents enter real business operations, the assumptions people hold in their heads start to become a problem.

For agents to participate in work reliably over time, they cannot be left to guess every time: whether “equipment” in one table is the same concept as “equipment” in another system; whether “approval complete” means that the workflow has ended or that the business objective has been achieved; or whether a message is merely informational or calls for action.

Business structures that were never made explicit in systems do not disappear simply because models become more capable.

On the contrary, **AI exposes the ambiguous areas that enterprises have long relied on people to handle.**

That is why enterprise AI projects often run into questions about business definitions, the allocation of responsibilities, data governance, and system architecture once they reach a certain depth. This is not scope creep. These have always been prerequisites for agents to operate reliably in real business environments.

## Requirements management must move from projects to continuous evolution

If requirements emerge over time and business representations need to be revised continuously, enterprise digitalization and AI development can hardly be understood as a series of independent projects.

Projects still need boundaries. Each stage must define what it will deliver and what problem it will solve; otherwise, development can easily lose focus.

But above individual projects, enterprises also need a longer-term mechanism to keep asking: Have business objects and rules changed? Where should a new local requirement fit in the existing structure? Could a system change break other scenarios? Should a capability introduced in one project become a shared enterprise capability? And how should compromises made today for a quick solution be brought into alignment over time?

That is why the most valuable long-term role should not be limited to continuously “taking requirements and delivering projects.”

It is closer to maintaining the enterprise’s business domain model and its digital representation over time: understanding new realities through each local implementation, then putting those changes back into the overall structure to decide which should become lasting definitions and which are temporary solutions for a particular situation.

**Requirements are not collected once and for all, and systems are not designed once and for all.**

What complex enterprises truly need to build is the ability to keep understanding, modeling, validating, and revising themselves as the business changes.

In the age of AI, this becomes even more important. Enterprises need not only people to understand their business world, but also systems and agents to operate within the same continuously evolving digital world.
