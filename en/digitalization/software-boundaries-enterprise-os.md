An enterprise needs to run its business from customer demand through delivery and payment collection. When building digital systems, however, it faces products with their own boundaries: enterprise resource planning (ERP), customer relationship management (CRM), office automation (OA), product lifecycle management (PLM), and manufacturing execution systems (MES), as well as platforms such as Feishu and DingTalk.

When a customer changes delivery requirements, sales needs to confirm commitments, engineering must review the design, and procurement and production may need adjustments. The relevant systems are already in place, yet the work still frequently returns to group chats and Excel.

Enterprises start from very different positions. At many internet companies, core operations run directly in software. Business objects and execution rules are already represented relatively fully in systems, with internal teams maintaining them. Even without explicitly using the term “ontology,” much of the modeling may already be well developed, giving AI clearer data and action interfaces.

Many businesses that were not born digital lack these conditions. Their operations began offline, with software introduced at different stages by departments and projects. Much of the overall business logic remains in spreadsheets and people's experience, and no one may be continuously coordinating business modeling and system development.

This article focuses on the latter group: enterprises with plenty of software serving individual areas, but still relying on people to connect the business as a whole.

## 1. Software keeps expanding, while enterprises are left to resolve the boundaries

ERP, CRM, and similar systems start in particular management domains and gradually expand into adjacent areas. Platforms such as Feishu and DingTalk start from instant messaging (IM) and collaboration, supporting more individual business activities through approvals, tables, low-code tools, and applications.

Products therefore leave both gaps and overlaps. For the enterprise buying them, the immediate question is: where should this work actually happen?

For example, sales maintains a contract in CRM, OA holds its approval record, and the corresponding order is entered in ERP. To track delivery, planners maintain a separate spreadsheet that sales checks every day before updating the customer.

When the customer changes the delivery date, should sales update CRM first or initiate an approval? Can the planning spreadsheet be changed directly? Who updates the ERP date? If the dates disagree, which one should production follow?

Every product can offer an “edit date” function. What the enterprise needs to establish is where the customer's request, the internal feasibility assessment, and the parties' formal confirmation each happen, and how they connect.

Software vendors can generally explain what their own products do. The enterprise buying the software must determine whether the business can operate from end to end when those products are combined.

**A software product's functional boundaries cannot simply be treated as the boundaries of the enterprise's business.** What remains poorly designed between the two becomes manual checking, information transfer, and coordination.

## 2. Integration was already supposed to solve these problems

This work did not first appear with AI. System integration was already meant to make individual products work together. Yet connecting interfaces may still leave the business disconnected.

Consider the delivery-date change again. Automatically synchronizing every CRM date change to ERP and the planning spreadsheet may seem to eliminate duplicate entry, but it can create a more serious problem: sales has only recorded the customer's request, while production plans are changed as though the arrangement were already confirmed.

The missing business definitions concern what “customer-requested delivery date” and “enterprise-confirmed delivery date” mean, who confirms them, and under what conditions downstream plans may change.

Effective integration must follow these definitions. Otherwise, an interface merely passes an ambiguous field along faster.

