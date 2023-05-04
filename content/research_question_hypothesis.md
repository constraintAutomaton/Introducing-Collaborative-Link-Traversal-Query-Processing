## Research question and Hypotheses

Building on the proposal above proposal of section [](#proposal) and of the section [](#litterature_review) we formalize research questions

**Question 1**: Can we archive better query result completness in the context of Linked Data Query Processing by making multiple SPARQL query engine collaborate?

**Question 2**: How can we minimized the overlapping of data source exploration during collaborative Link Traversal Query Processing?

**Question 3**: How can we exploit the structure of Solid pods and application to restrict the links follow?

**Question 4**: How can we in the context of Link Traversal Query Processing share the cache of SPARQL query engine?

In relation to those question I form the following hypothesis.

**Hypothesis 1**: It is possible to partition the search space of a Link Traversal Query Processing query.

**Hypothesis 2**: We can exploit the links betweens the solid pods in relation to the domain of application when distributing the search space. 
For example, in the case of a social media platform we can exploit the ration between folower and followed to distribute search space between
query engine.

**Hypothesis 3**: Given a large enough search space the it is possible to optimize the general query execution time by increasing the number of Query engine 
in the collaboration.

**Hypothesis 4**: It is possible to during Link Traversal Query Execution share join and/or triple patern to reduce execution time.

**Hypothesis 5**: It is possible to on to during execution to delegate part of the search space to an other query engine.