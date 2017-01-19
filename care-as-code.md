---
layout: page
title: Care as Code
permalink: /care-as-code/
---

Care as Code

Computerized physican order entry (CPOE) was originally conceived as a means to eliminate illegible written orders as a source of medical error and is in most cases augmented by a clinical decision support (CDS) system. CPOE with CDS effectively addresses problems surrounding order entry and post-order processing. Together they have improved health care efficiency and patient safety. However, they both ignore the critical pre-order contemplation phase of order entry. Order contemplation usually occurs in isolation or is facilitated by consultation with a peer or medical reference. A declarative approach to order design offers a straightforward solution for providing CDS during order contemplation without modification of the underlying CPOE system.

Before tackling this problem it is worth drawing a parallel between computer programming and patient care, or, more specifically, computer programs and provider orders. A computer program is a set of instructions expressed in a programming language designed to control a computer. There are many different programming languages, allowing software engineers to solve computing problems using any of a number of programming paradigms. The imperative and declarative styles of programming encapsulate two such paradigms. Imperative statements produce a result by describing how to return it. Declarative statements produce a result by describing what to return and leaving it to the language to determine the best approach.

Here's an example of an imperative order:
respiratory virus culture by nasal swab
oseltamavir 200mg PO BID for 5 days

Here is a declarative version of the same order:
test for influenza
treat influenza

The orders could even be chained together declaratively:
test for and treat influenza

Computerized provider order entry (CPOE) is a  piece of health information technology (health IT) systems. The motivation to move from written orders to CPOE is derived primarily from needs for increased legibility, eliminating a common cause of medical errors, and the opportunity to integrate physician orders with clinical decision support (CDS) logic (1). Although CPOE "has been shown to improve health care efficiency and patient safety," (2) a continuous effort to improve provider interactions with health IT should include consideration of the best approach to designing electronic orders.

A common pattern for CPOE with CDS follows. The provider searches for an order, selects the best option from the results, provides additional instructions such as timing and priority, and then submits the finished order. The CDS system, integrating relevant patient data, intercepts the order before being finalized and either approves it for submission or throws a context specific error, warning, or recommendation requiring a provider response. This provides a hitherto unachievable level of system level situation awareness and is the standard for CPOE and CDS.

Consider the steps involved in the above example. They are search, select, specify, submit, validate, and either accept, reject, or modify, and they can be grouped into 2 phases, order entry and post-entry processing. CDS systems effectively address post-entry concerns, but what if they could also anticipate the provider's needs or answer provider questions before the order is even placed in a third pre-entry phase, and how would that look?

Before a provider even considers entering an order, however, she must either want to know something about the patient or want to do something for the patient. In the days of paper charting the providers intent would be expressed in a series of individual orders, or in some cases in a pre-printed order set. The difference between individual orders and pre-printed order sets is analagous to the difference between turn-by-turn directions to a destination and its physical location. In one case you tell the GPS system how to guide you to your destination. In the other case, you tell the GPS system to guide you to the destination. Let's borrow some terminology from computer science and call the turn-by-turn directions imperative orders and call the destination declarative orders. Imperative orders describe the process of answering a question or performing an intervention. Declarative orders simply ask the question or request the intervention.

Influenza testing
Let's say you want to screen your patient for influenza.

The imperative paradigm would provide all the different options for respiratory virus testing:
rapid influenza screen
influenza/RSV PCR
respiratory virus culture

The declarative paradigm would provide one option: test for influenza A/B.

Imperative: influenza A/B and RSV nasal swab PCR

Declarative: test for influenza

In the imperative example:

The provider:
1) asks whether this patient has influenza
2) considers the different tests available for answering that question, rapid influenza screen, influenza and RSV PCR, and respiratory virus culture
3) orders one of the possible tests based on her knowledge of the availability, turnaround time, implications for infection control, and epidemiologic value

The system:
1) performs post-entry validation
2) submits the order to the lab or returns the order to the provider for modification

The institution:
1) provides education to medical staff regarding the availability of different influenza tests, their implications for infection control requirements, their epidemiologic value, and their seasonal availability repeatedly at multiple levels with variable penetrance.

In the declarative example:

The provider:
1) asks whether this patient has influenza

The system:
1) considers the available tests
2) orders one of the tests according to an algorithm designed by the CDS team
3) performs post-entry validation
4) submits the order to the lab or returns the order to the test algorithm to select the next best test

The institution:
1) provides education to medical staff regarding the availability of a simplified influenza test that takes into account various considerations to provide the fastest meaningful result with the least time spent on unnecessary infection control precautions
2) designs the CDS logic for the declarative order
3) reviews the CDS logic annually to take into account changes in testing technology and availability

The initial investment in designing the declarative order scales to reduced educational requirements and mental effort for each provider in the system who orders influenza testing and reduces the risk of exposing patients to unnecessary isolation and inappropriate testing.

(1) https://healthit.ahrq.gov/ahrq-funded-projects/emerging-lessons/computerized-provider-order-entry-inpatient/inpatient-computerized-provider-order-entry-cpoe
(2) https://healthit.ahrq.gov/ahrq-funded-projects/emerging-lessons/computerized-provider-order-entry-inpatient
