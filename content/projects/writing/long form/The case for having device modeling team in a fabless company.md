---
title: The case for having device modeling team in a fabless company
status: wip
tags:
  - teambuilding
project: substack
---
I have worked as a device modeling engineer in a fabless company, and the most common question I get by far from people within and outside the company is - "Why do you need an internal modeling team? Doesn't the foundry do models?" A device modeling team is like having medical insurance. You think you don't need them, till you do. Here's why.

There are several reasons why a fabless semiconductor company, especially those working in the analog and RF space should consider having their in-house team of device modeling experts (or at least one person):

- Quality assurance of foundry device models
	- When an IC product design team commits to a technology node, they have to design or port all the foundation building blocks such as bias circuits and core IP blocks to the new node. This is typically a labour and cost intensive process. Making sure that the device models do what they are advertised to do is an essential step in this process. All the simulation hours that will be put into the design of these IP blocks and design optimizations that will be made should be based on solid device models to begin with. This is where foundry model QA comes in.
	- An in-house device modeling team can vet the device models against in-house measurement data to ensure that the models capture important phenomena before they are used for circuit design. Additionally, testing structures such as ring oscillators, amplifier cores, and other critical blocks, pre and post-layout extraction can bring out subtle double counting issues that might exist in the model-PDK parasitic extraction interaction.
- Tailor device models to suit exact bias conditions used in the application
	- The role of a foundry provided device model is to cater to all customer products using that technology node. As a result, foundries are not inherently able to focus on one specific operating region over the other, and the resulting device model is built to have a reasonable fit over the entire IV space. Foundries cannot give you such a model because they do not know *a-priori* what the customers end application will be. They have to made models that are generally applicable.
	- Inside a company, however, the design teams usually know which region of bias is most important to their circuit operation. For example, a company designing products for the cellular market or wireless IOT will focus its efforts on low power operation. On the other hand, a company designing products for the wireless infrastructure market will like emphasize on high gain and high linearity.
	- Both these applications are entire different regions of the IV space - one low I and low V, while the other is high I and high V. As such, the device models can be optimized to provide improved accuracy depending on the region of operation.
	- But you can argue why the device model should not fit all regions of operation. After all is that not what a device model is supposed to do? Yes, but in reality that is never true. The accuracy and speed of model development does not usually keep up with modern complex devices. The physics is increasingly complex and not everything can be captured to the level of desirable accuracy
- Avoid re-spinning products due to systematic modeling errors
	- If in fact, there are errors in the device model that go unseen, several generations of product design might be conceived using incorrect models in that technology node. The mistakes propagate from one generation to the next resulting in sub optimal performance. In the worst case scenario, even RMAs.
	- Having even one in-house device modeling expert will easily pay for that person multiple times over if they are able to avoid respin of a single product. This becomes increasing important in state-of-the-art technology nodes due to increased maskset and tooling costs.
- Keep model improvements within the company to provide competitive advantage
	- Designing good products that beat the competition in performance metrics ultimately comes down to making the right design tradeoffs to squeeze out performance. To make good trade-offs require good device models. And once the model fixes are implemented in any tech node, it is in the company's best interests to keep that knowledge within its walls. Providing that feedback to the foundry means that all of the company's competitors have access to the improved device models too. And that means losing the competitive edge.
- Provide rapid changes to the device model to solve design issues
- Help understand if simulation results can be trusted
	- This can be done by comparing the model performance against more realisitic implements of the product on test vehicles.
	- This information can further be used to improve the models
	- Modeling engineers usually stay abreast of what device models are actually capable of simulating, what effects are captured and what are not.
- Capable of creating more state-of-the-art models using the latest model frameworks. They do not have to be beholden to the model being used by the foundry. Foundries are usually risk average, and wont risk trying out new stuff if they know that something might break. As a result, RF design still remains something of a dark art, when in-fact.
- Extended validation via load pull. Not all foundries validate loadpull on their standard device modeling flow. If it is important to the application, then an in-house modeling team can verify the accuracy of the nonlinear modeling.
- Support internal device development.