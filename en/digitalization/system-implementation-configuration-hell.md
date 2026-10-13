Anyone who has worked on enterprise software implementation will probably recognize this scene: business departments go through repeated discovery interviews and provide their existing spreadsheets, policies, and processes. Implementation staff use these to configure fields, approval steps, roles, and permissions, then keep adjusting them in response to feedback from trial use.

A missing case means adding another option. If someone cannot handle a task, grant another permission. If a workflow gets stuck, add another branch. By the time the system finally goes live, few people can fully explain how all these settings relate, which can be changed, or what a change will affect.

In a product demonstration, all of this is often summed up in a single sentence: **It supports customization and flexible configuration.**

Configuration capabilities do lower the barrier to adapting software to a business. But why does implementation remain so laborious as tools become more flexible? Why does switching systems so often mean going through discovery, configuration, and rework all over again?

Because much of what looks like “configuration” actually determines how the business enters the digital world. Tools make these decisions easier to implement, but do not automatically resolve how they should be made.

## 1. Adding a field may involve business modeling

Suppose a company needs to manage sales contracts. It already has a form for new contracts and now needs to support contract amendments. The easiest approach seems to be adding a “business type” field to the existing form—new contract or amendment—and configuring different fields and approval branches for each type.

But further questions quickly take us beyond form configuration.

Which contract does an amendment relate to? Does the original contract remain valid after the amendment is submitted? Which version should govern fulfillment while approval is pending? If deliverables, payment arrangements, or service-level commitments change, which teams need to reassess them, and which downstream plans need to be adjusted?

These questions determine what the system actually needs to represent.

The contract needs to maintain the terms currently in force. An amendment has its own submission time, proposed changes, assessment process, and conditions for taking effect, and needs a relationship with the original contract. If these distinctions are squeezed into a single type field, more conditions may need to be added later: when original values can be changed, when old values must be retained, which fields appear under which conditions, and what gets updated after approval.

**What appears to be adding fields and branches is actually work on object boundaries, state changes, and business rules.**

Configuration tools make operations quick, but a dropdown alone cannot decide these structures for the company. Whether the final implementation uses code or drag-and-drop configuration, someone still needs to do the modeling.

## 2. “Customization supported” also leaves design decisions to the customer

When a product offers custom fields, workflows, and permissions, it appears to give customers part of the design space.

This is like a renovation company offering a wide range of materials and construction capabilities: walls can be removed, wiring and plumbing changed, and cabinets made to order. But the homeowner must decide how to divide the space, how people will move through it, and how the different elements should fit together. Easier construction does not mean the design is complete. Without a design, the homeowner may discover problems while living there and keep reworking the space. Or imagine LEGO selling only bricks, with no building instructions: users would first have to learn some design themselves.

Companies do differ, and plans need to be adapted to their actual business. But if the product's answer remains “you can configure it yourself” at the field level, it amounts to handing customers building materials and construction tools while leaving the overall design unresolved.

Business staff know their work. Turning that knowledge into a coherent business model that supports operations across departments requires a different skill set. They usually start from current spreadsheets, established habits, and immediate inconveniences, asking to “add a field,” “include another approver,” or “allow changes here.”

Implementation staff understand the product and can turn these requests into settings. But if the project's way of working mainly involves collecting, confirming, and implementing requirements, who decides whether a field belongs to a different object, whether two workflows duplicate the same business activity, or what responsibility an approval step actually carries?

**Customers gain configuration capabilities and are also asked to make modeling judgments, without necessarily realizing they are taking on this work.**

The customer may therefore expect the software vendor to provide a sound business design, while the vendor believes the customer has already confirmed the requirements. Both sides complete the work as they understand it, yet the questions that determine the system's structure remain insufficiently addressed.

## 3. Reasonable local choices become difficult to maintain together

This gap does not appear only before launch. It keeps accumulating during everyday use.

For example, to identify which project a purchase serves, a company adds an “Associated project” field to its purchase order and enters the project name. The page appears to show a relationship, but one purchase may meet the needs of several projects. The field does not represent how much is allocated to each project, how much has arrived, or how much is still missing.

