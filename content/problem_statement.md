## Problem statement
{:#problem_statement}

### Proposal
{:#proposal}

This paper aims to create a LTQP paradigm called
CLTQP.
It consists of using multiple SPARQL query engine with the aim of improving the completeness of LTQP
by exploring more of the search space and to reduce the execution time by the means of exchange of intermediary results.
In this PhD project, I will apply this query paradigm in the context of Solid, 
which imply that there is a strong consideration for privacy during querying [](cite:cites Taelman2020). 
Also, the structure of the data hosted inside the Solid pods [](cite:cites verborgh2020) and the structure of the virtual
social interaction that the users engage when using the app can be leveraged to optimize link traversal. 
The collaboration process can be divided into two parts: 
<span class="comment" data-author="RT">Instead of listing these two parts in terms of the technical solution, could you explain them in terms of the problems they aim to solve? i.e., why is better exploration needed, and why is caching needed?</span>
first, collaboration in exploring data sources, and second, collaboration in caching results and intermediate results.

The purpose of the first part is to investigate more of the search space.<span class="comment" data-author="RT">But why? What problem are you solving this this?</span>
In this case we suppose that an engine wants to make an LTQP <span class="comment" data-author="RT">query?</span> and ask other engines
at a certain moment to assist it to execute that query.
[As seen before](#litterature_review_LTQP), in LTQP, the search space tends to be huge or pseudo-infinite
which means that it's difficult to guarantee completeness of results.
An important property emerging from the difficulty of reaching completeness is the bias of the query results. 
This bias emerges from a sensibility to the initial condition, induce by the seeds URL provided to the engine. <span class="comment" data-author="RT">I don't really understand what you mean by this bias.</span>
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
<span class="comment" data-author="RT">After reading this paragraph, you have not convinced me yet of the need for collaboration to improve discovery. Perhaps talking about sharing computational effort, and perhaps even different collaborative engines exploring using different algorithms, could help here.</span>

The second part <span class="comment" data-author="RT">Repeat what the second part is about</span> can be divided into multiple consideration. 
<span class="comment" data-author="RT">It's not clear to me what the 3 things below are exactly. Are they related work? Are they methods you want to apply? Are they open problems?</span>
For the first one, [](cite:cites Hartig2011) demonstrate that caching in LTQP can
help improve the completeness of results, but in some condition the query execution time can be increased.
The second consideration is to be related to the first part of the collaboration <span class="comment" data-author="RT">What are you referring to exactly now?</span>,
because there is a need to synchronize the results between the query engines. 
The third <span class="comment" data-author="RT">I would suggest using inline 1), 2) etc. Because "the first", "second", etc are confusing with respect to the 2 high-level parts of your approach.</span> is related to query performance as the same or similar query can have been executed previously by
other query engine and put into the cache, hence, we can reuse those results to speedup the query execution time as
it has been demonstrated in the academic literature but not in the case of LTQP.<span class="comment" data-author="RT">Yes, this last sentence is important! But it should have come much sooner! You could even mention it the first time you introduce these 2 parts of your approach, because this is really at the core of your research, while now it feels as an unimportant afterthought.</span>

<span class="comment" data-author="RT">I would specifically make use of the term "incentive" here.</span>
It has to be considered that a mechanism to assure reciprocity might <span class="comment" data-author="RT">It _is_ necessary!</span> be necessary to ensure
fairness and the good functioning of the system,
it can be implemented in multiple ways for example as an obligation to participate in a ratio of query,
a number of triples or links to provide, and so on.
Their enforcement could be managed by a community like structure with policies in that regard.
Given a user doesn't respect the policy than they cannot access the results of that community,
so it is a form of social contract.

### Research question and Hypotheses
{:#research_question}

Building on the proposal and of related works of the [](#litterature_review) 
research questions and hypotheses are formalized,to guide the study.

<span class="comment" data-author="RT">I would recommend to elaborate on each question and hypothesis below it, because some of them require some more details.</span>

<div class="sidebysidecontainer">
    <span class="comment" data-author="RT">I would not put them in 2 columns, as it breaks the line of reading.</span>

<div>
<ul>
<li><span class="question_hypothesis">Question 1</span>: Can we achieve better query result completeness, 
better query execution time and less result bias <span class="comment" data-author="RT">Unclear what this bias is</span> in the context of LTQP by making multiple SPARQL query engine collaborate?</li>

<li><span class="question_hypothesis">Question 2</span>: How can we minimize the overlapping of data sources <span class="comment" data-author="RT">What is this overlapping? Why is it a problem?</span> exploration during CLTQP?</li>

<li><span class="question_hypothesis">Question 3</span>: How can we in the context of CLTQP share the cache of SPARQL query engine? </li>
<span class="comment" data-author="RT">Instead of saying how to use a cache, start by saying how to solve problem X, which is solved by using a cache.</span>

<li><span class="question_hypothesis">Question 4</span>: Does cache reduces the query execution time? What is the influence of the number of engines sharing their cache with the query execution time? Are there scenarios where caching is better than others and what are the property of those scenarios?</li>
<span class="comment" data-author="RT">Those are multiple questions. Can we summarize it into one high-level question, and then mention these sub-questions in the text below it?</span><span class="comment" data-author="RT">These may also be rephrased as just hypotheses.</span>

<li><span class="question_hypothesis">Question 5</span>: Does the structure of decentralized web environment applications 
have an impact on the completeness and query execution time on CLTQP?</li>
<span class="comment" data-author="RT">Interesting question, but feels unrelated to collaboration.</span>
</ul>
</div>
 

<div>
<ul>
<li><span class="question_hypothesis">Hypothesis 1</span>: It is possible to partition the search space in the context of CLTQP,
in a way that each engine can perform their query without too much <span class="comment" data-author="RT">What is too much? Hypotheses must be precise.</span> synchronization and domain overlap.</li>


<li><span class="question_hypothesis">Hypothesis 2</span>: We can exploit the GLTQP technique in CLTQP to optimize the queries <span class="comment" data-author="RT">Optimize in terms of what?</span> without producing too much <span class="comment" data-author="RT">What is too much?</span> overlap <span class="comment" data-author="RT">overlap in terms of what?</span>.</li>

<li><span class="question_hypothesis">Hypothesis 3</span>: Given a large enough <span class="comment" data-author="RT">What is large enough?</span> search space, then 
the more engines collaborating, the lower average execution time and the higher the search space explored <span class="comment" data-author="RT">how will you measure this?</span>.
</li>

</ul>
</div>

</div>