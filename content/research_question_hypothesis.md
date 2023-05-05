## Research question and Hypotheses

Building on the proposal of the section [](#proposal) and of related works of the section [](#litterature_review) research questions are formalized,
to guide the study. 

**Question 1**: Can we archive better query result completeness in the context of Linked Data Query Processing by making multiple SPARQL query engine collaborate?

**Question 2**: How can we minimize the overlapping of data sources exploration during Collaborative Link Traversal Query Processing?

**Question 3**: How can we exploit the structure of Solid pods and applications to restrict the links follow in the context of Collaborative Link Traversal Query Processing ?

**Question 4**: How can we in the context of Collaborative Link Traversal Query Processing share the cache of SPARQL query engine?

In relation to those questions,  those hypotheses are formed.

**Hypothesis 1**: It is possible to partition the search space of a Link Traversal Query Processing query.

**Hypothesis 2**: We can exploit the links between the solid pods in relation to the domain of the application when distributing the search space. 
For example, in the case of a social media platform we can exploit the ration between follower and followed to distribute search space between
query engine.

**Hypothesis 3**: Given a large enough search space it is possible to optimize the general query execution time by increasing the number of query engines 
in the collaboration.

**Hypothesis 4**: It is possible during Collaborative Link Traversal Query Execution to share join and/or triple pattern to reduce execution time.

**Hypothesis 5**: It is possible during execution of Collaborative Link Traversal Query Processing to delegate part of the search space to other query engines.