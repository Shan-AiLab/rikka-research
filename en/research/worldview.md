How do we understand a complex world, collaborate with others, and continue to make decisions and act as conditions change?

**World, representation, Decision Space, and action form the foundational structure of this approach.** Atlas and DS address different parts of that structure, while enterprise digitalization and AI implementation are its concrete expression in organizational settings.

## I. The world in which we act has a complex structure

Whether we are dealing with personal life, enterprise operations, or collaboration across society, we encounter different actors, resources, relationships, rules, activities, and continuously changing states.

These elements are interdependent. A change in one object may alter the state of another; a change in a rule may affect many people’s choices; achieving one local goal may consume resources needed by other goals.

Every actor occupies a particular position, has its own goals, experience, and capabilities, and can access only part of the world. The same situation reveals different structures when observed from different positions.

An order, for example, represents a commitment to the customer, work to be completed for production, material requirements for procurement, and revenue, cost, and cash arrangements for finance. These perspectives point to the same business fact while each preserving what matters for action from its own position.

**Understanding complex reality requires identifying its objects, relationships, and changes, while also knowing from which perspective and at what resolution we are observing it.**

Some structures arise from natural conditions; others are established collectively by people. Organizational responsibilities, product definitions, transaction rules, and contractual commitments all need to be defined, interpreted, and maintained. We are not only understanding the world, but also helping shape it.

## II. To understand and collaborate, we form representations of the world

Things in reality need to enter our understanding and communication through some form.

A mental model, a spoken sentence, a sketch on paper, a description in a document, a record in a table, and an object or state in a system are all representations. They preserve selected aspects of reality so that we can remember, discuss, compare, calculate, and act on them.

Every representation involves trade-offs. An organization chart focuses on responsibilities and reporting relationships; a contract focuses on rights and obligations; a production schedule focuses on tasks, resources, and time. Their scope, mode of expression, and frequency of update also differ.

**The value of a representation lies in preserving the distinctions and relationships needed for current understanding and action.**

When multiple actors need to work together, the question becomes more demanding: are we describing the same object? Which moment in time does the state refer to? Are the concepts, rules, and premises for judgment consistent?

A document can help people establish shared understanding, and a table can make facts comparable. But as the number of objects grows, relationships become more complex, and states keep changing, we also need to manage how different representations correspond to one another:

- How is the same object identified across different records?
- How do descriptions from different perspectives connect to shared facts?
- How should definitions, instances, states, and rules each be represented?
- When reality changes, which content needs to be updated?

Traditional digitalization is one form of representation. Project backgrounds, specs, and other materials in today’s Markdown documents also contain extensive representations of the world. Cognito Atlas grows out of this question: **organizing our representations of the world so that objects, relationships, states, and content from different perspectives can correspond to one another and be continuously maintained.**

Such representations can contain both structured and unstructured content. Narrative preserves context, tables organize comparable attributes, diagrams express relationships, state models carry change, and rules and constraints support inspection and computation.

In settings that require continuous sensing, monitoring, and simulation, these representations can be connected further and kept synchronized with reality to form a digital twin. It is an idealized form of representation, much like a map that provides live traffic conditions.

## III. Constructing a Decision Space around a goal and situation

Once we have an understanding of the world, we still need to answer a concrete question: what should we do next?

The same facts produce different judgments under different goals and situations. Faced with the same inventory, “deliver as quickly as possible,” “reduce capital tied up,” and “secure future supply” each direct attention to different factors, constraints, and trade-offs.

We therefore need to select the relevant content from existing representations and organize it around the current problem:

Who is making the judgment? What outcome do they want? Which facts affect the result? What constraints and possible actions exist? Along which paths will different choices have effects? By what criteria should those outcomes be evaluated?

**DS—Decision Space—addresses how these elements of judgment and their dependencies can be organized into an explicit structure.**

It involves selecting information from existing representations, adding missing factors, organizing constraints, constructing viable paths, and making value trade-offs explicit.

