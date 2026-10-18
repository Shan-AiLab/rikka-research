*Complexity left unresolved in business definitions, product design, and technical implementation ultimately lands on the agent.*

Large language models can already understand complex problems, generate code, call tools, and even complete multistep tasks independently. Yet in real enterprise operations, many agent projects remain at the demo stage.

Are agents insufficiently capable, or are they being made to handle too much complexity that should have been addressed elsewhere?

## 1. Start with AI-powered data queries

Suppose a user asks, “What were last month's sales?”

It looks simple: the model understands the question, generates SQL, queries the database, and returns the result.

But first, what does “sales” mean?

Contract value, order value, shipped value, invoiced value, or payments actually received? Which date determines the reporting period? Are canceled, returned, or amended orders included? Does the amount include tax?

We also need to know which business objects the metrics involve, which systems contain them, how the tables relate, which sources are trustworthy, and which data the current user is authorized to see.

Until these questions are resolved, generating SQL is only a small part of the task.

**The challenge of asking AI about business data is not just whether the model can generate the right query. It is whether the enterprise can explicitly define what it is asking and how the answer should be calculated.**

## 2. Complexity left unresolved upstream is passed to the agent

Trace this example back through the work that precedes it.

Business teams need to define what sales means, the reporting scope, and calculation rules. Product teams need to organize those definitions into reusable metrics and analytical capabilities. Technical teams need to implement the data models, calculation logic, data relationships, and access controls.

What happens at the agent layer when this work is incomplete?

We start explaining metric definitions in prompts, packing database schemas, metric documentation, and special instructions into context, saving experience from previous queries in memory, and improving success rates through tool calls, SQL validation, and retries.

These engineering capabilities have value, but the problems they address do not all originate within the agent.

**Complexity left unresolved in business definitions, product design, and technical implementation becomes complexity in the agent's context management, reasoning, and execution.**

For a demo, we can prepare data, restrict the questions, and supply accurate schemas. In day-to-day operation, business rules change, metric definitions evolve, and data and permissions keep updating.

If every agent must interpret the business definitions again, and every change requires extensive updates to prompts and context configuration, duplicated definitions, inconsistencies, and maintenance costs may grow as agents and tasks multiply.

This is the problem that [From business to code: Reasoning across three architecture models](https://rikkalab.com/en/digitalization/business-product-technical-architecture/) aims to address: explicitly connect business definitions with product capabilities and technical implementation, rather than explaining them afresh at each successive layer.

## 3. The harness gets more complex, but the environment doesn’t improve

Much agent engineering today centers on harnesses, context, and memory: organizing tasks, calling tools, compressing context, retaining memories, and resuming execution.

Two different kinds of problems are mixed together here.

One concerns the agent itself: its current plan, tentative hypotheses, intermediate results, past experience, and execution state.

The other concerns the business environment: customers, orders, metrics, rules, permissions, their relationships, and current states.

**An actor's cognitive state is not the environment's operational state.**

An agent can remember how it analyzed sales data last time, but the enterprise's definition of sales should not exist only in one agent's memory. A rule change should not require every agent to update its own interpretation independently.

If the environment continuously maintains this stable, shared business information, agents can retrieve and use it as needed rather than infer it from scratch each time.

A harness still connects intelligence with the environment, organizes execution, and handles exceptions. Context and memory retain their own roles. They need not maintain the enterprise's entire business world on its behalf.

These are the boundaries I discuss repeatedly in [Context engineering: Managing AI’s scratch paper](https://rikkalab.com/en/digitalization/context-engineering-scratchpad-management/) and [Understanding agent harnesses in the context of digitalization](https://rikkalab.com/en/digitalization/harness-in-digitalization/).

**How much complexity an agent must handle depends not only on the task, but also on how much the environment already represents and manages for it.**

## 4. Don't just build all-terrain vehicles. Build a road!

Much agent engineering today resembles developing all-terrain vehicles.

When the environment is chaotic, improve adaptability. When rules are unclear, add context. When the agent loses its way, upgrade memory. When execution is unreliable, strengthen the harness.

But if we drive back and forth through the same mud every day, **why not consider building a road?**

Building it takes investment, but once it exists, every vehicle can use it. New vehicles need not overcome the same obstacles again.

Enterprise AI faces a similar choice.

Client enterprises also struggle with complex business environments, fragmented systems, and extensive manual coordination. They may not realize that, beyond adding tools and people, they can rebuild the business environment itself.

For enterprises with control over that environment, road building is a system-level improvement worth considering. B2B providers that do not control the “land” need opportunities to participate in improving the environment, rather than repeatedly customizing mud-capable vehicles for each customer.

All-terrain vehicles still have value, of course. The real world always has places roads cannot reach.

But where roads can be built, we need not leave every bit of complexity to the vehicles.

**Don't just keep building all-terrain vehicles. Build a road!**
