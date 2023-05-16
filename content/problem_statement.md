## Problem statement
{:#problem_statement}

### Proposal
{:#proposal}

This paper aims to create a SPARQL query paradigm called CLQTP.
It consists of using multiple SPARQL query engines with the aim of improving the completeness of query
by exploring more of the search space and reducing the query execution time through the means of exchange of results.
Both problems have been engaged in the academic literature, but not in the case of LTQP and  particularly in LTQP in a structured environment from my knowledge and considering distributed SPARQL querying [](cite:cites 8029358).
In this PhD project, I will apply this query paradigm in the context of Solid, 
which implies that there is a strong consideration for privacy during querying [](cite:cites Taelman2020)
and a structured environment that can be leveraged to speed up the query [](cite:cites taelman2023, verborgh2020).

The first problem I try to solve is to increase the query completeness, particularly in the case of LTQP.
To do so, CLTQP attempts to explore more of the search space by having multiple query engines engaging in a 
non-overlapping partition of the huge or pseudo-infinite search domain and executing the query.
Hence, in the same amount of time, having more triple process compared to an approach with one engine.
The engines can either be independent and execute the whole query process themselves with little synchronization 
or they can in the other extreme specialize themselves and distribute the role of query processing. For example,
engines can specialize in the exploration of the search space and others on the joint of triples [](cite:cites 8029358).
An important property emerging from the traversal of links is a structural bias of the query results, which
means that from the link traversal method, some data sources have a tendency to be discovered more easily regardless of their potential
influence on the query completeness and the interpretation of the query results.
The bias has two interconnected sources: a sensitivity to the initial conditions induced by the seed URLs and the structure of the web,
which is not a fully connected graph.
Hence, a data source that takes more steps to be accessed, in regards to the seed URLs, will be more difficult to discover.
Corollary, there is a bias based on the popularity of the data source, as it is easier to find a data source that is
referenced more times and in a wide range of data source types (by data source types, I mean data sources that focus on specific topics)
than data sources having the reverse properties.
Hence by exploring more of the search space or even by making some engine having different lookup 
policies to answer a query there is more chance to discover those data sources.

The second problem is to reduce the execution time, and we utilize the mean of P2P caching.
[](cite:cites Hartig2011) demonstrates that caching in LTQP can help improve the completeness of results,
but in some conditions, the query execution time can be increased.
In the [literature](#literature_review_P2P_caching), there are contributions on the topic of P2P caching,
but from my knowledge, none engage with the problem of LTQP and its particularities,
such as long execution time, exploration of multiple sources and difficulty for completeness 
(can we start from cached results and continue the query from there), which may change the conclusion of the caching and network strategy.
Additionally, in environments like Solid, privacy is an additional consideration for caching [](cite:cites 10.1145/2413176.2413215).

It has to be considered that a mechanism to incentivize reciprocity is necessary to ensure fairness and the good functioning of the system.
It can be implemented in multiple ways, for example, as an obligation to participate in a ratio of queries,
a number of triples or links to provide, and so on.
Their enforcement could be managed by a community-like structure with policies in that regard.
Given a user doesn't respect the policy, then they cannot access the results of that community,
so it is a form of social contract.


### Research question and Hypotheses
{:#research_question}

Building on the proposal and of the related works of the [](#litterature_review) 
research questions and hypotheses are formalized, to guide the study.




<ul>
<li><span class="question_hypothesis">Question 1</span>: Can we achieve better query result completeness (and capture isoled data sources), 
better query execution time in the context of LTQP by making multiple SPARQL query engine collaborate?</li>

<li><span class="question_hypothesis">Question 2</span>: How can we minimize the overlapping of data sources exploration during CLTQP to avoid useless repeated calculation?</li>

<li><span class="question_hypothesis">Question 3</span>: How can we reduce query execution time by utilizing P2P caching in the context of CLTQP?</li>

<li><span class="question_hypothesis">Hypothesis 1</span>: It is possible to partition the search space in the context of CLTQP,
in a way that each engine can perform their query without the synchronization dominating the execution time.</li>


<li><span class="question_hypothesis">Hypothesis 2</span>: We can exploit the structural aspect of Solid to reduce the query execution time in CLTQP.
</li>

<li><span class="question_hypothesis">Hypothesis 3</span>: Given a large enough search space, as in the number of data sources is such as the execution time is not dominated by the communication time, then 
the more engines collaborating, the lower average execution time and the higher the number of data sources explored.</li>
</ul>
Question 1 is the main question of my work. It is to determine if CLTQP is a useful query paradigm.
Questions 2 and 3 aim at determining the efficiency of the specific method that will be employed to solve
the two main problems that I try to resolve. Those questions can be extended to consider the number
of query engines and the types of scenarios (query, data sources, privacy policy, and so on) encountered.
The hypotheses are the intuitive expected results and set a ground base for the development of our approaches.
