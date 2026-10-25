An enterprise wants to build a procurement agent that can move beyond making purchasing recommendations to placing orders autonomously. At that point, what permissions should it receive?

“Allow it to create purchase orders” does not answer the question. Drafting a document for approval and sending a formal order to a supplier create different business commitments. We may want the agent to place orders only within specified categories and budget limits, referring anything outside that scope to a person. But create, read, update, and delete permissions cannot express these boundaries on their own.

When authorization stays at the level of enabling tools and reading or writing data, keeping the agent in a sandbox or drafting area leaves people to finish the work. Opening up the tools requires additional rules and human confirmation to constrain it. What we want to delegate is work with clearly defined boundaries; what the system asks us to configure is a set of action permissions.

**The difficulty of authorizing agents makes an existing gap between the division of responsibilities and system permissions more visible.**

Today, the division of responsibilities within an organization is expressed mainly through departmental responsibility statements, job descriptions, and authorization policies. To understand the relationship between business authority, responsibility, and system permissions, we should return to these documents.

## 1｜Unpacking job descriptions: Authority, responsibility, and limits

Consider a typical procurement job description:

> Be responsible for procurement within designated categories; solicit supplier quotations and coordinate supplier evaluations; determine procurement plans within authorized financial limits; track order delivery and promptly report delivery exceptions; ensure procurement information is accurate and progress can be traced. Refer matters exceeding those limits to the procurement manager for approval.

This description already contains objects, responsibilities, authority, and boundaries:

| Wording in the description | Business structure already expressed |
|---|---|
| Designated categories | The scope of objects covered by the assignment |
| Suppliers, procurement plans, and orders | The business objects involved in the work |
| Solicit supplier quotations and coordinate supplier evaluations | Work to be undertaken and the corresponding execution permissions |
| Determine procurement plans | Decision authority over specific procurement matters |
| Within authorized financial limits | Financial limits on exercising authority |
| Track delivery and promptly report exceptions | Ongoing work obligations and coordination requirements |
| Accurate information and traceable progress | Required outcomes and standards for fulfilling responsibilities |
| Refer matters exceeding the limits to the procurement manager | The boundary of the role’s decision authority and who decides matters beyond that authority |

Here, responsibility describes the ongoing work to be undertaken and the outcomes for which someone is accountable. Authority describes the decisions and actions they may take. Limits specify the objects and conditions under which that authority applies. A responsibility brings work obligations and accountability for outcomes together; concrete work assignments determine who takes it on.

The description already distinguishes conducting inquiries from deciding on a plan. Looking beyond this role to the wider organization reveals two other kinds of work: who sets procurement policies and authorization limits, and who checks compliance with them. These activities connect to the current role’s work and together form the allocation of authority and responsibility in procurement.

Unpacking these existing business arrangements by their nature gives us four kinds of authority: governance authority, operational decision-making authority, execution authority, and oversight authority. Operational decision-making authority means making decisions about specific matters within established rules.

| Authority | Business meaning | Example involving a procurement contract |
|---|---|---|
| Governance authority | Establish or change applicable rules, standards, and rules for allocating authority | Set contract change procedures, acceptance standards, and approval limits |
| Operational decision-making authority | Decide how specific objects or matters are arranged or handled within the rules | Decide whether to accept a delivery adjustment or approve a contract change within the authorized scope |
| Execution authority | Perform concrete business activities within the authorized scope | Contact suppliers, record progress, initiate change requests, and carry out approved plans |
| Oversight authority | Examine and evaluate business processes and outcomes, and issue findings or take measures as authorized | Check compliance with change procedures, review performance evidence, and require corrective action |

Following a single contract delay makes these four kinds of authority easier to understand.

A supplier reports that it cannot deliver on time. The person following up verifies the situation, records the facts, and analyzes the impact: these are execution activities. An actor with the relevant operational decision-making authority decides whether to accept a revised delivery arrangement. That decision must follow the existing change procedure. Who may change the procedure or adjust approval limits is a governance question. Subsequent checks on whether the change followed the rules and whether the evidence is complete involve oversight.

