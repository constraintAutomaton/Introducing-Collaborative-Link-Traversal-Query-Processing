# Introducing Collaborative Link Traversal Query Processing in the Context of Structured Decentralized Environments
Available as a web page at https://constraintautomaton.github.io/Introducing-Collaborative-Link-Traversal-Query-Processing/
## Abstract
Decentralized web environments aim to give users data autonomy and control.
Data sovereignty focus on two aspects: privacy and provider choice.
However, the concept remains incomplete if it fails to incorporate the actual utilization of the data.
Specifically, in the context of application functionality,
data sovereignty can be relinquished to the owner of the computational units or applications.
The exploration and retrieval of information are core functionalities of web-based social
applications because it is from those mechanisms that shared experiences to foster interactions are created.
A promising example of web discovery techniques is Link Traversal Query Processing (LTQP),
a SPARQL query paradigm that aims at exploring the web to answer queries by following the links between documents.
In my doctoral research, I introduce Collaborative Link Data Query Processing,
a paradigm where multiple query engines collaborate to improve query result completeness and execution performance in LTQP.
I divide the research on the cooperation of query engines into two parts: 1) Improving the completeness of results, by exploring more of the search space,
and 2) reducing the potentially long query execution time by caching results.
To validate this proposal, I will develop a prototype and evaluate it using existing benchmarks.
Based on my analysis of the state of the art,
previous studies have made contributions to collaborative SPARQL query execution and RDF peer-to-peer caching.
However, there is currently a research gap regarding the investigation of such systems in
the context of LTQP within a structured decentralized environment.

## Editing the article
### Development mode
```
bundle install
bundle exec guard
```

### Build
```
bundle install
bundle exec nanoc compile
```

View on http://localhost:3000/

**This article makes use of the [ScholarMarkdown](https://github.com/rubensworks/ScholarMarkdown/) framework.**
