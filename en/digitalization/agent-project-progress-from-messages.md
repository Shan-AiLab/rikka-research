When enterprises begin using AI agents, a natural idea often follows: isn’t all the project information in the group chats? If an agent reads every relevant chat, meeting note, email, and document, could it automatically know how the project is progressing?

The idea sounds reasonable. A great deal of project information does accumulate in these places. A customer confirms a proposal. Procurement reports a material shortage. Engineering says drawings need to be revised. A project manager follows up on a delivery date. A problem is discussed at length in a chat, until someone finally says, “Let’s go with that.”

If the goal is simply to find out what people discussed yesterday, today’s large language models can already do a good job. The harder question is different: **where exactly does the project stand now?**

Suppose someone writes in the group chat: “The customer has confirmed it. We can move ahead.”

When people read this, they usually understand more than its literal meaning. We automatically place it in the broader project context: which version of the proposal was confirmed, where work had been blocked, what the confirmation means, whether design, procurement, or production can now begin, and whether any other prerequisites remain unmet.

In other words, we never understand just a sentence.

We already have a model of the project in mind, which lets us interpret that sentence as a state change.

This is also where the difficulty lies for an agent.

With chat histories alone, it receives a sequence of things people have said, but may lack a stable representation of the project in which to place them. It can summarize that “the customer confirmed the proposal,” “a material has been delayed,” or “delivery may be affected.” But which objects these statements refer to, which states have changed, and what else those changes will affect do not automatically become clear just because the agent reads enough text.

This is why giving an agent more context cannot fully solve the problem.

Context addresses whether information has been seen. Project progress is a different concern. It requires the system to know which objects make up the project, their current states, their dependencies, and which events cause those states to change.

Otherwise, asking an agent to summarize progress today and again tomorrow may produce two fluent pieces of prose. A person might manage to compare them and infer what has changed, but the system itself has not maintained a project state that evolves over time.

Group chats are therefore more like a stream of signals produced as real work unfolds than the project itself.

The stable structures should be projects, tasks, requirements, issues, milestones, and the relationships among them. Chat histories can help an agent discover what has just happened. But those changes still need to be reflected in a more stable structure so that the system can maintain an up-to-date project state.

The question then shifts from whether an agent can read all the information to something more fundamental:

**Does the enterprise have a way to continuously represent its unfolding business world?**

This is why I increasingly believe that before discussing agents, we must first discuss representation.