[The invisible gap in traditional enterprise digitalization: Who defines how business enters the digital world?](https://rikkalab.com/en/digitalization/business-modeling-defines-representation/) discusses this problem: people who know the business may not undertake modeling, while software teams often only implement requirements already proposed. Cross-system business definitions can therefore lack an owner.

If no one takes responsibility for this work, every additional system requires another round of mappings. Every business change means checking interfaces individually again. Integration costs accumulate as individual systems are built.

## 3. Enterprise OS: Organizing systems around the business as a whole

In [The end state of enterprise digitalization is a business digital twin](https://rikkalab.com/en/digitalization/business-digital-twin/), I discuss what the enterprise's digital world should represent and support. Building on that, I use Enterprise OS to describe the shared digital environment that supports the enterprise's ongoing operation.

It must first establish what makes a business event or commitment valid, then determine which parts each software product supports.

In the delivery-date example, the customer's new request first becomes a change awaiting assessment, linked to the original order. Planners assess feasibility against materials and capacity. If the technical design needs changing, the relevant responsible person confirms it. Only after the final commitment is confirmed are the official delivery date and affected plans updated.

CRM can continue recording customer communications, ERP can store orders, and production systems can organize execution. These products support different parts of the same business matter, with their relationships determined by business definitions.

This also provides a basis for examining software requirements. What is “adding a delivery-date approval” meant to resolve? Is the required judgment about capacity, technical feasibility, or a commercial commitment? Which judgments are already complete, and which still lack a responsible person? These questions need to be separated before deciding which pages and workflows are needed.

For how responsibilities can be tied to objects, see [Before discussing where to use agents, rethink business functions and the division of work in organizations](https://rikkalab.com/en/digitalization/enterprise-agent-functional-division/).

An Enterprise OS can begin with a limited business scope. Start by making delivery-date changes move correctly across existing systems, then expand. Each time a local problem is resolved, incorporate the new definitions into the shared business model so the next requirement does not become another isolated workflow.

## 4. Bridging natural language and business operations with LLMs requires new ways to interact

Traditional systems require people to understand how the software is organized, then translate reality into inputs it accepts. After a customer makes a remark, sales must find the order, identify the requested changes, fill in a form, and prepare explanations for other departments.

LLMs have an opportunity to perform some of this translation, connecting natural language with structured business information. Using that capability also requires redesigning interaction.

Suppose a customer sends this message:

“Could the ten cabinets for Project A in this batch be brought forward to next Friday? Keep the rest on the original schedule.”

The business assistant needs to use the customer and orders associated with the current conversation to identify possible delivery items. If two orders could match, it should ask sales to confirm before changing any date.

Once the objects are identified, the system can present a draft change:

| Item | Current arrangement | Customer's new request |
| ---- | ---- | ---- |
| Delivery scope | Twenty units in the original batch | The ten units for Project A |
| Delivery date | Previously confirmed date | Next Friday |
| Remaining units | Delivery under the original plan | Keep the original plan |
| Current status | Confirmed plan | New request awaiting assessment |

After sales confirms that the system has understood correctly, the draft enters delivery-date assessment. The customer's original words are retained, so later participants can see how they were interpreted.

The change here is that people can express business intent first, while the system reveals the structure that needs confirmation. It asks follow-up questions when information is missing, presents the changes in a table when several items are involved, and opens the relevant drawing version when needed. The interaction adapts to the work at hand.

In the other direction, the system can turn business structure back into an explanation suitable for people. If assessment finds that two of the ten units lack components, it can identify those units, the missing materials, and their expected arrival dates, showing sales exactly what is preventing the customer's request from being met.

What needs redesigning is the entire interaction: how people turn everyday language into business actions, and how the system communicates the results back to them. LLM-generated content must be grounded in explicit objects before it can provide a basis for subsequent work.

## 5. IM deeply integrated with business will become a core part of the infrastructure

Delivery-date assessment is rarely completed by one person. Sales contacts planning, planning asks procurement, and engineers may need to confirm alternatives. Many critical facts and decisions emerge in these exchanges.

This makes IM an important entry point for everyday conversation to become part of formal business operations.

Return to the ten cabinets. Procurement replies in a group chat: “The supplier says the missing components can arrive on Thursday.” If the system only retains the message, planners still need to identify which materials it concerns and update the spreadsheet manually. When someone asks about delivery risk days later, they must search the chat history again.

With deeper integration, the reply can be linked to the relevant procurement item and become arrival information awaiting confirmation. It must retain the meaning “the supplier promises arrival on Thursday,” rather than being treated as confirmation of receipt.

Planners viewing that information can also see the ten affected cabinets and the production time still needed after the components arrive. If Thursday is too late, participants can continue discussing alternatives around the same delivery-date change. Once an approach is confirmed, the corresponding tasks and plans are updated.

When the components actually arrive, the warehouse's receipt record feeds back into the same business context. Participants need not ask everyone individually how far the work has progressed or reconstruct conclusions from the entire conversation.

This requires messages to reference business objects, suggestions in discussions to become items awaiting confirmation, and formal decisions to trigger execution. IM therefore needs to be designed together with LLMs and business systems.

Expanding from IM into business operations has clear value. But if commitments in group chats, plans in spreadsheet-like database tools, and ERP orders are updated independently, people still do the connecting—even when everything is accessed through the same platform.

## 6. Why implementation can still fall short after introducing an ontology

What matters is whether the business has been clearly modeled and whether the model extends through actual operations. An ontology provides an explicit, computable way to organize it. Good business models already established in existing systems also provide foundations AI can use.

[Palantir](https://www.palantir.com/docs/foundry/platform-overview/overview/) provides a practical reference: it organizes data, logic, and actions around its Ontology, connecting capabilities distributed across systems to business decisions and execution.

Yet implementation can still break in two places after introducing an ontology.

The first is between the model and system implementation. The model distinguishes “customer-requested delivery date” from “confirmed delivery date,” but the page still has only one “delivery date” field, and interfaces continue synchronizing it to every system. New definitions exist only in the model, while actual operations follow the old logic.

The second is between the work handled by different AI assistants. A sales assistant understands the request and produces an explanation that ten units need earlier delivery. Sales copies it to a production assistant, which recommends checking materials, then copies that to a procurement assistant to obtain the supplier's expected delivery date. Finally, sales still has to assemble the answers into a spreadsheet, seek confirmation, and update each system.

Each assistant has completed its own exchange, but they have not jointly advanced the delivery-date change. Even with an ontology underneath, the work has not actually been organized around it.

To avoid these breaks, the business model must become part of system development and operation. State distinctions in the model must be preserved in pages and interfaces. Work spanning systems needs a business object that can be referenced throughout, recording results already established and work still outstanding.

[From business to code: Reasoning across three architecture models](https://rikkalab.com/en/digitalization/business-product-technical-architecture/) explores this correspondence further: when a business definition changes, it should be possible to identify the affected parts of the system, and completed functionality should be checked for whether it correctly supports the business.

An Enterprise OS takes shape through this continuing work. As these models capture patterns shared across an industry and extend along real collaboration among customers, suppliers, and other participants in the value chain, they provide a foundation for further development into an Industry OS.
