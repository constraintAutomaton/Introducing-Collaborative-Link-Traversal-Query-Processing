## Methodology
{:#methodology}

As discussed in [the proposal](#proposal), my work can be divided into two sub-problems;
the division of the search space and the caching. 
This implies two sets of potential solutions detailed below.

### Search domain division problem

The first problem I try to solve is to increase the query completeness;
For that purpose we try to divide the search space among peers.
It has to be considered first that we don't know in advance the shape of the domain,
the topology of the part of the web to explore with the aims to answer the query;
hence we cannot divide it before the execution of the query.
I propose three strategies to divide the domain.

- <span class="question_hypothesis">Collect the seed URLs and to divide them between the query engines</span>: 
The advantage of this strategy is the communication between the engine is minimal,
at the start or at a moment where we have a large number of URLs we let the engine execute the query on their own and at
the stopping condition, the engine share the results.
The limitation of this strategy is that we don't consider if the data source discoverable inside the seed URLs overlaps.

- <span class="question_hypothesis">Set the reachability criteria of each engine so that they cannot or are less likely to have overlapping search field</span>:
The advantage of this strategy is, like the first one, the communication between engines is low.
However, unlike the previous one, there is a mechanism to avoid redundant calculations.
By doing so, the query engine has a lookup policy that restricts links visited by others.
For example, the engine might be responsible for a specific semantic section of the domain, 
e.g.: cities in geospatial query. 
The limitation of this strategy is that the criteria might have to be changed depending on the executed query
and the type of dataset from which we expect to find results.
Additionally, we might also lose results if the criteria are too strict.

- <span class="question_hypothesis">Use a global link queue shared between all the query engines</span>:
The advantage of this strategy is that it's a simple way to avoid redundant calculations as all engines have the same link queue.
Every engine can then execute the query on their own with no consideration for redundancy.
Another possibility would be to let one peer do the join operation while the other peers handle the traversal and
the execution of the query as inspired by the "slave-master" paradigm of [](cite:cites 8029358).
The problem with this strategy is the necessary communication and the potential locking mechanism to avoid inconsistencies.


I am planning to build a prototype using the SPARQL meta query engine [Comunica](cite:cites taelman_iswc_resources_comunica_2018),
because it already has LTQPs algorithms implemented and it is a highly extensible software build which 
will facilitate the implementation of those algorithms.
I will evaluate it against the Solid social media benchmark;
[SolidBench](https://github.com/SolidBench/SolidBench.js) [](cite:cites taelman2023)
and compare the results with other LTQP approaches.
I will evaluate those methods while varying the number of engines 
collaborating by increasing the number until the performance stagnates or diminish.
I propose to measure the following metrics:

<ul>
<li>Result accuracy: The F-score; a fraction indicating the correctness and completeness of results</li>
<li>Query execution time: The total time it takes to complete a query</li>
<li>The ratio between the execution time and the communication time between the engines</li>
<!-- Not sure yet how to do it-->
<li>Ability to access isolated documents: Measured by analyzing the number of links leading to query-relevant data sources and evaluating their actual contribution</li>
<li>Overlapping of the search space exploration of the Query engine: The number of times a triple and data source has been queried</li>
<li>Query result arrival times: The time it takes for each triple from the beginning of the query to be obtained</li>
</ul>

### Caching problem

The problem is to reduce the query execution time by using already computed results from a shared cache.
The information cached could be the *data source URLs that are contributing to a query*,
the *joint* given triple patterns to avoid their calculations, or the *triple patterns*.
The cache could also be interpreted as a checkpoint for a longer execution or as a map of the data sources to explore.
I propose to investigate those two strategies:

- <span class="question_hypothesis">
Use an unstructured network where the peers are clustered based on their behavior</span>: 
This approach consists of grouping the engines based on similar behavioral characteristics 
so that the lookup time to find information in the cache is constant and the peer known 
has a high probability of possessing the knowledge desired. 
The clustering can be based on the engine that has engaged in a query collaboration with the subject engine.
The disadvantage of that method is that it relies on a type of self-organization of the network of engines,
it does not consider that engine that has not collaborated might still have results in common.

- <span class="question_hypothesis">Use a DHT to find the cached element</span>:
The advantage of this approach is that we can get every cached element of the engine implementing the protocol.
The disadvantage of this approach is that the lookup time is logarithmic with the number of elements cached,
also the private information of the users will be dispersed in the DHT, with no regard to the will of the user [](cite:cites Grall2020),
but it's still possible to use a DHT combined with a gossip protocol and keep privacy [](cite:cites 10.1145/2413176.2413215).
Also, an alternative would be to not share private information.

Building on the evaluation method of the first set of solutions, those metrics are added:

- Access time: The time it takes to retrieve information from the cache
- Cache miss and cache hit rates