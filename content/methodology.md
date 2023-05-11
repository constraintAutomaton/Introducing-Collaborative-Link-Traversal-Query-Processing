## Methodology
{:#methodology}

I am planning to build a prototype using the SPARQL query engine [Comunica](cite:cites taelman_iswc_resources_comunica_2018)
and evaluate it against existing RDF social media benchmark [](cite:cites Angles2020TheLS, Angles2014TheLD, Spasic2016)
and compare the result with LTQP and GLTQP approaches.
Like presented at the ["Proposal" section](#proposal) the collaboration can be divided into two, hence we formulate two 
relatively independent problems; the search domain division and the caching (and communication).

### Search domain division problem
There are multiple strategies (combinable) that could be employed to divide the domain.
It has to be considered first that we don't know in advance the limit of the domain,
hence we cannot divide it before the execution of the query.
A strategy can be to **collect the seed URLs and to divide them between the query engine**,
the limitation is that we don't consider if the data source discoverable inside the seed URLs overlaps.
Another strategy would be to **communicate between the engines, the link queue and/or the link visited**. The
problem with that approach is the increase in execution time due to the communication of the engine and we still
need a mechanism to react on the detection of the overlap and to redistribute the domain.
A last strategy that I propose is to **set the reachability criteria of each engine so that they cannot or are less likely to have overlapping search field**, the limitation of that strategy is that the criteria might have to be 
changed depending on the query executed and the type of dataset that we expect to find result, 
we might also lose result if the criteriums are too strict.


Using a benchmark, I could evaluate those methods alone and in combination to measure, while making the **Number of engine** vary. 
I propose to measure those metrics:
**Result completeness**, 
**Ability to access isolated documents (we can evaluate their isolation by the degree of the node (only the edge that end in the node) and the number of paths that can lead to it)**,
**Number of requests (of a single engine and globally)**, 
**Overlapping of the search space exploration of the Query engine**,
 **Query execution time**, **Rate of production of results**, **Delay between the first result and the start of the execution**.

### Caching and Communication  problem
Given that in our collaborative context, we want all the engines implicated in the query 
to communicate with each other, for the collection of results and the redivision of the domain,
a **unstructured network** might be the best choice as the lookup for the client as it have a constant time complexity and we know all the peers.

For the caching following the [related work](#litterature_review), an unstructured approached with a profile overlay might be preferred.
In regards to that approach, there is a consideration for the privacy and the usefulness of the discovery of new peers.
Contrary to the approached viewed in the related work, we might not be able to share the whole cache, because some data are private. 
It comes that considering the overhead and the ratio of data that can be shared, the discovery of peers might not be or be less profitable than expected. 
If the discovery of peer is more profitable than we can either create profiles based on the query executed like [](cite:cites Folz2016)
and rotate the peers or instead navigating the chain of peers, like [](cite:cites Aebeloe2021).

Using a benchmark, I could evaluate the same metric as in the search domain problem with the addition of: **Communication time** and **Cache miss and rates of use of the cache**.
And while making the **Number of engine** vary.