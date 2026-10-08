In a meeting, as soon as a problem becomes even slightly complex, people naturally reach for a pen and start drawing. Someone sketches a process, someone lays out a timeline, and someone circles the actors and connects them with arrows. For a project discussion, they might open a spreadsheet; for an architecture question, they might draw systems and interfaces directly on a whiteboard.

Behind this habit lies a simple fact: **natural language alone is not well suited to carrying every kind of structure.**

Language is good at explaining context, expressing judgments, and adding exceptions. But when a problem involves many objects, relationships, states, constraints, and dependencies at once, listeners must reconstruct the structure in their minds while trying to understand the content. The versions they reconstruct may not even be the same. This is why proposals need to be reviewed: review is a necessary, but insufficient, path to consensus.

So people keep inventing external representations. Flowcharts carry sequences and branches; tables carry objects and attributes; state machines carry state transitions; architecture diagrams carry modules and connections. Their real purpose is to externalize structures previously implicit in people's minds, allowing multiple actors to observe and modify the same object together.

Seen this way, a group gathered around a whiteboard is essentially building a shared representation.

---

Yet collaboration in many multi-agent systems today still relies primarily on natural language.

One agent completes a task and outputs some text. Another reads it and produces the next piece. In more elaborate setups, results are written into Markdown, memory, skills, or long documents for subsequent agents to process.

This can certainly work. But translate it into human terms and the problem becomes apparent: one person writes a 3,000-word Word document and sends it to another, who reads it and writes 5,000 words for a third. All the structure is hidden in prose, and everyone has to parse it again.

So the question worth asking may not be just how much context agents should pass between them, but **what kind of representation they should share.**

---

This is why I propose the concept of Cognitive IR.

IR, or intermediate representation, is already a well-established concept in compilers. Complex cognitive tasks have a similar need: often, what is missing is not text, but an intermediate layer that can carry structure explicitly.

It might be a graph representing dependencies between objects, the propagation of changes, and conflicts. It might be a table comparing candidate solutions, constraints, and missing factors. It could also be a tree, a state machine, a set of constraints, an equation, or even a program.

The value of these forms is not that they make answers look better. It is that they preserve the genuinely structured parts of thinking, so subsequent actors do not have to reconstruct them from natural language every time.

Cognitive IR is therefore better understood as a collection of cognitive structures that humans, agents, and systems can read and write together. Natural language remains important, but it is better suited to explaining structure than to carrying all of that structure on its own.

---

Maps may be one of the most mature shared representations in everyday life.

A city can, of course, be described entirely in words. We could say: “Head north for three kilometers, pass two intersections, and turn right under the second overpass. Keep going, then turn left after you see the gas station. This road tends to get congested during the morning rush hour; if it does, take the small road beside it…”

A paper map is already far more efficient. Roads, positions, directions, and connections are compressed into a unified coordinate system. People no longer need to repeatedly describe the city in natural language or individually reconstruct its spatial structure from scratch.

In this sense, a paper map is itself a good static IR.

But a mapping service such as Amap today is clearly more than a more detailed paper map.

The road structure is still there, but it is overlaid with continuously changing states: live congestion, road closures, accidents, vehicle locations, and more. These states are continually sensed and updated, and can feed into queries, route planning, and dispatch calculations.

The change here is not merely that “the map contains more information.”

**A static representation begins to carry state, continuously reflect reality, and participate in computation.**

At this point, it is no longer just a World Representation for people to look at. It is closer to a running model of the real world in digital space: as reality changes, the digital world updates, and different actors can make different decisions based on that shared state.

Navigation asks how to get from A to B. Delivery asks how to combine orders into routes. Ride-hailing platforms ask how to match vehicles with demand. Emergency systems ask which resources can arrive fastest.

These tasks do not need a single decision-making algorithm. What they really need to share is **the same city, and what is happening in that city right now.**

A map is not itself a decision-making system. But a continuously updated, computable map allows many different decisions to be grounded in the same reality.

---

Agents within an enterprise face the same problem.

Procurement, project, production, and after-sales agents can have different goals and use different forms of intelligence. Some tasks suit an LLM; others suit rules or an optimizer; some need only a function.

The real problem is that if every agent has to work out from scratch “what this enterprise is,” they are still living in separate local worlds.

Is an “order” in one agent really the same object as an “order” in another? When a project's state changes, which tasks are affected? Where do the relationships among customers, contracts, orders, projects, materials, and production tasks actually reside? Today's ERP systems are more often saying: however you choose to define these things, we can support it through configuration.

This means enterprises are not entirely without digital representations. Rather, those representations are often scattered across systems, table structures, configurations, and documents. Systems can hold them, but that does not mean the enterprise already has a unified, continuously updated, computable Business Atlas.

If these structures and states exist only in separate prompts, memory, Markdown, and business systems, so-called multi-agent collaboration can easily devolve into multiple actors repeatedly exchanging natural language, then each filling in the rest of the world for themselves.

So **what agent collaboration really needs is not just shared context, but shared structures and states representing the real world.**

Documents are, of course, still part of this world. But they should form a representation layer together with databases, object models, relationship graphs, states, rules, and Cognitive IR.

Within that layer, Cognitive IR addresses how many kinds of structure can be expressed explicitly. When those structures are further connected to instances, real-time states, sensing, and computation, what we have is no longer merely a static cognitive map. It begins to approach a continuously running digital world.

This is why I increasingly understand digital twins as a more mature form of representation: they not only describe reality but continuously reflect it, allowing different Decision Spaces to be built on that shared reality.

Different tasks then extract the local factors genuinely relevant to their own goals, forming their own Decision Spaces. Whether a particular DS is ultimately handled by an LLM, rules, a function, an optimizer, or a person is not the most important issue. What matters is that they do not each have to recreate a world of their own.

---

When reading long texts, people make notes that only they can understand. When collaborating, we seek an external object that everyone can understand together as consistently as possible.

A whiteboard provides a local shared representation; a paper map provides a static representation of a city. Systems such as Amap have begun to maintain a continuously updated digital city that can be queried and computed on.

The digital world inside an enterprise needs a similar progression: from scattered local records in documents and systems, to structured Cognitive IR, and then to a business digital twin that continuously carries objects, relationships, states, rules, and changes.

Future agent collaboration should not primarily take the form of “I read your document, then tell you my understanding.” It should increasingly resemble this:

**Multiple actors jointly observing, modifying, and operating on the same continuously updated, computable world.**

At that point, collaboration among multiple agents has a shared foundation that can be maintained over time.
