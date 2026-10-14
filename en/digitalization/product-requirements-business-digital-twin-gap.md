## 1. What is inside a requirements list?

“Add a procurement workflow for me.” It sounds as though creating a form and assigning approvers would be enough. But asking where purchase requests come from may reveal that procurement staff in manufacturing aggregate material shortages across projects every day, compare them with inventory and outstanding orders, and manually calculate how much to buy. For fixed assets, the questions become whether a purchase is warranted and whether there is a budget—entirely different business problems.

An approval workflow determines who approves, but does not necessarily establish why to buy, what to buy, or how much. If people still need to reconcile these manually, the new workflow may simply give procurement staff another form to fill in.

The previous article, [“With so many systems in place, why does the business still rely on group chats and shared Excel spreadsheets?”](https://rikkalab.com/en/digitalization/why-business-still-relies-on-chat-and-excel/), discussed how people fill in work that systems do not support. This article asks a further question: **when we ask systems to implement requirements, what problem are we actually solving?**

I call the collection of digital systems that supports an enterprise's business operations its digital twin. From this perspective, product requirements define the gap between the capabilities the business needs and what its existing digital twin supports. Procurement workflows, reports, usability improvements, and agent requirements can all be examined this way.

## 2. Requirements analysis must distinguish the requested form from the underlying gap

In the age of agents, requests for “a faster horse” deserve closer examination: what underlying need does the proposed solution express?

### Business changes and their effects are not supported by systems

“Add a contract amendment feature.” A contract's presence in a system does not mean the system can handle changes to it correctly.

Changes to quantities, configurations, or delivery dates affect orders, procurement, production, and subsequent settlement. If the system only allows original fields to be edited, or requires another new-contract workflow, people must explain outside the system what changed, when it takes effect, what needs redoing, and which version governs subsequent work.

The form is only an entry point. Behind it, the system needs records before and after the change, its scope, related objects, and follow-up actions. Otherwise, the new feature still leaves explanation and coordination to people.

### Several layers separate business records from usable judgments

“Create a customer renewal risk report.” Account managers want to know which customers to follow up with first, so they request a report.

Someone may already produce it manually: finding expiry dates in contracts, checking complaints in the service system, asking about recent customer usage, and finally assigning red, amber, or green ratings from experience.

Breaking this down reveals different gaps. Customers may lack stable relationships with contracts and service records. The definition of “high risk” may be unclear. Or the data and calculations may already exist, with only a view organized around each account manager's responsibilities missing.

Only by identifying the actual gap can we decide whether to supplement data, define metrics, add calculations, or change the presentation. Copying a manual spreadsheet into the system does not necessarily produce reliable results over time.

### Gaps in rules, responsibilities, and coordination call for clarifying business logic first

“Add another approval step.” A sales discount exceeds an authorized range and needs a responsible manager's approval. The underlying work is to judge a transaction outside the existing scope of authority and take the corresponding responsibility.

Some approvals, however, merely inform people or initiate the next stage of work. Although all appear as clicking “approve,” they may perform notification, handoff, condition verification, or an actual authorization decision.

We first need to establish why this work exists and who is responsible, then determine what needs system support. Unclear responsibilities or authority need to be addressed in business management. If rules are explicit but easy to overlook in execution, system validation, reminders, or workflows may be needed.

The relevant business owners need to define how the work is organized; product requirements primarily define the parts that digital systems need to support.

### The functionality exists; an integrated working view is missing

“Can this operation be simpler?” Procurement staff need to compare suppliers' prices, delivery dates, and fulfillment history. The information is in the system, but scattered across modules. A comparison requires opening several layers of pages and copying the results into Excel.

Data or algorithms may not be missing. The system has not organized information and actions around this work, leaving users to assemble them.

Putting the necessary information in a single working view, with direct comparison, selection, and purchase initiation, may solve the problem. Whether digital capabilities exist also depends on whether people can use them effectively where the work happens.

### An agent requirement may involve several capabilities that need to be developed together

“Let an agent automatically handle stockouts.” When a store runs out of stock, it can replenish, transfer goods from another store, adjust promotions, or accept a temporary shortage. Inventory, transport times, costs, and business goals constrain the options.

If inventory is inaccurate, goods in transit are invisible, or reservation relationships are missing, facts and relationships need to be completed first. When the conditions for routine replenishment are clear, rules or forecasting models can determine when and how much to replenish. Tight supply and several stores competing for the same goods introduce further comparison of options and resource trade-offs.

Agents can help gather information, generate options, explain effects, and execute operations. The work they take on needs to follow from the gaps identified and the capabilities already available.

## 3. Define the gap, then define how far this project will close it

Identifying a gap requires examining both business goals and the current systems.

Business goals determine which capabilities are worth developing. Customer renewal management, for example, needs to help account managers identify risks and act promptly, but may not require structuring every detail of every conversation. The actual needs of the work should determine which facts to retain and which metrics to calculate.

Capability maturity needs to be checked along the task: does the necessary information exist, is it timely, and can it be connected? Are the grounds for judgment explicit? Can people act on a judgment, and can the results be recorded and used in subsequent work?

We also need to ask whether the business itself is insufficiently defined. “Delivery complete” may refer to different milestones across departments. The warehouse may treat “delivery complete” as meaning the goods have been dispatched; sales may use it to mean the customer has acknowledged receipt; the project owner may require installation, commissioning, and formal acceptance. Different responsibilities can lead people to use the same term for the end of their own stage. Sharing a single “completed” state may make downstream participants assume that subsequent work is also finished.

The relevant business owners must first distinguish shipment, receipt, installation, and acceptance, define the completion conditions for each, and determine which milestone fulfills the contractual delivery obligation. Only then can they decide how systems should represent and support them.

A requirements description therefore needs to explain at least:

- Who needs to complete which business task, and in what situation?
- What is missing today, and what extra work or business losses does it cause?
- How far will this project close the gap, and what will systems, people, and agents each undertake?
- How will we verify that the business can operate as intended?

**A product requirements document (PRD) defines which part of the gap this project will close, and under which resources, rules, and constraints.** Pages, fields, interfaces, and model capabilities should all be traceable to this definition.

Acceptance testing must therefore return to the business. Being able to submit a contract amendment only shows that the entry point works. Identifying affected orders, ensuring relevant people receive and complete the adjustments, and using the correct version in subsequent execution show whether the gap has actually been addressed.

## 4. Why do requirements keep appearing?

Some gaps come from previously uncovered business activities, some from inaccurate or difficult-to-use digital support, and others from changes to the business.

A new delivery method, reassigned responsibilities, or revised discount policies can expose new gaps in systems that previously supported the work. People begin using new spreadsheets, group chats, and informal agreements to keep operations going, and requirements follow.

Technological changes alter the feasibility of closing gaps. Extracting facts from large volumes of unstructured records may once have been too expensive. With large language models, some manual burdens previously accepted as unavoidable now have potential solutions worth trying.

Product requirements therefore need to be continually checked against the business and its systems. Priorities must consider the gap's impact, the cost of closing it, and dependencies on other capabilities. “A report” on a requirements list may first require a complete set of object relationships and metric definitions. A seemingly small usability change may improve work performed frequently every day.

## 5. What are product managers responsible for?

Gathering requirements, designing prototypes, writing PRDs, working with engineering, and conducting acceptance testing all serve a shared responsibility: **identifying the digital capabilities the business needs, defining how systems will support them, and verifying the effects together with business and technical teams.** Translating users' proposed approaches into features one by one makes it difficult to assess how much of the gap has been closed.

Today, some of what so-called agent engineers do when orchestrating steps, designing fields, distinguishing intents, and configuring nodes also involves defining business logic and building business models. Yet responsibility for this work is often ambiguous, and the business itself may not be clearly defined. Questions that require joint clarification then enter product design and technical implementation: **complexity left unresolved in the business is ultimately taken on by product and technical teams.**

This is also a problem with some AI product manager job descriptions. They list prompts, retrieval-augmented generation (RAG), and agents without clarifying the business problems the role must solve or how it divides work with business owners and engineers. Detailed tool requirements cannot fill a gap in responsibility definitions.

Organizations need to reconsider how these kinds of work connect. Business owners define goals and operating rules; product teams identify and organize digital capability requirements; technical teams assess implementation methods and costs. Together, they determine the scope of development. The next article will discuss how business architecture, product architecture, and technical architecture connect to provide a shared basis for this collaboration.
