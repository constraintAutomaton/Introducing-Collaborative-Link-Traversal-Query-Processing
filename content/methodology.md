## Methodology
{:#methodology}

As discussed in [](#proposal) my work can be divided into two sub-problems;
the division of the search space and the caching.
<span class="comment" data-author="RT">Note: these are not problems, they are solutions to problems</span>

### Search domain division problem

The first problem I try to solve is to increase the query completeness;
hence we try to divide the search space among peers.
It has to be considered first that we don't know in advance the limit of the domain<span class="comment" data-author="RT">What is this limit? Is it the link queue size?</span>;
hence we cannot divide it before the execution of the query.
I elaborate three strategies to divide the domain.

<span class="comment" data-author="RT">These are good strategies! :-)</span>

<ul>
<li><span class="question_hypothesis">Collect the seed URLs and to divide them between the query engines</span>: 
The advantage of this strategy is the communication between the engine is minimal,
at the start or at a moment where we have a large number of URLs we let the engine execute the query on their own and at
the stopping condition, the engine share the results.
The limitation of this strategy is that we don't consider if the data source discoverable inside the seed URLs overlaps.

</li>

<li><span class="question_hypothesis">Set the reachability criteria of each engine so that they cannot or are less likely to have overlapping search field</span>:
The advantage of this strategy is, like the first one, the communication between engines is low.
However, unlike the previous one, there is a mechanism to avoid redundant calculations.
By doing so, the query engine has a lookup policy that restricts links visited by others.
For example, the engine might be responsible for a specific semantic section of the domain. 
If the data is geospatial, the criteria could be in relation to the links associated with cities.
The limitation of this strategy is that the criteria might have to be changed depending on the executed query
and the type of dataset from which we expect to find results.
Additionally, we might also lose results if the criteria are too strict.
</li>

<li><span class="question_hypothesis">Use a global link queue shared between all the query engines</span>:
The advantage of this strategy is that it's a simple way to avoid redundant calculations as all engines have the same link queue.
Every engine can then execute the query on their own with no consideration for redundancy.
Another possibility would be to let one peer do the join operation while the other peers handle the traversal and
the execution of the query.
The problem with this strategy is the necessary communication and the potential locking mechanism to avoid inconsistencies.

</li>
</ul>

I am planning to build a prototype using the SPARQL query engine [Comunica](cite:cites taelman_iswc_resources_comunica_2018) <span class="comment" data-author="RT">Why this one, and not another? (modularity, link traversal, ... ?)</span>
and evaluate it against the existing RDF social media benchmark [](cite:cites Angles2020TheLS) <span class="comment" data-author="RT">Not SolidBench? Problem with pure LDBC SNB is that it's based on a centralized dataset.</span>
and compare the results with other LTQP approaches.
Using a benchmark, I will evaluate those methods while varying the number of engines <span class="comment" data-author="RT">engines in the P2P network I assume?</span><span class="comment" data-author="RT">Ranging between what numbers exactly?</span>.
I propose to measure the following metrics:

<ul>
<li>Result completeness: The ratio of the answers found in relation to the possible answers<span class="comment" data-author="RT">That's an incorrect definition of completeness. Perhaps it's better to talk about result accuracy (see my last paper).</span></li>
<li>Query execution time <span class="comment" data-author="RT">Which is defined as ... ?</span></li>
<li>Ratio between the execution time and the communication time <span class="comment" data-author="RT">What is communication time?</span></li>
<li>Ability to access isolated documents: An analysis of the degree of the data source (considered as edges of a graph) queried<span class="comment" data-author="RT">Not sure what you mean by this</span></li>
<li>Number of requests (of a single engine and globally <span class="comment" data-author="RT">I would split up these two</span>) <span class="comment" data-author="RT">HTTP requests? Or P2P network operations? Or both?</span></li>
<li>Overlapping of the search space exploration of the Query engine: The number of times a triple and data source have been queried</li>
<li>Rate of production of results (with consideration of its variation in time) <span class="comment" data-author="RT">Do you mean result arrival time? (see my last paper)</span></li>
</ul>

### Caching problem

<span class="comment" data-author="RT">The paragraph below doesn't sounds very well thought out yet. Could you try to explain your methodology in a more structured manner like in the previous section? You could for instance also try out various strategies, each having their own advantages and disadvantages.</span>

The objective of this problem it to reduce the query execution time by taking already produced results from a shared cache.
Following the [related work](#litterature_review), an unstructured approached with 
a profile overlay might be preferred, but given the potential long execution time a 
*Structured network with a DHT* could also be a profitable solution.
In regards to that approach, there is a consideration for the privacy and the discovery of new peers.
Contrary to the approached viewed in the related work, we might not be able to share the whole cache or distribute the data to any peers,
because some data are private [](cite:cites Grall2020). 
The information that could be cached is the *data source URLs that are contributing* given a query,
the *joint* given triple patterns to avoid their calculations or the *triple patterns*.
The cache could also be considered as a checkpoint for a longer execution or as a map of the data sources to explore
depending on the data source and the type of queries.

Building on the evaluation method of the first problem <span class="comment rephrase" data-author="RT">I add those metric</span>:
<ul>
<li>Access time: The time it take to retrieve information from the cache</li>
<li>Cache miss and rates of use of the cache <span class="comment" data-author="RT">don't fully understand this. Do you mean cache hit-rate?</span></li>
</ul>
