## Problem statement
{:#proposal}

### Proposal
<span class="comment" data-author="RT">I'm wondering if we need the related work section before this one, because you go in quite some detail on link traversal, but the reader doesn't really know the background yet. Perhaps we can even merge this section with res questions and hypotheses, and call the section "Problem Statement".</span>

This paper aims to create a Link Traversal Query Processing paradigm called
Collaborative Link Traversal Query Processing.
It consists of using multiple SPARQL query engine with the aim of improving the completeness of LTQP
by exploring more of the search space and to reduce the execution time by the means of exchange of intermediary results.
In this PhD project, I will apply this query paradigm in the context of Solid, 
which imply that there is a strong consideration for privacy during querying [](cite:cites Taelman2020). 
Also, the structure of the data hosted inside the Solid pods [](cite:cites verborgh2020) and the structure of the virtual
social interaction that the users engage when using the app can be leveraged to optimize link traversal. 
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
dividing between them non-overlapping or minimally overlapping portion of the search space to query.
It is also necessary to share the result between each other.

The second part can be divided into multiple consideration. 
For the first one, [](cite:cites Hartig2011) demonstrate that caching in LTQP can
help improve the completeness of results, but in some condition the query execution time can be increased.
The second consideration is to be related to the first part of the collaboration,
because there is a need to synchronize the results between the query engines. 
The third is related to query performance as the same or similar query can have been executed previously by
other query engine and put into the cache, hence, we can reuse those results to speedup the query execution time as
it has been demonstrated in the academic literature but not in the case of LTQP.

### Research question and Hypotheses
{:#research_question}

Building on the proposal of the [](#proposal) and of related works of the [](#litterature_review) research questions are formalized,
to guide the study. 

<span class="comment" data-author="RT">The first question below is quite good, but I'm wondering if we can add some more structure to the questions.
    A suggestion: keep a variant of the first question as main research question, and then have questions on the 2 parts of your research: reducing search space, and caching. And then we can have corresponding hypotheses.</span>

**Question 1**: Can we achieve better query result completeness in the context of LTQP by making multiple SPARQL query engine collaborate?
<span class="comment" data-author="RT">Just better result completeness? Or also better in terms of other metrics, such as exec time?</span>

**Question 2**: How can we minimize the overlapping of data sources exploration during CLTQP?
Does the technique for the fragmentation of the domain should vary depending on the type of app?
<span class="comment" data-author="RT">I don't understand this second sentence.</span>
<span class="comment" data-author="RT">Is this question referring to the goal of improving discovery?.</span>

**Question 3**: How can we exploit the structure of Solid pods and applications to restrict the links follow in the context of CLTQP?
Do these structural aspects have an influence on the result completeness and query execution time?
<span class="comment" data-author="RT">Good question, but I don't see how it relates to collaboration. Perhaps it doesn't fit in your current topic?</span>

**Question 4**: How can we in the context of CLTQP share the cache of SPARQL query engine? And those cache reduces the query execution time? What is the influence of the number of engines sharing their cache with the query execution time? Are there scenarios where caching is better than others and what are the property of those scenarios?
<span class="comment" data-author="RT">Good one, but these are multiple questions. We'll have to either summarize, or decompose into multiple questions</span>

In relation to those questions, these hypotheses are formed.

**Hypothesis 1**: It is possible to partition the search space in the context of CLTQP.
<span class="comment" data-author="RT">Sure, it's trivial that we can do that :-) But to what purpose? What do we want to achieve exactly?</span>

**Hypothesis 2**: We can exploit the links between the solid pods in relation to the domain of the application when distributing the search space. 
<span class="comment" data-author="RT">Unclear what you mean by this. By the way, we may want to add a paragraph below each hypothesis/question to elaborate on them.</span>

**Hypothesis 3**: Given a large enough search space it is possible to optimize the general query execution time by increasing the number of query engines 
in the collaboration.
<span class="comment" data-author="RT">Perhaps this one can be simplified: "the more engines collaborating, the lower average exec time."</span>

**Hypothesis 4**: It is possible during CLTQP to share join and/or triple pattern to reduce execution time.
<span class="comment" data-author="RT">But how will you do this? What techniques do you hypothesize will achieve this?</span>

**Hypothesis 5**: It is possible during execution of CLTQP to delegate part of the search space to other query engines.
<span class="comment" data-author="RT">Let's rephrase this to something like: "by doing x, we can delegate part of the search space, and thereby lowering exec time."</span>