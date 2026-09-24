People often use autonomous driving as a metaphor for enterprise AI. In the ideal version of this future, enterprise systems should behave like increasingly intelligent vehicles: sensing their environment, understanding goals, planning routes, handling exceptions, and gradually requiring less human intervention as their capabilities improve.

One crucial point is often overlooked. Autonomous driving has never meant that once the model becomes smart enough, a vehicle can simply roam the physical world unaided. Leaving aside the different levels from L1 to L5, even highly autonomous driving still depends on positioning, digital maps, navigation, environment models, and continuous sensing of real-time conditions.

A map is not a flat image at one fixed scale. On a long journey, we care about cities, regions, and road networks. At a particular intersection, the view naturally zooms in to lanes, turning relationships, and the immediate surroundings. Navigation systems constantly zoom in and out because the same physical world must reveal different information at different decision scales.

As the vehicle becomes more intelligent, the map does not disappear.

On the contrary, once the vehicle begins to act autonomously, questions such as “Where am I? What is around me? What can I reach? Where is my destination? Where will the next action take me?” become even more important.

Enterprise AI faces the same class of problem.

We have spent a great deal of effort discussing model capabilities, agents, harnesses, knowledge bases, and context engineering—how AI reasons, executes, and closes the loop. Beneath these questions, however, lies a more fundamental one that has received far less attention:

What kind of business world should AI live in?

I call this the Business Atlas.

## From POIs and roads to real-time traffic

The map metaphor makes it easier to understand what a Business Atlas should contain.

A city map contains hospitals, airports, restaurants, and subway stations: POIs that can be identified consistently. An enterprise has its own “POIs”: customers, contracts, orders, projects, products, equipment, materials, suppliers, tasks, and more. These relatively stable things that can be recognized and referenced are Business Objects.

But POIs alone do not make a map. A map becomes useful because roads and topological relationships connect those locations.

The same is true of business objects. A project does not exist in isolation inside a “project management module.” It fulfills a contract and a customer commitment, while connecting onward to deliverables, products, materials, and tasks. A procurement task is not merely a record on a procurement screen. It may originate from a material shortage in a project, connect a supplier to a purchase order, and ultimately affect whether the project can be delivered on time.

Business objects can therefore be understood as POIs on a map, and their relationships as the road network that connects them. Which objects can connect, how a change propagates through those relationships, and where an action may ultimately have an effect all depend on the structure of this map.

Roads also come with traffic rules. You cannot drive the wrong way down a one-way street; U-turns are prohibited in some places; different vehicles have different permissions. Enterprises similarly have permissions, business rules, prerequisites, compliance requirements, and mandatory paths for particular actions. Together, these rules and constraints define which actions are feasible.

Then there is real-time traffic. A congested road or a temporarily closed exit may correspond, inside an enterprise, to a delayed order, insufficient inventory, a supplier default, an equipment failure, or an overdue task. These conditions change quickly, but they become meaningful only when attached to a relatively stable business structure.

A Business Atlas therefore contains at least two distinct layers. Business objects, relationships, rules, and constraints form its relatively stable structure; the current states of those objects form its continuously changing traffic conditions. For AI to work inside the business world, it must understand both.

## The Business Atlas makes action legible and plannable

Imagine dropping someone into a completely unfamiliar city and telling them to reach point B. Without a map, arrival is not impossible. They can read signs, ask for directions, try different routes, and turn back after making a mistake. Given enough time, they may even develop a rough understanding of the entire city.

The problem is this: at every fork in the road, how do they know whether they are getting closer to B or farther away?

If the final outcome is the only feedback, then a great many intermediate actions receive the same signal: “Not there yet.” After traversing countless routes, they may slowly infer patterns from success and failure and form an internal judgment about which places connect and which directions look promising.

In a sense, they are paying for an implicit model of the world through environmental interaction.

