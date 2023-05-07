## Research project proposal
{:#proposal}

This paper aims to create and propose a Link Traversal Query Processing (LTQP) that I decided to call
Collaborative Link Traversal Query Processing (CLTQP).
It consists of using multiple SPARQL query engine with the aim of improving the completeness of LTQP
Query by exploring more of the search space and to reduce the execution time by this exchange too.
In this PhD project, I will apply this query paradigm in the context of Solid, which imply
consideration to privacy when querying [](cite:cites Taelman2020), it also has to be considered that Solid pods have structure documented
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
