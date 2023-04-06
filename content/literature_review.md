## Literature review
{:#litterature_review}

### Academic reference system
[Jin in](cite:cites jin2006 Ning2006SemreXTL) proposed a P2P system, called SemreX, to share academic paper with the personal comment made by the researchers.
It is based on semantic classification and querying.
Jin, state that most papers are not published in journals, hence making them difficult to find in a centralized paradigm, because the the centralized entity
has to be aware of the existence of those low output data sources.
Jin present that most unstructure P2P network used for example for music and video sharing are not adequat for academic publication,
because those systems are not made to described the content of the shared file.
Jin proposed to use [RDF](https://www.w3.org/TR/rdf11-concepts/), to decribe using [hypermedia description](cite:cites Fielding) the content of academic paper using the metadata of the PDF file,
which came with some diffuculty due to the hetorogious manner that article publisher encode their information insde the PDFs, for the classification the authors used machine learning algorithm that
take as input the pages of the paper and uses the connex cathegorisation from wikipedia[](cite:cites Yuan2012SemreXAS).


<!-- Talk about querying-->

[Bibster](cite:cites Haase2004) proposed a similar solution as Semrex, but focus more on the sharing of bibliographic metadata. The paper propose the use of SeRQL to query the RDF information from
the selected peers. The user of Bibster, can query it's local bibliographic metadata, a manual selection of peers or the whole networks. When it come to the query of the whole network Bibster
apply a expertise-based peer selection.


<!-- talk about duplication -->

Bibster also try to solve the problem of duplication of information has on a large network non coordinated network it is bound to have duplicate information. But those duplication might not
be completly identical, hence Bibster use it's ontologies and simularity function such as similarity into the title to measure the simularity between answer to avoid duplication.


<!-- Free riding -->
[free riding problem](cite:cites jin2006)

### Querying

[](cite:cites Haase2004a) propose a way to do peer selection when executing query to fetch bibliographic metadata in a peer-to-peer network.
Their system build a "virtual" semantic topology over the network peer to peer network, in that topology every node expose their "expertise".
The expertise is a semantic description of the knowledge contain inside the peer. Using the expertise the querying peer can make a request to all the peer
it knows and check if there expertise align with the query it is making, hence pruning or prioteriszing the peer to visit.
The limitation is that the peer must share the same ontology.
From the benchmark results, they found that the best results are produce when the distribution of the knowledge by peer was organize in accordance with the structrue of the ontology.
They mention that in there future work they would make so the network topology would mathch the network topology.