Reinforcement learning does something similar. Through extensive exploration, rewards, and feedback, an agent gradually learns which actions are more likely to produce good outcomes in a given state. This is entirely valid in theory. But when the structure of a world can already be expressed explicitly, relying on this method alone means spending vast amounts of interaction to reconstruct that representation from scratch.

A real enterprise is not a simulation that can be restarted indefinitely. A procurement error, a pricing mistake, or an overlooked compliance requirement carries real cost. More importantly, many business outcomes emerge only weeks or months later. By then, accurately attributing today’s result to a particular earlier action is already extremely difficult.

With a Business Atlas, the problem becomes much simpler. An actor can first establish its position, then understand the relationship among its current location, the destination, and the overall structure. It can begin to determine before acting which paths are unreachable and which apparently indirect route has the lower total cost.

The Business Atlas does not make decisions for the actor. It places action inside a space that can be planned.

This is why I think the most sensible relationship between AI and humans resembles a shared Business Atlas with intelligent navigation layered on top. With the Business Atlas, people can already reason through routes themselves, but they are slower and more dependent on personal experience. AI adds a high-performance navigation layer that can compare routes, simulate outcomes, and identify risks much faster.

AI adds computational and decision-making power; the Business Atlas makes the business world computable.

## Multi-actor collaboration requires a shared Business Atlas

If an enterprise contained only one person or one agent, whether that actor could gradually learn the world on its own would merely be a question of efficiency. A real enterprise, however, is inherently a multi-actor collaborative environment.

From signature to delivery, a contract may involve sales, R&D, procurement, production, finance, and management. Now we are preparing to add sales agents, procurement agents, scheduling agents, and business analysis agents to the same collaborative network. As the number of actors grows, a question even more fundamental than navigation emerges: how can these different forms of intelligence confirm that they are referring to the same business world?

In Sapiens, Yuval Noah Harari offers a useful idea. One important reason humans can collaborate at scales far beyond small groups is our ability to believe in and use a reality shared among many people. Money is the classic example: a banknote or a string of digits in a bank account has no inherent physical value, yet because large numbers of strangers recognize the meaning and rules behind it, money can organize economic activity on an enormous scale.

Companies, legal entities, contracts, equity, and organizational roles have similar properties. Physically, a contract may be only a few sheets of paper or a set of electronic records. But once the participants collectively recognize that “this contract is in force and creates these rights, responsibilities, and delivery commitments,” it can set an entire organization in motion.

From this perspective, an enterprise is itself a collaborative system built on a shared business reality. ERP, CRM, office automation, workflow, and other digital systems have already carried part of that reality: they gave business concepts such as contracts, customers, orders, and approvals—once scattered across human memory and paper records—a shared digital form.

In the past, most intelligent actors participating in this world were human. Today, silicon-based intelligence is entering the same collaborative network.

When someone says, “This project is at risk,” whoever handles it next—another colleague or an agent—must know exactly which business object “this project” refers to and be able to follow its relationships to the contract, deliverables, materials, and tasks. When a procurement agent hands an exception to a procurement specialist, both must also share the enterprise’s procurement rules: what requires approval, which actions are permitted, and where the boundaries lie.

Some of this has existed in digital systems; some remains in human experience and unstructured documents. As agents enter the enterprise, a harness that assembles context ad hoc will become increasingly insufficient. Collaboration needs more than an answer to “What information should the model receive in this conversation?” It also needs a more stable set of Business Semantics that humans and AI can identify together.

This is the value of the Business Atlas as a shared coordinate system.

## A shared Business Atlas does not mean a shared interface

It is easy to form a misconception here: if every actor shares the same business world, must sales, procurement, executives, and agents all face one enormous, complicated object graph?

Real-world maps show why this is unnecessary.

In the same city of Tokyo, a tourist cares about attractions, hotels, and transit lines; a driver cares about roads, congestion, and parking; an urban planner sees districts, population, and infrastructure. They all rely on the same city without using identical information views.

