# Introducing Collaborative Link Traversal Query Processing in the context of structured decentralized environment
Available as a web page at https://constraintautomaton.github.io/Introducing-Collaborative-Link-Traversal-Query-Processing/
## Abstract
Decentralized web environments aim to give users data autonomy and control, in other words, data sovereignty.
Data sovereignty focuses on privacy and provider choice 
but lacks emphasis on empowering users to create and manage applications without significant computational resources.
The exploration and retrieval of information play a pivotal role in web-based social applications.
A promising example of web discovery techniques is Link Traversal Query Processing (LTQP),
a SPARQL query paradigm that aims at exploring the web to answer queries by following the links provided by the documents,
hence exploiting the connectivity of data sources.
In my doctoral research, I introduce Collaborative Link Data Query Processing,
a paradigm where multiple query engines collaborate to improve query completeness and execution time in LTQP.
I divided the research on the cooperation of query engines into two parts: 1) Improving the completeness of results, by exploring more of the search space,
and 2) reducing the potentially long query execution time by caching results.
To validate this proposal, I will develop a prototype and evaluate it using existing benchmarks.
Based on my analysis of the state of the art,
previous studies have made contributions to collaborative SPARQL query and RDF peer-to-peer caching.
However, there is currently a research gap regarding the investigation of such systems in
the context of LTQP and LTQP within a structured decentralized environment.

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
