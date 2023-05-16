## Abstract
<!-- Context -->
Decentralized web environments aim to give users data autonomy and control.
<!-- Need -->
Data sovereignty focuses on privacy and provider choice, but lacks emphasis on empowering users to create and manage applications without significant resources.<span class="comment" data-author="RT">What resources do you mean? Especially in an RDF context, this can mean different things.</span>
<!-- Task -->
A crucial aspect of web social applications is <span class="comment rephrase" data-author="RT">the query of information</span> and its discovery.
Linked data describes information using <span class="comment spelling" data-author="RT">IRI and URL</span>.
The data source behind those URLs gives context of the information described, making the data richer, 
more easily reusable, and more interoperable than other publication standards.
An influential <span class="comment" data-author="RT">I wouldn't say it's particularly influential</span> example of web discovery techniques is Link Traversal Query Processing (LTQP),
a SPARQL query paradigm that aims at exploring the web to answer queries by following the links provided by <span class="comment spelling" data-author="RT">the document</span>,
hence exploiting the connectivity of data sources.
<!-- Object -->
In my doctoral research, I introduce Collaborative Link Data Query Processing, a paradigm where multiple query engines collaborate to improve query completeness and execution time in LTQP.
<!-- Findings -->
I divided the cooperation <span class="comment" data-author="RT">Not the cooporation itself, but the research towards it is divided into 2 parts</span> of query engines into two parts:
1) Improving the exploration of the search space, hence increasing the completeness of results <span class="comment" data-author="RT">I would start with this completeness here in this sentence</span>, and
2) Reducing the potentially long query execution time by caching results.
<!-- Conclusion -->
To validate this proposal, I will develop a prototype and evaluate it using existing benchmarks.
<!-- Perspectives -->
From my review of the literature, <span class="comment rephrase" data-author="RT">there exist contributions</span> pertaining to collaborative SPARQL <span class="comment spelling" data-author="RT">query</span> and RDF collaborative caching,
but there is none in the context of LTQP and of structured decentralized environment<del class="comment" data-author="RT">, hence making this contribution novel</del><span class="comment" data-author="RT">Saying something is novel is something you typically don't want to do. Instead, you want to say something that implies novelty. Such as saying that this research direction has not been investigated yet.</span>.
<span class="comment" data-author="RT">This is also a good place to come back to why such collaborative exec is useful for the end-users.</span>