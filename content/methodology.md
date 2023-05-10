## Methodology
{:#methodology}

### Resolution
In my current state of affaire, I have surveyed part of the literature as presented in [](#litterature_review),
I have also investigated the usage of the protocol [IPFS](cite:cites spec:ipfs) for
a backend of our P2P network in relation to the communication of the SPARQL query engine [Comunica](cite:cites taelman_iswc_resources_comunica_2018).
I am also participating in a group with other researchers to investigate how to use Solid for the use case of social media applications
and medical applications in a  P2P manner and while preserving privacy.
Lastly, I experimented with GLTQP in Comunica for the use case of fragmented databases.

<span class="comment" data-author="RT">The text above is too vague. We'll need to make each thing more concrete, but only if we can show something preliminary already, or can say what kind of methodology we applied.</span>

To evaluate this work, I plan to build a prototype and test it against an existing RDF social media benchmark [](cite:cites Angles2020TheLS, Angles2014TheLD, Spasic2016).
Additionally, I will use the prototype to test a use case involving self-publication of academic papers.

### Evaluation

For the evaluation metrics, I will take inspiration from the authors discussed in the literature review [](#litterature_review) and consider the following measurements: **Number of engine**, **Result completeness**, **Ability to access isolated documents**, **Number of requests**, **Overlapping of the search space exploration of the Query engine**, **Query execution time**, **Rate of production of results**, **Delay between the first result and the start of the execution**, **Cache miss and rate of use of the cache**.

<span class="comment" data-author="RT">This section is super important, and we need to explain our evaluation plan in much more detail. You need to talk about the different research questions here, how you will approach them, what kind of experiments you will do for each of them, and how you will answer the hypotheses. The metrics you mention are good, but you'll need to elaborate more on them, and explain *why* they are important here.</span>
<span class="comment" data-author="RT">Bonus points: you could talk about potential risks in your plan, and come up with mitigation strategies.</span>