## Related works
{:#litterature_review}


### Link Traversal Query Processing

LTQP of Linked Data documents is a technique that consists of [recursively lookup URL from dereferenced named nodes acquired by the query engine in order to explore 
the surrounding information around the original response](cite:cites Hartig2016) using the follow-your-nose principle of Linked Data[](cite:cites Yu2014).
The query first start with a small set of URI called [seed URIs](cite:cites Hartig2013AnOO) that form the initial data source for the execution.
The engine then resolves the URI of the named node it encounters in order to explore unknown data sources following a lookup policy [](cite:cites hartig2012).

Link traversal has a great exploratory potential but it comes with some difficulties. 
A first difficulty is the [open-endedness of the web](cite:cites Umbrich2014LinkTQ).
Naively following all the links from a discovered document can potentially generate a seemingly infinite number of new links to follow.
This pseudo-infinite search space necessitates query optimization technique in order to provide the user fast and adequately complete results.
Another obstacle comes from the [difficulties to evaluate the cost of a query plan prior to the execution.
We can't always have information about the data source,
it's content,
the reachability of the document and their potential contribution to the results prior to the execution](cite:cites Hartig2014LinkedDQ, verborgh2020).
A current solution to optimize the plan of execution is to use a query planning heuristic [](cite:cites Hartig2011ZeroKnowledgeQP), but as they are
simply heuristic their power is limited and they don't take capture the particularity of each query and data sources.
A better approach in the absence of those a priori knowledges would be to use adaptative query processing [](cite:cites taelman2023),
which means adapting the query plan based on either inference from the data collected or from new knowledge acquired while querying.


The traditional form of link traversal consists of following more or less naively the links inside the response payload
and dereferencing them to get a new data source. In most cases, the data source encountered,
does not have a strict structure that can be leveraged
to speed up the execution. Nonetheless reachability criterium can be defined to restrict the links that are followed based on conditions,
classical examples are $$ c_all $$ which follow every link and $$ c_match $$ which 
follow links that match the query pattern [](cite:cites hartig2012, Bogaerts).


### Guided Link Traversal Query Processing in Solid

When there is a priori knowledge about the linked data documents a technique called [Guided Link-Traversal-Based](cite:cites verborgh2020) (GLTQP), can be used to restrict further potential links to follow by using.
GLTQP uses a priori knowledge about the structure of the data 
(eg: Which link to follow to find a new relevant documents) and meta knowledge 
to find while traversing information that can be used to diminish the traversal search horizon,
hence restricting even more the links to follow by the query engine.
In practice, it has been used to query over multiples [Solid pods](cite:cites spec:solid),
using the [Linked Data Platform specification](cite:cites spec:ldp) to access the information and the [Solid type index](cite:cites spec:typeIndex) located inside the pods to know 
the emplacement of the information requested [](cite:cites taelman2023).
Other specifications could also be used to gain knowledge while traversing to guide the link traversal such as 
[shape trees](cite:cites spec:shapeTree) and Shape [constraint languages (SHACL)](cite:cites spec:shacl).
The result on the search domain explore by the SPARQL query engine remain pseudo-infinite or unknowns,
but at every traversal step we might get a finite domain pertaining to getting complete information about the current subject.


<!-- What can we learn from it-->
<!--network topology -->


### Collaborative SPARQL Querying
In the [](cite:cites grall:hal-01805154)


### P2P caching in the context of the web

Caching is a common mecanism to diminush the processing time given 
that we repeat an operation that has been done in the past and that it's result has not been invalidated. 
HTTP come natively with it's caching mecanism[](cite:cites spec:httpcache), but this cache is local 
hence does not exploit, the possibility that another agent have in it's own cache the data requested.
We also have to take into consideration that a large number of triple are published online [](cite:cites Verborgh2016author, Ermilov2013author) 
, but linked data principle emphasis the design of dataset that can be 
[reused](https://lod-cloud.net/) and the usage of standar vocabularies[](cite:cites spec:linkedDataBestPratices), which might have the repercussion if those principal
are applied that intermediary result or even result of queries could be shared and reused by multiple query engine.
In the context of the web and even particularly in the context of semantic web,
there exist P2P caching mecanism in the academic litterature.

[Squirrel](cite:cites Iyer2002SquirrelAD) proposed a P2P caching mecanism, where the URL are map to keys inside distributed hash table (DHT).
If the user does not have in it's local cache the content desired, it first make a query to the P2P network before doing the request to the
URL in question. 
Squirrel does not propose a mecanism to take into account the locality of the client making the request and the node that will answer the request.
[Flower-CDN](cite:cites Manal2009) propose to modify the keys of the DHT to consider the locality.
The content of the websites are distributed into peer of a locality, inside this locality 
a super peer knows where to locate the every content of all the websites. 
When a client makes a query to the DHT, the DHT direct to the super peer closest to the locality of the client
and the super peer find the content requested by the client.
[Behave](cite:cites Frey2014) proposed another paradigm instead of using a structured network with a DHT, it rely on an unstructed
network where each peer have a partial view of the whole web. Each peer's view of the network is partially random and
partially based on the websites the peer visits with its web browser to create a "behavioral locality". 
It uses a gossip protocol, at certain times the peer exchange randomly the node they know to change its view on the network.
With this approach behave was able to for 50% of their query to be retrieved with 0 hop which shows that the system has a great potential for scalability.
[CyCLaDEs](cite:cites Folz2016) adapted the concept of Behave for the use case of SPARQL query of RDF documents.