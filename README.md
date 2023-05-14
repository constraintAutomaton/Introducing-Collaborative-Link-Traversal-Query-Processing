# Introducing Collaborative Link Traversal Query Processing in the context of structured decentralized environment
Available as a web page at https://constraintautomaton.github.io/Introducing-Collaborative-Link-Traversal-Query-Processing-in-the-context-of-structured-decentralized/
## Abstract

Decentralized web environment aims at giving more autonomy and control of the users over their data.
Solid is a structured decentralized web protocol that emphasis on privacy and
interoperability via the usage of linked data and the current web technology stack.
I propose that the guarantee of privacy and choice (emerging from the interoperability) on the part of the user is not enough, 
we also need to create a state of affairs where the computational power can be produced 
by the user of the app themselves instead of delegated it to a third party to bring more potent democratic power
over applications that are often used in the day-to-day life of the individual.
A crucial aspect of web applications, particularly social one, is the query of information, and it's discovery.
An influential example of web discovery technique is Link Traversal Query Processing (LTQP) 
a SPARQL query paradigm aiming at exploring the web to answer query by dereferencing and following the named nodes inside the data sources.
For this doctoral research, I am introducing the concept of Collaborative Link Traversal Query Processing, a SPARQL
query processing paradigm for LTQP, where multiple query engine
collaborate together to increase their query results completeness and reduce their query execution time.
In this paper I formalize the objective of my research, document my method and anchor it with the current state of the art.
Doing so, I divided the cooperation of query engines into two parts; exploration of the search space, to mainly increase the completeness of results, by having more ground explored and caching for reducing the execution time.
To concretize the potential of this proposal, I will create a prototype and evaluate it using existing benchmarks.
From my review of the literature, there exist contribution pertaining to collaborative SPARQL query and RDF collaborative caching,
but there is none in the context of LTQP and of structured decentralized environment like Solid.
hence making this potential contribution novel.

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
