## Research project proposal
{:#proposal}

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
