## Related Work
{:#litterature_review} 

### Link Traversal Query Processing
{:#litterature_review_LTQP} 


LTQP is a technique that consists of [recursively looking up URLs from dereferenced named nodes acquired by the query engine in order to explore 
the surrounding information around the original response](cite:cites Hartig2016) using the follow-your-nose principle of Linked Data,
compared to traditional SPARQL queries that only query one document, and Federated Query Processing where the data sources are known beforehand.
The query first starts with a small set of URIs called [seed URIs](cite:cites Hartig2013AnOO) that form the initial data source for the execution.
The engine then resolves the URI of the named node it encounters in order to explore unknown data sources, following a lookup policy.
Link traversal has great exploratory potential. In its traditional form, it consists of following, more or less naively, the links inside the response payload
and dereferencing them to get new data sources. 
However, Link Traversal comes with some difficulties, such as the [open-endedness of the web](cite:cites Umbrich2014LinkTQ)
and query planning [](cite:cites Hartig2014LinkedDQ). 
In most cases, the encountered data sources do not have a strict structure that can be leveraged to speed up the execution.
Nonetheless, reachability criteria can be defined to restrict the links that are followed based on conditions.
Classical examples are `Call`, which follows every link, and `Cmatch`, which 
follows links that match the query pattern [](cite:cites hartig2012).


### Collaborative SPARQL Querying

Collaborative SPARQL Querying in that context consists of using multiple agents to facilitate querying by
diminishing the computation load of the execution or the discovery of data sources [](cite:cites Grall2020). 
[Snob](cite:cites grall:hal-01805154) proposes a mechanism for collaborative query based
on the continuous execution of queries over browser data sources that are rotating in a network of browsers. 
The browsers form an unstructured peer-to-peer (P2P) network where each peer has
a random and a profile-based (browsers with similar profiles execute similar queries) partial view of the network.
The browsers can share their intermediary results, and at specific intervals,
the peers are randomly shuffled by asking the peers that a browser knows for other peers.
In that way, over time, without necessarily having to query every data source, it is possible to achieve better query result completeness.
[ColChain](cite:cites Aebeloe2021) has a different approach. 
The query engines still have a partial view of the network, but the view is not random or profile-based;
it is community-based.
A community, in the ColChain context, is a set of
"nodes that participate in and observe [each other] and the fragments published [between them]" [](cite:cites Aebeloe2021).
So the division of the network is made intentionally by the users.
When querying the SPARQL query engine, it will look at its own data sources, then the data sources of the communities it knows.
To discover new communities, the engine asks the members of the communities it knows for communities it does not have knowledge of.
The collaborative aspect lies in the partition of a "global" knowledge graph into intentional semantic units and in the
maintenance and particularly update of the collective data sources, which is an important contribution of ColChain but is not related to the aim of my research.
Other academic contributions have also aimed to leverage the social links between data sources to diminish the query execution time by not flooding the network when querying, such as in
[](cite:cites Shen2014AnIP).
Also in that realm of studies, contributions have focused on using the structure of the object that is modeled,
such as academic papers, instead of the social links between the data sources,
for example [](cite:cites jin2006).



### P2P caching in the context of the web
{:#litterature_review_P2P_caching} 

We define P2P caching as a particular case of collaborative querying where the query engine share with each other in a network of peers,
their already computed and valid results.
[Squirrel](cite:cites Iyer2002SquirrelAD) proposed a P2P caching mechanism,
where the URLs are mapped to keys inside a distributed hash table (DHT).
If the user does not have in its local cache the content desired,
it first makes a query to the P2P network before making the request to the URL in question.
Squirrel does not propose a mechanism to take into consideration the locality of the client and the node’s acting.
[Flower-CDN](cite:cites Manal2009) propose to modify the keys of the DHT to consider the locality.
The content of the websites are distributed into peer of a locality,
inside this locality a super peer knows where to locate every content of all the websites of the locality.
When a client makes a query to the DHT,
the DHT direct to the super peer closest to the locality of the client and the super peer find the content requested by the client.
[Behave](cite:cites Frey2014) proposed another paradigm instead of using a structured network with a potentially slow DHT,
it relies on an unstructured network where each peer has a partial view of the whole web.
Each peer's view of the network is partially random and partially based on the websites visited to create a "behavioral locality."
It uses a gossip protocol, at certain times the peer exchange randomly the node they know to change its view on the network.
With this approach, behave was able in 50% of its query to retrieve the information with 0 hop which shows
that the system has a great potential for scalability.
[CyCLaDEs](cite:cites Folz2016) adapted the concept of Behave for the use case of SPARQL query of RDF documents.
