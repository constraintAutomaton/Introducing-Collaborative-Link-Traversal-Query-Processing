# Introducing Collaborative Link Traversal Query Processing in the context of structured decentralized environment
Available as a web page at https://constraintautomaton.github.io/Introducing-Collaborative-Link-Traversal-Query-Processing/
## Abstract

<!-- Context -->
Decentralized web environments aim to give users data autonomy and control.
Data sovereignty focuses on privacy and provider choice, but lacks emphasis on empowering users to create and manage applications without significant resources.
A crucial aspect of web social applications is the query of information and its discovery.
Linked data describes information using IRI and URL.
The data source behind those URLs gives context of the information described, making the data richer, 
more easily reusable, and more interoperable than other publication standards.
An influential example of web discovery techniques is Link Traversal Query Processing (LTQP),
a SPARQL query paradigm that aims at exploring the web to answer queries by following the links provided by the document,
hence exploiting the connectivity of data sources.
In my doctoral research, I introduce Collaborative Link Data Query Processing, a paradigm where multiple query engines collaborate to improve query completeness and execution time in LTQP.
I divided the cooperation of query engines into two parts:
1) To improve the exploration of the search space, hence increasing the completeness of results, and
2) To reduce the potentially long query execution time by caching results.
To validate this proposal, I will develop a prototype and evaluate it using existing benchmarks.
From my review of the literature, there exist contributions pertaining to collaborative SPARQL query and RDF collaborative caching,
but there is none in the context of LTQP and of structured decentralized environment, hence making this contribution novel.

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
