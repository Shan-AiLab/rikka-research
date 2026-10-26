**Core principle: Every important business abstraction should be accompanied by concrete instances that can be checked. Abstract structures and instance data should participate in modeling together, rather than adding examples after the model is complete.**

## 1｜The problem: A self-consistent model is not necessarily correct

A common risk in business modeling is that concept definitions look rigorous, relationships appear complete, and the reasoning contains no obvious contradictions, yet the entire model rests on the wrong level of abstraction.

For example, during one metamodel design exercise, AI conflated two concepts:

- **object classification**: placing business objects into higher-level categories, such as relationship objects, requirement objects, and task objects.
- **business object definition**: a structured definition of a particular kind of thing in the business world, such as a customer, sales contract, contract deliverable, or purchase order.

Suppose a business metamodel already defines “object type” as a higher-level concept intended to represent categories such as relationship objects and requirement objects.

Later in the modeling process, however, the following definition appears:

> “Customer,” “sales contract,” and “contract deliverable” are different object types.

The problem is that these three concepts are different **business object definitions**, rather than object classifications in the sense established above.

This confusion is easy to introduce. In software engineering, “customer type” and “contract type” can indeed refer to different schemas. Each sentence may seem defensible in isolation.

But when “type” in the same metamodel sometimes means a higher-level category and sometimes a specific business object definition, the level of abstraction has drifted.

More subtly, this error need not produce an obvious logical contradiction. Even if actual customers, contracts, and other instances are mapped into the model, every individual mapping may work without revealing that “object type” has drifted between different levels.

This shows that **correct instance mappings do not establish correct abstraction levels; local logical consistency does not establish overall semantic consistency.**

AI collaboration amplifies this risk. AI can quickly generate logically coherent models, schemas, and documents while continuing to reason from an untested abstraction, embedding the initial conceptual confusion in subsequent designs.

Business modeling therefore needs both instances that test abstractions and checks on the abstraction system’s own levels and semantic conventions.

## 2｜The method: Present abstract structures and instance data together

Abstract modeling should show concrete business data as semantic anchors alongside concepts and their relationships.

Every important abstraction needs at least three kinds of checks.

### 2.1 Instance mapping: Can the abstraction explain concrete business facts?

Consider switchgear manufacturing:

| Abstract concept | Concrete business example |
|---|---|
| Product model | Switchgear model XXX |
| Product configuration | Rated voltage of 12 kV and rated current of 1,250 A |
| Product structure | Enclosure, circuit breaker, instrument transformers, busbars, and other components |
| Material | Vacuum circuit breaker, copper busbar, and other materials |
| Bill of materials (BOM) | Materials and quantities required for a particular model and configuration |
| Production task | A manufacturing task issued for a particular project and batch of enclosures |

The operation for this check is straightforward: **map concrete business instances into the model one by one, and check whether the model can express the business facts in those instances.**

If actual business records cannot be mapped to existing concepts, attributes, or relationships, record what cannot be mapped. Do not simply change the business facts to fit the model.

### 2.2 Boundary testing: Which situations reveal problems with concept boundaries?

Beyond checking whether existing instances can be mapped, actively seek situations that are easy to confuse.

For example, the same switchgear model may have different configurations in different orders. This raises further questions:

- Does a configuration change require a new product model?
- Can one standard BOM describe every order, or must the model distinguish a standard BOM from material requirements instantiated for a project?
- If a material appears in several product models, should it be independently referenceable, or can it only be represented as an internal component of a particular model?

These questions go beyond instance mapping. They are **boundary tests**: they examine the scope of existing concepts and whether further concepts or relationships need to be distinguished.

We can also introduce a conflicting case: an engineering change affects only some units in an order. Does this require an additional configuration level, or can the existing relationships between order lines and change records already express it?

The appearance of an unusual business situation should not immediately lead to a new object or attribute. First check whether the existing model can explain it and whether the distinction has stable, reusable business meaning.

Boundary testing asks whether **the scope of existing abstractions is reasonable**, rather than merely whether the model can accommodate one example.

### 2.3 Terminology consistency across abstraction levels: Does each term retain a consistent meaning at its intended level?

Instance mapping and boundary testing cannot replace this check.

For example, a metamodel may define “object type” as a higher-level category such as relationship objects or requirement objects, while other definitions use it to mean specific business object definitions such as customer or sales contract.

