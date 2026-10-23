An enterprise puts policies, product manuals, business documents, and historical records into a knowledge base, uses retrieval-augmented generation (RAG) to let AI retrieve information and answer questions.

Ask “What is the procurement process?” and it finds the policy. Ask “What are this machine’s specifications?” and it cites the manual. But ask “Will this order be delayed, and what should we address first?” and many judgments remain unfinished even after the relevant materials have been found. Which information belongs to this order? Do we need a factory-level summary or individual operations? Which gaps would change our actions, and which details can be set aside for now?

Being able to retrieve information does not mean it has been organized in the way the current question requires.

AI may then produce a seemingly comprehensive answer: “Supply chains, capacity, staffing, management, and other factors need to be considered together.” Every statement may be correct, yet we still do not know what to address first.

The experience is familiar. In meetings, someone invariably says, “We also need to consider corporate culture,” “Reality is often more complex,” or “Every solution has limitations.” After hearing this, we still do not know what to change in the proposal or what to do next.

These are “true but unhelpful statements.” Their problem is often not truth or falsehood, but a failure to explain how the addition relates to the current question and which judgment it changes.

From enterprise knowledge bases to meeting discussions, these situations share a modeling problem: within what scope, from which perspective, and at what level of detail are we discussing what? Without these conditions, related information can keep growing without bringing the problem closer to a solution.

Maps offer an intuitive comparison. Planning a journey from Beijing to Shanghai requires cities, airports, and railways. Getting from Shanghai Hongqiao railway station to a hotel requires streets, subway stations, and exits. Finding a room inside the hotel requires a floor plan. Room numbers are real information, but putting them all on a national transport map does not make that map more useful.

Modeling requires similar choices. It sounds like specialized technical work, but whenever we design systems, analyze business, or discuss proposals, we are already deciding which distinctions to preserve and which details to set aside temporarily.

