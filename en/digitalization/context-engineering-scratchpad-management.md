When people work, they often reach for a sheet of scratch paper to jot down ideas and organize clues. When it fills up, they start another sheet, returning to old notes when needed.

This looks remarkably similar to much of what agent Context Engineering and Memory Engineering do today.

At first, we gave a model a prompt and kept appending the conversation history. Then we discovered that context windows were limited, so we began truncating, compressing, and summarizing. Later came long-term memory, hierarchical memory, vector retrieval, dynamic context loading, and increasingly elaborate mechanisms for managing history.

In effect, we moved from an ever-longer sheet of scratch paper to pagination, archiving, indexes, sticky notes, and eventually an entire automated system for managing scratch paper.

These techniques do help agents sustain their work. But one question rarely seems to sit at the center of the discussion: **How much of what we record on scratch paper should actually be managed in another way?**

## Scratch paper vs. systems

Imagine a purchasing employee processing an order.

They might jot down a few temporary questions: Can this material be substituted? Is the supplier’s delivery date reliable? Which production tasks would a three-day delay affect? These are hypotheses, open questions, and intermediate judgments arising in the current work. Recording them on scratch paper is natural.

But once they confirm that a purchase order’s delivery date has changed, they should usually open the system and update that order. If they discover a material shortage, they should also update the relevant requirement, purchasing task, or exception record.

It is hard to imagine an enterprise asking purchasing employees to write every business change in personal notes, then developing an elaborate note-retrieval system so that others can reconstruct the current state of purchase orders by reading those notes.

Yet when we discuss agent memory, we readily accept similar designs.

As an agent works, it accumulates history, summarizes experience, and maintains task progress, relying on the next model invocation to recover the environment’s state from those records. For temporary cognitive processes, this is entirely reasonable. But if orders, projects, tasks, object relationships, and current state are also conveyed mainly through these texts, the problem has already moved beyond working memory.

**Scratch paper should support the work, but it should not be the only place where the objects of that work are represented.**

## An increasingly elaborate scratch-paper engineering project

This produces an interesting situation in many agent engineering efforts.

A great deal of work revolves around context and memory: how to compress, retrieve, archive, and pass along historical records.

**The office has no ERP, so it keeps upgrading how employees manage their scratch paper. It must also work out which sheets should be shared, and how to divide permissions once they are.**

More interestingly, even without an ERP, an Excel register with explicit fields, object identifiers, and states could bring us closer to a solution than accumulating more working notes.

Excel can, of course, also hold comments, explanations, and exceptions. Its value lies precisely in allowing people to retain the flexibility of natural language while beginning to separate objects, attributes, and states from narrative.

## Scratch paper provides external working memory

Context often mixes two different kinds of information.

One belongs to an actor’s own cognitive process: current hypotheses, work plans, intermediate reasoning, and unverified judgments. This information changes as the task progresses and needs working memory to hold it.

The other belongs to the environment in which the actor works: orders, equipment, projects, resources, rules, and their relationships and current states. Different actors typically need to refer to this information together, and it must be continuously updated as reality changes.

The two can be connected, but they should not be managed in a single textual history by default.

If the environment has a stable representation, an agent can query the relevant objects and states when needed, execute actions through explicit interfaces after reaching a judgment, and update the environment with the results. The next time work begins, the same agent, another agent, or a person can read this information again without first going through one actor’s entire collection of working notes.

This does not mean Context Engineering has no value. Even a comprehensive business system cannot do all our thinking for us; complex tasks still require plans, hypotheses, intermediate results, and accumulated experience.

But it does mean that **how much working memory an agent must maintain depends not only on the complexity of the task, but also on how much information the environment already holds on its behalf.**

When large amounts of state that should belong to the environment remain inside the actor, the harness has to become increasingly complex. Beyond managing model calls and execution flows, it must save, restore, and synchronize information that should have been directly available from the environment.

Conversely, the more mature the environment’s representation, the more an agent can concentrate on what actually requires understanding, judgment, and action.

## From managing scratch paper to building a Digital World

How to reliably record, organize, and continuously update business information is not a new problem. Decades of digitalization have explored these questions extensively, producing solutions ranging from Excel registers and databases to all kinds of business systems.

The arrival of agents will, of course, place new demands on this infrastructure. Objects in existing systems may be poorly defined, relationships scattered across applications, and rules confined to documents and people’s experience. Many states may not even have a digital representation yet.

These problems concern how the environment is represented, rather than only how models manage context.

**No matter how advanced scratch-paper management becomes, it will not automatically grow into a Digital World.**

Related reading: [Representation | What AI Can Understand Depends on How the World Is Represented](https://rikkalab.vercel.app/en/research/representation/)