The same applies to an enterprise. The underlying world is shared, while the view should change with the actor, task, and current state.

An executive may begin at the operating level, seeing several core objectives and the projects that threaten them. After identifying an abnormal project, they can drill down into delivery performance, zoom further into a particular deliverable, and finally locate a specific material shortage and procurement task. A procurement specialist may travel in the opposite direction: starting from the local exception of a supplier delay, then zooming out along object relationships to determine which project, contract, or even business objective it will ultimately affect.

This resembles zooming a digital map. When planning across a long distance, we do not need to see every lane marking. At a complex intersection, city-level information recedes into the background and the local structure takes priority.

“Resolution” here does not simply mean showing more or fewer fields in an interface. It describes the scale at which we are understanding the same business world.

A good enterprise AI workspace should not be a conventional portal frozen in advance around roles. It should combine the current actor, task, and real-time state to determine dynamically which information matters now. To an executive, a project may ordinarily appear as one node in an operating portfolio. If a critical material is delayed, it should automatically become more prominent in the view. The same object can likewise present very different local information to procurement, sales, and management.

The underlying Business Atlas stays consistent; task-specific views are dynamically derived from it.

A shared Business Atlas does not require everyone to see the same page. It requires the different slices seen by different people and agents to map back to the same business world.

## The Business Atlas determines what counts as useful context

Following this logic further gives us another way to understand harnesses and context, two widely discussed topics in agent deployment today.

Many current approaches naturally drift toward “give the model more information.” If context is insufficient, add more documents, more conversation history, and more database records. But a navigation system for a trip from Beijing to Shanghai does not place every POI, every alley, and all real-time traffic across every Chinese city in front of the driver at once.

The real value of a Business Atlas is that it allows the system to derive the relevant region and level of detail from the actor’s current position and goal.

Enterprise AI should work the same way. A particular decision may not require everything happening across the enterprise. It may instead require deciding which part of the Business Atlas to expose, what level of resolution to use, which relationships to expand, and which real-time states actually affect the current objective.

Seen this way, the Business Atlas and context belong to two different layers. The Business Atlas maintains a complete and relatively stable world structure. Context is a task-specific local view computed from the Business Atlas and its current state.

Without an underlying Business Atlas, every attempt to construct context risks guessing again from raw materials what might be relevant. With one, context becomes a computable view rather than an ad hoc bundle of documents.

## The key to collaboration is continuity in the business world

Much collaboration inside enterprises appears informal because so much context is actually stored in human memory. Tell someone familiar with a project, “Keep an eye on this project. There may be a supply-chain issue; pass it to procurement,” and they can often fill in the underlying objects, responsibilities, causes, and consequences automatically.

That ability comes from the implicit model of the business world formed in their mind through long-term work.

When collaboration begins to mix humans and agents—or multiple agents—the cost of relying on natural language to reconstruct context at every handoff rises rapidly. A stable handoff should land at explicit coordinates in the Business Atlas: a deliverable in a particular project is affected by a material shortage; that shortage is connected to an overdue procurement task; therefore a new responsible actor must intervene.

The person taking over may change, and the agent may change, but they enter at the same coordinates in the business world. Once the work is complete, the result updates the state of the original objects. The next participant no longer needs to infer what happened from a pile of chat logs.

The actors executing a chain of work may keep changing, while the business world itself remains continuous.

I believe this is the state human–AI collaboration should actually pursue. Collaboration does not require every actor to share the same interface or hold all context in its head. It requires every communication and action to be grounded in a shared business coordinate system.

## Experience becomes organizational memory only when it has coordinates

Enterprises produce vast amounts of “experience” every day: meeting notes, project reviews, emails, chat logs, exception handling, and approval comments. Recording these things is still a long way from turning them into organizational capability.

A ten-page retrospective on a delayed project may contain a great deal of valuable information. In the next project, however, the difficult question is: in what way is today’s situation actually similar to the previous one?