Large language models can help us discover and express more structure, but these choices still need to be made. In [“Business Modeling is fundamentally about defining how business is represented”](https://rikkalab.com/en/digitalization/business-modeling/), I discussed what modeling does. This first article on modeling methodology takes up two further questions:

**How do we determine a model’s boundaries, and when is it sufficient?**

The first requires clarity about domain, perspective, and resolution. The second depends on the problem at hand.

## 01 | Domain × perspective × resolution

A domain establishes where concepts and rules apply. The same machine, within the maintenance domain, involves failures, work orders, spare parts, and restoration to service. Within asset management, it involves original cost, depreciation, and disposal. Both domains concern the same object, but need to express different business relationships and rules.

Perspective determines the standpoint and question from which we observe a selected domain. For the same repair, the equipment user wants to know when availability will be restored and whether normal work will be affected. The repair service provider wants to diagnose the failure, assign staff, and complete the repair. Both are in the same maintenance domain and examining the same event, yet need different information emphasized. A perspective may arise from a participant’s standpoint or from the current question. It is not necessarily equivalent to a job position.

[“Why do people and AI still struggle to use equipment information as more fields are added?”](https://rikkalab.com/en/cases/equipment-views/) describes a concrete case. Maintenance, quality control, asset, and operational information kept being added to an equipment register. The page became more comprehensive but harder to use. Even showing and hiding fields by role did not solve the problem: the same maintenance manager needs different information when handling a failure, reviewing the month’s maintenance, or assessing equipment replacement.

Equipment identity stays stable, while the information organized around it needs to change with the current question. This case shows the role of domain and perspective. Looking further at summaries and drill-downs within the same business reveals what resolution changes.

Resolution determines the level of detail represented. When examining production progress, a general manager may focus on each factory’s monthly order completion rate. A factory manager needs task progress by workshop. A team leader needs to know which operation is blocking a particular work order.

The information can come from the same production records, yet the resulting representations differ:

| Resolution | Represented content | Question supported |
| --- | --- | --- |
| Factory level | Completion rates and expected delayed-order counts by factory | Which factory needs intervention? |
| Workshop level | Task distribution, load, and progress | Which workshop is the bottleneck? |
| Work-order and operation level | A task’s state, reasons for waiting, and completion time | What exactly should be addressed? |

Moving from a summary to a drill-down is more than enlarging the same table. Aggregation folds individual record identities and details into ratios, distributions, or trends. Following links to underlying records unfolds those distinctions again, making specific problems locatable. The two levels need consistent metric definitions and relationships to connect them.

Maps work similarly. At a small scale, a city can be a point. Zooming in reveals districts, roads, and buildings. The point was not wrong; it simply was not intended to represent the city’s internal structure.

Together, these three dimensions determine which distinctions a model preserves. An object does not become a different object because the way we observe it changes, but the representation we need does change.

## 02 | Stop when further distinctions no longer affect the current judgment

Continue with the production example.

The general manager notices that one factory’s completion rate is low this month. If the question is simply “Which factory manager should I speak to first?” a factory-level summary may suffice. There is no need to read every work order first.

Deciding whether to send additional staff to that factory requires a closer look. A low completion rate may reflect insufficient staffing or materials that have not arrived. These causes call for different actions, so the distinction must be preserved.

A drill-down reveals that most delayed tasks are waiting for the same batch of purchased materials. Additional staff will not help. Procurement has confirmed an arrival date, and the existing schedule confirms that the order can still be delivered on time after the materials arrive. The decision can stop here: do not reassign staff for now; track the arrival.

Whether every affected work order and subsequent operation must be expanded individually depends on whether doing so would affect this judgment. With little delivery slack, further checking is necessary. If the existing schedule provides sufficient confirmation, there is no need to repeat a full analysis merely to see everything more completely.

The same data may allow continued drill-downs, but each drill-down addresses a different unresolved question.

Three checks make the stopping condition concrete:

- Would further distinctions change the available options or their ranking?
- Would they change judgments about feasibility, risk, or responsibility?
- Would they change the next action or the information that needs to be obtained?

If none would change, we can stop at the current resolution.

The claim that something “would not change” needs a basis. When a factor’s importance is uncertain, we can first investigate its effect. Establishing whether it matters does not require modeling the entire related domain.

The map analogy applies here too. If the estimated travel times of two routes suffice to choose between them, we do not need to inspect every intersection. But if one route involves a transfer with only five minutes available, walking distance inside the station becomes a detail that must be examined.

A reusable model should therefore state its applicable domain, perspective, resolution, and supported questions alongside its content. People or AI using it later can then decide whether additions are needed, without guessing which omissions were intentional.

## 03 | Automated knowledge graph extraction also needs these boundaries

This is also one of the problems automated knowledge graph extraction can encounter without modeling constraints.

Identifying entities, concepts, and relations in source materials answers “What did the source mention?” It has not yet answered “What kind of model do we need?”

Suppose we give AI a factory’s company introduction, equipment manuals, procurement policies, and production meeting minutes, and ask it to extract a knowledge graph.

The company introduction mentions factories, workshops, and products. An equipment manual describes one machine’s components in detail. Procurement policies specify approval positions and spending thresholds. Meeting minutes mention suppliers, orders, and reasons for delays. AI can extract many traceable nodes and relations from these materials.

But why does one machine expand down to its bearings while another has only a name? Why is procurement approval represented as a complete process while production scheduling has only a few descriptions? Perhaps simply because a detailed manual happened to exist for the former and not the latter.

The model’s resolution is then determined by the sources’ level of detail, and its boundaries by their coverage.

If the actual question is “Which orders may be delayed?” the bearing structure may be unnecessary for now, while relationships connecting orders, material shortages, expected arrival dates, and remaining operations are essential. Even if every extracted relation is correct, a graph missing these connections still cannot support the judgment.

This resembles combining travel guides, geological reports, and restaurant menus into a map. Some places show rock layers; others specify signature dishes. Yet no roads connect the destinations. There is plenty of information, but navigation remains impossible.

Extraction accuracy and model sufficiency need separate checks. The former asks whether the extraction is faithful to its sources; the latter asks whether the model supports its purpose.

Automated extraction should therefore be constrained by modeling goals. To assess order delays, first identify the required order, material requirement, supply commitment, and production task information. Then extract it at the necessary level of detail and check for gaps. If the materials lack expected arrival dates, the result should expose that gap rather than manufacture a sense of completeness through more unrelated nodes.

Coverage can be an extraction metric, but cannot alone determine when modeling should stop.

This is the concrete meaning of [Cognito Atlas](https://rikkalab.com/en/research/cognito-atlas/)’s principle of defining the coordinate system before identifying and constructing objects. Domain, perspective, and resolution provide grounds for deciding which objects and relations belong on the current map.

## 04 | Many unbounded debates keep changing the coordinates

“Is it still the same thing?”

The Ship of Theseus is a familiar example. A ship’s planks are gradually replaced until every plank has been changed. Is it still the original ship?

The discussion can continue: if the discarded planks are reassembled into a ship, which one is the original?

The question can keep expanding because “the same” may invoke different criteria.

Someone maintaining voyage records cares about which ship continues the original operating identity. A researcher studying ancient shipbuilding materials may care more about the original planks. Someone tracing maintenance needs the relationships between replacements and preceding and subsequent states. These questions require different representations; a single “yes” or “no” cannot answer all of them.

A more personal question is “Am I still the same person I was ten years ago?”

A person may have moved cities, changed careers and values, or no longer identify with their former self. Yet saying “I made that choice ten years ago” attributes the past and present to the same person.

At least two questions are involved: whether this is one continuously existing person, and whether that person’s characteristics remain the same. Philosophically, these can be distinguished as numerical identity and qualitative similarity. A person’s having changed greatly does not by itself establish that there are two people. Nor do two strangers become one person because their personalities and appearances are very similar.

Further questions arise when memory is lost or personality changes dramatically. Should personal identity be judged by bodily continuity, psychological continuity, or other conditions? These are philosophical questions that require further examination.

Distinguishing the questions does not necessarily give an immediate answer. It prevents “their personality has changed” from directly answering “are they the same person?” and makes clear where the discussion is stuck.

Business faces similar questions. If a machine’s motor, controller, and casing are replaced, is it still the original machine?

Its maintenance history may continue under the original equipment ID to preserve its full service history. Spare-parts inventory, however, must record the removed motor and the installed motor as two objects. Unless both sides explain what they are managing, one may insist that it is clearly the same machine while the other says that everything has changed, so it cannot be.

The answers use different identity criteria. Both sides’ facts may hold without resolving the disagreement.

Philosophical analysis can encounter the same pattern: domain, perspective, or resolution changes, while a proposition is expected to continue holding after that change. Local statements then face counterexamples from other scopes, and the discussion keeps expanding.

We need to ask why we are distinguishing the two situations and what the distinction would change.

The purpose may be clarifying concepts, checking logical consistency, or comparing explanations. It need not lead to practical action. We still need to specify the current question and which distinctions would affect its answer.

If the goal is to study different identity criteria, further exploration is valuable. If it is to decide which equipment ID should hold a maintenance record, we first need a rule for maintaining identity that can be applied in practice. Registering a repair cannot wait until every philosophical question about identity has been resolved.

## 05 | From constructive input to true but unhelpful statements

A discussion intended to solve a problem is a joint effort to build and refine a decision model sufficient to support action.

Suppose a team is designing procurement request approvals with approval levels based on spending amounts.

Someone adds: “Is the purchase already included in an approved budget? A budgeted purchase of fifty thousand yuan executes an existing arrangement; an unbudgeted one requires a decision on additional spending. Classifying only by amount misses this distinction.” This identifies a condition within the process that affects the basis and path of approval, so it belongs in the model.

Someone else says, “Organizations differ greatly, management practices keep changing, and every process has limitations.” This may be true. But without identifying a missed situation, its consequences, and a rule that should change, the comment does not help the team reach the current judgment.

We now have a concrete criterion for the “true but unhelpful statements” mentioned at the beginning: does the comment introduce a distinction that contributes to the current decision?

Its costs are concrete too. Hearing “We also need to consider corporate culture” may pause rule design while the team explains its organizational background. An agent adding “Reality is often more complex” requires further time explaining which situations have already been considered. Before settling the approval conditions, everyone has had to supply another round of context for reminders with no clear implications.

Whether a statement belongs in the discussion depends on what it contributes at that moment. Avoiding unnecessary remarks is, in this sense, a way of controlling the discussion’s resolution.

The same criterion distinguishes constructive feedback from an agent’s unproductive argument.

A user is designing a task assignment feature for an internal pilot. An agent points out: “The current design records who executes the task but not who is authorized to accept the result. After completion, it may be unclear who can close it.” This identifies a specific gap and explains its consequences.

If the agent merely keeps adding “Complex organizational relationships also matter,” “Departments may not cooperate in practice,” or “Corporate cultures differ,” without explaining how these affect this pilot, it can drag a local design into an endless organizational discussion.

The criterion is not whether the agent agrees with the user. It is whether it can explain:

**Why does this distinction matter to the current question, and which judgment would it change?**

An agent can also challenge the chosen domain, perspective, or resolution. A team focused only on its department’s speed might shift all information checking downstream. If an agent finds this would force repeated checks downstream and increase total delivery time, it has grounds to expand the analysis to the full process.

Expanding boundaries itself needs a reason. The existence of more connections in the world does not mean they all belong in the current discussion.

For people and AI alike, modeling includes restraint: identifying distinctions that must be preserved and details that need not be expanded yet. How far to draw the map depends on the next part of the journey. When further distinctions no longer affect the current judgment, let the model stop there and let action continue.
