---
layout: page
title: Care as Code
permalink: /care-as-code/
---

Care as Code I: The Declarative Order Paradigm

The Care as Code series is meant to explore the parallels between medical practice and computer programming in the age of the electronic health record (EHR). Over the course of the series I will touch on such topics as providers as medical programmers, automation of patient care, and open source standardization of care. In this first installment, I argue that orders should be designed to reflect the intent of the provider rather than the logic of the underlying electronic system. It is the declarative order paradigm.

Computerized physician order entry (CPOE) was originally conceived as a means to eliminate illegible written orders as a source of medical error and is in most cases augmented by a clinical decision support (CDS) system (1). CPOE with CDS effectively addresses problems surrounding order entry and post-order processing. Together they have improved health care efficiency and patient safety (2). Now that the provider-computer partnership has been cemented, it is appropriate to continuously reevaluate how to harness that relationship to yield increased health care value. The discussion that follows will cover past and present models for provider order entry and present an argument in favor of moving toward a declarative ordering paradigm in health care similar to the declarative programming paradigm in computer science.

Orders are medical code

Orders are the building blocks of patient care. They determine the nature and timing of every intervention and measurement that happens to the patient. Orders are specific and elemental instructions that resemble the statements of a computer program, dictating an unambiguously specific action. Orders are, in a sense, medical code, and health care providers assemble them to program patient care.

It's worth taking a closer look at computer programming before revisiting the analogy. A program is a collection of instructions designed to control a computer. It is translated from technical but human-readable statements into processor specific machine instructions that can be simple enough to turn on a light or complex enough to model weather patterns. Some programs are so valuable that corporations can charge licensing fees to use them. Other programs are just as valuable but are offered for free. Regardless of complexity or motivation, every program starts with a problem in some domain for which their may be countless solutions. It is the job of the software engineer to devise a solution to the problem with attention to the cost, performance, maintainability, and reliability of the code. The job responsibilities may sound familiar to health care providers, but is that where the similarities end?

The computer programmer fortunately has the freedom to choose any number of languages with which to compose a solution, the style of which might be a particularly good match for the problem domain. Machine learning? Python. Statistics? R. Web development? JavaScript. Cross-platform computation? Java. String processing? Perl. Linux administration? Bash. The same options do not exist in health care. Providers program patient care using whatever language is dictated by the organizations in which they work. Just as in the early days of computing, it is up to providers and their organizational partners to work within the constraints of their systems to optimize their tooling for the shared purpose of enhancing health care value. A review of past order patterns may provide insight into current solutions.

Pre-EHR patient care

In the days of paper documentation a handwritten order was placed in the patient's chart by a provider in human-readable language conforming to conventions established by tradition and was interpreted by other humans down the chain until someone in pharmacy, laboratory, medical imaging or another service could translate it into action. Many providers who were trained in the paper charting era can still remember the feeling of opening a chart to a blank order sheet and relying on memory and a peripheral brain to handcraft a complete plan of care from individually handwritten orders. It was a daunting, time consuming, and rarely rewarding chore more analogous to programming a computer with punch cards than to using any modern programming language. Building a complex patient care plan on a foundation of handwritten orders invited medical errors related to illegibility, incompleteness, and unexplained clinical variance. Pre-printed order forms addressed some of those issues by allowing providers to quickly, completely, and consistently order common but complex plans with just a few check boxes and a signature, but they only covered a small fraction of the total patient care surface area.

CPOE and CDS

Then along came CPOE with CDS. Orders were no longer handwritten but were defined in advanced by the vendor or facility and then selected by the provider, usually through a search interface. The provider would search for an order, select the best option from the results, provide additional instructions such as timing and priority, and then submit the finished order. The CDS system, in turn, would intercept the order for validation, integrating relevant patient information before approving it for submission or throwing a contextual error, warning, or recommendation. This provided a hitherto unheard of level of system level situation awareness and became the standard for order management, though it hasn't been without some frustration. For instance, basic search algorithms and missing synonyms and acronyms can cause critical delays when trying to locate an order that could have been written in seconds.

It is usually the responsibility of the EHR or CPOE customer to design orders and make sure they integrate with the organization's infrastructure. In most cases, elemental orders are well represented in the EHR, and in many cases electronic order sets have been effectively leveraged in much the same way that pre-printed orders were used in the days of paper charting. The result is a system that works pretty well from day to day but rarely seems magical the way that advanced technology should. I propose that what is lacking is an opinionated design principle for computerized orders that takes both the human and computer actors into account to maximize the strengths and minimize the weaknesses of each. It is the declarative order paradigm.

Programming paradigms

There are as many programming styles as there are dialects of any human language, and programming paradigms provide an interesting scaffolding for the examination of ordering patterns. Two programming styles that are commonly contrasted are imperative and declarative. An example will be easier to follow than a description, so consider driving to a destination. Writing a series of turn-by-turn instructions on a sheet of paper is imperative. Entering the address in a GPS device is declarative. Imperative instructions are elemental and describe the journey. They require no high level abstractions. Declarative instructions are terse and describe the goal. But they depend on higher level abstractions. Both methods can be used to solve the same problems or even be used together, but the declarative style more effectively expresses the solution in terms of the goal.

