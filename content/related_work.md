## Related Work
{:#litterature_review} 

### Link Traversal Query Processing
{:#litterature_review_LTQP} 

LTQP is a technique that consists of [recursively looking up URLs from dereferenced URIs acquired by the query engine
to explore the surrounding information around the original response](cite:cites Hartig2016) using the follow-your-nose
principle of Linked Data. 
In contrast, traditional SPARQL queries only query one document,
and Federated Query Processing where the data sources need to be known beforehand. 
The query first starts with a small set of URIs called [seed URIs](cite:cites Hartig2016) that form
the initial data sources for the execution.
The engine then uses a predefined lookup policy to discover new URIs inside the documents obtained from the seed URIs.
Link traversal has great exploratory potential.
In its traditional form, it consists of following,
more or less naively, the links inside the response payload and dereferencing them to get new data sources.
However, Link Traversal comes with some difficulties,
such as the open-endedness of the web and query planning [](cite:cites Hartig2014LinkedDQ). 
Reachability criteria can be defined to restrict the links that are followed based on conditions.
Classical examples are `cAll`, which follows every link, and `cMatch`, which follows links that match the query pattern [](cite:cites hartig2012).


### Collaborative SPARQL Querying

Collaborative SPARQL Querying consists of using multiple agents to facilitate querying by
diminishing the computation load of the execution or the discovery of data sources [](cite:cites Grall2020). 
[Snob](cite:cites grall:hal-01805154) proposes a mechanism for collaborative query based
on the continuous execution of queries over rotating browser data sources. 
The browsers form an unstructured peer-to-peer (P2P) network where each peer has
a random and a profile-based (browsers with similar profiles execute similar queries) partial view of the network.
The browsers can share their intermediary results and at specific intervals,
the peers are randomly shuffled by requesting new peers from known browsers.
With this technique,
it becomes possible to enhance the completeness of query results over time without the need to query every individual data source.
[ColChain](cite:cites Aebeloe2021) has a different approach. 
The query engines still have a partial view of the network but it is based on communities instead of being random or profile-based.
A community, in the ColChain context, is a set of
<q>nodes that participate in and observe [each other] and the fragments published [between them]</q> [](cite:cites Aebeloe2021).
So the division of the network is made intentionally by the users.
For the query process the engine examines its own data sources and then expands the search to include the data sources of known communities.
To discover new communities, the engine inquires peers to identify unknown communities.
The collaborative aspect lies in the partition of a "global" knowledge graph into intentional semantic units.
Other academic contributions have also aimed to leverage the social links between data sources to diminish the query execution time by not flooding the network when querying, such as in
[](cite:cites Shen2014AnIP).
Another approach is to use the structure of the object modeled,
such as academic papers as in the contribution of the authors of [](cite:cites jin2006).



### P2P caching in the context of the web
{:#litterature_review_P2P_caching} 

We define P2P caching as a particular case of collaborative querying 
where the query engine shares their already computed and valid results.
[Squirrel](cite:cites Iyer2002SquirrelAD) proposed a P2P caching mechanism,
where the URLs are mapped to keys inside a distributed hash table (DHT).
If the user does not have the desired content in its local cache,
it first queries the P2P network before requesting the URL.
Squirrel does not propose a mechanism to take into consideration the distance between the client and the node’s acting.
[Flower-CDN](cite:cites Manal2009) proposes to modify the keys of the DHT to consider the locality.
The content of the websites is distributed to peers of a locality,
inside this locality a super-peer knows where to locate every content of all the websites of the locality.
When a client makes a query to the DHT,
the DHT directs to the super peer closest to the locality of the client and 
the super peer finds the content requested by the client.
[Behave](cite:cites Frey2014) proposed another paradigm instead of using a structured network with a potentially slow DHT,
it relies on an unstructured network where each peer has a partial view of the whole web.
Each peer's view of the network is partially random and partially based on the websites visited to create a 
<q>behavioral locality</q> [](cite:cites Frey2014).
It uses a gossip protocol, at certain times the peers exchange randomly the nodes they know to change their view on the network.
[CyCLaDEs](cite:cites Folz2016) adapted the concept of Behave for the use case of SPARQL query of RDF documents.
