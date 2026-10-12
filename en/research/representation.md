AI does not understand the real world directly. Neither do people. What we can observe, discuss, compute, and operate on is always a **representation** formed by transforming reality in some way. A flowchart represents how a business operates. Orders, customers, and materials in an enterprise resource planning (ERP) system represent real business objects. Excel spreadsheets, database tables, and metric dashboards represent business states. A policy document, a product requirements document (PRD), or a Markdown file is also a representation.

A map is not the city itself, but people can use it to understand the city, find routes, and judge distances. Digital systems inside an enterprise are similar: they are not the business itself, but a mapping of real business into a Digital World. What we can manage and compute is never the whole of reality, but the world that has been represented.

This deserves attention in its own right because **what AI can understand and operate on depends not only on model capability, but also on how reality is represented.** However capable the model, if it encounters a fragmented, ambiguous, internally conflicting Digital World, it will still struggle to maintain a consistent understanding over time, let alone act reliably.

## 01 | Enterprises have plenty of data, but lack representations that support action

Discussions of agents today often reduce the problem to “not enough enterprise data” or “poor data quality.” This describes part of the problem, but is not precise enough. Enterprises often have no shortage of information: databases contain business data; ERP, customer relationship management (CRM), and manufacturing execution systems (MES) contain objects and states; Excel holds extensive records; “knowledge bases” are often packed with policies, operating manuals, PRDs, and other documents; meeting notes and chat histories preserve yet more business facts and rules.

In the agent era, these representations keep multiplying. System prompts, knowledge bases, text retrieved through retrieval-augmented generation (RAG), README files, memory.md, handoff.md, and skill.md all serve essentially the same purpose: telling an agent what its environment is like, what has happened, and how it should work next.

Agents today therefore do not live in a world without representations. On the contrary, representations are piled up all around them.

The real problem is that these representations are usually fragmented. The same business object may appear in three systems, five spreadsheets, and a dozen documents. Object definitions, current instances, and historical records are mixed together. Stable rules and temporary states are not clearly distinguished. Different departments use the same word for different things. When a business rule changes, the workflows, metrics, tasks, and system configurations that depend on it do not automatically change with it.

If the environment is described mainly through text, an agent must reconstruct its structure from natural language every time it starts a task: who is who, what relates to what, which statements are definitions, which describe the current state, which rules remain valid, and what a particular change will affect.

Much of what we call “long-term memory” therefore looks more like an accumulating collection of working notes. Those notes have value, but they do not automatically become a stable environment model.

This is why I believe **unlimited context cannot replace stable representation.** A longer context window only lets an agent see more material at once. It does not mean that material already forms a world with consistent structure, explicit states, and continuous updates. Information can keep growing while the world remains fragmented.

The real challenge in putting enterprise AI to work is therefore not simply whether AI has obtained the data. It is **whether real objects, relationships, states, rules, constraints, and changes have been represented in a sufficiently stable way.**

## 02 | Representation is a purposeful projection of reality

Every representation loses information. A map does not show every tree and brick in a city, and an enterprise system cannot reproduce every detail of real business in a Digital World. The question representation needs to answer is not how to preserve everything in reality, but **which distinctions are worth preserving for the problem at hand.**

Consider a large piece of equipment. From a sales perspective, it is first an item to be quoted, with a product model, configuration, price, and lead time. During engineering design, it becomes a combination of technical parameters, a standard product definition, and nonstandard configurations. Procurement focuses on the resulting material requirements, inventory shortfalls, and substitution relationships. In production, attention shifts to whether all required materials are available, production tasks, and delivery milestones. After delivery, the equipment is tracked as an individual asset in after-sales service, with an operating state, faults, and maintenance history.

The equipment itself has not changed in what it fundamentally is. **What changes is where we look at it from, why we look at it, and how much detail we need.** Every representation therefore implies a coordinate system of its own: **business domain, perspective, resolution, and intent** jointly determine what becomes visible and what is left out. Resolution here means the level of detail required.

This is also why more complete modeling is not always better. If a distinction has no further consequences for the current problem, including it in the representation only adds complexity.

