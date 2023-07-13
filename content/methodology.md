## Methodology
{:#methodology}

As discussed in [the proposal](#proposal), my work can be divided into two sub-problems;
the division of the search space and caching. 
This implies two sets of potential solutions detailed below.

### Search domain division among peers

My first aim is to increase the query completeness;
For that purpose I will try to divide the search space among peers in a P2P network.
It has to be considered first that the topology of the domain is not known, 
so we cannot divide the search space a priori.
Below I present three strategies to divide the domain and process the query. 

1. **Collect the seed URLs and divide them between the query engines**: 
The advantage of this strategy is the communication between the engines is minimal,
at the start or at a moment when we have a large number of URLs we let the engines execute the query on their own and at
the stopping condition, the engines share their results.
The limitation of this strategy is that we don't consider if the data sources discoverable inside the seed URLs overlaps.
Another important limitation is the loss of accuracy if part of the solution is present inside the documents processed by different engines.
In that case, to find those results and retain the accuracy, the solution map would need to be joined.
By detecting those cases and using adaptative query planning [](cite:cites taelman2023, Acosta2011),
it would be possible to change strategy to avoid the loss of accuracy.

2. **Set the reachability criteria of each engine so that they cannot or are less likely to have overlapping search field**:
The advantage of this strategy is, also, the low communication between the engines.
However, unlike the previous one, there is a mechanism to avoid redundant calculations.
The query engines have a lookup policy that restricts links visited by others.
For example, the engines might be responsible for a specific semantic section of the domain, 
e.g., cities in geospatial query. 
The limitations of this strategy are that the criteria might have to be changed depending on the executed query
and the type of dataset from which we expect to find results ,and the loss of accuracy explained in the first strategy.

3. **Use a global link queue and solution map shared between all the query engines**:
The advantage of this strategy is that it's a simple way to avoid redundant calculations as all engines have the same link queue.
Also with the shared solution map the engines would avoid the problem of loss accuracy mention in the first strategy.
Another possibility would be to let one peer do the join operation while the other peers handle the traversal and
the execution of the query as inspired by the "slave-master" paradigm of the article [](cite:cites 8029358).
The problem with this strategy is the necessary communication and the potential locking mechanism to avoid inconsistencies.


I am planning to build a prototype using the SPARQL meta query engine [Comunica](cite:cites taelman_iswc_resources_comunica_2018),
because it already has LTQP algorithms implemented and it is a highly extensible software which 
will facilitate the implementation of those algorithms.
I will evaluate it against the Solid social media benchmark;
[SolidBench](https://github.com/SolidBench/SolidBench.js) [](cite:cites taelman2023)
and compare the results with other LTQP approaches.
I will evaluate those methods while varying the number of engines
collaborating by increasing the number until the performance stagnates or diminishes.
I propose to measure the following metrics:

- **Result accuracy**: The F-score; a fraction indicating the correctness and completeness of results
- **Query execution time**: The total time it takes to complete a query
- **The ratio of the execution time and the communication time between the engines**
<!-- Not sure yet how to do it-->
- **Ability to access isolated documents**: Measured by analyzing the number of links leading to query-relevant data sources and evaluating their actual contribution
- **Overlapping of the search space**: The number of times a triple and data source has been queried
- **Query result arrival times**: The time it takes for each triple from the beginning of the query to be obtained [](cite:cites Acosta2017)

### Collaborative Caching

My second aim is to reduce the query execution time by using already computed results from a shared cache.
The information cached could be the *data source URLs contributing to a query* and
the *intermediary joint results with the associated solution map*, given some triple patterns to avoid their calculations.
The cache could also be interpreted as a checkpoint for a longer execution or as a map of the data sources to explore.
I propose to investigate those two strategies:

1. **Unstructured network where peers are clustered based on their behavior**: 
The advantage of this strategy is that the lookup time to find information in the cache is constant and the peers 
have a high probability of possessing the knowledge desired. 
The clustering can be based on the engines that have engaged in a query collaboration with the subject engine.
The disadvantage of that method is that it relies on a type of self-organization of the network of engines,
and it does not consider that engines that have not collaborated might still have results in common.

2. **Distributed Hash Table to find the cached element**:
The advantage of this approach is that we can get every cached element of the engines implementing the protocol.
The disadvantage is that the lookup time is logarithmic with the number of elements cached,
also the private information of the users will be dispersed in the DHT, with no regard to the will of the user [](cite:cites Grall2020),
but there are strategies with the combination of a gossip protocol to keep privacy [](cite:cites 10.1145/2413176.2413215).
Also, an alternative would be to not share private information.

Building on the evaluation method of the first set of solutions, those metrics are added:

- **Cache access time**: The time it takes to retrieve information from the cache
- **Cache miss and cache hit rates**: The ratio of time the query engine get the information requested from the cache
- **Execution time reduction**: The ratio between the execution time of a query with and without the cache
