## Problem statement
{:#problem_statement}

### Proposal
{:#proposal}

This paper aims to create a SPARQL query paradigm called Collaborative Link Traversal Query Processing.
It consists of using multiple SPARQL query engines with the aim of improving the completeness
of queries by exploring more of the search space and reducing the query execution time through the means of exchange of results.
Both problems have been engaged in the academic literature, but not in the case of LTQP and considering the distributed SPARQL querying domain [](cite:cites 8029358).
In this PhD project, I will apply this query paradigm in the context of Solid, 
which implies that there is a strong consideration for privacy during querying [](cite:cites Taelman2020)
and a structured environment that can be leveraged to speed up the query [](cite:cites taelman2023).


The first problem I aim to solve is to increase the query completeness.
In this context, I define the domain and the search space as a subset of a graph containing all the triple of the web of linked data
that can be explore by the query engine.
To increase the query completeness, CLTQP attempts to explore more of the search space by having multiple query engines engaging in 
non-overlapping partitions of the huge or pseudo-infinite search domain and executing the query.
Hence, in the same amount of time, having more triples processed compared to an approach with just a single query engine.
An important property emerging from the traversal of links is a structural proximity bias of the query results, which
means that from the link traversal method, some data sources tend to be discovered more easily regardless of their potential
influence on the query completeness and the interpretation of the query results.
The bias has two interconnected sources: a sensitivity to the initial conditions induced by the seed URLs and the structure of the web,
which is not a fully connected graph.
Hence, a data source that takes more steps to be accessed, in regards to the seed URLs, can be more difficult to discover.
Corollary, there is a bias based on the popularity of the data source, as it is easier to find a data source that is
referenced more times and in a wide range of data source types (by data source types, I mean data sources that focus on specific topics)
than data sources having the reverse properties.
Hence by exploring more of the search space, there is more chance to discover those data sources.
The second problem is to reduce the execution time, and I explore the method of P2P caching to alleviate this issue.
Hartig in [](cite:cites Hartig2011) demonstrates that caching in LTQP can help improve the completeness of results,
however, in some conditions the query execution time can be increased.
In the [literature](#literature_review_P2P_caching), there are contributions on the topic of P2P caching,
but none engage with the problem of LTQP and its particularities,
such as long execution time, exploration of multiple sources, and difficulty in attaining completeness
which may change the conclusion of the caching and network strategy.
Additionally, in environments like Solid, privacy is an additional consideration for caching [](cite:cites 10.1145/2413176.2413215).
For both problems, it has to be considered that a mechanism to incentivize reciprocity is necessary to ensure fairness and the good functioning of the P2P system.
It can be implemented in multiple ways, for example, as an obligation to participate in a minimum percentage of queries or
a number of links to provide.
This enforcement could be managed by a community-specific structure with policies in that regard.
Given that a user does not respect the policy, they cannot access the results of that community,
so it is a form of social contract.


### Research questions and Hypotheses
{:#research_question}

Building on the proposal and the related work of [](#litterature_review),
I formalize my research questions and hypotheses below:

- **Question 1**: Can we achieve better query result completeness
and lower global query execution time in the context of LTQP by making multiple SPARQL query engines collaborate?

- **Question 2**: Does the CPU usages and the number of HTTP request for each engine diminish with the increase of engine collaborating?

- **Question 3**: How can we prevent multiple query engines from repeating identical calculations over the same data sources?

- **Question 4**: How can we reduce query execution time using P2P caching in the context of CLTQP?

- **Hypothesis 1**: Given a large enough search space, in which it is possible to split it between the engines, 
there is an inverse correlation between the number of engines collaborating and 
the execution time, and a direct correlation with the number of data sources explored. 

- **Hypothesis 2**: It is possible to partition the search space in the context of CLTQP,
in a way that the query processing time of overlapping data sources is less than the time to process distinct data sources.

- **Hypothesis 3**: It is possible to index a P2P cache and create a procedure for its usage in the context of CLTQP
so that its lookup time is faster than the execution of the query.


Question 1 and 2, on the one hand, is the main question of my work, which aims at determining if CLTQP is a useful query paradigm.
Questions 3 and 4, on the other hand, are asked to determine the efficiency of the specific method 
that will be employed to solve the two main problems.
Those questions can be extended to consider the number
of query engines and the types of scenarios (query, data sources, privacy policy, and so on) encountered.
The hypotheses are the intuitive expected results and set a ground base for the development of my approaches.
