---
title: A Beginner's Guide to the Process of RFIC design
tags:
  - circuit
project: substack
date_published: 2024-03-17
status: 🟢
final title: A Beginner's Guide to the Process of RFIC design
url: https://www.viksnewsletter.com/p/a-beginners-guide-to-the-process?r=222kot&utm_campaign=post&utm_medium=web
---
In this article, I describe the process of RFIC chip design to the best extent I understand it. The purpose is to provide a glimpse into this world for readers who have not had a chance to work directly in this field. For people who do, maybe you’ll get a fresh perspective. I do understand every company has their own way of implementing this workflow. My goal is to provide a general overview helpful to a newcomer in the industry.

**We will broadly discuss the following:**

- Process for getting specifications and starting design
    
- Planning, designing and reviewing a chip design
    
- Preparing a chip for manufacture - DRC, LVS, Density, Antenna
    

Let's dive in!

---

### Defining a Design Specification

RFIC design in any company starts with answering the following questions:

- What does this RFIC do, and what industry does it serve?
    
- Who are the competitors to this design?
    
- What is the differentiating feature that will set this design apart?
    
- Who are the potential customers for this chip?
    
- What is the volume of expected sales and expected lifetime of the product?
    

The chip design can serve customers both internal and external to the company. While its easier to understand how a chip may be packaged up and sold to other original equipment manufacturers (OEMs), larger companies have chip design teams that provide products for the larger chipset or module they are building. 

The answers usually come from discussions between the technical sales and marketing team, and RFIC design managers. This requires a solid understanding of what is actually possible in terms of IC design and knowing the playing field well. Prior experience plays a role in knowing what is possible to achieve in a given time frame, and pushing back when the specifications seem unreasonable. The technical sales/marketing teams drive meetings with potential customers to define what would constitute a product that could be sold to them.

### Project Kickoff

Once the specifications are agreed upon, they are handed to the IC design teams along with a completion deadline. The product has an official kick-off meeting where the high level details are presented to an audience containing marketing, design, technology, packaging, test and production teams. 

A program manager is assigned to the project who ensures that the product design is proceeding according to the timeline specified. They also make sure there is good communication between various teams involved, maintain workload reports and project status.

Significant groundwork needs to be laid out before the design process can actually begin. IC design is quite an involved process as we will see. Laying a solid foundation in the beginning goes a long way in ensuring that the company’s resources are being deployed appropriately.

### Understanding Design Needs

Once the specification for the design has been finalized, what kind of circuit should you choose to implement it? If you’re an aspiring RFIC designer, the answer may surprise you. In most large companies, you will have surprisingly little leeway to implement any fancy design techniques you learned in school, or invented in a graduate program. Smaller companies and startups provide more excitement in this regard.

The workhorses of RFIC design are still the basic circuits you learn in school. Most design managers are weary of implementing any "unproven" techniques published in papers or conferences. Understandably so, because they have a short time span in which their team has to deliver a fully working chip. 

Design specifications are often based on a previous product that was successful. In all likelihood, using a similar circuit topology will ensure the greatest chances of success. Proven circuits provide insurance against the unknown unknowns. 

You might even be designing a derivative product, i.e., a slight improvement on an earlier product. This could be a wider frequency range, a different supply voltage, or a few additional features. In such cases, there is no reason to start afresh with a new circuit topology. Simply use what has worked before and make the necessary changes.

### Floor-planning and Estimation

If you're lucky to get to work on a brand new project that's not a derivative, it is important that you floor-plan first. The specification will define the overall chip area, and your design should fit into it. So don't plan on making any monstrous inductors. 

The best thing to do at this point is to quickly design a schematic and estimate the values of components that will be necessary. Plan out where your transistors will go, where and in what orientations your inductors will be placed, where your connections to the external world will be, and where the supply bypass capacitors will go. 

Most importantly, communicate with the packaging team and understand where the input-output pins should be placed. This will guarantee that your chip will fit into the desired package later. Pin outs are fixed early in the design for the large part, with only minor changes to accommodate things like extra ground connections.

Run some simulations in an electromagnetic tool if you need to validate that your floor-plan will work. Mutual coupling between critical inductors in your chip should be caught early. Reorient them as necessary to find the optimal placement.

### The Design Process

Circuit design is where the meat and potatoes are. This is the most exciting part of the process. You have to optimize the design for the best performance possible. You iterate over the design to meet all the current draw requirements, gain, linearity and matching specifications provided. 

In addition, you will have to verify that the design works in all possible conditions. You will estimate impact of temperature, voltage, and process variation with corner and statistical monte-carlo simulations.

As you progress through the design phase, you develop a _feel_ for how sensitive the design performance is to various components in the circuit. You learn the black magic of RF design through trial and error. This is important for several reasons:

