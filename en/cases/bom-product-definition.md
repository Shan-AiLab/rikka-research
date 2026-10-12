**The initial request: We already have the drawings—can AI generate the materials list automatically?**

In the electrical distribution cabinet business, drawings contain extensive information about products and configurations. Organizing that information into a bill of materials (BOM) is an important step connecting the technical proposal to procurement and production.

The customer’s initial idea was straightforward: give the drawings to AI, identify the components, their model numbers, parameters, and quantities, and generate a BOM to reduce the work of compiling it manually, item by item.

But assessing whether this approach was viable required answering another question: **did the drawings contain enough information to determine a BOM that could actually be used in the business?**

**Looking deeper: From what was recognized to what determines the required materials**

During the investigation, two gaps became clear.

The first was the definition of standard products. The customer produced both relatively standard products and nonstandard products. Even the standard products, however, had multiple configurations that still needed to be clarified. Different configurations required different materials. Until the configurations and material selection rules were explicit, drawings alone could not yield a complete BOM.

The second was material substitution rules. When a material needed replacing, there had to be explicit criteria for which alternatives were acceptable, under what conditions, and when engineering confirmation was required. Recognizing the names and parameters of two materials was not enough to establish that they were interchangeable.

This also gave the broad complaint of “inaccurate data” a more specific explanation: some of the difficulty arose from product definitions and business rules that had not yet been clarified. Improving drawing recognition accuracy alone could not resolve it.

Without those criteria, generating a BOM would continue to require repeated human judgment.

**Narrowing the scope: Define the standard products first**

After discussing this with the customer, we decided to begin by clarifying the standard products and turning the definitions already established into a small tool that people could try.

We selected six product models as a starting point and mapped each product model and its parameters to the corresponding BOM. Users could select a product model, enter parameters, and obtain the corresponding BOM. An engineering confirmation form captured the key questions that still needed to be resolved.

Material substitution rules involved more complex conditions and were left outside this phase. Nonstandard cases also needed a separate route for confirmation, so that unresolved judgments would not be built directly into the tool.

The first phase therefore established a clear path:

**Select a product model → Enter parameters → Generate the corresponding BOM → Confirm key engineering questions.**

**The result: Putting the clarified definitions to work**

This phase delivered a single-page tool covering six standard product models. The relevant departments are already using the tool and report an approximately 25%–30% improvement in efficiency for the work it supports.

The improvement depended on clarifying product definitions and parameter relationships within a limited scope. This also created a maintainable starting point for further development: add product definitions when introducing new models, specify parameter relationships when adding configurations, and establish applicable rules when handling material substitutions.

The original request to “generate a BOM automatically” was thus broken down into several different kinds of work:

- Recognizing information in drawings
- Determining standard configurations
- Handling nonstandard variations
- Assessing material substitutions

The criteria and implementation approach for each could be discussed and validated separately.

**What this case shows**

When an enterprise requests an AI solution, it has often already chosen an intuitive implementation approach, such as reading drawings to generate a materials list. Asking how the output will be used and what determines its correctness reveals which parts actually need to be addressed.

In this project, clarifying product definitions produced a useful tool for the immediate need while establishing more explicit business criteria for introducing AI later. The boundaries became clearer: which information needed to be recognized, which results could be generated according to rules, and which cases required human confirmation.
