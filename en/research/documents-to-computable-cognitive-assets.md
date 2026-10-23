## 01 | Why documents are no longer the ideal unit for organizing knowledge

Traditional knowledge management centers on documents. A document contains knowledge, organizes relationships within that content, and presents it for people to read. Folders, directories, links, citations, and diagrams help people connect large numbers of documents.

This approach suits human reading and writing habits, but it has a long-overlooked problem: **knowledge definitions, relationships, and presentation are bound to individual documents.**

A business concept, for example, may appear in a concept explanation, a business architecture diagram, departmental responsibility definitions, a requirements mapping table, and a system design document. These references concern the same concept, yet they often have to be maintained separately. When the concept changes, each document must be updated. As content and relationships grow, maintenance costs rise and definitions can drift.

Documents also bind knowledge organization to particular forms of presentation. A hierarchical explanation works well for reading a classification but poorly for examining complex relationships. A relationship diagram shows connections but cannot accommodate detailed explanations. A mapping table helps check coverage but struggles to express the full logic of business operations. Producing different views often requires reorganizing or even copying the content.

The issue is therefore not that documents cannot express knowledge. It is that they perform three jobs at once: storing knowledge, maintaining relationships, and presenting views. People have traditionally maintained all three, and the flexibility of documents has compensated for their limitations. As AI begins to participate in ongoing knowledge production, we have an opportunity to redesign the relationships among these responsibilities.

## 02 | How can knowledge be organized beyond documents?

Moving beyond the constraints of documents first requires answering a more basic question: what exactly should we preserve and maintain independently of any particular document?

Knowledge cannot simply be equated with paragraphs of text, nor does it consist only of business objects, attributes, and relationships. Developing knowledge involves at least several kinds of knowledge units worth expressing independently.

**Concepts** define and distinguish the things, phenomena, and abstract categories we understand, such as business requirements, capabilities, responsibilities, tasks, and the entities or systems that perform or support them. Concepts need relatively stable identities so they can be referenced across documents, systems, and perspectives. Stable identity does not mean an unchanging definition, however. Conceptual boundaries still depend on the modeling purpose, business domain, perspective, and resolution, and may evolve as understanding develops.

**Propositions** express judgments, relationships, and regularities concerning concepts, objects, or phenomena. Examples include “An enterprise’s position in its industry and operating boundaries determine which business requirements apply to it,” “The same business capability can be realized through different combinations of people, systems, and other resources,” and “A business form is not the same as a business object.” Each can be discussed, referenced, and used in further reasoning independently. Concepts establish what we are talking about; propositions state what we judge to hold about it. Propositions may have conditions of applicability, grounds for derivation, supporting evidence, competing explanations, and open questions. They need not all be compressed into simple triples.

**Relations** connect concepts, propositions, and other knowledge units, expressing meanings such as composition, refinement, dependency, support, explanation, and derivation. Their types, directions, and conditions affect subsequent reasoning. Two items should not be connected by a vague “related to” relation merely because some association exists.

**Evidence and examples** support, challenge, or explain propositions while preserving sources and context. Examples help make abstract principles understandable, but a phenomenon observed in one case cannot automatically be elevated into a general rule.

These knowledge units can each have stable identifiers and connect through explicit relations. This does not require all knowledge to be broken into independent records immediately. It provides a finer organizing granularity for its ongoing accumulation.

The same concept can then appear in several articles, while the same proposition can be supported by multiple examples and participate in different theoretical derivations, without duplicating independently maintained definitions.

**The unit of knowledge organization extends beneath the document to concepts, propositions, and their relations. Documents become one way of organizing and expressing that knowledge.**

## 03 | Structured data, natural language, and existing intermediate representations

Structured data and natural language have distinct strengths and limitations.

Structured systems such as databases make identities, attributes, relationships, and constraints explicit, supporting queries, computation, and automated checks. But structured expression requires data types and organizational forms to be determined in advance. Knowledge exploration often involves concepts that are not yet stable, propositions still taking shape, and multiple possible explanations. Fixing structures too early can compress or distort knowledge to fit a data model.

Natural language is more flexible. It accommodates explanations, hypotheses, conditions, disagreements, and open questions, but lacks an explicit, stable structure for machine computation. A concept may be expressed in different ways, and many relationships remain implicit in the text. Subsequent participants must repeatedly reconstruct their meaning.

Human cognition and collaboration have never depended on these two forms alone, however.

