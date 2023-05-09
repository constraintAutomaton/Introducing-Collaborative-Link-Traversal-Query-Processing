## Research question and Hypotheses
{:#research_question}

Building on the proposal of the [](#proposal) and of related works of the [](#litterature_review) research questions are formalized,
to guide the study. 

<span class="comment" data-author="RT">The first question below is quite good, but I'm wondering if we can add some more structure to the questions.
    A suggestion: keep a variant of the first question as main research question, and then have questions on the 2 parts of your research: reducing search space, and caching. And then we can have corresponding hypotheses.</span>

**Question 1**: Can we achieve better query result completeness in the context of LTQP by making multiple SPARQL query engine collaborate?
<span class="comment" data-author="RT">Just better result completeness? Or also better in terms of other metrics, such as exec time?</span>

**Question 2**: How can we minimize the overlapping of data sources exploration during CLTQP?
Does the technique for the fragmentation of the domain should vary depending on the type of app?
<span class="comment" data-author="RT">I don't understand this second sentence.</span>
<span class="comment" data-author="RT">Is this question referring to the goal of improving discovery?.</span>

**Question 3**: How can we exploit the structure of Solid pods and applications to restrict the links follow in the context of CLTQP?
Do these structural aspects have an influence on the result completeness and query execution time?
<span class="comment" data-author="RT">Good question, but I don't see how it relates to collaboration. Perhaps it doesn't fit in your current topic?</span>

**Question 4**: How can we in the context of CLTQP share the cache of SPARQL query engine? And those cache reduces the query execution time? What is the influence of the number of engines sharing their cache with the query execution time? Are there scenarios where caching is better than others and what are the property of those scenarios?
<span class="comment" data-author="RT">Good one, but these are multiple questions. We'll have to either summarize, or decompose into multiple questions</span>

In relation to those questions, these hypotheses are formed.

**Hypothesis 1**: It is possible to partition the search space in the context of CLTQP.
<span class="comment" data-author="RT">Sure, it's trivial that we can do that :-) But to what purpose? What do we want to achieve exactly?</span>

**Hypothesis 2**: We can exploit the links between the solid pods in relation to the domain of the application when distributing the search space. 
<span class="comment" data-author="RT">Unclear what you mean by this. By the way, we may want to add a paragraph below each hypothesis/question to elaborate on them.</span>

**Hypothesis 3**: Given a large enough search space it is possible to optimize the general query execution time by increasing the number of query engines 
in the collaboration.
<span class="comment" data-author="RT">Perhaps this one can be simplified: "the more engines collaborating, the lower average exec time."</span>

**Hypothesis 4**: It is possible during CLTQP to share join and/or triple pattern to reduce execution time.
<span class="comment" data-author="RT">But how will you do this? What techniques do you hypothesize will achieve this?</span>

**Hypothesis 5**: It is possible during execution of CLTQP to delegate part of the search space to other query engines.
<span class="comment" data-author="RT">Let's rephrase this to something like: "by doing x, we can delegate part of the search space, and thereby lowering exec time."</span>