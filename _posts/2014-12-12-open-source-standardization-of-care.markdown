---
layout: post
title:  "Open Source Standardization of Care"
date:   2014-12-12 14:14
categories: introduction
tags:
image: /assets/article_images/2014-08-29-welcome-to-jekyll/desktop.jpg
---
I propose a platform for hosted health care order set, protocol, and bundle management that embraces key concepts of the open source software movement. If this product existed commercially, it might be called [GitHub](http://www.github.com/about) Health.

#Inspiration
I recently attended the [2014 World Symposium of Perinatal Medicine](http://www.worldsymposium.net/2014topics), a fantastic triennial conference that I can't recommend highly enough. That is where I had my first thoughts about open source standardization of care.

[Steven Clark, MD](http://www.ncbi.nlm.nih.gov/pubmed?term=Clark%2C%20Steven%20L%5BAuthor%5D) of the Baylor College of Medicine and Texas Children's Hospital delivered a presentation at the conference entitled, "Standardization of Care and Perinatal Outcomes Improvement," in which he shared his experience building a high reliability organization and the evidence backing up that approach. He advocated simple and sometimes obvious quality improvement strategies employing protocols to standardize approaches to commonly encountered clinical problems. The most primitive example he cited was an induction of labor order set he jotted down while taking a break from fishing.

Another presenter, [Alan Spitzer, MD](http://www.ncbi.nlm.nih.gov/pubmed?term=Spitzer%2C%20Alan%20R%5BAuthor%5D) approached the same topic from the other end of the spectrum as the Senior VP for Research, Education and Quality at [Mednax, Pediatrix Medical Group, and American Anesthesiology](http://www.mednax.net). He delivered a presentation entitled, "How do we safely improve care in the NICU?." In it, he highlighted the importance of measuring outcomes at every level of a health care organization and using that data to design and implement strategies to improve outcomes for underperforming providers and sites across the organization.

One of the messages I took away from each presenter was that there remain multitudinous targets for standardization of care across broad swaths of the medical landscape. On the other hand, there are immense challenges involved in the development of best practices within an organization. On top of that, there are further obstacles in the way of sharing them with the broader health care community. I considered all of these things against the backdrop of my experience as a rural provider affiliated with a small, independent hospital and concluded that there is just as much room for innovation in this space as in any other.

#Terminology
For those unfamiliar with medical practice, most of the care that is delivered, particularly in the hospital setting, is triggered by healthcare provider orders. Orders encompass everything from activity restrictions and nursing instructions to medication dosing and imaging requests. They used to be exclusively handwritten. Medication errors, in particular, were common. In 1999, the [Institute of Medicine](http://www.iom.edu) (IOM) released a report, ["To Err is Human: Building A Safer Healthcare System."](http://www.iom.edu/Reports/1999/To-Err-is-Human-Building-A-Safer-Health-System.aspx) In it, adoption of computerized provider order entry **(CPOE)** systems with clinical decision support modules comprised one aspect of the quality improvement strategy. CPOE systems are now much more common, but there remain major performance gaps between the best and worst of these systems.

When we talk about standardization of care, several terms come to mind: order sets, protocols, and bundles. There are semantic distinctions between these terms that I won't get into now, though the [Institute for Healthcare Improvement](http://www.ihi.org/resources/Pages/ImprovementStories/WhatIsaBundle.aspx) hosts a great discussion of what constitutes a bundle. Regardless of the differences in meaning, I submit that they can all be described using a common syntax. For this reason, and in a nod to the formerly pejorative term, cookbook medicine, I will hereafter refer to that underlying structure as a **recipe**. Specifically, a recipe is the machine-readable script of instructions that represents an order set, protocol, or bundle that conforms to an open standard.

Software developers are familiar with the terms version control system and **repository**, but they might be new ideas to clinicians. At the risk of oversimplification, a version control system allows a team of software developers to collaboratively access and modify project files with careful tracking and attribution of every change made along the way. There are usually specific work flows that support the management of new features, bug fixes, and releases. Repositories are the specialized file systems that house the projects. Such systems greatly simplify not only development but also distribution.

**Open source** is a term that has most frequently been applied to software development because that is where it originated. It generally refers to software for which the source code is available for inspection and modification, but it has since found applications across the spectrum of media under a variety of licenses. Licensing is a critical feature of all open source material and determines how it may be shared and modified. The written material on this site, for example, is licensed under the [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/legalcode). Licensing considerations are just as critical to open source standardization of care as they are to any other form of media. Existing licenses in the [BSD](https://www.gnu.org/licenses/license-list.html#ModifiedBSD), [GNU](https://www.gnu.org/licenses/license-list.html), and [Apache](http://www.apache.org/licenses/) spectrum may be entirely adequate to meet the needs of open source health information technology, but the choice of license will need to be considered carefully as the arena evolves.

#Implementation
What I propose is a software ecosystem that revolves around a central host of version controlled open source recipes that conform to a well defined specification.

###Recipe specification
The recipe specification ideally leverages existing tools and familiar data structures. Ideally, there already exists a specification for computer physician order entry (CPOE) for which EHRs already have integration modules, and which is openly available. Otherwise, I would recommend a lightweight CPOE JavaScript or CoffeeScript framework or a CPOE templating engine to handle not just data objects but instruction logic.

###Recipe managment
Consider a source code management platform like GitHub. Now imagine that instead of source code repositories, it hosts standardization of care repositories. Each recipe repository would track changes and attribute contributors along with optionally including a description of the recipe and providing citations for each component. Additionally, each repository would have its own permalink, be indexed for search, and have a rating. A public API would facilitate the development of authoring clients, mobile viewers, and EHR integration.

###Authoring
A capable first-party authoring client in the form of a web application is critical to the success of this project. Until a recipe specification is defined, we must just take it for granted that such an application would be produced before public release.

###Validation
A strong validation tool or test suite must be run against any recipe before sharing is permitted. With careful consideration of the recipe specification, it should be possible to develop a universal test suite that can be run against any recipe on the host any time a modification is made. While this would not obviate the need for client-specific testing in the case of EHR integration, it would provide a basic level of security to the community.

###Support
I'm not convinced that endorsement from policy makers and EHR vendors is absolutely critical to the success of this endeavor, but it would be immensely helpful to gain some support from industry or government in the initial drive to gain traction for a CPOE-like recipe specification. Health information technology does not have the best track record when it comes to interoperability, but I would treat this as an opportunity to make a positive change on that issue.

#Conclusion
In summary, what is needed is a recipe specification and a platform that supports authoring, version control, sharing, rating, searching, and viewing of care recipes along with an API to support the development of a range of client applications, including EHR integration.

I think such a platform has the potential to enhance sharing and accelerate adoption of best practices in standardization of care across organizational and regional boundaries and ultimately improve patient care and outcomes at all levels of the health care system.