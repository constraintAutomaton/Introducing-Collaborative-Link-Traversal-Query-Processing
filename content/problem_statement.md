## Problem statement
{:#problem_statement}

### Proposal
{:#proposal}

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
dividing between them non-overlapping or minimally overlapping portion of the search space to query,
the sharing of the results between the engines is also a requisite for this collaboration.

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

Building on the proposal and of related works of the [](#litterature_review) 
research questions and hypotheses are formalized,to guide the study.

<div class="sidebysidecontainer">

<div>
<ul>
<li><span class="question_hypothesis">Question 1</span>: Can we achieve better query result completeness, 
better query execution time and less result bias in the context of LTQP by making multiple SPARQL query engine collaborate?</li>

<li><span class="question_hypothesis">Question 2</span>: How can we minimize the overlapping of data sources exploration during CLTQP?</li>

<li><span class="question_hypothesis">Question 3</span>: How can we in the context of CLTQP share the cache of SPARQL query engine? </li>

<li><span class="question_hypothesis">Question 4</span>: Does cache reduces the query execution time? What is the influence of the number of engines sharing their cache with the query execution time? Are there scenarios where caching is better than others and what are the property of those scenarios?</li>

<li><span class="question_hypothesis">Question 5</span>: Does the structure of decentralized web environment applications 
have an impact on the completeness and query execution time on CLTQP?</li>
</ul>
</div>


<div>
<ul>
<li><span class="question_hypothesis">Hypothesis 1</span>: It is possible to partition the search space in the context of CLTQP,
in a way that each engine can perform their query without too much synchronization and domain overlap.</li>


<li><span class="question_hypothesis">Hypothesis 2</span>: We can exploit the GLTQP technique in CLTQP to optimize the queries without producing too much overlap.</li>

<li><span class="question_hypothesis">Hypothesis 3</span>: Given a large enough search space, then 
the more engines collaborating, the lower average execution time and the higher the search space explored.
</li>

<li><span class="question_hypothesis">Hypothesis 4</span>: It is possible during execution of CLTQP to delegate part of the search space to other query engines by subsplitting the search space of the subject query engine by applying modification to their reachability criterium and link priority.</li>
</ul>
</div>

</div>