The distinction comes from the meaning of the business action. Changing a rule, deciding on an exception, and recording a fact may all happen through an “Edit” button. Neither the button’s label nor the database update reveals the difference in authority.

The same applies to “Create.” Adding a contract performance record documents a business fact; establishing and publishing a new rule changes the constraints on subsequent work. Creating an object instance and defining an applicable rule should not be treated as the same kind of authority simply because both produce a new record.

These four kinds of authority help unpack the broad term “management” into things that can be authorized separately. In practice, we still need to name the actual business permissions, such as authority to decide contract changes or to follow up contract performance. One actor may hold several kinds of authority, while matters that require separation can be assigned to different actors.

Responsibilities correspond to these forms of authority. The person following up is responsible for timely information, accurate records, and exception reporting; the decision-maker bears responsibility for the decision; the overseer is responsible for the agreed oversight work. The organization must also clarify who is accountable for overall contract performance. We cannot assign all responsibility to whoever clicked the final button.

## 2｜From departmental responsibility statements and job descriptions to system configuration: Where the gap emerges

A job description containing a structure of authority and responsibility does not mean that structure is sufficiently explicit. The example above mentions “designated categories” and “authorized financial limits,” but other arrangements must specify which objects are covered and how the limits apply. Real descriptions are often broader: “responsible for procurement management” may cover many kinds of work.

First is the scope of objects. Production materials and equipment may be procured by different teams. Even procurement of production materials may be divided further by category or project. These boundaries may be maintained through everyday assignments and organizational conventions rather than written into job descriptions.

Second is the division of responsibilities for the same object. For one contract, procurement may track delivery while engineering handles acceptance. Both may be described as “responsible for contract performance,” without specifying what each can decide or who takes over when an exception occurs. Identical responsibility labels do not imply identical work or authority.

Boundaries left implicit in documents still require choices during configuration. Production materials and equipment procurement may use different forms, or follow different approval branches within the same workflow according to category. Delivery tracking and technical acceptance for one contract may be represented through separate tasks, action permissions, and notification rules.

This is why implementation usually requires interviews, workflow walkthroughs, and concrete cases to understand how work is allocated. Studying departmental responsibility statements and job descriptions alone rarely provides enough information to configure a system directly. These documents express the broad arrangement, but often lack the detail the system needs: which matters follow which branch, who may change which content, and who handles exceptions must be established during discovery.

