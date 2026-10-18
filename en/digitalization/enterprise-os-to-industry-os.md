In [Software boundaries are not business boundaries: Why an Enterprise OS is needed](https://rikkalab.com/en/digitalization/software-boundaries-enterprise-os/), I discuss how to organize systems around the business as a whole. Continuing this work raises two questions: How much of one enterprise’s model of its operations can other companies in the same industry reuse? And can work continue across company boundaries without losing its context?

The first concerns the cost of building these systems; the second concerns industry collaboration. The extension from Enterprise OS to Industry OS, a shared digital environment across the industry value chain, emerges where these two directions meet.

## 1. Industry software has always sought reuse; the difficulty is separating the sources of variation

Whether software is deployed on premises or delivered as SaaS, capturing industry models and reducing repeated implementation have long been goals. The difficulty is that “customer requirements” collected during projects often combine needs with very different origins.

Consider the checks required before accepting delivered equipment. A customer may ask for product documentation to be uploaded, the medical equipment department to verify it, an additional approval above a spending threshold, and a summary to be sent to the hospital director.

Some requirements come from industry regulations, others from staffing and departmental arrangements, internal management policies, or simply how a particular manager wants information presented. In a requirements list, they can all become fields, workflow steps, and notification settings.

When these sources are not separated, a common response is to leave the choices to customers: fields, workflows, permissions, and notifications can all be customized. Tools become more flexible, yet each enterprise must still decide how to put them together. [Why has system implementation become configuration hell?](https://rikkalab.com/en/digitalization/system-implementation-configuration-hell/) explores this problem.

**Configuration options provide a way to accommodate differences, but we still need to understand where those differences come from before configuring anything.**

For example, “the medical equipment department verifies the documents” can be separated further. Document verification is a business function the enterprise needs; the medical equipment department is the assignee this hospital has chosen. At another hospital without a separate medical equipment department, the assignment must change, while the verification requirements themselves may remain the same.

Once these layers are separated, the next enterprise can start from an existing model and identify its own differences. Modeling still has a cost, but reusable parts can become accumulated industry knowledge rather than work every project must repeat.

## 2. One industry rule becomes different requirements in different enterprises

Medical device registration certificates provide a concrete example.

In China, medical devices are subject to registration or filing requirements, and procurement also involves checking supplier qualifications and product conformity documentation and keeping records of those checks. The following example concerns products that require registration.

When a hospital purchases a device, it needs to verify the product's registration information and its correspondence with the model actually delivered. This becomes part of the checks required before accepting delivered equipment, expressed as documentation checklists and document verification records.

The supplier sees another set of tasks arising from the same matter: find the registration certificate and related documents for the product, organize them according to the hospital's requirements, and submit them. Selling the product to another hospital requires preparing the materials again.

A later audit of the purchase may also require the qualification documents and document verification records used at the time. The hospital then searches its procurement system, attachment folders, or paper archives for the evidence.

Collecting requirements separately from these parties produces features such as acceptance documentation checklist management, supplier documentation management, and audit document retrieval. Yet some of them share a source: the same industry requirement unfolds into work performed by different actors.

The model therefore needs more than “a registration certificate attachment.” It must identify which product the certificate concerns, which models it covers, and which documents this delivery and document verification reference.

One certificate can cover several models, and many individual devices may share the same model. If each device merely has its own uploaded file copy, it becomes difficult to determine whether they reference the same evidence or to identify model mismatches and missing documentation.

**These object relationships and applicable rules already have elements shared across the industry.** They can be maintained jointly, with each enterprise adding its own requirements for accepting deliveries. What a particular hospital received in a particular purchase, and who verified it, belong to specific business records.

## 3. Shared definitions connect work across the value chain

Suppose a supplier sells the same equipment model to three hospitals. Each hospital uses its own procurement or asset system. The supplier must enter the product name, model, and registration certificate number in three different spreadsheet formats and upload the same product documentation repeatedly.

If both sides use product definitions that can be matched, the supplier can maintain one set of product information, reference it across transactions, and fill any gaps required by each hospital. On receipt, the hospital links the documents to its own purchase and delivery records and performs its own document verification.

The reusable part is the product documentation and the links between products, models, and certificates. Each hospital still needs its own document verification results and must retain the version of the materials used at the time. Later supplier updates must not overwrite the evidence used for past acceptance.

When an audit examines a device, its purchase record can lead back to the documents submitted and the document verification results recorded at the time. Work previously scattered across systems gains business relationships that connect it.

This is also what Industry OS means: reusable industry models become part of actual business across enterprises, providing a foundation for participants to work together.

It reduces two kinds of repetition. Companies in similar roles need not redefine the same industry requirements, and upstream and downstream participants need not identify from scratch what the other party is providing in every transaction. Actual collaboration and authorization determine what is shared. For example, a supplier provides the materials needed for a delivery while the hospital retains its internal approval records.

With AI, it becomes even more important to build this shared foundation across the industry.

A supplier's agent prepares registration documents, a hospital's agent checks the documentation required for acceptance, and an audit assistant examines the basis for procurement. If each independently reads regulations, interprets requirements, and identifies products, they repeat part of the same work and may reach inconsistent interpretations.

Jointly maintained industry rules and product definitions let these agents perform their respective tasks on an established basis. If a hospital's agent finds that a delivered model lacks supporting documents, it can specify what is missing. The supplier's agent can use the same product identifier to find the documents and submit them so the existing document verification can continue.

The more participants there are, the more worthwhile this shared foundation becomes. A new agent can inherit existing business definitions and then receive the authorization needed for its tasks.

## 4. Different organizational structures do not require defining functions from scratch

A common objection to industry reuse is that every enterprise has different departments, staffing levels, and management practices. How could they use a shared model?

We first need to consider what function the enterprise performs in the industry's value chain.

Equipment manufacturers produce products, distributors provide supply and transaction services, and hospitals purchase equipment for diagnosis and treatment. They need different models. Even within the same industry, we should distinguish their roles in the value chain and operating models before discussing what can be reused.

For enterprises in similar positions, however, organizational differences do not imply entirely different business functions.

At one equipment supplier, sales staff may also follow up on delivery; another may have a dedicated delivery department. Both need to confirm customer requirements and deliver the agreed equipment and documentation. As staffing grows, work previously combined in one person's role can be divided among positions, while delivery responsibilities still need to be covered in full.

The same applies to hospitals. Equipment management staff may verify documentation, or procurement and technical staff may share the work. Shared industry rules can define what must be checked; the hospital's own conditions determine who verifies it and who handles exceptions.

[Before designing an agent, understand where tasks come from](https://rikkalab.com/en/digitalization/where-tasks-come-from-agent-boundaries/) traces tasks to an organization's functions in a value network. [Before discussing where to use agents, rethink business functions and the division of work in organizations](https://rikkalab.com/en/digitalization/enterprise-agent-functional-division/) further distinguishes function definitions from responsibility assignments. These two layers also provide a basis for reusing industry models.

**First establish which functions are needed within the industry's division of work, then decide how to assign them in light of enterprise resources and management choices.**

Objective conditions and management preferences can also be expressed separately. Limited staffing may require one person to hold several responsibilities. A manager's wish to confirm certain matters personally is an internal authorization arrangement. Both affect how work is organized, but neither necessarily requires redefining basic objects such as products, transactions, or acceptance.

In the future, AI may perform some document checks while people continue to judge exceptions. How the function is assigned changes; the shared model can remain in use.

## 5. AI will reshape the division of work; the digital environment must support that change

Agent design today often puts industry rules, company policies, and personal preferences together in a harness, memory, or prompts. The instructions for an assistant that helps verify deliveries before acceptance may simultaneously say “check product registration information,” “refer purchases above a threshold to the responsible manager,” and “show exceptions first in the summary.”

These three instructions come from industry regulations, the company’s approval and authorization rules, and the user’s preferences, respectively. Their scopes, maintainers, and rates of change differ. If all are packaged inside one assistant, a different hospital, a new manager, or even another assistant may require fresh interpretation and adjustment.

The earlier method of separating industry commonalities from enterprise differences also applies to agents. Shared rules provide industry requirements. Company policies define who is responsible and who is authorized to act. Personal preferences shape specific interactions. Agents receive the basis needed for their work and can distinguish what they may handle themselves from what must go to other actors.

The value of separating these layers extends beyond designing today's agents.

As AI capabilities change, the division of work may change as well. Suppliers may automatically check documentation completeness before delivery, while hospital staff focus more on exceptions. Specialist providers may perform preliminary document reviews for several institutions. Work once requiring an internal position may become an external service, and a function may be divided differently among collaborating actors.

If business logic is fixed to today's departmental, company, or agent boundaries, every change in the division of work requires restructuring systems, moving data, and explaining context again. An industry perspective lets us first understand why the work exists, what it depends on, and what result it needs to produce, then decide who should undertake it.

**Company boundaries and agent boundaries reflect how work is divided across an industry at a given point in time.**

This also means Industry OS models must be able to evolve. When an industry requirement changes, the affected work can be identified. When AI can undertake new functions, assignments can be revised. When a step is no longer necessary, there is a basis for removing it. Confirmed product facts and business records can remain available for subsequent work.

Industry OS can therefore begin with a very small business scope, but its design should encompass the industry relationships in which that work sits. As the division of work among people, AI, and enterprises continues to change, the digital environment must let later work build on existing results and allow new forms of collaboration to grow from them.

**The longer-term value of an Industry OS lies in enabling advances in capability to improve how work is divided across the industry, without existing software and organizational boundaries standing in the way.**