When procurement is delayed, the system still cannot calculate which projects will be affected or by how much. Nor can it accurately allocate procurement costs when calculating project costs. This requires explicit allocation relationships between purchase line items and project material requirements, with the corresponding quantities recorded. Adding a project name to a document still leaves a layer of structure missing before the system can support business calculations.

The same problem resurfaces during system integration. An API can send the “Associated project” field to the project system, but does the transmitted name uniquely identify a project? When a purchase line item is allocated to multiple projects, what quantity goes to each? If these relationships have never been defined, an interface cannot reconstruct them. The data has been transferred, but the business relationships still do not connect.

The same applies to workflows and permissions.

If no suitable owner can be found for a step, assign someone for now. If a department might be overlooked, add another approval layer. For an exception, copy a workflow and handle it separately. Each setting solves the immediate problem, but over time they form a way of operating that only a few long-serving employees can explain.

When the business changes, maintainers have to investigate each dependency: which form uses this field, which workflow checks this state, and which permissions are still tied to the former role. These settings accumulate through local decisions, without necessarily being grounded in consistent business definitions.

Across systems, the problem grows. The same responsibility appears as an approver in an office automation (OA) system, an operating permission in a business system, and a task owner in a project system. Each is maintained separately, so changes in staffing or responsibilities require repeated updates.

**This is how configuration hell develops: local requirements keep being met, while the overall relationships become increasingly difficult to identify and maintain.**

The company invests heavily in discovery and implementation and gets a configuration that runs, but may not develop a shared understanding of its business structure. The next project still requires piecing things together from old spreadsheets, old workflows, and people's experience. Change the software, and the same definition problems return.

## 4. The company needs to take responsibility for defining its business

At this point, we need to ask whose job business modeling is.

Modeling concerns how a company understands its business: what counts as an order, under what conditions delivery is complete, which commitments a contract amendment affects, and who has authority to make the corresponding decisions. The company ultimately needs to confirm these definitions and keep adjusting them as the business changes.

**Responsibility for business definitions belongs to the client company itself.** External teams can provide methods and assistance, but the company needs the capability to make these judgments and take responsibility for their long-term consequences.

Software implementation usually centers on a specific product and project scope, with the goal of bringing the system live according to confirmed requirements. Continuously understanding the entire enterprise, coordinating definitions across departments, and maintaining business structures across systems are unlikely to fall naturally within a single software vendor's implementation responsibilities.

Internet companies are generally better placed to establish mechanisms for this work. Business, product, and technical teams are all inside the organization. Product staff translate business problems into objects, rules, and system behavior; technical teams participate in design and continue maintaining the system after launch. A relatively continuous working chain connects business changes with system adjustments.

Traditional enterprises often have business teams familiar with reality and have purchased mature software, yet lack a function that continuously connects the two. Departments submit their own requirements. IT may mainly handle procurement, operations, and vendor coordination, while different external providers carry out separate projects. There may be no clearly designated owner for how the enterprise's overall business should be defined and represented in its systems.

When configurable tools enter such an organization, this missing work falls onto countless field, workflow, and permission options, becoming “please confirm how you want this configured.”

Configuration hell ultimately exposes an organizational problem: **the company needs to continuously define its digital business world, but has not established a function responsible for that work.** This is the modeling gap discussed in [“The hidden gap in traditional enterprise digitalization: Who defines how business enters the digital world?”](https://rikkalab.com/en/digitalization/business-modeling-defines-representation/).

This gap also carries over into putting AI agents to work. Previously, people familiar with the business could resolve ambiguities between business objects, states, and responsibilities as they worked. Now, if an agent is expected to take over, it needs to know which object to operate on, which rules to follow, who has authority to confirm, and what counts as completion. If the company has not even reached an internal consensus on these definitions, the agent can only guess anew on every task.

**The gap in business definitions that traps system implementation in configuration hell today is also preventing agents from moving beyond demonstrations into everyday operation.**
