## 1. How are the three architecture diagrams usually created?

Business architecture diagrams commonly show areas such as marketing, sales, procurement, production, and delivery, then break down their business capabilities. Product architecture diagrams turn these into modules such as customer and order hubs, procurement management, and production management. Technical architecture diagrams show applications, services, databases, messaging, caches, and infrastructure.

Different teams often create these diagrams separately. Business teams start with operations and the division of work; product teams organize functionality; technical teams organize implementation and deployment. Each approach makes sense, but when the diagrams are placed together, how can we establish that they describe the same business?

A rough mapping assigns “procurement” to a “procurement management module,” implemented by a “procurement service.” The names resemble one another and the boxes connect, so the three diagrams appear aligned.

But what does the procurement box actually contain? Calculating procurement requirements, requesting and comparing quotes, placing orders, following up on deliveries, or managing suppliers? What do systems perform, and what still depends on people? How much do the product modules and technical services cover? Lines between a few boxes cannot readily answer these questions.

**Apparent correspondence between the diagrams does not establish that product capabilities support the business requirements, much less that the technical implementation ensures those requirements are met.**

The previous article, [“Product requirements define the gap between the business and its digital twin”](https://rikkalab.com/en/digitalization/product-requirements-business-digital-twin-gap/), discussed how to identify gaps. This article takes the next step: what connections should business, product, and technical teams establish to build and maintain the digital twin together?

## 2. In principle, derivations can follow the mappings across the three diagrams

Business architecture describes how the business operates. Product architecture organizes the digital capabilities that support it. Technical architecture explains how those capabilities are implemented. Following this relationship, the three diagrams should connect: what the business needs, which product capabilities support it, and which technical components implement them.

**My proposal is to model the three diagrams as a whole, explicitly mapping business requirements, product capabilities, and technical implementation.**

This does not require identical structures. Several product modules may jointly support one business activity, while a shared service may support several product capabilities. The specific connections need to be retained, rather than linking large boxes by name.

For example, “delivery management” includes shipment, receipt, installation, and acceptance, each with its own completion conditions and responsibilities. Product design must organize the corresponding records, judgments, and coordination capabilities. The technical implementation must support their underlying data and execution logic. Starting from a business completion condition, we should be able to locate the corresponding product behavior and then its implementation.

| Business requirement | Product capability | Technical implementation |
| --- | --- | --- |
| Obtain customer acceptance confirmation for the scope of this delivery | Record the acceptance scope, results, and supporting evidence | Associate acceptance records with delivery objects and retain confirmation information |
| Mark delivery complete only after the agreed conditions are met | Determine delivery status and prevent completion when conditions are unmet | Execute state rules and check conditions at the operation entry point |
| Continue handling items that fail acceptance | Generate tasks and show responsible people and progress | Store task relationships and support notifications and state updates |

“Derivation” here means following explicit definitions and mappings to derive the capabilities needed, identify what is missing, and trace where changes may have effects. Specific solutions still require choices informed by costs and constraints.

These mappings provide a basis for discussing whether business needs are covered, where requirements should address gaps, and which systems a change will affect.

## 3. The digital twin can also reveal gaps in the business

The mappings can be examined in reverse. Problems exposed during system operations sometimes point to parts of the business architecture that remain undefined.

A typical example is implementing a system with people assigned to build its functionality, but no clear division of responsibility for defining standards and maintaining data. Who defines material codes, merges duplicate material records, confirms specification changes, and maintains discontinued status? This work may temporarily fall to procurement, engineering, or IT as an additional duty alongside their regular work.

A concentrated cleanup at launch can produce a relatively clean dataset. But subsequent additions and changes, without ongoing ownership, gradually accumulate duplicate codes, inconsistent specifications, and outdated states. Users find it increasingly difficult to locate trustworthy information, eventually describing the problem as “the system is hard to use” or “the data is dirty.”

Tracing backwards through the three architecture diagrams may reveal that product functionality exists and the technical implementation works, while the business responsibilities needed to sustain those capabilities have never been established. The missing pieces are authority to define standards, responsibility for maintaining data, and resources and mechanisms for performing this work continuously.

**Building and operating a digital twin also tests the completeness of the business architecture.** It exposes work previously sustained through tacit understanding and temporary cover, prompting the organization to clarify who undertakes it.

## 4. A business change should be traceable through all three diagrams

Consider delivery management again. Suppose a company begins allowing delivery and acceptance in batches. A project previously had one acceptance event; it may now have three batches, respectively in transit, being installed, and accepted.

The business must first define the acceptance scope of each batch, how completion of the entire order is determined, and who continues handling the parts that fail acceptance.

Product capabilities must change accordingly. One “acceptance complete” option is no longer sufficient. Results need to be recorded by delivery batch, remaining work summarized at project level, and relevant people given a way to find their own outstanding work.

The technical implementation also needs review: can the project's single acceptance field still represent the facts, or are independent batch acceptance records needed? How should existing interfaces, state calculations, and historical data adapt?

If these connections are retained, a change in acceptance rules can be traced to affected capabilities and implementations, followed by checks on downstream notifications, reports, and other functions. Impact analysis gains a shared basis rather than depending entirely on one person's memory.

Technical constraints also influence the solution in reverse. If a logistics system currently provides arrival status only by order, without batch detail, the three parties must jointly decide whether to collect additional information, use manual confirmation, or develop in stages, while making any temporarily remaining gap explicit.

**Business, product, and technical teams need to determine solutions together through these exchanges.** Mappings ground discussion in specific effects and trade-offs.

## 5. AI makes these connections more feasible to maintain continuously

Maintaining these connections used to be costly. Business rules live in documents, product designs in product requirements documents (PRDs) and prototypes, and technical implementations in code. Technical architecture and implementation plans are now also being placed in harnesses. These materials already exist, but different teams own them, and every change requires someone to search and reconcile information across them.

AI can help extract definitions, establish relationships, identify inconsistencies, and analyze potentially affected areas during changes. But this requires reliable foundations: explicit identifiers for objects and rules, clearly written state conditions, and retained relationships between designs and implementations, reducing repeated guesswork.

In principle, an HTML artifact could organize this content: prose explains the context, tables define rules, diagrams show relationships, and mappings between business requirements, product capabilities, and technical implementations remain available. Large language models reduce the cost of generating and updating such artifacts, making continuous maintenance more feasible.

A further direction worth exploring is using some of these definitions directly as validation criteria. Could “a project without acceptance confirmation must not be shown as delivery complete” be linked to interface behavior and test results? After a business rule changes, could the system indicate which implementations and tests need updating?

This remains a direction to validate progressively. Architecture documentation could then guide development and operations on an ongoing basis, rather than being consulted only during design presentations.

## 6. Go two steps upstream from coding tools and development processes

Connecting the three diagrams also requires explicit organizational responsibilities. Business owners define goals and operating rules; product teams organize digital capabilities; technical teams provide implementation options and report constraints. Together, they determine the scope of development and check whether the business operates as intended after launch. Different roles may undertake this work, or one person may combine them, but none of it can be absent from the collaboration.

The same question can be used to examine where AI improvements are directed.

From model training to agents, harnesses, and development tools, if improvements all begin with predefined development tasks and focus on writing code, calling tools, and completing tasks, then the questions “why do these tasks exist?” and “what business should the software actually support?” remain outside the discussion.

Going two steps upstream along the three architecture diagrams returns us to product capabilities and business operations. A difficult-to-implement feature may arise from an unclear business definition. A complex automated workflow may become much simpler after the work is reorganized. AI participating at these two levels could change the software that needs to be built and its complexity.

This points to a broader question in system design: complexity is not necessarily conserved. Changing the structure of upstream business may reduce complexity across the system as a whole. See [“Complexity doesn’t disappear—it only shifts. Or does it?”](https://rikkalab.com/en/digitalization/complexity-does-not-disappear/).

[Before optimizing a task, ask why it exists.](https://rikkalab.com/en/digitalization/what-it-means-for-ai-to-complete-tasks/)