- You anticipate possible changes needed if your assumptions didn’t work out. To this end, you include spare, unconnected transistors, resistors and capacitors that so that you can hook it up in a design re-spin if necessary.[1](#footnote-1)
    
- You create "variants" of the design by over or under designing components to bracket the performance. This ensures that you get at least one working version.
    
- When the time comes to debug the circuit (and it always does), you know where to look based on the intuition you developed.
    

### The Design Review

This is one of the most grueling parts of chip design. Or at least it should be. Your design will be critiqued by a wide audience for many hours at a time. I've even seen teams of over 50 people critique a design for 4+ hours. Repeat that over a couple of days. This kind of critique is important because chip manufacturing is an expensive and time-consuming process[2](#footnote-2) and the last thing a company wants is to make obvious mistakes that sets the program back.

The key piece of advice here is to not take any of the critique in a design review personally even if it is stressful. A rigorous and thorough design review is what makes a chip successful. Fixing problems that you missed after the chip is manufactured is infinitely harder. Understand that your colleagues are trying to help you be successful and always thank them for their inputs.

Based on the design review feedback, you will be expected to make the changes suggested by the team. In most cases, you will also run an extensive battery of extra tests to verify the concerns raised in a design review. 

Once you make the requested changes to your design, there will be several follow up rounds to ensure that the changes haven't broken anything. The extra simulations you run will help prove to the team that critical issues brought up in the previous design review have been looked at. At this point, the design lead or manager will sign off on it and you're off to the races.

The official term is that you are now ready to 'tapeout', and the assumption is that you have already met all the requirements that make the chip manufacturable, and its time to export your design. The term tapeout itself comes from the time when paper tape or magnetic tape were loaded with design files to create photomasks at the factory. 

### The Final Countdown

Apart from the design simulations meeting the required specification, there are four major checks that need to be satisfied before the design leaves your hands.

#### #1: Layout vs Schematic (LVS)

Layout vs. schematic ensures that the physical connections on the chip accurately represent the schematic used for design simulations. Using your circuit design tool of choice along with the process design kit (PDK) provided by the foundry, you can run the LVS check quite easily with the click of a button. You _need_ to pass the check.

#### #2: Design rule checks (DRC)

The foundry provides a set of highly specific rules that must be met to ensure your design can be reliably and repeatably manufactured. As the technology node shrinks, the number of DRC that must be met exponentially rises.

https://semiwiki.com/eda/synopsys/4062-design-rule-checking-drc-meets-new-challenges/

This is not possible to do visually. Electronic design automation (EDA) tools offer design rule checkers that do the task for you. The process design kit (PDK) provided by the foundry implements these rules in the EDA tool. All you have to do is run the checker and make sure that no design rules are failing.

#### #3: Density Fill and Cheesing

Silicon technologies require the chip to be filled with millions of tiny little metal squares called “Density Fill” on every level to prevent the chip from collapsing on itself. Think of this as scaffolding inside the chip to maintain its physical integrity. There is a minimum and maximum level of density fill allowed on every metal level on the chip. This is defined by the foundry and is checked during DRC.

When designing RFICs, the density fill must be kept sufficiently far away from sensitive components like inductors and important traces on the chip. The metal fill affects the electromagnetic field distribution on the chip if it is too close, and alters circuit performance.

What’s worse is that there is almost no way to accurately take into account the effect of density fill on your chip. Some electromagnetic tools provide approximate methods, but it is best if you can avoid simulating its impact entirely by keeping it far away.

Cheesing is the process where wide metal lines on the chip are punched with holes, much like a slice of Swiss cheese. If density filling is the process of insertion of extra metal, cheesing is the selective deletion of metal. Cheesing is essential for uniformity, stress reduction and thermal management during wafer processing. These rules are also checked during DRC.

#### #4: Antenna Rule Checks

This has nothing to do with antennas in the conventional sense. Instead of [antenna effect](https://en.wikipedia.org/wiki/Antenna_effect), I much prefer “Plasma induced gate oxide damage” even if it’s a mouthful. These rules exist to ensure that the gate oxide of a transistor does not breakdown during chip processing. The excess charge built up during processing of metal when it is connected to a polysilicon gate needs to be discharged before it destroys the gate oxide. Usually diodes are strategically placed in the design so that the excess charge discharges through it instead of the gate oxide, thereby protecting it.

The actual antenna rules in a process PDK check that the ratio of metal area to the connected gate area is under a certain limit. If the rule is violated, antenna errors are flagged which must be fixed by the designer. Failing to fix antenna rules can result in reliability problems when gate oxides randomly break down.

### A Piece of Advice

If you're new to designing chips and doing layout, passing LVS, DRC, density fill and antenna rules is harder than you think. The moment you fix one error, you likely created two more. A lot of this is iterative and time-consuming but with enough repetition you will get better and faster at it. With enough experience, you will preemptively avoid violations from the start.

If you're a young engineer starting out, I highly recommend that you learn to do your own layouts. It is something of a rite-of-passage in my opinion, and it gives you an appreciation for what it takes to make a chip work in the real world. In large companies, teams of layout experts take care of all this, but it is still instructive to do it yourself as a learning experience.

[1](#footnote-anchor-1)

During manufacturing, each layer on the chip has a mask and if you can reconfigure your circuit with only metal rewiring, then the cost of a re-spin goes down. If you need to add to or change transistors in the design, it requires an “all-layer” re-spin which costs more.

[2](#footnote-anchor-2)

Depending on the technology node in question, the cost can vary from a hundred thousand to more than a million dollars for a single run. Processing time for silicon technologies is typically several months. Gallium Arsenide technologies need fewer masks and take a few weeks to a month.