Now consider medical orders. The imperative and declarative styles lie on a continuum. Handwritten admission orders are almost purely imperative. A printed order set or checklist lies somewhere in the middle. A bundle or protocol is almost purely declarative.

Declarative order design

Orders should be declarative. Wherever possible the orders in a CPOE system should reflect the provider's intent rather than the system's internal logic. The underlying logic of the declarative order should be visible to the provider, but it should not have to be specified by the provider. The elements of the declarative order should be individually available orders, but they should not be confused with the primary goal of the CPOE system, to expose the full range of provider intents as orders.

Another example will do here. Take the simple and common clinical question, "Does this patient have influenza?" The system likely already exposes a number of specific ordered for tests that can be used to detect influenza A/B, but the question should be exposed in the form of an order like, "Test for influenza." Such an order captures the clinical intent and encapsulates the logic involved in choosing the appropriate testing method and also acts as a form of documentation of the internal logic. It's worth dissecting this example.

*Clinical intent*
Answer the question, "Does a patient with 36 hours of cough, fatigue, and body aches have influenza?"

*Imperative*
Order options:
rapid influenza screen
influenza A/B and RSV PCR
respiratory virus culture
oseltamivir

Entered orders:
rapid influenza screen
oseltamivir (75mg cap PO BID for 5 days)

Order logic:
unchanged

*Declarative*
Order options:
test for influenza

Entered orders:
test for influenza (duration of symptoms < 48 hours)

Order logic:
if (rapid influenza screen is available)
  order rapid influenza screen
else
  order influenza A/B and RSV PCR
if (symptoms < 48 hours)
  order oseltamivir 75 mg cap PO BID for 5 days

Creating a CPOE interface that reflects the intention of the provider shifts the responsibility for awareness of details like test availability and value from the provider to the CPOE system while also providing transparent documentation of the declarative order's underlying logic. See a full breakdown of the provider, system, and institution level responsibilities for each paradigm below.

*Imperative responsibilities*

The provider:
1) asks which of the available tests is the best one to use for the circumstance, optionally seeking help from an outside source
2) asks whether the patient should be treated while awaiting a results, optionally seeking help from an outside source
3) enters orders for one of the available tests and oseltamivir

The system:
1) submits the orders to the lab and pharmacy

The institution:
1) provides education to medical staff regarding the availability of different influenza tests, their implications for infection control requirements, their epidemiologic value, and their seasonal availability via email, meetings, conferences, and posters with incomplete penetrance

*Declarative responsibilities*

The provider:
1) enters the order to test for influenza, specifying duration of symptoms when prompted

The system:
1) considers the available tests and the duration of symptoms
2) follows the order logic to choose the appropriate test and initiate appropriate therapy if necessary
3) submits the orders to the lab and pharmacy

The institution:
1) provides education to medical staff regarding the availability of a simplified influenza test that takes into account various considerations to provide the fastest meaningful result with the least time spent on unnecessary infection control precautions
2) designs the CDS logic for the declarative order
3) reviews the CDS logic periodically as part of a continuous improvement strategy

The initial investment by the institution and design team to create the declarative order delivers a return every time the order is executed and a patient is spared inappropriate testing and treatment.

Implementation

Should every conceivable order be expressed in a declarative style? Probably not. A reasonable first step would be to give someone on the design team the freedom to explore the technical requirements for some sample declarative orders and propose a framework for designing them. Understand the hurdles. Then as new orders are requested or unmet needs are identified they can be designed in declarative terms.

Discovering provider intentions is a challenge that is best met by measuring order behavior and patterns. Identify the most common orders, the most time-consuming orders, the most often canceled and abandoned orders. Ask providers to submit their intent with their orders. Give providers an opportunity to give feedback about and request declarative orders. Create a matrix of national standards from professional societies and government agencies, making an effort to track and implement each of them.

A bigger challenge than identifying unmet needs is devoting the resources necessary to meet those needs. Some existing processes might need to be reworked or even abandoned in order to gain efficiency. Replace meetings with asynchronous online collaboration and create new pathways for design and approval of declarative orders. Add employed technical staff or invite unpaid providers to participate in the design process. Cultivate a culture of continuous improvement that embraces change and accepts feedback on how processes can be improved.

Measure success. A declarative order is composed of imperative elements which together may be tracked in terms of time spent ordering or some other relevant metric. The same metric could be applied to the declarative version, and the two could be compared to generate an estimate of efficiency that either validates or invalidates the approach. Other measures might include variations of inappropriate testing or therapy.

Endpoint

Is it not true that the ultimate reduction of all provider intent is, "Take great care of the patient?" And if all patient care could be expressed in a single declarative order, would it be appropriate to do so? In time it might be. Maybe that should even be the goal. For now, though, providers and health care organizations should simply consider the declarative order paradigm the standard for designing new order sets.

(1) https://healthit.ahrq.gov/ahrq-funded-projects/emerging-lessons/computerized-provider-order-entry-inpatient/inpatient-computerized-provider-order-entry-cpoe
(2) https://healthit.ahrq.gov/ahrq-funded-projects/emerging-lessons/computerized-provider-order-entry-inpatient
