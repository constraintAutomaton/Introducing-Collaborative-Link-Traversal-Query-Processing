## Abstract
<!-- Context -->
Decentralized web environments aim to give users data autonomy and control.
<!-- Need -->
Data sovereignty focuses on privacy and provider choice,
<span class="comment" data-author="RT">I honestly don't understand the remainder of this sentence, so I suspect the reviewers won't either.</span>
but the concept is not complete if it does not include the concrete usage of the data,
if when it comes to the working of applications sovereignty can be
surrendered to the owner of the computational units or apps.
<!-- Task -->
The exploration and retrieval of information are core functionalities of web-based social
applications because it is from those mechanisms that shared experiences to foster interactions are created.
A promising example of web discovery techniques is Link Traversal Query Processing (LTQP),
a SPARQL query paradigm that aims at exploring the web to answer queries by following the links between documents.
<!-- Object -->
In my doctoral research, I introduce Collaborative Link Data Query Processing,
a paradigm where multiple query engines collaborate to improve query result completeness and execution performance in LTQP.
<span class="comment" data-author="RT">Make sure to briefly mention here the importance and novelty of the collaborative aspect, or what collaborative means to you.</span>
<!-- Findings -->
I divide the research on the cooperation of query engines into two parts:
1) Improving the completeness of results, by exploring more of the search space,
and 2) reducing the potentially long query execution time by caching results.
<!-- Conclusion -->
To validate this proposal, I will develop a prototype and evaluate it using existing benchmarks.
<!-- Perspectives -->
Based on my analysis of the state of the art,
previous studies have made contributions to collaborative SPARQL query execution and RDF peer-to-peer caching.
However, there is currently a research gap regarding the investigation of such systems in
the context of LTQP within a structured decentralized environment.
