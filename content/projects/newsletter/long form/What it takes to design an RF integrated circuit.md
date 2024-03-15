---
title: What it takes to design an RF integrated circuit
tags:
  - circuit
project: substack
date_published: 
status: 🚧
final title: 
url:
---
The process of designing an RF integrated circuit (RFIC) is a long and arduous one. With the advent of AI, there is a lot of activity among researchers and industry to automate away the design process as much as possible. There is also an undercurrent in the industry that once AI takes over, knowledge workers are going to lose a lot of jobs.

In this article, I'd like to describe the process of RFIC chip design to the best extent I understand it. The purpose is to provide a glimpse into this world for readers who have not had a chance to work directly in this field. For people who do, perhaps this will still be instructive and maybe you'll take away some new perspectives you can apply.

Here,  we will discuss:
- thing1
- thing2
- thing3

Let's get into it!

---

## Specification and Program Management

The start of RFIC design in any company starts with answering the following questions:
- What does this RFIC do, and what industry does it serve?
- Who are the competitors to this design?
- What is the differentiating feature that will set this RFIC design apart?
- Who are the potential customers for this chip?
- What is the volume of expected sales and expected lifetime of the product?

The chip design can serve customers both internal and external to the company. While its easier to understand how a chip may be packaged up and sold to other original equipment manufacturers (OEMs), larger companies have chip design teams that provide products for the larger chipset or module they are building. 

The answers usually come from discussions between the technical sales and marketing team, and RFIC design managers. The technical sales/marketing teams meet with customers to define the requirements and then convene with RF design managers to come up with a specification that is both reasonable and achievable.

This requires a solid understanding of what is actually possible in terms of IC design from everyone involved. A lot of technical marketing folks I've worked with in the past, have been IC design engineers in their previous lives. Their experience is vital in communicating a reasonable specification to the customer and pushing back when they become too challenging to implement.

Once the specifications are agreed upon, they are handed to the IC design teams along with a completion deadline. The product has an official kick-off meeting where the high level details are presented to an audience containing marketing, design, technology, packaging, test and production teams. 

A program manager is usually assigned to the project who ensures that
- the product design is proceeding according to the timeline
- there is good communication between various teams involved
- monitors the workload of the different teams and maintains project statuses

Significant groundwork needs to be laid out before the design process can actually begin. IC design is quite an involved process as we will see. Laying a solid foundation in the beginning goes a long way in ensuring that the companies resources are being deployed appropriately.
## Circuit design

Let's say that an RF amplifier needs to be designed. What kind of circuit should you choose? This is where most young engineers especially fresh out of graduate school will be surprised. In most large companies, you will have surprisingly little leeway to implement any fancy design techniques you invented in your PhD program.

The bread and butter of RFIC design is still the basic circuits you learn in school, and most design managers are weary of implementing any "unproven" techniques published in papers or conferences. Design specifications are often based on a previous product that was successful. In all likelihood, using a similar circuit topology will ensure the greatest chances of success. 

You might even be designing a derivative product, i.e., a slight improvement on an earlier product. This could be a wider frequency range, a different supply voltage, or a few additional features. In such cases, there is no reason to start afresh with a new circuit topology. Simply use what has worked before and make the necessary changes.

If you're lucky to get to work on a brand new project that's not a derivative, it is important that you floor-plan first. The specification will define the overall chip area, and your design should fit into it. So don't plan on making any monstrous inductors. 

The best thing to do at this point is to quickly design a schematic and estimate the values of components that will be necessary. Plan out where your transistors will go, where and in what orientations your inductors will be placed, where your connections to the external world will be, and where the supply bypass capacitors will go. 

Most importantly, communicate with the packaging team and understand where the input-output pins should be placed. This will guarantee that your chip will fit into the desired package later. This is usually fixed early in the design for the large part, with only minor changes to accommodate things like extra ground connections.

Run some simulations in an electromagnetic tool if you need to validate that your floor-plan will work.  Mutual coupling issues between critical inductors in your chip should be caught early. Reorient them as necessary to find the optimal placement.

Circuit design is where the meat and potatoes are. This is the most exciting part of the process for most. You get to optimize the design to ensure that you extract the best performance possible. You iterate over the design to meet all the current draw requirements, gain, linearity and matching specifications provided. 

In addition, you will have to verify that the design:
- works over process variation by simulating corners and running statistical monte-carlo simulations
- works across temperature and voltage by simulating each case and evaluating performance

As your progress through the design phase, you develop a "feel" for how sensitive the design performance is to various components in the circuit. This is important for several reasons:
- you will include spare transistors, resistors and capacitors that are not connected to anything, so that you can hook it up in a metal redesign later if needed. 
- you will create "variants" of the design by over or under designing components to bracket the performance. This ensures that you get at least one working version.
- when the time comes to debug the circuit (and it always does), you know where to look based on the intuition you developed.