In this process, information gaps themselves become objects of judgment. Which unknowns could change the choice and are worth investigating further? Which will not affect action for now and can remain as uncertainty?

Atlas and DS therefore connect to one another:

**Atlas organizes our understanding of the world; DS organizes our judgment about a specific problem.**

The same representation of the world can support multiple Decision Spaces. Problems discovered while constructing a Decision Space can, in turn, drive the representation to be extended, corrected, and reorganized.

## IV. Action and feedback keep changing the world while revising the representation system

Judgment needs to become action, and action produces real outcomes.

A purchase changes the state of resources; an organizational adjustment changes relationships of responsibility; a conversation may change participants’ understanding and commitments. The world after an action is no longer the same as the world before it.

These changes need to be sensed and represented again, and the representation system needs to be updated. We can then inspect whether the action was completed, whether the outcome matched expectations, whether our prior understanding of facts, relationships, and causality needs revision, and whether the goals and strategy still apply.

**World—representation—Decision Space—action thus form a continuous feedback loop.**

Participants in this loop may be people, software systems, or agents. Any of them may participate in acquiring information, maintaining representations, making judgments, and executing actions. Their division of labor depends on the task and on what each participant can access and operate.

An agent can organize documents, propose revisions to a model, or call tools to execute actions. A system can record events, calculate results, and make choices under explicit rules. People can take part in observation, interpretation, design, judgment, and action at every stage.

Reliable collaboration among these participants requires a clear expression of the facts each uses, the tasks each undertakes, the operations each can perform, and the feedback produced by action.

## V. Enterprise digitalization is this logic unfolding inside an organization

An enterprise is a concrete world in which multiple actors continuously collaborate around goals, resources, and rules.

As the scale of the business and the complexity of collaboration increase, more facts, relationships, and judgments need to be externalized, shared, and maintained. One person’s experience needs to be understood by others, the state of one department needs to be used by another, and a change needs to propagate along business relationships to the relevant places.

Digitalization provides a durable substrate for this work: business facts can be recorded, objects and relationships connected, states updated, and rules, computations, and actions shared.

This naturally raises a question:

**What representation does an enterprise need so that different roles can understand the same business situation and collaborate and act on it?**

This is also the starting point for asking why an enterprise needs a Business Atlas. A Business Atlas helps organize the objects, relationships, activities, rules, and responsibilities within an enterprise, allowing information scattered across people’s experience, documents, and systems to return to an interconnected business structure.

Building these representations repeatedly exposes more fundamental questions: how is a product actually defined, how should responsibilities be divided, who maintains the rules, and how should competing goals be balanced? These questions must be answered at the business and organizational levels, then carried by systems and agents.

Enterprise implementation can therefore unfold further along **Business → Organization → Systems → Agents**.

The maturity of the representation also determines what kinds of governance and decision-making the entire loop can support. Which objects it covers, whether relationships are complete, whether semantics are consistent, and whether states are timely determine the scope within which we can see conditions clearly, trace impacts, coordinate action, and run simulations.

Three dimensions need to be distinguished:

- **Representation maturity:** how fully the world has been represented and whether those representations can remain usable over time.
- **Governance and decision capability:** which problems can be identified, judged, coordinated, and adjusted under current conditions.
- **Actor access capability:** where people, systems, and agents can participate and which operations each can undertake.

These dimensions build on the same foundational structure. As representations improve, collaboration and decision-making can expand across a wider scope; new actions and problems then continue to drive further improvements in representation.

## Related content

- **Representation:** how reality is represented and how different forms can carry understanding together.
- [**Cognito Atlas**](/en/research/cognito-atlas/): how objects, relationships, states, and multiple perspectives are organized.
- [**Decision Space**](/en/research/decision-space/): how an inspectable Decision Space is constructed around goals and situations.
- [**Why does enterprise AI need a shared Business Atlas?**](/en/digitalization/shared-business-map/): how an enterprise forms a shared, maintainable business representation.
- **Enterprise digitalization and AI implementation:** how a continuously operating collaboration loop is built from business and organization through systems and agents.
