Discussions about agents often suggest the following future: traditional software requires people to follow predefined workflows step by step, while agents will only need a goal. They will understand the environment, call tools, and decide what to do next autonomously. Traditional workflows will therefore gradually lose their purpose.

This judgment is only half right.

The first problem is that what we call a “workflow” has never been a single mechanism. Dependencies within the business, the cognitive process of progressively resolving uncertainty, risk checks, access controls, and many operational steps introduced to accommodate the limits of traditional software have long been compressed into the same flowchart.

In [“Why must ‘approval’ be unpacked before an agent can automate it?”](https://rikkalab.com/en/cases/oa-approval-modeling/), I explored this through approval workflows. What looks like a complete workflow may, once unpacked, be a series of changes to business objects, with a few points requiring judgment in between. A flowchart records how these elements have been orchestrated; it does not mean the business inherently consists of those steps.

Agents make this mixture impossible to leave ambiguous. Once the actor doing the work no longer follows prescribed interfaces and steps strictly, we have to distinguish the routes previously laid down from the constraints that no actor can skip.

## 1. Coding agents are encountering problems software development has faced before

The software industry offers a useful way to understand this.

A product requirement cannot jump straight from “support refunds” to implementation simply because the eventual output is code. Traditional development involves requirements analysis, product design, technical reviews, testing, and other activities. These forms are not sacred or indispensable in themselves; complex implementation requires different kinds of uncertainty to be resolved progressively.

In [“Understanding agent harnesses in the context of digitalization”](https://rikkalab.com/en/digitalization/harness-in-digitalization/), I discussed an ordinary example: **why does a product requirements document (PRD) need review?**

A PRD is already a shared document, but product managers, developers, and testers reading the same passage do not necessarily imagine the same system. A review addresses differences in understanding, implicit assumptions, and questions about boundaries, then records the resulting agreement explicitly.

This also explains why the software industry has begun emphasizing specifications, plans, and reviews again as coding agents enter development. Conditions that previously remained implicit in engineers’ minds, meetings, and established working relationships suddenly become unreliable when the actor doing the work is an agent. They have to be made explicit again.

This is not the invention of a new method called “spec.” It is another encounter with the same fact: **complex work has cognitive dependencies.**

Agents can change how these dependencies are resolved. Several meetings might become an automated check, and traditional documents might become structured constraints. But greater execution capability does not allow an agent to jump from an ambiguous goal directly to a reliable result.

The form of a workflow can therefore change or even disappear, while the functions it performed must be preserved or replaced by new mechanisms.

## 2. Tool access does not provide action governance

Another frequently conflated question is what it means for an agent to be able to call tools.

MCP, tool calling, browser use, and connectors primarily determine which external capabilities an agent can access. In organizational terms, this resembles giving a new employee accounts for CRM, ERP, databases, email, and other systems.

Having an account does not mean the organization has decided which actions that employee should take under which circumstances.

In [“From agent authorization to a digital twin of responsibilities”](https://rikkalab.com/en/methods/agent-authorization-responsibility-digital-twin/), I discussed this gap. A system can grant “permission to create purchase orders,” but drafting a document awaiting approval and actually placing an order with a supplier create very different business commitments. What we usually want to delegate to an agent is work with a defined object scope, conditions, and responsibility boundaries, rather than a set of abstract action permissions.

MCP therefore provides **action access**, rather than **action governance**.

A `create_purchase_order` tool can tell an agent that an action is available. The tool alone cannot determine whether a purchase order should be created now, much less the amount thresholds, categories, or business states under which it may take effect without further approval.

Many such constraints used to be hidden in the division of responsibilities, workflow steps, and system interfaces. That made it harder to recognize the difference between these constraints and the ability to operate a system. As agents gain more freedom in calling tools, the distinction becomes much clearer.

## 3. Human organizations have never relied on actors always being right to ensure safety

This is one aspect of agent safety that I think most deserves another look.

Human organizations train employees, establish professional standards, and emphasize integrity, compliance, quality, and safety. But no mature system truly expects that instruction to make everyone’s judgment correct all the time.

Banks do not remove transfer limits because tellers have received ethics training. Manufacturers do not dismantle equipment interlocks because employees remember “safety first.” Software engineers knowing that they must not accidentally delete production data does not mean everyone should have unrestricted production access.

These mechanisms rest on an ordinary engineering assumption: **actors make mistakes.**

The aim of system safety is to limit the consequences of errors even when an actor makes a poor judgment, overlooks information, or takes an incorrect action, rather than to find an actor who is always right.

Some mechanisms restrict permissions before an action occurs. Others add checks before critical state changes. Still others use the system’s structure to make invalid states impossible. Their forms vary, but they all move part of the responsibility for safety from inside the actor to the external environment.

That is why increasingly capable models do not imply that these mechanisms will lose their purpose.

Better models can reduce certain errors, but they cannot replace risk governance itself. Seen this way, relying only on prompts or value alignment to constrain an agent capable of real action resembles basing corporate internal controls primarily on employee training. Training has value, as does alignment, but mature systems do not abandon external controls on that basis.

**“The model is smart enough” is not a safety mechanism, just as “employees are careful enough” is not an internal control.**

This leads to a more direct design principle: **agent permissions should be tiered by the consequences of failure, not by model capability.**

Whether an agent can perform an action on its own, requires confirmation from another authorized actor, or should be blocked by the system depends on the potential loss from failure, how easily the action can be reversed, and how much decision authority the organization is willing to entrust to a single actor—not on the model’s average accuracy.

Agent safety therefore requires more than improving the model’s judgment. It also requires designing **what the agent is actually allowed to do under different states and risk conditions**.

## 4. Safety means shaping the space in which agents can act, as well as telling them what to avoid

This approach is common in human engineering.

Mistake-proofing means that correct behavior does not depend entirely on a user’s memory and judgment. If two connectors must never be confused, give them different shapes. If shipping is prohibited in a particular business state, the system should reject the action directly instead of requiring operators to remember the policy every time.

The same applies to agents.

If an order cannot be canceled in its current state, that constraint should exist in the business state and action rules. If a decision exceeding an authorized limit requires another actor to intervene, the rule should not merely sit in a policy text for an agent to read, with the expectation that it will always comply correctly.

Safety design in agent-native systems must therefore address how to define the actions an agent can actually take, as well as how to help it understand correct behavior.

These aims are compatible. The actor doing the work needs to understand the context and rules. For high-risk constraints, the environment should also be able to reject invalid actions, limit their scope, or require additional confirmation for certain state changes.

This brings a traditional engineering idea back into agent architecture: **design the environment, as well as educating the actor.**

## 5. From controlling paths to defining executable business functions

This is the structural change agents bring to traditional workflows.

Fixed workflows used to both organize work and enforce safety because many rules were implicitly encoded in the path. B became visible only after A was completed. A button appeared only on a particular page. Some actions could not happen in practice because the system provided no entry point.

An A → B → C → D workflow therefore described how work was done while also restricting how people could do it.

Agents change this premise. They can read multiple information sources, call APIs, and choose their next action dynamically according to the current situation. If business constraints still depend on page sequences and workflow entry points, those constraints may fail when agents gain new paths for action.

The necessary change goes beyond replacing a workflow with an agent loop. We need to make explicit the business structure that was previously hidden in the path.

A traditional workflow might specify that a form passes through A, B, and C in sequence. Once unpacked, what we need to define may instead be which business objects a business function concerns, what ongoing responsibilities it carries, which facts an actor needs in order to perform it, which actions that actor may take under which conditions, what outcomes count as completion, and which boundaries require another responsible actor to intervene.

This is the definition of an **executable business function**, rather than the design of a path.

In [“Before discussing where to use agents, rethink business functions and the division of work in organizations”](https://rikkalab.com/en/digitalization/enterprise-agent-functional-division/), I examined the other side of this question. Once a business function’s scope of responsibility, object relationships, action permissions, and business rules are explicit, they provide a common basis for deriving what an actor should see, what it can execute, when it should be notified, and when escalation is required. People, traditional systems, and agents can then be recombined around these functions, rather than dividing work along the boundaries of existing jobs and software modules.

Agents do not turn workflows into a space of completely unrestricted action. What they may change is this: **instead of organizing work by hard-coding an entire execution path, a system first defines the business functions that must be performed continuously and their boundaries, then lets suitable actors complete specific tasks autonomously within them.**

Paths can change dynamically, as can the actors undertaking the work. The objects, responsibilities, rules, and completion conditions behind the functions remain.

This is also the greatest difference between an executable business function and a traditional job description. A phrase such as “responsible for procurement management” gives only a general direction. Only when it is elaborated into object scope, responsibilities, states, action permissions, rules, and collaboration interfaces does it become a business structure that systems can understand, actors can undertake, and ongoing checks can assess.

Agents need more than additional tools.

They need an environment that clearly expresses **what the work is, and how it can be completed within defined boundaries**.

## Conclusion: From workflow steps back to how business gets done continuously

Following this line of reasoning, whether agents will eliminate workflows becomes a less important question.

Some workflows will disappear because they are merely operational sequences left over from the limitations of traditional software. Some steps will be recombined because agents no longer need to follow prescribed pages and procedures strictly. But the business dependencies, judgment requirements, and governance boundaries those steps represented will not disappear when the path is dismantled.

The real change is that we can no longer be satisfied with expressing them indirectly through a sequence of workflow steps.

A workflow tells us whose turn comes next, but it does not necessarily explain why that actor needs to intervene, which objects and responsibilities are involved, what information should inform the judgment, or what the actor is allowed to change. People could previously fill in these meanings through experience. As agents enter real business work, these implicit structures increasingly need explicit definitions.

Once a workflow is unpacked, what remains is a question closer to the business itself, rather than an isolated action space:

**Which functions must the enterprise perform continuously, which objects do those functions concern, what rules do they follow, and which actors can undertake them within which boundaries?**

Clear definitions make flexible paths possible. Work performed today by people following a fixed workflow may tomorrow be redistributed among people, systems, and agents. Even within the same function, different paths can be chosen dynamically according to the state of the environment.

Agent-native systems therefore move from **prescribing execution paths** toward **defining executable business functions and letting actors act autonomously within their boundaries**, rather than toward a lack of structure.

This may be a deeper challenge agents pose to existing software and organizational arrangements as they enter enterprises. We finally have to articulate what has remained insufficiently digitalized beneath the question of how a workflow proceeds:

**How does the business actually keep getting done?**

Once the environment can reliably represent these functions, objects, and action boundaries, the next question is how an agent can stay connected to it, maintain its own state, and sustain action over long periods. This question is explored further in [“Understanding agent harnesses in the context of digitalization”](https://rikkalab.com/en/digitalization/harness-in-digitalization/).
