SUBMISSION: 381
TITLE: Introducing Collaborative Link Traversal Query Processing in the Context of Structured Decentralized Environments


----------------------- REVIEW 1 ---------------------
SUBMISSION: 381
TITLE: Introducing Collaborative Link Traversal Query Processing in the Context of Structured Decentralized Environments
AUTHORS: Bryan-Elliott Tam

----------- Overview -----------
This paper presents a proposal for a phd project that will investigate the development of a method for query answering over distributed web data. The paper gives a motivation for this based on current need for such distributed data in the context of data sovereignty, building on the foundations of the SOLID project. It bases the research question on the state of the art in Link Traversal Query Processing and distributed SPARQL solutions. The proposal poses two subquestions on query completeness as well as efficiency. The project will mainly be an engineering effort building prototypes on top of existing (SOLID-related) infrastructures and benchmarks.
----------- Originality and Novelty -----------
SCORE: 4 (good)
----- TEXT:
Based on SOTA, building on existing P2P and distributed querying but definitely valuable and novel
----------- Relevance to the Conference -----------
SCORE: 5 (excellent)
----- TEXT:
Clear relevance to the conference. This is core Semantic Web engineering research
----------- Technical soundness -----------
SCORE: 3 (fair)
----- TEXT:
The technical details in the proposal are quite limited, but what is there is solid (no pun intended)
----------- Clarity and quality of presentation -----------
SCORE: 3 (fair)
----- TEXT:
I found the introduction not very easy to read. This is partly because of some overly long sentences with many commas or brackets. Also, the political and economical statements and assumptions in the first part of the introduction are not really backed up. I would suggest a slight rewrite with more focus on the actual research problem. Make sure to state the research question/contribution of the paper in the introduction.

An running example would also highly increase the readability of the paper. What paper presents "querying in social applications" as main case, but what that would actually look like is unclear. For what type of applications and in what kinds of scenarios would the proposed solution work? In other words, what is the class of problems for which you design a (class of) solution(s)?
----------- Overall evaluation and additional comments -----------
SCORE: 2 (accept)
----- TEXT:
Clear paper with a good focused research problem. This is mostly an engineering problem, but one that is relevant to the overall conference and to current investigations into distributed privacy-preserving data sharing solutions. The method, the heuristics described and the metrics proposed make sense. In the current form, most technical details are missing, but for an early-stage proposal that is ok.

The demarcation and illustration of the problem can be improved with examples of situations where such distributed querying is reasonable.

A figure illustrating the high-level design of the solution would also be valuable.

Related to this, the paper explains that the main method will involve SOLID-related infrastructure, benchmarks and likely also use cases. The benchmark is not described in this paper so for the reader it is not clear what datasets, network settings or tasks are considered. It would be good if a discussion could be added on the generalizability of the solution (beyond SOLID).

The formulation of RQ1 can be improved, it is not clear with respect to what the better completeness and lower execution time is calculated. Is there an obvious baseline (non-distributed solutions?)? What is the independent variable in this case?

The introduction now mentions economic factors as well (monetary barriers), but these are not present in the research questions or metrics. What is the relation between the stated contribution in the introduction and the method with respect to this? The same holds for privacy, how is that taken into account in the method? Is it a factor restricting the solution space or a variable that you measure?

on P1: " In this PhD program [...]" -> this sentence is overly long and quite hard to understand. It seems to state that you want to move a definition, whereas you are actually contributing a method to facilitate efficient data querying. I would split up this sentence and rephrase it.



----------------------- REVIEW 2 ---------------------
SUBMISSION: 381
TITLE: Introducing Collaborative Link Traversal Query Processing in the Context of Structured Decentralized Environments
AUTHORS: Bryan-Elliott Tam

