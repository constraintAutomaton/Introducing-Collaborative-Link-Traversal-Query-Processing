## Introduction
{:#introduction}



The [Solid Protocol](https://solidproject.org/TR/protocol), is an effort to "realise a space where individuals can maintain their autonomy,
control their data and privacy, and choose applications and services to fulfil their needs."[](cite:cites spec:solid) while using existing web standards.
It's principle are based on the [W3C TAG Ethical Web Principles](https://www.w3.org/TR/ethical-web-principles/).
However, those principal and the Solid Protocol motivations, does not concretly engage on the means that they will realise these principal and neither do they engage with the
economic disparity incresate by the web, which have an impact on the reach of the individual communication.
In those two documents, there is an assumption that the societal structure stay the same but that the web can change to forwards changws or maintain autonomu and control,
whitout clearly what is consider to be autonomy, what is privacy and what is control.
Nonetheless, the W3C TAG Ethical Web Principles and the Solid protocol propose descentralization as a mean to enhance individual power and control.
In this paper, we take the position that individual power and collective go one in the same.
Decentralization and federation can have multiple meaning it can be from above or it can involve directly the actor using the system.
In this paper we propose a collaborative aggretator inside Solid as a mean to keep the control of the user over social application futhermore 
it can also be use in more centralized context.
By collaborative

<!-- Let's define terms also, power autonomy privacy -->

---
<!-- General introduction about the web and it's problem, critic of the utopian vision, structural aspect of the problem-->
Popular narative claim that the web is a free, inovative and discrimination free environment.
<!-- reference-->
But the web exist into a social and economical environment with it's own inertia hence it have a tendency to reproduce certain aspect of society. Hence we

Yet the web have an emantipiraty carcacter-

[language](https://w3techs.com/technologies/overview/content_language)

<!-- website visited -->

<!-- cap rich and poor -->

<!-- type of content -->



societal/structural part of Linked data in general and Solid in particular
and the technical part.

## Proposal
{:#proposal}

This paper aims to create and propose a Link Traversal Query Processing (LTQP) that I decided to call
Collaborative Link Traversal Query Processing (CLTQP).
It consists of using multiple SPARQL query engine with the aim of improving the completeness of LTQP
Query by exploring more of the search space and to reduce the execution time by this exchange too.
In this PhD project, I will apply this query paradigm in the context of Solid, which imply
consideration to privacy, it also has to be considered that Solid pods have structure documented
using RDF vocabularies and web specifications, so the solution
has to exploit those already existing optimization.
The purpose is also to give to users of a community the ability to manage and generate their own computational power,
allowing social applications to function without relying on profit-driven enterprises, hence it is an
effort to deco modify the online information sharing.
The collaboration process can be divided into two parts: 
first, collaboration in exploring data sources, and second, collaboration in caching results and intermediate results.

The purpose of the first part is to investigate more of the search space,
indeed, in LTQP, the search space tends to be huge or pseudo-infinite
which means that it's difficult to guarantee completeness of results. 
We can nonetheless apply search strategies called reachability criterion to restrict the links followed by the
SPARQL query engine and use stopping condition such as a limit of time or triples to close the query processing.

An important property emerging from the difficulty of reaching completeness is the bias of the query results. 
This bias emerges from a sensibility to the initial condition, induce by the seeds URL provided to the engine.
We have to consider that in LTQP, we can only follow links encounter inside the data sources discovered,
via the triple present inside an already discovered data source;
also the web cannot be modeled as a fully connected graph;
hence some data sources are more difficult to access than others based on the first links provided to the SPARQL query engine.
Corollary, there is a bias based on the popularity of the data source has it is easier to find a data source that is
referencing more time and in a wide range of data source type (by data source type I mean data sources that focus on specific topics)
than data sources having the reverse properties.
But we cannot assume that less popular data sources are less relevant to the query response and to the
interpretation of the results, so it is profitable to facilitate their discovery.

A collaboration of SPARQL query engine could explore more of the search space by
dividing between them non-overlapping or minimally overlapping portion of the search space.
It is also necessary to share the result between each other, doing so might alleviate the problem stated above.

The second part can be divided into multiple consideration. [](cite:cites Hartig2011) demonstrate that caching in LTQP can
help improve the completeness of results, but in some condition the query execution time can be increased.
The second consideration is to be related to the first part, because there is a need to synchronize the results
between the query engine. 
The third is related to query performance as the same or similar query can have been executed previously by
other query engine and put into the cache hence, we can reuse those results to speedup the query execution time as
it has been demonstrated in the academic literature but in the case of querying of single sources.




<!-- 
* Problem statement
    * what is the problem that you are trying to solve? Importance: Why is this problem important and for whom? Who will benefit and who should care? What is the impact of solving this problem (for the research community, or society in general).
* Related work 
    * Has a solution to this problem been attempted before and how? If not, have research efforts tried or solved similar problems? What can you learn from these efforts? If you are addressing an existing problem, what are the limitations of current solutions? What are you adding that is novel? Why?
* Research question(s) and hypotheses 
    * What hypotheses do you make in formulating your solution? What are the questions you need to answer in order to solve the problem? Are there boundary cases you plan to exclude or assumptions you base on?
* Preliminary results 
    * What research methods did you follow in your proposal? Have you produced any results so far?
* Evaluation
    * How do you know you’ve answered your question(s)? What are the methods you apply to test your hypotheses? Have you identified criteria to measure the degree of success of your solution?
* Reflection and future work: Are there any limitations in your approach? What are your planned next steps to complete your investigation?

-->