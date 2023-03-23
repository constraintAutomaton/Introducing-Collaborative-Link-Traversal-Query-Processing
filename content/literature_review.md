## Literature review
{:#litterature_review}


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
apply a expertise-based peer selection

The selection of peer is expertise-based, 


<!-- talk about duplication -->

Bibster also try to solve the problem of duplication of information has on a large network non coordinated network it is bound to have duplicate information. But those duplication might not
be completly identical, hence Bibster use it's ontologies and simularity function such as similarity into the title to measure the simularity between answer to avoid duplication.


<!-- Free riding -->
[free riding problem](cite:cites jin2006)