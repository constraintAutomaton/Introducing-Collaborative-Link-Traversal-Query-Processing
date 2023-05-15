## Methodology
{:#methodology}

<span class="comment" data-author="RT">The next sentence should only be mentioned at the end of your methodology, as it is the implementation of your methods.</span>
I am planning to build a prototype using the SPARQL query engine [Comunica](cite:cites taelman_iswc_resources_comunica_2018)
and evaluate it against existing RDF social media benchmark [](cite:cites Angles2020TheLS)
and compare the result with LTQP and GLTQP approaches.
Like presented at the ["Proposal" section](#proposal) the collaboration can be divided into two, hence we formulate two 
relatively independent problems; the search domain division and the caching (and communication).

### Search domain division problem

<span class="comment" data-author="RT">Repeat first briefly why dividing the search space is needed.</span>

There are multiple strategies (combinable) that could be employed to divide the domain.
It has to be considered first that we don't know in advance the limit of the domain;
hence we cannot divide it before the execution of the query.
<span class="comment" data-author="RT">Can we take a more structured approach at listing these strategies? Perhaps as a list with strategy names and descriptions.</span>
A strategy can be to **collect the seed URLs and to divide them between the query engines**,
the limitation is that we don't consider if the data source discoverable inside the seed URLs overlaps, also if the list of seeds URL is very short, then the distribution will be minimal.
A variance of that strategy would be to distribute the link queue when it is big enough among the peers.<span class="comment" data-author="RT">Isn't the previous approach then just a special case of this approach? Maybe we can explain it as such.</span>
Another strategy would be to **communicate between the engines, the link queue and/or the link visited**. <span class="comment" data-author="RT">I don't see the difference with the previous one.</span>
The problem with that approach is the increase in execution time due to the communication of the engine and we still
need a mechanism to react on the detection of the overlap and to redistribute the domain.
A different strategy that I propose is to **set the reachability criteria of each engine so that they cannot or are less likely to have overlapping search field**, the limitation of that strategy is that the criteria might have to be 
changed depending on the query executed and the type of dataset that we expect to find result, 
we might also lose result if the criteriums are too strict.
A last strategy would be **to have a global link queue that all the participating engine maintains together**.
The problem with this strategy is the communication necessary and the potential locking mechanism to avoid inconsistencies.
A variance of this strategy would be to let one peer do the joins and the other peers doing the traversal and
the execution of the query.
<span class="comment" data-author="RT">It feels to me that all of the above approaches in essence dividing the link queue among peers, but have different methods for achieving it. If that is correct, I would explain it as such. You could even consider the different division methods on an axis, ranging from not requiring any inter-peer communication, to requiring a lot of inter-peer communication.</span>

Using a benchmark, I could evaluate those methods alone and in combination to measure, while making the **Number of engine** vary.
I propose to measure those metrics:
<span class="comment" data-author="RT">No need to put everything here in bold</span>
**Result completeness**, 
**Ability to access isolated documents (we can evaluate their isolation by the degree of the node (only the edge that end in the node) and the number of paths that can lead to it)**,
**Number of requests (of a single engine and globally)**, 
**Overlapping of the search space exploration of the Query engine**,
 **Query execution time**, **Rate of production of results**, **Delay between the first result and the start of the execution**.
 <span class="comment" data-author="RT">The presentation of these metrics is very messy. Can we explain them in a list, with a proper description for each metric?</span>

### Caching and Communication problem

<span class="comment" data-author="RT">Below, you start by diving into the technical details of structured/unstructured networks. Let's start first by repeating the problem you want to solve, and how caching can solve it. Then, talk about the methods for achieving this cache.</span>

Given that in our collaborative context, we want all the engines implicated in the query 
to communicate with each other, for the collection of results and the redivision of the domain,
a **unstructured network** might be the best choice as the lookup for 
the client is of constant time complexity and we know all the peers.

For the caching following the [related work](#litterature_review), an unstructured approached with 
a profile overlay might be preferred,but given the potential long execution time a 
**structured network with a DHT** could also be a profitable solution.
In regards to that approach, there is a consideration for the privacy and the usefulness of the discovery of new peers.
Contrary to the approached viewed in the related work, we might not be able to share the whole cache or distribute the data to any peers
, because some data are private. 
It comes that considering the overhead and the ratio of data that can be shared,
the discovery of peers might not be or be less profitable than expected. 
If the discovery of peer is more profitable than we can either create profiles based on the query executed like
[](cite:cites Folz2016)
and rotate the peers or instead navigating the chain of peers, like [](cite:cites Aebeloe2021).
The information that could be cached is the **data source URLs that are contributing** given a query,
the **joint** given triple patterns to avoid their calculations or the **triple patterns**.

Using a benchmark, I could evaluate the same metric as in the search domain problem with the addition of: **Communication time** and **Cache miss and rates of use of the cache**.
And while making the **Number of engine** vary.
<span class="comment" data-author="RT">I would use a more structured approach here for presenting the metrics.</span>