----------- Overview -----------
The paper proposes a PhD topic that aims to enhance techniques for Linked Data Query Processing (LTQP) in a Solid setting. The key idea is to explore collaborative ways in which multiple clients can evaluate LTQP more efficiently as part of a peer-to-peer system. Exploring this idea involves some interesting challenges, such as how to avoid crawling redundant data, how to avoid cycles, etc. The author also proposes to explore caching techniques in the P2P setting.
----------- Originality and Novelty -----------
SCORE: 3 (fair)
----- TEXT:
While the topic is interesting, the originality of the proposed idea arises more from a novel combination of known techniques rather than something highly original in and of itself.
----------- Relevance to the Conference -----------
SCORE: 5 (excellent)
----- TEXT:
Wonderfully relevant. We need more web-centric submissions.
----------- Technical soundness -----------
SCORE: 5 (excellent)
----- TEXT:
The paper is not particularly technical (nor need it be), but what I reviewed seemed to be sound.
----------- Clarity and quality of presentation -----------
SCORE: 4 (good)
----- TEXT:
The paper is generally quite clear, with a few minor exceptions:

* "Link traversal has great exploratory potential" You need a citation or justification here.
* "and query planning" It's not really a difficulty. Maybe something like "and the complexity of query planning".
* "be accessed, in regards to the seed URLs[,] can be"
* "[21] demonstrates that caching in LTQP" Would say better: "Hartig [21] demonstrates that caching in LTQP", which reads much better than "Twenty-one demonstrates that caching in LTQP"
* Question 2 requires rephrasing, in particular "the overlapping of data sources exploration"
* The purpose of caching is not very clear: do you wish to cache intermediate results of one query or data across queries, or both?
----------- Overall evaluation and additional comments -----------
SCORE: 1 (weak accept)
----- TEXT:
On the one hand, the proposed topic is currently a combination of some known techniques in an already fairly well-explored setting. On the other hand, I think that the idea of a P2P/collaborative system for LTBQ is interesting, and could help to overcome some of the practical limitations of this query execution method.

One aspect in which the paper could improve is in terms of the related works, particularly outside of the Linked Data sphere. It would be interesting to know how the current work relates to problems studied in other areas, such as distributed crawling of the web, etc. (just as an example from a quick search: [A]). Looking into the P2P literature would be crucial, if you have not already.

[A] Apoidea: A decentralized peer-to-peer architecture for crawling the world wide web.



----------------------- REVIEW 3 ---------------------
SUBMISSION: 381
TITLE: Introducing Collaborative Link Traversal Query Processing in the Context of Structured Decentralized Environments
AUTHORS: Bryan-Elliott Tam

----------- Overview -----------
Th PhD project described in this paper aims to study how the traversal-based query execution paradigm can be employed in a collaborative manner, with multiple query engines that collaborate in a P2P-like approach to produce the result of a query over a Web of Linked Data. According to the paper, the project is focused on two problems related to such a "collaborative link traversal query processing": 1) how to divide the "search space" between the participating query engines and 2) how to leverage collaborative caching to reduce the execution times of such collaborative traversal-based query execution processes.

The actual contributions of the given paper are to introduce the idea of collaborative traversal-based query execution and to outline a few high-level ideas related to the two problems to be considered (see above).
----------- Originality and Novelty -----------
SCORE: 4 (good)
----- TEXT:
The idea of performing traversal-based query executions in a collaborative manner is quite original and challenging. In terms of actual results, however, there is hardly anything novel (yet!) in the given paper.
----------- Relevance to the Conference -----------
SCORE: 5 (excellent)
----- TEXT:
The topic is clearly relevant to the conference.
----------- Technical soundness -----------
SCORE: 3 (fair)
----- TEXT:
n/a (the paper does not present any technical results)
----------- Clarity and quality of presentation -----------
SCORE: 4 (good)
----- TEXT:
The paper is well written and easy to understand. Yet, some sentences are very long and complex.
----------- Overall evaluation and additional comments -----------
SCORE: 2 (accept)
----- TEXT:
Hi Bryan-Elliott, this is Olaf. You have picked an interesting but also very challenging problem for your PhD, which is good! I am already looking forward to the results of your research and to the solutions that you will come up with.

Judging from Sec.2 of your paper, you already have a good grasp of the most relevant areas of related work.

