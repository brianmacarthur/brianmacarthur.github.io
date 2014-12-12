---
layout: post
title:  "Open Source Standardization of Care"
date:   2014-12-12 14:14
categories: introduction
tags:
image: /assets/article_images/2014-08-29-welcome-to-jekyll/desktop.jpg
---
I propose a platform for hosted health care checklist, protocol, and bundle management that embraces key concepts of the open source software movement. If this product existed commercially, it might be called GitHub Health.

#Inspiration
I recently attended the 2014 World Symposium of Perinatal Medicine, a fantastic triennial conference that I can't recommend highly enough. That is where I had my first thoughts about open source standardization of care.

Steven Clark, MD of the Baylor College of Medicine and Texas Children's Hospital delivered a presentation at the 2014 World Symposium of Perinatal Medicine entitled, "Standardization of Care and Perinatal Outcomes Improvement," in which he shared his experience building a high reliability organization and the evidence backing up that approach. He advocated simple and sometimes obvious quality improvement strategies employing protocols to standardize approaches to commonly encountered clinical problems. The most primitive example he cited was a medication management checklist that he jotted down during a 10 minute fishing break.

Another presenter, Alan Spitzer, MD approached the same topic from the other end of the spectrum as the Senior VP for Research, Education and Quality at Mednax, Pediatrix Medical Group, and American Anesthesiology. He delivered a presentation entitled, "How do we safely improve care in the NICU?." In it, he highlighted the importance of measuring outcomes at every level of a health care organization and using that data to design and implement strategies to improve outcomes for underperforming providers and sites across the organization.

One of the messages I took away from each presenter was that there remain multitudinous targets for standardization of care across a broad swathe of the medical landscape. On the other hand, there are immense challenges involved in the development of best practices within an organization. On top of that, there are further obstacles in the way of sharing them with the broader health care community. I considered all of these things against my background as a once rural provider affiliated with a small, independent hospital and how magnified these challenges are in that setting.

#Terminology
When we talk about standardization of care, at least 3 terms come to mind: checklists, protocols, and bundles. There are semantic distinctions between these terms that I won't get into now, though the IHI website has a great discussion of what constitutes a bundle. Regardless of there differences in meaning, they can all be represented by a common syntax. For this reason, and in a nod to the formerly pejorative term, cookbook medicine, I will hereafter refer to them collectively as recipes. Specifically, a recipe is the underlying data structure of a checklist, protocol, or bundle.

Software developers are familiar with the terms version control system and repository, but they might be new ideas to clinicians. At the risk of oversimplification, a version control system allows a team of software developers to collaboratively access and modify project files with careful tracking and attribution of every change made along the way. There are usually specific work flows that support the management of new features, bug fixes, and releases. Repositories are the specialized file systems that house the projects.

Open source is a term that has most frequently been applied to software development because that is where it originated. It generally refers to software for which the source code is available for inspection and modification, but it has since found applications across the spectrum of media under a variety of licenses. Licensing is the critical feature of all open source material that determines how the material may be shared and modified. The written material on this site, for example, is licensed under the Creative Commons Attribution-ShareAlike 4.0 International License. Licensing considerations will be just as critical to open source standardization of care as they are to any other form of media. Common licenses in the MIT, BSD, GNU, and Apache spectrum may be entirely adequate to meet the needs of open source health information technology, but the choice of license will need to be considered carefully as the arena evolves.

##Key terms
- recipe
- version control system
- repository
- open source
- licensing

#Implementation
What I propose is a software ecosystem that revolves around a central host of version controlled open source recipes that conform to a well defined specification.

##Recipe specification
The recipe specification ideally leverages existing tools and familiar data structures. Ideally, there already exists a specification for computer physician order entry (CPOE) for which EHRs already have integration modules, and which is openly available. Otherwise, I would recommend a lightweight CPOE JavaScript or CoffeeScript framework or a CPOE templating engine to handle not just data objects but instruction logic.

##Recipe managment
Consider a source code management platform like GitHub. Now imagine that instead of source code repositories, it hosts standardization of care repositories. Each recipe repository would track changes and attribute contributors along with optionally including a description of the recipe and providing citations for each component. Additionally, each repository would have its own permalink, be indexed for search, and have a rating. A public API would facilitate the development of authoring clients, mobile viewers, and EHR integration.

##Authoring
A capable first-party authoring client in the form of a web application is critical to the success of this project. Until a recipe specification is defined, we must just take it for granted that such an application would be produced before public release.

##Validation
A strong validation tool or test suite must be run against any recipe before sharing is permitted. With careful consideration of the recipe specification, it should be possible to develop a universal test suite that can be run against any recipe on the host any time a modification is made. While this would not obviate the need for client-specific testing in the case of EHR integration, it would provide a basic level of security to the community.

##Support
I'm not convinced that endorsement from policy makers and EHR vendors is absolutely critical to the success of this endeavor, but it would be immensely helpful to gain some support from industry or government in the initial drive to gain traction for a CPOE-like recipe specification. Health information technology does not have the best track record when it comes to interoperability, but I would treat this as an opportunity to make a positive change on that issue.

#Conclusion
In summary, what is needed is a recipe specification and a platform that supports authoring, version control, sharing, rating, searching, and viewing of care recipes along with an API to support the development of a range of client applications, including EHR integration.

I think such a platform has the potential to enhance sharing and accelerate adoption of best practices in standardization of care across organizational and regional boundaries and ultimately improve patient care and outcomes at all levels of the health care system.