---
layout: post
title:  "Open Source Standardization of Care"
date:   2014-12-12 14:14
categories: introduction
tags:
image: /assets/article_images/2014-08-29-welcome-to-jekyll/desktop.jpg
---
I propose a platform for sharing and managing medical treatment algorithms that embraces key concepts of the open source software movement. If this product existed commercially, it might be called [GitHub](http://www.github.com/about) Health, and in Canada a similar platform already exists. It is the [Canadian CPOE Toolkit](https://cpoe-toolkit.ca/).

###Inspiration
I recently attended the [2014 World Symposium of Perinatal Medicine](http://www.worldsymposium.net/2014topics), a fantastic triennial conference that I can't recommend highly enough. That is where I had my first thoughts about open source standardization of care.

[Steven Clark, MD](http://www.ncbi.nlm.nih.gov/pubmed?term=Clark%2C%20Steven%20L%5BAuthor%5D) of the Baylor College of Medicine and Texas Children's Hospital delivered a presentation at the conference entitled, "Standardization of Care and Perinatal Outcomes Improvement," in which he shared his experience building a high reliability organization and the evidence backing up that approach. He advocated simple and sometimes obvious quality improvement strategies employing protocols to standardize approaches to commonly encountered clinical problems. The most primitive example he cited was an induction of labor order set he jotted down while taking a break from fishing.

Another presenter, [Alan Spitzer, MD](http://www.ncbi.nlm.nih.gov/pubmed?term=Spitzer%2C%20Alan%20R%5BAuthor%5D) approached the same topic from the other end of the spectrum as the Senior VP for Research, Education and Quality at [Mednax, Pediatrix Medical Group, and American Anesthesiology](http://www.mednax.net). He delivered a presentation entitled, "How do we safely improve care in the NICU?." In it, he highlighted the importance of measuring outcomes at every level of a healthcare organization and using that data to design and implement strategies to improve outcomes for underperforming providers and sites across the organization.

One of the messages I took away from each presenter was that there remain multitudinous targets for standardization of care across broad swaths of the medical landscape. On the other hand, there are immense challenges involved in the development of best practices within an organization. On top of that, there are further obstacles in the way of sharing them with the broader healthcare community. I considered all of these things against the backdrop of my experience as a rural provider affiliated with a small, independent hospital and concluded that there is just as much room for innovation in this space as in any other.

###Terminology
**CPOE:** For those unfamiliar with medical practice, most of the care that is delivered, particularly in the hospital setting, is triggered by healthcare provider orders. Orders encompass everything from activity restrictions and nursing instructions to medication dosing and imaging requests. They used to be exclusively handwritten. Medication errors, in particular, were common. In 1999, the [Institute of Medicine](http://www.iom.edu) (IOM) released a report, ["To Err is Human: Building A Safer Healthcare System."](http://www.iom.edu/Reports/1999/To-Err-is-Human-Building-A-Safer-Health-System.aspx) In it, adoption of computerized provider order entry (CPOE) systems with clinical decision support modules comprised one aspect of the quality improvement strategy. CPOE systems are now much more common, but there remain major performance gaps between the best and worst of these systems. For more information, see the [Leapfrog Group's Fact Sheet](http://www.leapfroggroup.org/media/file/FactSheet_CPOE2.pdf).

**OrderScript and recipe:** Standardization of care brings to mind several terms: order sets, protocols, and bundles represent a few of the most common concepts. There are semantic distinctions between these terms that I won't get into now, though the [Institute for Healthcare Improvement](http://www.ihi.org/resources/Pages/ImprovementStories/WhatIsaBundle.aspx) hosts a great discussion of what constitutes a bundle. Regardless of the differences in meaning, I submit that they all represent treatment algorithms that could be described with a common syntax. I will call the machine-readable version of that syntax OrderScript. And in a nod to the formerly pejorative term, cookbook medicine, I call a document that conforms to the OrderScript specification a recipe.

To summarize, a recipe is a treatment algorithm that is expressed in OrderScript.

**Repository:** Software developers are familiar with the terms version control system and repository, but they might be new ideas to clinicians. At the risk of oversimplification, a version control system allows a team of software developers to collaboratively access and modify project files with careful tracking and attribution of every change made along the way. There are usually specific work flows that support the management of new features, bug fixes, and releases. Repositories are the specialized file systems that house the projects. Such systems greatly simplify not only development but also distribution.

**Open source:** A term usually associated with software development, open source generally refers to software for which the source code is available for inspection and modification. These days open source material can be found across the creative spectrum under a variety of licenses. Licensing is a critical aspect of all open source material and determines how it may be shared and modified. The written material on this site, for example, is licensed under the [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/legalcode).

Licensing considerations are just as critical to open source standardization of care as they are to any other material. Existing licenses in the [BSD](https://www.gnu.org/licenses/license-list.html#ModifiedBSD), [GNU](https://www.gnu.org/licenses/license-list.html), and [Apache](http://www.apache.org/licenses/) spectrum may be entirely adequate to meet the needs of open source health information technology, but the choice of license will need to be considered carefully as the arena evolves.

###Implementation
What I envision is a software ecosystem that revolves around a central host of version controlled recipes that conform to a well defined specification.

#####OrderScript specification
Remember that a recipe expresses a treatment algorithm in a syntax that conforms to the OrderScript specification. That specification is yet to be defined, but the advantages of sharing an open standard are obvious.

One might question why it's necessary to define a new scripting language just to author, share, and discover treatment algorithms. After all, it would be possible to create a platform that hosts a searchable database of protocol PDFs and make them available for sharing, commenting, rating, downloading, and printing. And that alone would be an improvement over the current method of disseminating best practices in the medical community. A standard scripting language, however, would unlock several additional features that are currently lacking such as portability, EHR integration, simulation, and validation. This will be the subject of a later post.

To support interoperability, several public databases exist to enable normalization of codes, medications, and terms: [LOINC](http://loinc.org/), [ICD-10](http://www.who.int/classifications/icd/en/), [HL7](http://www.hl7.org/), and [RxNorm](http://www.nlm.nih.gov/research/umls/rxnorm/). More information about interoperability can be found at [HealthIT.gov](http://www.healthit.gov/providers-professionals/standards-interoperability) and the [Standards and Interoperability (S&I) Framework](http://www.siframework.org) site.

#####Recipe management
Consider a source code management platform like GitHub. Now imagine that instead of source code repositories, it hosts recipe repositories. Each repository would track changes and attribute contributors along with optionally including a description of the recipe and providing citations for each component. Additionally, each repository would have its own permalink, be indexed for search, and have a rating. A public API would facilitate the development of authoring clients, mobile viewers, and EHR integration.

Each repository would also have an owner, either an individual or an organization, who accepts or rejects contributions. Although other users would have the ability to fork a recipe, it would be accompanied by a clearly identified change in name and ownership. Contributors would be expected to disclose conflicts of interest, and industry contributions would be clearly identified under penalty of fines and litigation.

#####Stakeholders
There is room for a grassroots campaign to demand greater interoperability and sharing of not only medical knowledge but also medical best practices, but the task would be easier with support from policy makers and the EHR industry. The stakeholders with the most interest in improving sharing and interoperability of best practices in the form of recipes are providers and patients. They require a well articulated message to clarify the problems this proposal intends to address and the benefits that would be enjoyed by each group if it were successful.

A reasonable first step in gaining industry support would be to become an active participant in the S&I Framework and gain some official momentum within the Office of the National Coordinator for Health Information Technology. Health IT does not have the best track record when it comes to interoperability, but I would treat this as an opportunity to make a positive change on that issue, making improvements in patient care and outcomes the centerpiece of that drive.

#####Concerns
I recognize that consolidation of data brings with it real and perceived risks. The following questions are all reasonable. Who is allowed to contribute to the system and what are their credentials? How will the influence of the drug and device industries be either limited or clearly cited in an open platform? Could order scripting become a new target for hackers?

I will attempt to address these issues separately in a future post, but I do think there are effective measures available to mitigate those risks. And in an open system, there is room for continued debate and refinement of those measures.

For an interesting discussion of drug industry influence in the world of academic publishing, see [this BMJ podcast](https://soundcloud.com/bmjpodcasts/publishing-drug-funded-research?in=bmjpodcasts/sets/the-bmj-podcast).

###Conclusion
In summary, what I propose is 1) an OrderScript specification and 2) a platform that supports authoring, version control, sharing, rating, searching, and viewing of recipes that conform to that specification along with an API to support the development of a range of client applications, including EHR integration.

I think such a platform has the potential to enhance sharing and accelerate adoption of best practices in standardization of care across organizational and regional boundaries and ultimately improve patient care and outcomes at all levels of the healthcare system.