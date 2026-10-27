Approval is one of the most common entry points for work in enterprise office automation (OA) systems. Leave requests, purchasing, project initiation, quotations, contracts, information changes—once these activities enter the system, many end up as a form and an approval workflow.

In the AI era, a natural request follows: **Could an agent help me fill out approval requests, follow up on them, or even handle some of them automatically?**

This looks like a straightforward efficiency problem. But before an agent can take over these workflows, a more fundamental question arises: **Are all the things that OA systems call “approvals” actually approvals?**

This is also a broader workflow problem. When business activities have long been represented through fixed workflows, we can easily mistake the system’s steps and their sequence for the business itself, forgetting to ask why those steps exist and what each one actually does.

## An approval workflow may compress different business actions into the same interface

Traditional OA systems are good at expressing business activities in a fixed structure:

**Fill out a form → A handles it → B handles it → C handles it → workflow ends.**

But real business is not organized around “forms” and “workflow steps.”

Consider a quotation request. It may look as though a salesperson enters the requirements, a manager approves them, and quotation work then begins. From the perspective of business objects, however, what actually happens is closer to this: a customer needs a quotation; the company develops a quotation proposal in response; the necessary judgments are made about its price, margin, delivery date, or special terms; and a quotation is finally issued to the customer.

The “quotation request form” merely puts these processes into a single form for the time being. The request and the quotation proposal are two different objects. Nor is an approval step an inherent part of the business; it is simply how the system presents some of the judgments involved—as “approve / reject.”

Other workflows are similar. When a project initiation request is approved, what actually happens is that a project is created. When an information change request is completed, the state or attributes of an existing object are changed. Some so-called approvals only require someone to be aware of something, with no decision for that person to make.

When systems fail to represent these business meanings explicitly, the easiest response is to put everything into the workflow engine: use an approval workflow to create an audit trail, notify someone, or create an object.

Eventually, actions with different business meanings look increasingly alike in the interface:

**Here is a form. It is your turn to handle it.**

Seen this way, an “approval workflow” is not an atomic business structure. It orchestrates different mechanisms—object changes, gathering missing information, judgment, responsibility handoffs, notifications, and audit trails—into a fixed path.

## OA tells you “it is your turn” without explaining what you need to do

This is one reason OA systems can feel awkward after prolonged use.

A system can tell someone precisely that they have 12 pending approvals, eight CC'd items, five notifications, and several overdue workflows. But these numbers do not directly answer a more important question in their working day: **What should I actually do now?**

The problem is not just the volume of messages. The workflow steps themselves have lost much of the business meaning.

“Quotation request awaiting approval” does not tell a manager whether they need to judge whether the margin is acceptable, whether the delivery date can be promised, or whether a special term requires additional authorization.

“Project initiation awaiting approval” can also compress very different kinds of work into a single step. One person must confirm that resources are sufficient, another is responsible for the budget, and someone else is merely being informed that the project has been established so they can prepare for subsequent work.

OA systems maintain comprehensive records, but what they show people is often **where the workflow has reached**, rather than **the current state of the business and why that person needs to intervene**.

This also explains why aggregating approvals, notifications, emails, and chat messages and then asking AI to choose “today’s three most important tasks” often still falls short. AI can infer urgency and priority from the text, but it must still guess which business object a step concerns, what has changed, what responsibility the person has, and what action actually needs to be completed.

The problem is not simply that information has not been aggregated. The existing digital systems have not clearly represented the work itself.

## Before optimizing the approval workflow, ask what has changed in the business objects

A redesign should start by asking **what is actually happening in the business**, rather than which steps an approval form must pass through.

Take quotations again.

When a customer requests a quotation, the system should first create an explicit quotation request containing facts such as the customer, product, quantity, delivery date, and special requirements. The salesperson or system can then develop one or more quotation proposals containing price, cost, margin, delivery date, and commercial terms.

Only a few issues may actually require human judgment: whether the margin falls below the authorized threshold, whether special payment terms are acceptable, or whether the delivery schedule carries risk. Decisions arise where a responsible person needs to weigh such trade-offs.

Once the quotation proposal is settled, it is confirmed, issued to the customer, and may subsequently become a contract or order.

What was once an entire “quotation approval workflow” has now been unpacked into **the creation and changes of business objects, with a few points that genuinely require judgment in between**.

Those judgments should not be compressed into a generic “quotation approval” either. Assessing whether the margin falls below the authorized threshold requires costs, the proposed price, target gross margin, and authorization rules. Assessing special payment terms concerns customer credit, payment policies, and financial risk. Assessing whether a delivery date can be promised depends on inventory, capacity, procurement lead times, and the current order load. These judgments concern the same quotation proposal, but their grounds and the actors responsible for them differ.

Whether humans or agents make these judgments in the future, the better design is to first make explicit what is being judged, what context is needed, what reasoning applies, and who is responsible. Only then should we decide which parts suit automation, which require assistance with judgment, and which must be confirmed by a human, rather than building a “quotation agent” expected to understand everything.

This is a very different product direction from having an agent automatically click approval buttons.

**The former understands and advances the business; the latter merely automates an existing interface.**

## A further step: From an approval center to a work hub

Once business activities are no longer compressed into approval workflows, another question naturally follows. If the system already knows which objects have changed, where judgment is needed, and which actions a person must complete, why should the home page still organize work around “approvals, notifications, and CC'd items”?

A system designed around work might instead explain what I need to complete now, why it is my responsibility, which business object it concerns, and what would be affected if I did not act.

At this point, a “task” begins to need its own definition as an object, rather than being an approval step, a notification badge, or a message with a deadline.

Looking beyond OA reveals a clear direction: **the future work hub should directly show what is happening in the business and who needs to take what action now, rather than merely bringing approvals and notifications together.**

As the actors doing the work expand from humans to agents, this question goes a step further. Fixed workflows could implicitly encode many preconditions, judgment rules, and responsibility boundaries in the sequence of steps. Once an agent no longer follows that path strictly, these constraints must be expressed separately.

Agents can have more freedom in choosing their paths, but business dependencies and governance boundaries do not disappear with that freedom. On the contrary, the less a system relies on fixed workflows, the more clearly it must state **which actions are allowed in which states, and which changes require additional checks**.

This question is explored further in [“Agents will not eliminate workflows; they will force us to rethink them”](https://rikkalab.com/en/digitalization/agents-workflows-executable-functions/): once fixed paths are dismantled, how should we express the business dependencies, checkpoints, and action boundaries previously hidden in workflows?