The research questions that you list are suitable and the corresponding hypotheses are reasonable. It is also good that you already have some initial ideas for the two sub-problems that you want to focus on.

I think that participating in the DC of ISWC 2023 will be a good opportunity for you to discuss your ideas with the community and, thereby, develop these ideas further.

Of course, I also have some more critical comments and suggestions.

1/ Your notion of "the search space" (sometimes also referred to as "search domain" or "the domain" in other parts of your paper) is a key concept in the context of the work that you want to do. However, you are not actually explaining what exactly this search space is. I guess you mean the space of all the Linked Data documents in the Web of Linked Data to be queried. Other readers who are less familiar with the topic may have a hard time guessing. Hence, you should be more clear about such key concepts.

2/ I miss a third relevant problem that I think you need to address (in addition to "the division of the search space and caching"): Assuming the part about the "search space" relates to the traversal of the queried Web of Linked Data and the corresponding discovery of query-relevant documents in this Web, the question remains how the participating query engines collaborate with one another when it comes to producing the result of the given query based on the discovered data. In fact, the whole aspect of query result production (including join processing) seems under-developed in your proposal.

3/ The first two of your envisioned "strategies to divide the domain and process the query" (Sec.4.1) have significant further limitations: Instead of "achiev[ing] better query result completeness" (quoted from RQ1), they may have the exact opposite effect! Take your first strategy. The idea of this strategy is that each of the participating engines uses a different subset of the seed URIs, executes the query on its own based on its subset of seeds, and then the results produced by the engines are shared. The problem in this case is that the part of the query result produced by each engine would be based only on the data discovered by this engine. As a consequence, solution mappings that can (only) be produced by joining data discovered by different engines may not be found by this strategy. The second strategy has the same issue.

4/ The third of these strategies is not entirely clear. If the engines looks up URIs that they take out of such a global link queue, then each of the engines has only the documents from the URIs that it took. How can such an engine "then execute the query on [its] own"? In the best case, it may be able to produce some solution mappings of the query result based on the data of the documents that it has, but solution mappings for which data from other documents (retrieved by other engines) is needed cannot be produced by the engine, let alone solution mappings that can (only) be produced by joining data discovered by different engines.

5/ Another question that you may have to think about: What happens if participating engines fail or leave the P2P network during the (collaborative) execution of a query?

Further suggestions to improve your paper:

6/ You seem to have a tendency to write very long and complex sentences. An extreme example is the following sentence in Sec.1: "In this PhD program ... substantial computational power." This sentence captures several different thoughts, interrupted by nested sub-sentences on other related thoughts. There are other similar examples, perhaps less extreme. To make it easier for your readers to follow your thoughts, try to rephrase these long sentence into multiple, simpler ones.

7/ Similarly, it is allowed to use multiple paragraphs within a (sub)section! :-)  Breaking these long paragraphs (e.g., Section 1 and 3.1) into multiple smaller ones---typically, one per argument---makes it easier to consume the text.

8/ Readers who are less familiar with the topic may have a hard time understanding what type of queries you aim to support with your approach. While you mention in the abstract that "LTQP" is "a SPARQL query paradigm," it would not hurt to pick this thought up again in the paper itself and state explicitly what query language you are planning to consider.

9/ In Sec.3.1 you mention "the initial conditions induced by the seed URLs." I wonder what kind of conditions you might mean here. It would be good if you elaborate a bit more on this part.

10/ A bit further down in Sec.3.1 you outline your proposal "to explore the method of P2P caching". Here I wonder what kind of things you aim to cache. I know that you mention this later in Sec.4.2, but without mentioning it already when outlining your proposal, the description of this part of the proposal remains a bit too abstract.

11/ In Sec.4.2 you all of a sudden start talking about "those two strategies." Since you did not talk about strategies before in this paragraph/section, it is not clear what kinds of strategies you are talking about now (these are strategies for what exactly?).

---
This review was created by Olaf Hartig. Feel free to get in touch to discuss my review comment