Even if every customer instance maps correctly to the “customer” business object definition, the confusion between terminology levels remains.

This check requires an explicit operation:

**List the model’s key terms, recording each term’s definition, level, and reference locations. When a term appears in several places, every use must be traceable to the same explicit definition. If it actually refers to different levels, distinguish the terms or revise the definition.**

Focus on these questions:

- Does each term have a stable, explicit definition within the current model?
- Is one concept being used to refer to things at different abstraction levels?
- Are the relationships among higher-level categories, business object definitions, and their schemas clear?
- Where a term admits several interpretations, are the contexts and meanings explicitly distinguished?

**Instance mapping checks the correspondence between abstractions and reality; boundary testing checks the scope of concepts; terminology consistency across abstraction levels checks semantic order within the abstraction system.**

These checks address different problems and cannot replace one another.

Constructed examples can explain an abstraction, but real business data can challenge it more effectively. Constructed examples are easily shaped to fit the author’s existing mental model, while real business data often reveals unexpected distinctions.

## 3｜Instances are not decoration added after the model is complete

A common sequence in traditional modeling and documentation is:

Define concepts → design relationships → complete the model → add examples.

This completes the abstraction first and then uses examples to explain it.

The problem is that, if the abstraction itself is wrong, subsequent examples may be selected or adjusted, consciously or otherwise, to fit the existing model.

A more reliable process is:

**Observe instances → propose abstractions → map instances → check conflicts and terminology levels → revise abstractions → expand the instance set.**

### 3.1 Propose initial abstractions from business records

Suppose we are building a production and procurement model for a medium-voltage switchgear manufacturer.

Begin by observing several kinds of actual business records:

- Sales order: a customer orders ten switchgear units.
- Technical proposal: six units use one configuration and four use another.
- Standard BOM: the product model already has a base material structure.
- Project material requirements: certain circuit breakers, instrument transformers, and other materials are adjusted to meet the customer’s technical requirements.
- Procurement records: some materials are supplied from inventory; others must be purchased.
- Production records: materials are ready for some enclosures, allowing their production to start first.

These records help identify initial business objects:

Sales orders, order lines, technical proposals, product models, BOMs, material requirements, procurement tasks, production tasks, and so on.

But we should not immediately fix all of them as independent objects.

For example, observing that the same product model uses different configurations in different projects leads to a hypothesis to test:

“Product model” and “project product configuration” may need separate definitions.

Then map concrete order data into those definitions:

| Project | Product model | Order quantity | Configuration |
|---|---|---:|---|
| Project A | KYN28-12 | 6 units | Configuration A |
| Project A | KYN28-12 | 4 units | Configuration B |
| Project B | KYN28-12 | 8 units | Configuration C |

*These are constructed examples illustrating the modeling method, not actual customer orders.*

The instances suggest an initial observation: product models can be reused, while configurations and quantities vary by project. Writing project configurations directly into a product model definition may therefore confuse a stable product definition with information that varies by order.

### 3.2 Introduce conflicting instances to challenge the initial abstraction

Now consider another situation.

*The following engineering changes and quantities are also constructed examples, not actual customer business records.*

Of the six units originally using Configuration A in Project A, two undergo an engineering change because of requirements at the customer’s site. The other four remain unchanged.

The initial model now faces a new question:

If “project product configuration” corresponds to just one order line, can different units under that line have different configurations?

Several modeling choices are possible:

- Split the order line into different configuration groups.
- Introduce independently managed configuration instances under the order line.
- Link engineering change records to the affected units.

Which choice is appropriate requires further examination of how the enterprise actually handles technical confirmation, changes, procurement, and production.

**The value of a conflicting instance is to reveal distinctions the original abstraction does not cover, rather than immediately prove a particular model correct.**

### 3.3 Revise the abstraction and broaden instance coverage

Suppose further examination shows that a change affects only two units for which procurement tasks have already been issued but production has not started. The modeling problem now extends to relationships among configuration versions, material requirements, procurement tasks, and production tasks.

We can then check:

- Which configuration instances does the engineering change affect?
- How do configuration changes propagate to material requirements?
- How should materials already purchased be handled differently from those not yet purchased?
- Are production tasks with all required materials ready affected in the same way as tasks still waiting for materials?