At this point arrives one of the most grueling parts of chip design: The Design Review. Or at least it should be grueling. Your design will be critiqued by a wide audience for many hours at a time. I've even seen teams of over 50 people critique a design for 4+ hours. This kind of critique is important because chip manufacturing is a costly (hundreds of thousands of dollars) and time-consuming process (many months) and the last thing a company wants is to make obvious mistakes that sets the program back.

Based on the design review feedback, you will be expected to make the changes suggested by the team. In most cases,  you will also run an extensive battery of extra simulations to verify the concerns raised in a design review. The key piece of advice here is to not take any of the critique in a design review personally even if it becomes a heated discussion. A rigorous and thorough design review is what makes a chip successful. Fixing problems that you missed after the chip is manufactured is infinitely harder. Understand that your colleagues are are trying to help you be successful.

Once you make the requested changes to your design based on the review process, there will be several follow up rounds to ensure that the changes haven't broken anything. The extra simulations you run will help prove to the team that critical issues brought up in the previous design review have been looked at. At this point, the design lead or manager will sign off on it and you're off to the races.

The official term is that you are now ready to 'tapeout', and the assumption is that you have already met all the requirements that make the chip manufacturable, and its time to export your design. The term tapeout itself comes from the time when paper tape or magnetic tape were loaded with design files to create photomasks at the factory. This is the overall flow, but we will look at several aspects in more detail.

## Designing for manufacturability

There are four major checks to satisfy that ensures a chip is manufacturable.
### Layout vs Schematic

Your schematic is what you've actually simulated in a circuit simulator to create your design. The layout is the actual placement of devices, components and trace routing that implements what your schematic is intended to do. The process of Layout vs Schematic, or LVS, ensures that the layout exactly represents what is on your schematic design.

You HAVE to pass LVS checks, otherwise there is no guarantee that whatever you have implemented in layout actually works the way it is intended to in practice. If you're a chip designer reading this, it seems obvious that this must be done. But I have seen far too many people not run LVS thinking that it the circuit is simple enough. The biggest culprits in my experience are device modeling and technology development folks who typically deal only with a single or a few devices at a time. I have seen far too many errors slip by without LVS checking. 

In many design teams, especially in large companies, the layout is done by a specialist team of layout experts. From an efficiency point of view, this is a reasonable approach. If you're a young engineer starting out, I highly recommend that you learn to do your own layouts. It is something of a rite-of-passage in my opinion, and it gives you an appreciation for what it takes to make a chip work in the real work.

### Design rule checks (DRC)

The chip foundry provides a set of highly specific rules that must be met to ensure your design can be reliably and repeatably manufactured. In Gallium Arsenide technologies, there are about 50 rules or so to be followed. But in advanced CMOS nodes, there are hundreds if not thousands of design rules to be met.

This is not usually possible to do visually, so electronic design automation (EDA) tools offer  design rule checkers that do the task for you. The process design kit (PDK) provided by the foundry implements these rules in the EDA tool. All you have to do is run the checker and make sure that no design rules are failing.

If you're new to designing chips and doing layout, passing DRC is harder than you think. The moment you think you fixed one error, you likely created two more. So DRC is an iterative process that takes time and experience. It is another reason that I suggest you do your own layout so that you get an understanding how DRCs work.
https://semiwiki.com/eda/synopsys/4062-design-rule-checking-drc-meets-new-challenges/

### Density Fill and Cheesing


- Density fill and why its needed. What is cheesing? Why is it needed?
- Run electromagnetics again if time permits.
- 
## Device Models, Parasitic Extraction and Electromagnetics
- Device models - a primer. What they are. What they're not. How much to believe them.
- What is parasitic extraction and why do we need it.
- How do device models interact with parasitic extraction
- Why EM is required? Where do you get the process stackup?
- What is the best EM tool? 
- Correlating EM tool accuracy



## Packaging, Board Evaluation and Testing
- Impact of packaging on the IC design
- Introduction of new ground planes and coupling paths
- Impedance control and good ground plane access on the EVB
- Testing a chip for all its specs - across voltages, temperatures and multiple samples.
- Generating the data sheet in collaboration with marketing.
- Providing samples to customers

## Iterations
- Few ICs work straight out of the gate. 
- Always correlate your measurements with simulation. this takes extra work but its worth it.
- There will be some spec not being met, or something the customer doesnt like
- Do a tapeout revision-- if you can use the spares to reconfigure the circuit, you can only do a metal mask spin. otherwise you have to do an all-layer change -- more $

## Productization
- what is involved here.