> **Whether a distinction is worth representing depends not on whether it objectively exists, but on whether it makes a further difference to the problem at hand.**

Representation is not a photocopy of reality. It is a projection intended to support cognition and action.

## 03 | One object usually needs both structured and unstructured representations

Traditional digitalization often treats representation as structured data, as though defining objects, fields, and data dictionaries were enough to describe the business world. Real business is rarely so orderly.

For a piece of equipment, we can certainly define fields such as equipment ID, product model, manufacturer, installation location, current state, and maintenance interval. This information belongs naturally in a database and can form a clear data dictionary. But defining those fields alone is not enough for a newcomer, let alone an agent, to understand what the object means in the business.

Does “out of service” in the state field mean scrapped, temporarily idle, or awaiting repair? Why does one batch of equipment have a much higher failure rate? What has a particular anomaly usually indicated in the past? Why cannot a certain product model be used in a particular project? Such knowledge often lives in employees’ experience, policy explanations, maintenance records, meeting discussions, or even a single comment.

The same business object therefore usually has **both structured and unstructured representations**. Structured information is well suited to recording identities, relationships, states, and facts that can be enumerated. Unstructured information is better suited to explanations, context, experience, and knowledge that cannot yet be fully formalized. With text alone, machines struggle to compute reliably. With fields alone, much of the information that actually shapes business judgment is lost.

Between the two lies a broad range of structures that have not been represented well in the past. Dependencies are suited to graphs; classification and decomposition to trees; lifecycles to state machines. A business boundary may be a set of constraints, while some judgments are themselves formulas or programs.

This is why I identify **Cognitive IR (cognitive intermediate representation)** as a distinct concept. It does not attempt to create a new universal data format. It recognizes that cognitive structures already take many forms: natural language, tables, graphs, trees, house-shaped framework diagrams, state machines, constraints, equations, and programs. Each preserves different aspects of reality and the relationships among them.

Reality does not naturally become a two-dimensional table because databases are good at tables. Nor is it naturally suited to being compressed into Markdown because large language models are good at text.

## 04 | From recording the world to running it

Many representations in traditional digitalization still focus on records: who a customer is, how much an order is worth, what repairs a piece of equipment has undergone, or what a policy says. They answer what has been recorded about the world, but an agent needs more than the ability to read facts.

An actor that needs to keep taking action must also know the current state, why that state arose, which changes affect which objects, which constraints currently apply, and what might happen after an action is taken.

Representation then begins to develop from static records into an operational digital environment. Objects have states as well as attributes. Relationships express dependencies and influence, rather than merely indicating an association. Rules participate in judgments rather than remaining confined to explanatory documents. Changes in reality continuously update the Digital World, while judgments within that world can in turn drive action.

In this sense, **a digital twin is not the same thing as a 3D visualization.** Its more fundamental meaning is that the real objects, relationships, and states important to the current goal can be continuously mapped into a digital representation that can be understood, computed over, and acted upon.

As representation develops from records for people to read into an environment actors can use, AI begins to have a world in which it can work over time.

## 05 | Representation is a shared interface between people, systems, and agents

People are not the only actors inside an enterprise. Traditional systems can trigger actions automatically according to thresholds and rules. Agents can observe states, make judgments, and call tools. People set goals, make complex judgments, and take responsibility. In future enterprise environments, people, agents, and systems will increasingly participate in the same business activities.

They will need more than shared documents. They will need some shared understanding of what the world currently looks like.

In my current framework, the process can be roughly expressed as:

**Business world → Representation → World model / Cognito Atlas → Decision Space → Action**

Representation sits between reality and cognition. It determines which aspects of reality enter the Digital World and in what form. Cognito Atlas further organizes these objects, relationships, workflows, metrics, and knowledge. For a specific goal, Decision Space extracts the factors, constraints, paths, and value judgments relevant to a decision from the represented world. An actor then acts on that basis, and the results feed back into the representation.

If this layer is unstable, an agent can only keep rereading the world, guessing at it, and temporarily rebuilding its understanding for each task.

As a sufficiently stable, updatable representation layer that supports computation takes shape, an agent begins to have the possibility of doing more than reading material about the world. It can **live in a Digital World that persists over time**.