If the past experience can be attached to stable business objects, it gains coordinates. We can know which project it occurred in, which products and materials were involved, which supplier it concerned, how a particular task changed at the time, and through which relationships that change ultimately affected delivery. Only when a similar structure appears again can the earlier experience truly be retrieved.

Otherwise, so-called “enterprise knowledge” easily becomes an ever-growing text repository.

This is also why I remain skeptical of the idea that “if we give AI every enterprise document, it will naturally learn the business.” Consider a new human employee: give them SOPs, historical projects, meeting notes, and thousands of emails, and they can certainly learn many facts quickly. But no company would say onboarding is complete the moment access to the shared drive is granted.

The truly difficult knowledge often lies between the materials: which rules still apply, why this is the current objective, why one object affects another, who should make the judgment when conflicts arise, and why a local action eventually affects the overall outcome.

AI can drive the cost of reading one hundred thousand pages close to zero. But if the world behind those pages has not been organized, what it gains is still only one hundred thousand pages.

Reading faster does not automatically organize the world into a Business Atlas.

## AlphaZero never operated without an explicit world model

Go offers another useful comparison.

AlphaZero is often used to show that AI can move beyond human experience and learn extremely strong strategies through self-play. That is true. But Go also has one condition the enterprise world can hardly expect: its world structure is astonishingly clear.

The board, the stones, the legal moves, how the state changes after a move, when the game ends, and what winning means have all been fully formalized.

AlphaZero can therefore concentrate its immense learning capacity on the question of how to play well. It does not need to spend years inferring from game records, chat logs, and historical databases what Go actually is.

This distinction matters enormously.

Strategy learning in Go happens only after the world has already been modeled to a very high degree.

Many difficulties facing enterprise AI today occur at an earlier stage: whether “orders” in several systems are actually the same concept, how a project relates to a contract, which attributes truly belong to the object itself, which fields are merely legacy fields left behind by earlier processes, which rules are durable, and which changes are only part of the current state.

If these structures remain ambiguous, asking an agent to learn the optimal strategy is like asking a player to play while simultaneously inferring the boundaries of the board and the rules of the game. No matter how powerful AI becomes, this cost will not disappear automatically.

## AI can help build the Business Atlas, but the enterprise still needs one

I do not believe the Business Atlas of the future should be maintained painstakingly, line by line, by people alone. AI can play a central role: helping discover objects, identify candidate relationships, detect inconsistencies between models, recognize rule changes, and continuously revise how we represent the enterprise world as the business evolves.

A Business Atlas will never be finished in a single pass. The business changes, and so does our understanding of it.

The worthwhile question, then, is not the binary choice between manual modeling and AI-driven learning. It is which relatively stable structures of the world deserve to be preserved explicitly, and which dynamic judgments and strategies should be left for intelligent systems to learn.

As AI participates in more and more enterprise actions, a shared, addressable, multi-resolution representation of the business world will only become more important.

Objects are the POIs in the Business Atlas. Relationships form its roads and topology. Rules define how traffic can move. Dynamic states become real-time conditions. Different people and agents derive different views from the same world, zooming out when they need the whole picture and zooming in when they are ready to solve a specific problem. Once an action changes reality, the new state is written back to the Business Atlas, and past experience gains coordinates of its own.

Human society has already shown that large-scale collaboration depends on shared objects, rules, and meaning. The enterprise of the future simply adds a new class of participant: some intelligence is carbon-based, and some is silicon-based. They do not need to understand the world in exactly the same way, nor do they need to see exactly the same page. But to collaborate over time, they need a shared coordinate system into which their different views can be mapped.

I increasingly believe that one of the foundational infrastructures worth building for the enterprise AI era may be neither an endlessly expanding but unstructured knowledge base, nor merely an increasingly capable agent.

It may be a Business Atlas that carbon- and silicon-based intelligence can jointly reference, understand, and use at multiple levels of resolution.
