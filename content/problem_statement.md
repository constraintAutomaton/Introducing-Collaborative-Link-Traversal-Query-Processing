## Problem statement
{:#problem_statement}

### Proposal
{:#proposal}

This paper aims to create a SPARQL query paradigm called CLQTP.
It consists of using multiple SPARQL query engines with the aim of improving the completeness
of queries by exploring more of the search space and reducing the query execution time through the means of exchange of results.
Both problems have been engaged in the academic literature, but not in the case of LTQP from my knowledge and considering the distributed SPARQL querying domain [](cite:cites 8029358).
In this PhD project, I will apply this query paradigm in the context of Solid, 
which implies that there is a strong consideration for privacy during querying [](cite:cites Taelman2020)
and a structured environment that can be leveraged to speed up the query [](cite:cites taelman2023).
The first problem I try to solve is to increase the query completeness.
To do so, CLTQP attempts to explore more of the search space by having multiple query engines engaging in 
non-overlapping partitions of the huge or pseudo-infinite search domain and executing the query.
Hence, in the same amount of time, having more triple processes compared to an approach with one engine.
An important property emerging from the traversal of links is a structural proximity bias of the query results, which
means that from the link traversal method, some data sources tend to be discovered more easily regardless of their potential
influence on the query completeness and the interpretation of the query results.
The bias has two interconnected sources: a sensitivity to the initial conditions induced by the seed URLs and the structure of the web,
which is not a fully connected graph.
Hence, a data source that takes more steps to be accessed, in regards to the seed URLs, will be more difficult to discover.
Corollary, there is a bias based on the popularity of the data source, as it is easier to find a data source that is
referenced more times and in a wide range of data source types (by data source types, I mean data sources that focus on specific topics)
than data sources having the reverse properties.
Hence by exploring more of the search space, there is more chance to discover those data sources.
The second problem is to reduce the execution time, and we explore the mean of P2P caching to alleviate this issue.
[](cite:cites Hartig2011) demonstrates that caching in LTQP can help improve the completeness of results,
but in some conditions, the query execution time can be increased.
In the [literature](#literature_review_P2P_caching), there are contributions on the topic of P2P caching,
but from my knowledge, none engage with the problem of LTQP and its particularities,
such as long execution time, exploration of multiple sources, and difficulty for completeness,
which may change the conclusion of the caching and network strategy.
Additionally, in environments like Solid, privacy is an additional consideration for caching [](cite:cites 10.1145/2413176.2413215).
It has to be considered that a mechanism to incentivize reciprocity is necessary to ensure fairness and the good functioning of the system.
It can be implemented in multiple ways, for example, as an obligation to participate in a ratio of queries,
a number of triples or links to provide, and so on.
Their enforcement could be managed by a community-style structure with policies in that regard.
Given a user doesn't respect the policy, then they cannot access the results of that community,
so it is a form of social contract.


### Research question and Hypotheses
{:#research_question}

Building on the proposal and the related works of the [](#litterature_review) 
research questions and hypotheses are formalized to guide the study.
<ul>
<li><span class="question_hypothesis">Question 1</span>: Can we achieve better query result completeness (and access isolated data sources) 
and better query execution time in the context of LTQP by making multiple SPARQL query engines collaborate?</li>

<li><span class="question_hypothesis">Question 2</span>: How can we minimize the overlapping of data sources exploration during CLTQP to avoid useless repeated query processing?</li>

<li><span class="question_hypothesis">Question 3</span>: How can we reduce query execution time by utilizing P2P caching in the context of CLTQP?</li>

<li><span class="question_hypothesis">Hypothesis 1</span>: It is possible to partition the search space in the context of CLTQP,
in a way that the query processing time of overlapping data sources is less than the time to process distinct data sources.
</li>

<li><span class="question_hypothesis">Hypothesis 2</span>: We can exploit the structural aspect of Solid to obtain a ratio of query execution time
similar to their consideration in LTQP.
</li>

<li><span class="question_hypothesis">Hypothesis 3</span>: Given a large enough search space,
as in the number of data sources is such as the execution time is not dominated by the communication time,
then there is a reverse relation between the number of engines collaborating and 
the execution time and a direct relation with the number of data sources explored. 
</li>
</ul>


Question 1 is the main question of my work, which aims at determining if CLTQP is a useful query paradigm.
Questions 2 and 3, on the other hand, are asked to determine the efficiency of the specific method 
that will be employed to solve the two main problems.
Those questions can be extended to consider the number
of query engines and the types of scenarios (query, data sources, privacy policy, and so on) encountered.
The hypotheses are the intuitive expected results and set a ground base for the development of my approaches.