At the same time, check that the relevant terminology and object levels remain consistent. For example, “project product configuration” cannot be treated as a product definition in one place and a concrete business record within an order elsewhere without explaining the distinction.

The model must now do more than describe a static product structure: it needs to explain how business changes propagate through object relationships.

The point is to keep checking concrete business facts and abstract structures against each other, rather than design every object in one pass.

### 3.4 Avoid overfitting to a single instance

Instance-driven modeling does not mean adding an object or attribute whenever an unusual case appears.

For example, one customer’s temporary request to change nameplate text does not necessarily justify a separate “nameplate change object.”

First check whether an existing engineering change, delivery requirement, or configuration attribute can express it.

Instance checks must therefore guard against errors in both directions:

**Insufficient abstraction**: the model cannot express important business distinctions.

**Overmodeling**: every concrete difference gets an independent concept, reducing the model’s shared structure and reusability.

A good model does not create a special structure for every instance. It explains a sufficiently broad range of business facts with structures that are as stable and simple as possible.

### 3.5 When should the instance set stop expanding?

Instance checks do not require exhausting every possible business situation, nor increasing model complexity whenever an exception is found.

When additional instances no longer reveal problems with abstraction levels, concept boundaries, or key relationships, we can stop expanding the set for now and record the model’s current scope and uncovered conditions.

Restart the checks when new business facts, business rules, or system constraints arise.

**The stopping condition is not proof that the model is absolutely correct. It is that additional evidence currently no longer changes our judgment about the model’s structure.**

## 4｜Modeling deliverable standards

For important concepts, schemas, and relationship models, the following rules are recommended:

1. **Provide concrete instances alongside concept definitions.** Prefer real business data. When it is unavailable, use constructed examples and label them explicitly.
2. **Show a complete instance chain for hierarchical relationships.** For example: product model → project product configuration → BOM → concrete material requirements. Explain the business meaning of each level and its relationship with adjacent levels.
3. **Show concrete linked records for relationships between objects.** Naming relationships such as “contains” or “depends on” is insufficient; explain which specific object is linked to which other object.
4. **Test important boundaries with at least one easily confused instance.** Explain why it belongs or does not belong to the concept.
5. **Check terminology consistency across abstraction levels.** A term should have a stable meaning within the current model. Distinguish it explicitly when different levels need to be expressed.
6. **When instances cannot be mapped, check the model’s assumptions first.** Do not simply modify the data or force it to fit the model.
7. **Identify the source and nature of instances.** Distinguish real data, anonymized data, and constructed examples, so that reasoned scenarios are not mistaken for validated business facts.
8. **Explain why a new object, relationship, or level is needed.** Identify which problem an existing instance exposes that the model cannot explain, and whether a simpler expression is available.

## 5｜Specific requirements for AI collaboration

AI should do more than extend existing abstractions. After each important model definition, it should perform instance checks:

**Define → instantiate → test boundaries → check terminology levels → report conflicts → revise the model.**

When real data is unavailable, state explicitly that the work remains logical reasoning and has not yet been validated against business instances.

If an important abstraction lacks concrete instances, cannot distinguish neighboring concepts, or cannot explain how terms are used at different levels, treat it as an unresolved modeling question, rather than write it directly into a stable definition.

The following can serve as a default requirement for AI modeling collaboration:

> Whenever a new business concept, object level, or important relationship is introduced, provide concrete business instances, identify whether they are real or constructed, and try to find at least one instance that could challenge the definition. Also check whether the related terms have consistent levels and meanings within the current model.
>
> If instance mappings conflict, concept boundaries are unclear, or terminology drifts between levels, first report the problem, list possible explanations and their implications, and then decide whether to revise the model. Do not force changes to business facts to preserve an existing definition, or fix a schema before its key semantics are clear.

AI’s value is not only in generating structures quickly. It should also help discover reality that the current structure cannot explain, along with semantic problems the model itself has not yet resolved.

## 6｜The core principle

**Abstraction should help us explain the concrete world more accurately and economically, rather than take us further away from it.**

A good business model can form stable structures at higher levels while also explaining complex, concrete, and even irregular business facts at lower levels.

Instances are an indispensable way of checking abstractions, rather than an accessory to them.

Instance checks are not the whole task, however. Checking correspondence with reality, concept boundaries, and terminology levels together reduces the risk of a locally self-consistent model continuing to drift away from business semantics.
