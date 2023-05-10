## Related Work
{:#litterature_review} 

### Link Traversal Query Processing

LTQP of Linked Data documents is a technique that consists of [recursively lookup URL from dereferenced named nodes acquired by the query engine in order to explore 
the surrounding information around the original response](cite:cites Hartig2016) using the follow-your-nose principle of Linked Data [](cite:cites Yu2014).
The query first start with a small set of URI called [seed URIs](cite:cites Hartig2013AnOO) that form the initial data source for the execution.
The engine then resolves the URI of the named node it encounters in order to explore unknown data sources following a lookup policy [](cite:cites hartig2012).

Link traversal has a great exploratory potential, in it's traditional form it consists of following more or less naively the links inside the response payload
and dereferencing them to get a new data source. 
It has to be taken into account that Link Traversal comes with some difficulties, such as the [open-endedness of the web](cite:cites Umbrich2014LinkTQ),
and query planning [](cite:cites Hartig2014LinkedDQ, verborgh2020, Hartig2011ZeroKnowledgeQP, taelman2023). 
In most cases, the data source encountered, does not have a strict structure that can be leveraged to speed up the execution.
Nonetheless reachability criterium can be defined to restrict the links that are followed based on conditions,
classical examples are $$c_{all}$$ which follow every link and $$c_{match}$$ which 
follow links that match the query pattern [](cite:cites hartig2012, Bogaerts).


### Guided Link Traversal Query Processing in Solid

When there is a priori knowledge about the linked data documents a technique called [Guided Link Traversal Query Processing (GLTQP)](cite:cites verborgh2020) ,
can be used to restrict further potential links to follow by using.
GLTQP uses a priori knowledge about the structure of the data 
(eg: Which link to follow to find a new relevant document) and meta knowledge 
to find while traversing information that can be used to diminish the traversal search horizon,
hence restricting even more the links to follow by the query engine.
In practice, it has been used to query over multiples [Solid pods](cite:cites spec:solid),
using the [Linked Data Platform specification](cite:cites spec:ldp) to access the information and the [Solid type index](cite:cites spec:typeIndex) located inside the pods to know 
the emplacement of the information requested [](cite:cites taelman2023).
Other specifications could also be used to gain knowledge while traversing such as 
[shape trees](cite:cites spec:shapeTree) and [Shape constraint languages (SHACL)](cite:cites spec:shacl).
The result on the search domain explored by the SPARQL query engine remain pseudo-infinite or unknowns,
but at every traversal step we might get a finite domain pertaining to getting complete information about the current subject.

### Collaborative SPARQL Querying
[Snob](cite:cites grall:hal-01805154) propose a mechanism for collaborative query based
on the continuous execution of queries over browsers data sources that are rotating in a network of browser. 
The browsers form an unstructured peer-to-peer (P2P) network where each peer has
a random (Ladda [](cite:cites Grall2017) apply a similar method) and a profile (browser with similar profiles execute similar queries) base partial view of the network.
The browsers can share their intermediary results and at specific intervals,
the peers are randomly shuffled by asking the peers that a browser knows for other peers.
In that way over time, without necessarily having query every data sources, it is possible to achieve better query results completeness.
[ColChain](cite:cites Aebeloe2021) has a different approach. 
The query engines still have a partial view of the network, but the view is not random or profile based,
it is community-based.
A community, in the ColChain context, is a set of
"nodes that participate in and observe [each other] and the fragments published [between them]."[](cite:cites Aebeloe2021)
So the division of the network is made intentionally by the users.
When querying the SPARQL query engine it will look at its own data sources, then the data source of the communities it knows.
To discover new communities, the engine ask the member of the comunities it knows for communities it does not have knowledge of.
The collaborative aspect is in the partition of a "global" knowledge graph into intentional semantic units and in the
maintenance and particularly update of the collective data sources which is an important contribution of ColChain but is not related to the aim of my research.
Other academic contributions have also aimed to leverage the social links between data source to diminish the query execution time, by not flooding the network when querying, such has in
[](cite:cites Shen2014AnIP, 10.1145/988672.988759, Bertier2010).
Also in that realm of studies contributions have focus on using the structure of the object that is modeled,
such has academic papers, instead of the social links between the data sources,
for example [](cite:cites jin2006, Haase2004).


### P2P caching in the context of the web

Caching is a common mechanism to diminish the processing time given 
that we repeat an operation that has been done in the past and that its result has not been invalidated. 
HTTP comes natively with its caching mechanisms[](cite:cites spec:httpcache), but this cache is local, hence does not exploit, the possibility that other agents might have in its own cache the data requested.
We also have to take into consideration that [a large number of triples are published online](https://lod-cloud.net/) [](cite:cites Verborgh2016author, Ermilov2013author) 
and that linked data principle emphasis the design of datasets that can be 
reused and the usage of standard vocabularies[](cite:cites spec:linkedDataBestPratices).
The massive adherence to those principles might have the repercussion that intermediary result 
or even complete result of queries could be shared and reused by multiple query engine.
In the context of the web and even particularly in the context of the semantic web,
there exist P2P caching mechanisms in the academic literature.

[Squirrel](cite:cites Iyer2002SquirrelAD) proposed a P2P caching mechanism, where the URLs are mapped to keys inside a distributed hash table (DHT).
If the user does not have in its local cache the content desired, it first makes a query to the P2P network before making the request to the
URL in question. 
Squirrel does not propose a mechanism to take into consideration the locality of the client and the node’s acting.
[Flower-CDN](cite:cites Manal2009) propose to modify the keys of the DHT to consider the locality.
The content of the websites are distributed into peer of a locality, inside this locality a super peer knows where to locate every content of all the websites of the locality. 
When a client makes a query to the DHT, the DHT direct to the super peer closest to the locality of the client
and the super peer find the content requested by the client.
[Behave](cite:cites Frey2014) proposed another paradigm instead of using a structured network with a potentially slow DHT, it relies on an unstructured
network where each peer has a partial view of the whole web. Each peer's view of the network is partially random and
partially based on the websites visited  to create a "behavioral locality." 
It uses a gossip protocol, at certain times the peer exchange randomly the node they know to change its view on the network.
With this approach, behave was able in 50% of its query to retrieved the information with 0 hop which shows that the system has a great potential for scalability.
[CyCLaDEs](cite:cites Folz2016) adapted the concept of Behave for the use case of SPARQL query of RDF documents.