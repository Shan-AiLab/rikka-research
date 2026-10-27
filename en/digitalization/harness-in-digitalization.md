Models are already highly capable within a single call. Increasingly, the difficult question is not whether a model can perform a task, but whether it can work reliably across many steps, hours, or longer in an environment that keeps changing.

Before asking how an agent can sustain its work, however, we need to ask a prior question: within which business boundaries is it allowed to act, and which constraints previously hidden in fixed workflows must be made explicit again? [“Agents will not eliminate workflows; they will force us to rethink them”](https://rikkalab.com/en/digitalization/agents-workflows-executable-functions/) addresses that layer. This article then considers how a harness connects an agent to an established business environment and its action boundaries.

A real task does not automatically end when one round of reasoning finishes. An AI agent needs to remember what it has done, know how far the task has progressed, call tools, handle failures, reconstruct context, and continue judging and acting as new information arrives. Context, memory, tool use, loops, retries, handoffs, and skills all address this problem.

> **The model handles one cognitive step; the harness connects countless such steps into a system that keeps running.**

This is the central value of an agent harness today. But as we move further into real business environments, we find that most harnesses still primarily address only half of the problem: **the agent’s own side.**

## 01 | Today’s harnesses mainly maintain the agent itself

For an agent to work over time, it must first maintain its own continuity. It needs to know its current goal, which actions it has taken, which information is worth retaining, what judgments it has formed, which skills it has acquired, what it intends to do next, and where to resume after a failure.

This closely resembles how a person maintains a personal system for work. People take notes, organize knowledge bases, maintain to-do lists, record project progress, and develop working habits. Agents’ memory, handoffs, skills, and context compression serve similar purposes. They help an actor maintain its task state and cognitive state over time.

From this perspective, many current harnesses can be understood as **infrastructure on the actor’s side**. Their first concern is how an agent can continue to be the same agent.

This is a reasonable starting point. Early agents had relatively limited responsibilities, faced a small set of tasks, and worked with comparatively simple environmental information. Temporarily keeping a large amount of context in their own memory or working directory did not immediately create serious problems.

But as agents enter real environments involving long-running work, many people, multiple systems, and continual change, a boundary becomes harder to ignore: **what the agent knows and what the world is actually like are not the same thing.**

## 02 | An actor’s cognitive state is not the environment’s operational state

Many agent implementations today mix these two kinds of information.

README files, memory.md, handoff.md, retrieval-augmented generation (RAG) results, and long contexts record what an agent has done and learned while also describing the external environment. The world the agent remembers gradually becomes a proxy for the world itself.

For simple tasks, this works well enough. In real business, the problems become increasingly apparent.

A procurement agent might remember: “The last time I handled a supplier delay, I checked inventory first, then substitute materials and delivery dates.” This is its own experience and can belong in its skills or memory.

But “Supplier A currently promises delivery on October 8,” “Project X is short of three categories of critical materials,” and “Procurement task Y is halfway complete” are environmental facts, rather than the agent’s personal memory.

Similarly, “I think this project may be delayed” is an actor’s current judgment. The project’s tasks, their dependencies, and the states that have just changed belong to the representation of the environment itself.

These kinds of information differ in lifecycle, responsibility, and scope of sharing. An actor’s judgment can be overturned, and personal experience may belong only to a particular agent. But an order’s current state should not be redefined whenever a different agent takes over.

> **Actors need to maintain their own cognitive states, and environments need to maintain their own operational states. The two cannot remain mixed together in the same Markdown file over the long term.**

This is fundamentally no different from human collaboration. My personal notes belong to me, but a team’s project status cannot exist only in those notes. A team can share a project space without putting all the company’s customers, orders, inventory, responsibilities, and rules into one project document.

Personal knowledge systems, team collaboration spaces, enterprise systems, and broader public infrastructure have different scopes.

The same holds for agents.

## 03 | Shared context does not mean shared understanding

Once we separate actors from their environment, another side of many apparent problems with agent capability becomes visible.

Agents certainly need perception, reasoning, and action. But how effectively they can use those capabilities depends on whether the environment provides sufficiently stable representations.

If order states are never maintained, even a highly capable agent can only guess at progress. If the same customer has different identities in three systems, it must repeatedly determine whether the records refer to the same object. If rules are scattered across policy documents and chat histories, every judgment requires reconstructing constraints from text. If related tasks, metrics, and dependencies are not updated after a business change, the agent continues acting on an outdated representation of the world.

Even when information has been “shared,” however, the problem is not over.

Human collaboration already offers a familiar example: **why do product requirements documents (PRDs) need review?**

A PRD is already a shared document. Product managers, developers, designers, and testers theoretically see the same text, but that does not mean they reach the same understanding. “Support batch editing” may mean one business action to a product manager. A developer will ask about the scope of the batch, transaction boundaries, and failure handling. A tester will focus on exceptional states, permissions, and rollback conditions. Everyone has read the same document, yet several different systems may already have taken shape in their minds.

That is why review is needed.

Review does more than let more people see the PRD. It identifies differences in understanding, makes implicit assumptions explicit, clarifies boundaries, and records the agreement eventually reached.

The most reliable practice is usually to write key conclusions back into requirements, interfaces, rules, or acceptance criteria, rather than treating a conversation as sufficient. If agreement exists only in a meeting, it can start drifting again a few days later.

This reveals a more fundamental issue:

> **Sharing information does not mean aligning semantics. Sharing the same text does not mean sharing the same world model.**

The same applies to multi-agent collaboration, where the problem becomes even more apparent.

A common approach today uses shared directories, shared Markdown, conversation histories, or shared state to give multiple agents the same context. But sharing in real collaboration has never been a matter of simply copying the same information.

The same business object can be viewed from different actors’ perspectives. Sales, procurement, and production may be looking at the same project while attending to different attributes, states, and relationships. Two agents can also reach different judgments from the same facts. Collaboration involves shared facts, information private to particular actors, and disagreements that cannot yet be resolved.

Compressing all of this into one shared text makes basic questions difficult to answer. Which parts are shared facts, and which are an actor’s judgment? When two judgments conflict, should one overwrite the other, should both coexist, or should versions be retained? Which object, state, or rule does a sentence refer to? Are the actors actually discussing the same thing?

Permissions add further complexity. Different actors should have different visibility and authority to act. A procurement agent can see supplier quotations, but a production agent may not need them. A manager’s access to business metrics across departments does not mean every execution agent should read the same information. Handling these differences through a single shared context can easily become a continuing exercise in splitting files, copying files, assembling context, and maintaining permission rules.

The problem is therefore not that Markdown is too short or the shared folder too small.

It is that **the natural-language sharing layer itself lacks sufficiently precise structure to support collaboration among multiple actors.**

Shared facts, object identities, relationships, states, rules, permissions, perspectives, and actors’ judgments need to be distinguished. We also need clearer ways to express which of them agree, which conflict, and which hold only from a particular perspective.

Multi-actor collaboration therefore needs more than a larger shared context. It needs a more rigorous structured representation layer. Text can remain, and can still be very important, but it cannot handle all semantic alignment on its own.

> **The difficulty in multi-actor collaboration is not making everyone see the same thing. It is helping them distinguish shared facts from their own interpretations, and identify precisely where they have reached agreement.**

Treating the environment separately makes this clearer. The shared environment maintains common facts. Actors obtain different views according to their roles, tasks, and permissions. Their judgments remain in their own cognitive states. Multiple actors can understand the same environment differently without creating separate “worlds” that drift apart.

> **Collaboration does not require actors to have identical contexts. It requires them to refer reliably to the same shared reality.**

## 04 | The harness is more like an interface than a container for the whole world

The prevailing direction is to keep adding capabilities to the harness: more memory, more complex knowledge bases, larger working contexts, and stronger task-state management, eventually hoping that the harness itself can hold everything an agent needs.

But if the actor and the environment are separate concerns, the harness probably should not expand without limit.

Its more appropriate position may be **between the actor and the environment**.

On one side, the actor maintains its memory, skills, task state, hypotheses, and work in progress. On the other, the environment maintains shared objects, relationships, states, rules, constraints, and events. The harness enables a particular actor to perceive that environment, obtain the representations it currently needs, form judgments, execute actions, and feed the results back into the environment.

A rough way to express this is:

**Actor ↔ Harness ↔ Environment**

The harness does not need to “own” the entire environment, just as human senses and the nervous system do not need to contain the whole physical world. It needs a reliable way to connect to the environment.

Multi-actor collaboration then no longer has to begin by synchronizing everyone’s context into one copy. Each actor can keep its own memory, perspective, and judgments, read the same environment through a harness according to its permissions, and refer to common objects, states, and facts when collaboration is needed.

The shared environment can also provide a more precise semantic anchor than natural language alone. Even with different perspectives, agents can know that they are discussing the same project, order, task, or rule. Disagreements can be attached to common objects instead of being scattered across separate Markdown files, waiting to be reinterpreted on the next call.

In other words, **sharing takes place at the environment layer, rather than by copying actors’ internal states.**

This also means that some information temporarily kept in an agent’s local workspace may gradually move outside it. Shared facts should not become an agent’s private memory, and objects belonging to an organization should not be tied to one particular harness implementation.

> **Let actors maintain what belongs to them, and environments maintain what belongs to them. The harness provides a stable interface for perception, understanding, and action between the two.**

This boundary may matter more than which additional modules a future harness should contain.

## 05 | The real direction of development is expanding shared environments across levels

Following this reasoning outward suggests that the evolution of harnesses does not necessarily mean larger harnesses. What expands may instead be the scope of the environment an agent can access.

At first, a single agent only needs to maintain its own memory, skills, and task state, much as a person manages notes and a workbench. At this stage, much of the context can remain private.

When several agents or people begin working on a task together, new sharing needs arise. The requirement is not for every actor to have identical memory, but for a shared team environment: people and agents collaborate around the same tasks, objects, and states while retaining their different perspectives, judgments, and permissions.

At the organizational level, customers, contracts, orders, projects, resources, responsibilities, rules, and metrics no longer belong to a single team. Together they form the enterprise’s shared Digital World. What is needed here is more than larger agent memory: it is an enterprise-wide representation of the environment, closer to the problems addressed by Enterprise OS and Cognito Atlas.

Beyond the enterprise, organizations also share product standards, supply-chain relationships, industry rules, objects involved in transactions, and common semantics. The environment’s scope continues to expand toward digital infrastructure at the industry level.

We can therefore see a progression:

**Personal cognitive system → Shared team environment → Enterprise Digital World → Industry Digital World**

Each level maintains a different scope of reality, with corresponding boundaries for sharing, perspectives, and permissions. Actors connect according to their roles and tasks, while the harness keeps a similar responsibility: enabling a stable cycle of perception, understanding, action, and feedback between the actor and its environment.

From this perspective, the next generation of harnesses need not become ever larger containers. Instead, their boundaries may become clearer: actors maintain their own cognition, environments maintain shared reality, and harnesses connect the two.

This returns to the question that has long concerned me:

> **How can the next generation of agents maintain cognitive consistency and act correctly over extended periods in complex, messy, continually changing real-world environments?**

The answer may require more than longer context windows, more memory, or more Markdown notes.

A more fundamental direction may be to make it unnecessary for an agent to remember the whole world on its own.
