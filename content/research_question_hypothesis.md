## Research question and Hypotheses
{:#research_question}

Building on the proposal of the [](#proposal) and of related works of the [](#litterature_review) research questions are formalized,
to guide the study. 

**Question 1**: Can we achieve better query result completeness in the context of LTQP by making multiple SPARQL query engine collaborate?

**Question 2**: How can we minimize the overlapping of data sources exploration during CLTQP?
Does the technique for the fragmentation of the domain should vary depending on the type of app?

**Question 3**: How can we exploit the structure of Solid pods and applications to restrict the links follow in the context of CLTQP?
Do these structural aspects have an influence on the result completeness and query execution time?

**Question 4**: How can we in the context of CLTQP share the cache of SPARQL query engine? And those cache reduces the query execution time? What is the influence of the number of engines sharing their cache with the query execution time? Are there scenarios where caching is better than others and what are the property of those scenarios?

In relation to those questions, these hypotheses are formed.

**Hypothesis 1**: It is possible to partition the search space in the context of CLTQP.

**Hypothesis 2**: We can exploit the links between the solid pods in relation to the domain of the application when distributing the search space. 

**Hypothesis 3**: Given a large enough search space it is possible to optimize the general query execution time by increasing the number of query engines 
in the collaboration.

**Hypothesis 4**: It is possible during CLTQP to share join and/or triple pattern to reduce execution time.

**Hypothesis 5**: It is possible during execution of CLTQP to delegate part of the search space to other query engines.