Yet filling these gaps is already a form of defining the business model: which objects need to be distinguished, who is responsible for them, which actions require which authorization, and how those relationships enter the system. This is the work discussed in [Business Modeling is fundamentally about defining how a business is represented](https://rikkalab.com/en/digitalization/business-modeling/).

**Defining the business model is reduced here to configuration work within system implementation.** The delivery standard often becomes “make this system run,” while the definitions of objects, responsibilities, and rules remain implicit in forms and workflows, without independent confirmation, maintenance, or reuse. The organization’s understanding of how it operates ends up scattered across systems and implementation staff’s experience.

Business authority and responsibility enter systems in this way: roles and create, read, update, and delete permissions express part of them, while forms, data scopes, notifications, reviews, and approvals express other parts:

| Question about the business relationship | Expression in the system |
|---|---|
| Which contracts does the work cover? | Data scope, row-level permissions, owners, or assignment conditions |
| Which actions may be performed? | Feature permissions, action permissions, and the scope of content changes |
| Which events require awareness or a response? | Notifications, subscriptions, tasks, and escalation rules |
| Which matters require whose judgment? | Reviews, approvals, joint sign-offs, and workflow routing |

The same assignment—“responsible for service contract performance in East China”—must be expressed repeatedly in roles, contract scopes, notification recipients, and approval routes. Maintaining these separately can leave someone with a task but no permission, able to act but unable to receive exception alerts, or with approvals still routed to a former owner.

**The basic unit of role-based access control (RBAC) is a permission; the basic unit of the division of business responsibilities is a responsibility.**

## 3｜Responsibility for an object requires corresponding authority

To translate business authority and responsibility into a system, we first need to clarify which objects and outcomes an actor is responsible for, and which decisions and actions that responsibility permits. We can then determine which system permissions are needed. For the same maintenance work order, the dispatcher, technician, and quality overseer all need access, but their responsibilities and available actions differ.

| Authority | Responsibility involving maintenance work orders | Concrete expression in the system |
|---|---|---|
| Governance authority | Define work order categories, handling rules, state transitions, and authorization boundaries | Change workflow rules, state constraints, and dispatch policies; these may also be fixed in code without a business-facing configuration interface |
| Operational decision-making authority | Be responsible for assigning work orders and allocating resources within a defined scope | View dispatch dashboards, assign and reassign work, adjust priorities, and cancel or close orders according to the rules |
| Execution authority | Be responsible for assigned maintenance work and its records | Start maintenance, record diagnosis and work performed, register spare parts used, and submit results |
| Oversight authority | Examine and evaluate processes and outcomes within the agreed scope | Read work orders and process evidence, receive overdue or exception alerts, record findings, and require corrective action as authorized |

Dispatch determines who handles a work order and therefore exercises operational decision-making authority. A technician clicking “Start maintenance” or recording work is executing it. Both may amount to updating fields in the database, but they represent different business authority. Oversight requires read access and notification capabilities to discover problems promptly. These capabilities should follow oversight responsibilities, rather than depend only on participation in the handling workflow.

Governance authority is easier to overlook. Whoever decides which states a work order can have, when it may be closed, and which exceptions must be escalated is defining business operating rules. Those rules may be distributed across configuration, validation logic, and code, with no system permission called “governance authority.” Who confirms a rule from the business side and who changes its technical implementation also need to be clarified separately.

Operational decision-making authority often corresponds to management permissions in a system. Management dashboards and operations such as creating or deleting objects are frequently bundled into an “administrator” role. But each operation still needs to be distinguished by its business meaning. Canceling a maintenance assignment handles a business matter; deleting a duplicate work order maintains system records; creating a work order may support different responsibilities.

## 4｜How permissions arise and change with responsibility relationships

Consider creating a maintenance work order. Both an equipment user reporting an abnormality and an engineer reporting a problem found during an inspection need to create one. The first permission comes from the user’s responsibility to report abnormalities during equipment use and requires an accurate description of the symptoms. The second comes from the engineer’s responsibility to identify and address inspection findings and requires a record of findings and professional judgment. The operation is the same, but its responsibility basis, required information, and subsequent obligations may differ. **Permission to perform the same business action can arise from different responsibilities.**

Who can confirm that equipment is ready for use after maintenance can also be determined from responsibility assignments. Here, the business action is to confirm whether the equipment is ready for use again. It follows the responsibility for using that equipment and need not always be performed by the original reporter. After a shift handover, the incoming user who has taken over responsibility for using the equipment and the corresponding permissions can confirm readiness for use based on maintenance records and actual use.

**Permission to create records often also implies responsibility for the consistency of system data.** Creating a record requires judging whether the object already exists, whether a new record is appropriate, which equipment it should reference, and whether it conflicts with existing work orders. Allowing data to be written provides an operation entry point; someone must still be explicitly responsible for keeping those records consistent with the real business.

Traditional enterprises often assign responsibility for “who performs maintenance” without equally clear responsibility for “who maintains an accurate representation of maintenance work in the system.” This work can fall to data entry staff, implementation staff, or IT as an incidental duty. Create, edit, and delete permissions may therefore be assigned while responsibility for data consistency remains unassigned.

[Before designing an agent, understand where tasks come from](https://rikkalab.com/en/digitalization/where-tasks-come-from-agent-boundaries/) discusses how responsibilities give rise to concrete tasks. Permissions need to follow the same relationships: responsibility for which objects entails which authority, and ultimately which operations, data scopes, and notifications. People and agents both need this correspondence.

## 5｜A digital twin of responsibilities is a future worth working toward

Ideally, the division of responsibilities expressed in departmental responsibility statements, job descriptions, and authorization policies should have a traceable correspondence with system permissions, notifications, and workflows. **A digital twin of responsibilities gives “who is responsible for which objects, and on what basis they exercise which authority” an inspectable, updatable representation in the system.**

This requires at least two tests. The first is **traceability in both directions**: from a responsibility, we should be able to find the corresponding action permissions, data scopes, notifications, and approvals; from a configuration, we should be able to return to the responsibility it supports and the basis for its authorization. The first direction helps identify missing support for fulfilling responsibilities; the second helps identify permissions or configurations that have lost their business justification.

The second is **continued consistency after change**: when a handover, role change, or adjustment of responsibility scope occurs, can the relevant permissions, notification recipients, and approvers be updated together according to the rules, while preserving history? The shift handover example provides a concrete test: can the incoming user obtain permission to confirm readiness for use, and are the outgoing user’s previous permissions handled correctly under validity periods and retention rules?

This ideal remains far from how enterprises currently operate.

For management, the division of responsibilities written into policies may have drifted away from what systems actually permit, yet that drift is difficult to see in an organization chart or permission table. Implementation documents, configuration records, and people’s experience connect the two, but there is no shared structure for checking their correspondence over time.

Every change in personnel or the division of responsibilities requires checking configurations across multiple systems. As conditions and exceptions accumulate, they create the maintenance problem discussed in [Why system implementation turns into configuration hell](https://rikkalab.com/en/digitalization/system-implementation-configuration-hell/).

Mapping these configurations consistently to responsibilities involves much more than organizing permissions. Checking existing jobs and the division of departmental responsibilities against objects and work reveals overlaps and gaps in the organization itself. Several roles may all say “responsible for contract management” without distinguishing their parts. Everyone may finish their own step while no one takes responsibility for exceptions. Someone may be accountable for outcomes without the decision authority needed to influence them. Some overlap is necessary collaboration, and some gaps may be filled through informal arrangements; both still need to be examined against the actual business.

The gap therefore exists among the division of responsibilities, departmental responsibility statements and job descriptions, and system implementation. Making it explicit helps reveal problems, but also requires business managers to confirm and coordinate the arrangements. Implementation or IT teams cannot resolve it through configuration changes alone.

In practice, immediately rebuilding everything around this ideal structure may be inappropriate. We can first use it as an analytical approach: take one class of objects or one responsibility, check how the existing division of responsibilities corresponds to permissions, notifications, and approvals, and prioritize mismatches already obstructing work. Broader clarification of responsibilities and coordination across systems can proceed as organizational conditions and actual benefits allow.

This echoes the argument in [Why enterprise AI must start with the business: Business → organization → systems → agents](https://rikkalab.com/en/digitalization/enterprise-ai-starts-with-business/). We can begin with a limited scope, but cannot skip the business definitions, the division of responsibilities, and supporting systems within that scope. For authority and responsibility, this means clarifying which objects a piece of work involves, who is responsible, and who may decide what, then checking whether system permissions correspond. There is no need to wait for an enterprise-wide restructuring, but adding a set of permission configurations cannot answer these questions for the organization.

**Agents have no job descriptions today. They will need executable ones.** For a procurement agent, this means specifying which responsibilities it assumes for which objects, what it may decide, and when it should hand work over to whom. Multiple collaborating agents also need the same relationships to allocate work, pass information, hand over responsibilities, and establish accountability for outcomes. **A traceable correspondence between the responsibilities, authority, and system permissions of people and agents—one that can be updated as the division of responsibilities changes—is the infrastructure needed for agent permission design and multi-agent collaboration.**
