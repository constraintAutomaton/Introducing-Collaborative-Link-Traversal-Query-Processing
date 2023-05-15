## Abstract
<!-- Context      -->

Decentralized web environment aims at giving more autonomy and control to users over their data.
<span class="comment" data-author="RT">For example...</span>Solid is a <del class="comment" data-author="RT">structured</del> decentralized web protocol that emphasises privacy and
interoperability via the usage of linked data and the <del class="comment" data-author="RT">current</del> web <del class="comment" data-author="RT">technology</del> stack.
<!-- Need         -->
I propose that <span class="comment rephrase" data-author="RT">the guarantee of privacy and choice (emerging from the interoperability) on the part of the user is not enough</span>, 
we also need to create a state of affairs where the computational power can be produced 
by the user of the app themselves<span class="comment" data-author="RT">What do you mean by producing computational power by the app user?</span> instead of delegated it to a third party to bring more potent democratic power
over applications <span class="comment" data-author="RT">I assume you're trying to motivate the need for distributing these computations. However, the "democratic power" argument is unclear.</span> that are often used in the day-to-day life of the individual.
<!-- Task         -->
A crucial aspect of web applications, particularly social <span class="comment spelling" data-author="RT">one</span>, is the <span class="comment spelling" data-author="RT">query of information</span>, and <span class="comment spelling" data-author="RT">it's</span> discovery.
An influential example of web discovery techniques is Link Traversal Query Processing (LTQP) 
a SPARQL query paradigm aiming at exploring the web to answer queries by dereferencing and following the <span class="comment rephrase" data-author="RT">named nodes</span> inside <del class="comment" data-author="RT">the</del> data sources.
<span class="comment" data-author="RT">It's not clear at this point why you want to build upon LTQP. What's important in LTQP that other techniques lack?</span>
For this doctoral research, I am introducing the concept of Collaborative Link Traversal Query Processing, a SPARQL
query processing paradigm for LTQP, where <span class="comment spelling" data-author="RT">multiple query engine</span>
collaborate together to increase their query results completeness and reduce their query execution time.
<span class="comment" data-author="RT">I remember asking this question before; but do you really need to focus on collaborative LTQP here? Wouldn't it be possible to introduce the collaboration techniques without LTQP? LTQP could surely be your main driver, but your solution could also be useful for other querying paradigms.</span>
<!-- Object       -->
In this paper I formalize the objective of my research, document my methods and anchor it with the current state of the art.
<!-- Findings     -->
<del class="comment" data-author="RT">Doing so, </del>I divided the cooperation of query engines into two parts;
1) <span class="comment" data-author="RT">to improve?</span>the exploration of the search space, to <del class="comment" data-author="RT">mainly</del> increase the completeness of results<del class="comment" data-author="RT">, by having more ground explored</del>, and
2) caching for reducing the execution time <span class="comment" data-author="RT">maybe also briefly say here why this is important</span>.
<!-- Conclusion   -->
To concretize the potential of this proposal, I will create a prototype and evaluate it using existing benchmarks.
<!-- Perspectives -->
From my review of the literature, <span class="comment spelling" data-author="RT">there exist contribution</span> pertaining to collaborative SPARQL query and RDF collaborative caching,
but there is none in the context of LTQP and of structured decentralized environment like Solid.
hence making this <del class="comment" data-author="RT">potential</del> contribution novel.

