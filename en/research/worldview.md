The world in which we live and act can be understood as a continuously changing complex system.

Humans, other carbon-based organisms, and the silicon-based intelligence now entering the real world are all intelligent actors within it. Each actor needs to perceive its environment, assess situations, and act with limited information, capabilities, and resources in order to survive, achieve its goals, and secure room for further development.

Yet no actor can access and process the world in its entirety. **How to confront an almost unlimited reality with limited cognition and turn that understanding into effective action is a fundamental problem shared by all intelligent actors.**

I currently describe this process in terms of four interconnected parts:

**World → Cognition and representation → Decision Space → Action**

Action, in turn, changes the world. Those changes enter our understanding again, forming a continuous feedback loop.

## I. The world is a complex system

By “world,” I do not mean a single system with a fixed boundary that contains everything.

Reality can be divided into many overlapping complex systems according to the questions and scope of attention involved. A person's life, a family, an enterprise, an industry chain, a city, or an ecosystem can each become the “world” we observe and act within. **A system's boundary depends on what we are focusing on and which interactions between its elements matter to the current problem.**

The “world” here is therefore not limited to the physical world. Organizations, markets, software systems, and games can all constitute worlds that actors inhabit and need to understand and act within. They may contain physical objects, but also roles, rules, relationships, goals, information, and institutions and concepts established collectively by different actors.

**In this sense, a world model is not the same as a model of the physical world. It is an actor's model of those parts of its world that matter for understanding and action.**

However its boundary is drawn, such a world typically contains different actors, resources, relationships, rules, actions, and continuously changing states. These elements are interconnected. A change in one object may alter the state of another; a change in a rule may affect many people's choices; achieving one local goal may consume resources needed by other goals. Actions take place locally, but their effects may continue to propagate outward along relationships.

Some structures arise from natural laws; others are established collectively by people. **States, money, laws, organizations, responsibilities, contracts, and commitments** all depend on shared definitions, interpretation, and maintenance, yet they have equally real effects on actors' choices and actions. We live in the world while also continually helping shape it through action.

At the same time, every actor occupies a particular position in the world, with different goals, experience, capabilities, and information, and can access only part of reality.

The same order represents a commitment to the customer, work to be completed for production, material requirements for procurement, and revenue, costs, and financial arrangements for finance. They face the same business world, but see different parts of it from different positions.

Therefore, **understanding complex reality is not just knowing “what happened.” It also requires knowing which objects exist, how they relate and change, and from which perspective and at what resolution we are observing them.**

## II. To understand and collaborate, we form representations of the world

The real world is too complex for any actor to access and process in full. What we can actually remember, discuss, compare, calculate, and manipulate is always a **representation** formed by selecting and transforming reality in some way.

A map is not a city, an organization chart is not an organization, and an order in an ERP system is not the real-world transaction itself. Each selectively preserves certain distinctions, relationships, and states within reality.

Therefore, **every representation is lossy.**

This is not a flaw, but a prerequisite for a representation to be useful. If a subway map tried to show every building, tree, and side street in the city, it would instead lose its ability to help people use the subway.

The real question is never how to reproduce the world in full, but:

**For our current understanding and action, which features are worth identifying and marking out?**

When multiple actors need to collaborate, a further question arises: can their representations be related to one another?

Are we talking about the same object? Does the state refer to the same moment in time? Are our concepts, rules, and premises for judgment consistent?

This is why representation concerns not only how individuals understand the world, but also the foundations of collaboration among people, systems, and agents.

I explore why representations are necessarily lossy, how perspective and resolution affect the world we see, and how structured data, natural language, graphs, trees, state machines, constraints, and other forms can jointly represent reality in a separate article:

[**Representation | What AI Can Understand Depends on How the World Is Represented**](https://rikkalab.com/en/research/representation/)

## III. Action needs the part relevant to the current problem, not the whole world

Even if we already have a sufficiently good map of the world, each action does not require us to process everything on that map.

Suppose someone needs to travel from home to the airport. A city map may contain thousands of roads, buildings, subway lines, and public facilities, but most of that information is irrelevant to this trip.

Once **the actor, current location, and goal** are established, the initial focus needs to be only on a local part of the map.

If the goal becomes “reach the airport as quickly as possible,” live traffic and estimated travel time become important. If the aim is to “spend as little as possible,” transport options and prices enter the judgment. If the person has a lot of luggage, “fewer transfers” may become a new constraint.

The map has not changed, but **the decision-relevant information needed for the current problem has.**

We therefore do not need to build a new world model for every problem. A more reasonable approach is:

**On top of a relatively stable representation of the world, dynamically select the local part relevant to this judgment according to the current actor, goal, and situation.**

I call this local part a **Decision Space**.

It contains the current goal, relevant facts, factors that influence judgment, constraints, possible actions, different paths and their outcomes, and the actor's way of evaluating those outcomes.

In this way, an almost unlimited real-world problem can gradually be reduced to a finite, inspectable, computable space.

I explore how to construct such a local problem space and progressively converge by gathering information, applying constraints, and comparing paths here:

[**Decision Space | Turning Complex Problems into Decision Spaces That Can Converge and Be Solved**](https://rikkalab.com/en/research/decision-space/)

Before Decision Space, however, there is another question: **how should the reusable “map” itself be organized?**

I discuss the relatively stable organization of objects, relationships, states, and different perspectives further in **Cognito Atlas**:

[**Cognito Atlas | Building a Shared Cognitive Map of Complex Reality**](https://rikkalab.com/en/research/cognito-atlas/)

A rough way to understand the relationship is:

**Atlas provides the map; for a particular action, Decision Space selects from that map the local part that needs to be addressed now.**

## IV. Action changes the world, and feedback revises our representations

Decisions ultimately need to become actions, and actions change the world again.

Return to the trip to the airport.

Once the person starts along the chosen route, their location changes. If congestion suddenly appears ahead, the environment changes too. If they miss a subway train, a previously feasible path may no longer be available. These changes feed back into the map, and the current Decision Space changes with them. The original judgment may remain valid, or it may need to be recalculated and a different option chosen.

The same applies to other actions in reality.

A purchase changes inventory and cash balances; an organizational adjustment changes relationships of responsibility; a conversation may change participants' understanding and commitments. The world after an action is no longer the same as the world before it.

The new state of the world needs to be perceived and expressed again, updating our existing representations. New information may then change the current Decision Space, triggering another round of judgment and action.

This is therefore not a one-way sequence, but a continuously operating loop:

**World → Representation → Decision Space → Action → Changes in the world → Updates to representation…**

We can never obtain a complete, static, and absolutely correct world model.

What truly matters is **whether we can preserve the structure needed for current action, keep revising it as the world changes, and base new judgments on updated understanding.**

## V. Building further on this foundational structure

This structure is not specific to AI, nor is it specific to enterprises.

This loop leads to a further judgment: **agents and their environments need to be modeled together.** What information an actor can obtain, what judgments it can form, and what actions it can take depend on its own capabilities, as well as on the structure and rules of its environment. Actions, in turn, change the environment and shape the conditions for the next round of judgment. Understanding and designing intelligent systems therefore requires describing the actor, the environment, and the relationships of perception, action, and feedback between them.

This also means that we can improve an intelligent system’s practical performance by working on both the actor’s capabilities and its environmental conditions. Improving how information is organized, making rules clearer, and providing timely feedback on the results of actions can all change how difficult it is for an actor to complete a task. I explore how modeling them together can help us identify where a problem lies and which part to improve in [“Agents and Environments Need to Be Modeled Together”](https://rikkalab.com/en/research/agent-environment-co-modeling/).

On this foundation, I am currently pursuing several directions:

- [**Representation**](https://rikkalab.com/en/research/representation/): how reality is selectively represented, and how different forms jointly support our understanding of the world.
- [**Cognito Atlas**](https://rikkalab.com/en/research/cognito-atlas/): how to organize relatively stable, shared, and continuously maintainable representations of the world.
- [**Decision Space**](https://rikkalab.com/en/research/decision-space/): how to select a local problem space from the world around a particular actor, goal, and situation, and progressively arrive at feasible action.
- [**Enterprise digitalization and AI implementation**](https://rikkalab.com/en/digitalization/): how this structure takes shape across business, organization, systems, and agents when multiple actors need to collaborate over time within organizations.

They address different levels of the problem, but share the same starting point:

**We inhabit a complex and continuously changing world. The foundation of intelligence is not possessing everything there is to know about that world, but forming representations sufficient for current understanding and action, and continually revising them through action and feedback.**