In [“Word, Excel, PowerPoint: Overlooked infrastructure”](https://rikkalab.com/en/research/office-tools-representation-infrastructure/), I discussed the different information structures supported by three basic tools. Word primarily organizes linear text. Excel organizes information through rows, columns, fields, formulas, and references. PowerPoint provides a canvas for freely combining text, graphics, and spatial relationships. Their widespread use reflects the need for different external representations of different information structures.

Looking further at everyday diagrams and tables, we find many forms of representation between free text and strictly structured data.

| Representation | Main expressive capabilities |
| --- | --- |
| Tables and matrices | Objects, attributes, comparisons, mappings, and numerical calculations |
| Trees and hierarchy diagrams | Classification, decomposition, containment, and hierarchical structure |
| Relationship networks | Nonhierarchical connections, dependencies, and topology |
| Flowcharts | Activity sequences, conditional branches, and execution paths |
| State machines | Sets of states, transition conditions, and lifecycles |
| Timelines | Event sequences, change histories, and temporal relationships |
| Architecture diagrams | System composition, responsibility boundaries, and module relationships |
| Rules, constraints, and formulas | Conditions, restrictions, judgments, and computational logic |
| Programs | Executable operations, transformations, and computational processes |

These do not all belong to a single category of “semistructured data” in a strict sense. They share a characteristic, however: specialized representations make some of the structure implicit in natural language explicit.

Flowcharts preserve activity sequences and branches; relationship diagrams emphasize connections between objects; state machines specify permitted state transitions. Compared with plain text, they express particular structures more directly. Compared with strict data models, they usually retain greater expressive freedom.

Yet **expressing structure does not establish a computable semantic structure.**

An arrow between two boxes in PowerPoint may mean dependency, invocation, transfer, or influence. Without explicit semantic definitions, a machine may recognize the arrow without knowing what the relation means. “Responsibility” appearing in different diagrams may also lack a stable identity that allows those references to be matched.

These representations help people understand, but people still often have to reconstruct and maintain the semantic connections among them.

We therefore do not need a universal format to replace every diagram and table. We need different representations to retain their strengths while referring to shared knowledge definitions and supporting further computation, checking, and transformation.

This connects directly to [“Representation: What AI can understand depends on how the world is represented”](https://rikkalab.com/en/research/representation/). Representation always involves purposeful selection from reality, and different forms preserve different kinds of distinctions. The question is how those distinctions can be reliably matched across actors and representations.

## 04 | Cognitive IR: An intermediate layer connecting knowledge and its representations

Cognitive IR (cognitive intermediate representation) aims to externalize the knowledge, grounds for judgment, rules, and relations needed for collaboration into expressions that can be shared, inspected, and reused.

It does not assume that we can reconstruct the complete internal cognitive processes of humans or AI. It focuses on external cognitive structures that support ongoing collaboration. Different actors need not have identical internal understanding. Reliable references to shared concepts, relationships, states, constraints, and results can allow them to continue one another’s work across tasks.

In [“From shared representation to a computable world”](https://rikkalab.com/en/research/shared-representation-computable-world/), I discussed how whiteboards and diagrams relate to Cognitive IR, and how shared representations can develop into digital environments that maintain states and support action. Here, the focus is the engineering question: how can knowledge acquire a computable, maintainable structure while retaining expressive flexibility?

Cognitive IR is not a particular file format, nor does it require all knowledge to end up in a database. Current lightweight engineering practices offer an example with several distinct layers.

### Metamodels and schemas: Semantic definitions and structural constraints

**A metamodel defines the basic concepts, relations, and modeling rules used to describe a particular kind of domain.** Business modeling, for example, needs to clarify the meanings of requirements, capabilities, business functions, responsibilities, objects, and tasks, along with the relations permitted among them.

A metamodel belongs to the semantic layer. It can be expressed through a combination of natural language, structured definitions, and formal rules. It is not equivalent to a database structure or a JSON Schema file.

**A schema defines how a class of structured records is organized and which structural constraints it must satisfy.** A concept record might have an ID, name, definition, and source references; a relation record might contain a relation type, source node, and target node. A schema can further specify field types, required fields, allowed values, and some formal rules.

The distinction is that a metamodel explains what concepts and relations mean in the business, while a schema specifies how they are recorded and constrained within a particular data structure. One metamodel may correspond to several kinds of schema. Passing schema validation does not establish that a business definition is correct or a proposition holds.

Schemas should therefore develop gradually from relatively stable modeling needs, rather than forcing knowledge still under exploration into predetermined fields.

### Markdown and JSON: Natural language and structured content

Markdown suits theoretical explanations, concept descriptions, proposition derivations, examples, evidence, and open questions. It preserves natural language’s expressive capacity while remaining lightweight, referenceable, and suitable for version control.

JSON suits content with stable identities and explicit structures, such as concept records, proposition records, relations, source references, and necessary rule configurations. Schemas constrain how these records are organized; JSON stores their actual content. Their business semantics still come from the metamodel and related definitions.

A concept can be linked both to detailed explanations in Markdown and to structured definitions in JSON. There is no need to turn all natural language into fields. Relations or judgments that are not yet stable can initially remain candidate content with sources and confirmation status.

This gradual structuring allows incomplete knowledge to participate in work without sacrificing the possibility of later computation and reuse.

### HTML: Generating and interacting with knowledge views on demand

HTML and JavaScript can generate different interactive views from structured records and related natural-language content.

They need not serve as the authoritative store of knowledge definitions. They can support presentation, browsing, interaction, editing, and assisted checking. Views are generated from the relevant knowledge sources when needed, and changes should be written back to the authoritative location responsible for the corresponding definition.

`Markdown + JSON + Schema + HTML` can therefore form one lightweight engineering combination for Cognitive IR. Markdown preserves open expression, JSON stores stable structures, schemas supply structural constraints, and HTML organizes views. LLMs participate in understanding, transformation, reasoning, and consistency checking across these forms.

This is not a mandatory technology stack. Its design principle is to **organize semantic definitions, structural constraints, content storage, and view presentation separately, then connect them through explicit references.**

## 05 | Generating different views from the same knowledge

A direct consequence is that knowledge definitions can be separated from their presentation.

Consider the business concept of “responsibility.” It may appear in a business function hierarchy, a responsibility–object relationship diagram, a requirements coverage matrix, and a responsibility description. Previously, each often required separate maintenance. Now they can reference the same concept ID and associated relations, generating views for different tasks.

The process can be summarized as follows:

<!-- diagram:knowledge-views -->

**Shared cognitive structures**

Concepts · Propositions · Relations · Rules · Evidence · Examples

↓

**Select content by business domain, perspective, resolution, and intent**

↓

**Generate different views**

Concept lists · Hierarchy trees · Relationship diagrams · Mapping matrices · Flowcharts · State machines · Timelines · Document views · Inspection views

<!-- /diagram:knowledge-views -->

A user investigating conceptual structure can view a concept relationship diagram. To check coverage between business functions and objects, they can switch to a mapping matrix. To understand how work is performed, they can examine changes in tasks and states. Knowledge definitions are not copied when the view changes. Each view selects and organizes the same knowledge sources differently.

### A concrete example: Enterprise product information

Product information offers a particularly clear example.

The same product in a manufacturing enterprise may appear in R&D’s product definition, engineering’s specifications, sales presentations, marketing brochures, the website, selection guides, and customer proposals. These materials address different readers and concerns, but should remain consistent about what the product is, its models and configurations, capabilities, performance parameters, applicable scenarios, and promises that can be made externally.

In practice, different departments often maintain these materials separately. A design change updates technical parameters first, while sales continues using an old presentation and marketing’s brochure contains another description. Even with a document repository, the difficult questions remain: who determines which materials are affected, which descriptions need reconfirmation, and how to keep content consistent across channels?

Document retrieval alone cannot solve these problems. Retrieval-augmented generation (RAG) can help AI find scattered product information and answer questions, but retrieval does not automatically resolve differences in versions or conflicting definitions.

An alternative starts with product definitions that have stable identities. Product families, models, configurations, technical parameters, capabilities, and conditions of applicability can be organized into a structured model and explicitly linked to product explanations, test evidence, use cases, and approved selling points.

A specification sheet then need not be an independently maintained copy of product knowledge, nor does creating a sales presentation require manually copying technical information from another document. Each can select, combine, and generate content from the shared product model for its particular purpose.

The same product definition can produce different deliverables:

| Deliverable | Main knowledge used |
| --- | --- |
| Technical specification sheet | Models, configurations, parameters, and conditions of applicability |
| Product selection guide | Product families, configuration differences, and selection rules |
| Sales presentation | Capabilities, typical applications, and customer value |
| Marketing brochure | Approved selling points, performance evidence, examples, and visual assets |
| Website product page | Product summary, key parameters, applications, and related materials |
| Customer solution proposal | Current customer requirements, suitable products, configurations, and constraints |

Technical parameters can be generated from confirmed product definitions. Selling points and customer value still require judgment in the target context, with evidence, conditions of applicability, and review results retained. Model-driven production does not let marketing content bypass business judgment. It links that judgment to specific product facts, reducing the need for departments to organize and cross-check materials from scratch.

When a product model’s technical specifications or intended applications change, the system can follow relationships to identify affected product descriptions, selection rules, and marketing content. It can regenerate what can be determined directly and flag what requires human review. Historical versions can also be preserved to distinguish previously published content from current definitions.

**In this approach, enterprises primarily maintain product knowledge and its relationships, generating content for different purposes, rather than relying on departments to maintain multiple corresponding product documents.**

This goes beyond the main uses of traditional knowledge bases and RAG. Knowledge bases usually start by storing and retrieving existing materials. Model-driven content production can generate deliverables directly from relatively stable knowledge structures and trace the effects of definition changes. RAG can still retrieve supplementary information, examples, and unstructured material, without having to be the main mechanism for reconstructing product knowledge each time.

Product information is simply an accessible example. The same approach can apply to product manuals, internal training materials, business policies, architecture documents, and other knowledge artifacts whose consistency must be maintained by multiple parties.

### From entity identity to concept identity

This follows the principle I previously used in equipment management: “stable equipment identity, views assembled on demand.”

In [“Why do people and AI still struggle to use equipment information as more fields are added?”](https://rikkalab.com/en/cases/equipment-views/), I discussed why the same piece of equipment needs different information structures for asset management, maintenance, quality control, and operational analysis. Its identity does not change with the scenario, but the business relationships, history, and action interfaces that matter to the user do. There is no need to put all information on a single equipment detail page.

At the cognitive level, concepts take the place of equipment instances; definitions, propositions, and semantic relations take the place of business attributes and relationships; and knowledge views take the place of business views.

There is still a distinction. Equipment identity is usually determined by business identification rules, whereas conceptual boundaries depend on modeling purpose, perspective, and resolution, and may be redrawn as understanding develops. Stable identifiers support continued reference and evolution. They do not require every perspective to share one universal concept.

**Views cease to be separately maintained copies of knowledge and become different projections of the same knowledge structure.**

When views are generated from a single authoritative source, updates to definitions or relations can regenerate the relevant expressions, reducing drift caused by manual synchronization. Independently evolving projects can instead connect through references, mappings, and consistency checks, without being forced into centralized storage or a shared schema.

A similar approach can extend across architectural levels. [“From business and product to code: Three mutually computable architecture diagrams”](https://rikkalab.com/en/digitalization/business-product-technical-architecture/) discusses explicit mappings between business requirements, product capabilities, and technical implementation so that architecture views no longer depend solely on manual comparison.

## 06 | From storing documents to ongoing cognitive production

Natural language and structured systems have traditionally been separated by a substantial gap. People discuss business in documents; analysts then convert the results into fields, data models, and system rules. When the business changes, people must again determine how to update documents, databases, and applications.

LLMs offer new capabilities for connecting these activities. They can read concept definitions and modeling principles in Markdown, use an existing metamodel to identify knowledge units, propose JSON records or schema adjustments, and check whether structured expressions omit important meanings from the source text. People and AI can also use different views to discover missing relations, conceptual conflicts, and new directions for reasoning, then feed those findings back into the knowledge system.

Knowledge production can thus become an ongoing cycle:

**Natural-language exploration → Knowledge externalization → Structuring as needed → Computation and multiple views → Feedback from practice → Knowledge evolution.**

This is not a one-way transformation. A person examining a relationship diagram may discover a new question. AI designing a schema may identify distinctions not yet made explicit in existing concepts. Real business cases may require earlier modeling rules to change. Representations complement one another, while knowledge structures evolve through continued use.

Engineering can begin with a lightweight project. Markdown stores theoretical and design explanations, JSON stores structured models, schemas provide necessary checking constraints, HTML generates browsing and interaction interfaces, Git manages versions, and AI can read the whole project and participate in subsequent work.

This does not require a large unified knowledge platform from the outset. Projects can retain independent documents, models, and implementations while collaborating through explicit references and consistency checks. New knowledge from one project can inform a general metamodel, which can in turn help analyze concepts and relations across projects. Everything need not be copied into one place.

With stable references, clear relations, and maintainable sources, content scattered across chat histories, documents, diagrams, and systems can gradually enter the relevant knowledge and production environments. It becomes more than historical material for people to revisit: it can serve as input for subsequent AI analysis, design, judgment, and execution.

This is the key distinction between cognitive assets and static knowledge archives: **knowledge can be preserved and continually used by different actors, then corrected and extended through that use.**

## Conclusion

The main limitation of traditional documents is not insufficient expressive power. It is the tight coupling of knowledge definitions, relations, and presentation, which raises maintenance costs as content and connections grow more complex. Purely structured systems support computation but cannot alone accommodate open, complex, continually evolving knowledge. Diagrams, tables, trees, and flows express different structures, yet without stable semantics, people must still maintain the connections among them.

Cognitive IR seeks to connect these fragmented forms so that concepts, propositions, relations, and their grounds can be continuously referenced, checked, and used by different actors. Natural language preserves room for open explanation, structured data provides stable identities and relations, schemas supply necessary structural constraints, and views are generated on demand for the current cognitive task.

As these mechanisms develop, knowledge management can move from maintaining large numbers of static documents to maintaining a cognitive environment that people and AI can jointly understand, compute over, examine, and develop.

**We need more than containers for storing knowledge. We need systems that continually put knowledge to work in creating something new.**
