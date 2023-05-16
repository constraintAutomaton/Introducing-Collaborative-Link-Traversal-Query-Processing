## Abstract
<!-- Context -->
Decentralized web environments aim to give users data autonomy and control in other words data sovereignty.
<!-- Need -->
Data sovereignty focuses on privacy and provider choice, but lacks emphasis on empowering users to create and manage applications without significant resources.
<!-- Task -->
A crucial aspect of web social applications is the query of information and its discovery and linked data can be used to help in
their decentralization effort.
Linked data describes information using IRIs and URLs.
The data source behind those URLs gives context of the information described, making the data richer, 
more easily reusable, and more interoperable than other publication standards.
An influential example of web discovery techniques is Link Traversal Query Processing (LTQP),
a SPARQL query paradigm that aims at exploring the web to answer queries by following the links provided by the document,
hence exploiting the connectivity of data sources.
<!-- Object -->
In my doctoral research, I introduce Collaborative Link Data Query Processing, a paradigm where multiple query engines collaborate to improve query completeness and execution time in LTQP.
<!-- Findings -->
I divided the cooperation of query engines into two parts:
1) To improve the exploration of the search space, hence increasing the completeness of results, and
2) To reduce the potentially long query execution time by caching results.
<!-- Conclusion -->
To validate this proposal, I will develop a prototype and evaluate it using existing benchmarks.
<!-- Perspectives -->
From my review of the literature, there exist contributions pertaining to collaborative SPARQL query and RDF collaborative caching,
but there is none in the context of LTQP and of structured decentralized environment, hence making this contribution novel.