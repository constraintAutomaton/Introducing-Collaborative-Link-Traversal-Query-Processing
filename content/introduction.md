## Introduction
{:#introduction}

<!-- General introduction about the web and it's problem, critic of the utopian vision, structural aspect of the problem-->
Popular narative claim that the web is a free, inovative and discrimination free environment.
<!-- reference-->
But the web exist into a social and economical environment with it's own inertia hence it have a tendency to reproduce certain aspect of society. Hence we

Yet the web have an emantipiraty carcacter-

[language](https://w3techs.com/technologies/overview/content_language)

website visited

cap rich and poor

type of content


The [Solid Protocol](https://solidproject.org/TR/protocol), is an effort to while using existing web standards "realise a space where individuals can maintain their autonomy,
control their data and privacy, and choose applications and services to fulfil their needs."[](cite:cites spec:solid),
based on the [W3C TAG Ethical Web Principles](https://www.w3.org/TR/ethical-web-principles/).
However, those principal and the Solid Protocol, does not concretly engage on the means that they will realise these principal and neither do they engage with the
economic disparity incresate by the web, which have an impact on the reach of the individual communication.
In those two documents, there is an assumption that the societal structure stay the same but that the web can change to forwards changws or maintain autonomu and control,
whitout clearly what is consider to be autonomy, what is privacy and what is control.
Nonetheless, the W3C TAG Ethical Web Principles and the Solid protocol propose descentralization as a mean to enhance individual power and control.
In this paper, we take the position that individual power and collective go one in the same.
Decentralization and federation can have multiple meaning it can be from above or it can involve directly the actor using the system.
In this paper we propose a collaborative aggretator inside Solid as a mean to keep the control of the user over social application futhermore 
it can also be use in more centralized context.
By collaborative

<!-- Let's define terms also, power autonomy privacy -->


<!-- 

<!-- Problem of central distribution -->
Centralized distribution of content comes with some problems.
It has a lack of democracy when it comes to who has the power to distribute its contents.
In a centralized paradigm, the distributor has to be able to provide servers that will be queried by a number of users,
ideally reliably and in a reasonable manner.
It is necesarry for an entity to distribute it's content online to have the monetary asset to host and maintain servers.
An alternative for a user is to rely on a distribution platform, that will host the content and organise it's distribution.
But this doesn't solve the democratic problem, even if we consider that the distribution platform is free or as an affortable cost for everyone.
Has those distribution platform are not public good and due to our economical system the objective of those platform is to make the maximum profit 
possible with usally consideration to the law and moral custom.
Hence, the content distributed must forwards or at least not enter into contraction with the objective of the creation of those platforms.
Which create a structural incentice to produce content in a certains ways, that will favor the aims of those platform.
Hence at least implicitly setting what can be express or not or what is allowed to be massively distributed without the 
the consent of the participant of the individual utilizing the plateform.
<!-- Find reference-->
<!-- Proposing P2P and describing-->
P2P distribution has the potential to change structuraly the sharing of information.
P2P file sharing offer the possibility to publish to a wide audience file.
It democratized the publication and distributions of content, because the cost barier of publication of content is split
among the individual who are interested into the content.
We can see the similarities with the business model of multiple distribution platform that offer free or really cheap storage for files,
but with those alternative the cost of storage is centalize to those platfom, hence they need to find a way to monetize there activities, plus they
started there interpresize for the start for the purpose of profit generation, hence there incentif is to always increaste there profit.

by splitting the cost between all the user that participate into the network,
and are interested in keeping the content available.


In a P2P network, the peer are regarded as clients and servers,
the participant into the network download and provdied data to their other peers in the network [](cite:cites Si2021).
We can divide P2P network into two categories, structured and unstructured.
In  a structure P2P network the data is distrubted in a Distributed Hash Tables (DHTs),
a user can acquite any data from the network by doing a look up into the DHTs, 
however the lookup operation as a logarithmic time complexity in relation to the number of node,
hence in a big network it can increaste significally the query execution time [](cite:cites Folz2016, Manal2009, grall:hal-01805154).
In an unstructure approach, the peers have knowledge to a part of the peer participating into the network,
hence a peer can only have acces to a segment of the data available in the whole network.
There is multiple strategy a node can have knowledge of other peers, it can for example random [find ref](cite:cites grall:hal-01805154)
or behavioral or by profile [](Frey2014 Folz2016 Manal2009 grall:hal-01805154 Shen2014AnIP) or by [comunities](cite:cites Aebeloe2021)
The peer can discover other peer via multiple strategies such as random shuffling [](cite:cites grall:hal-01805154).
<!-- Let's elaborate more -->

A problem come from the fact that those network have no understanding of the content of the files, they only know there addresses.
Hence, it is impossible for a user to make expressive queries like in centralized systems.

<!--Division of the article -->











<!-- 
Distribution plateform
    control
        Structural incenstif to move content in a specific direction
        Making profit over user data
        Modification of public consciencness
        No democratic control
        Internet has a right/expression has a right not compatible with coorporate control of the mean of expression
Problem with P2P file shating no knowledge of what is inside the file



* Problem statement
    * what is the problem that you are trying to solve? Importance: Why is this problem important and for whom? Who will benefit and who should care? What is the impact of solving this problem (for the research community, or society in general).
* Related work 
    * Has a solution to this problem been attempted before and how? If not, have research efforts tried or solved similar problems? What can you learn from these efforts? If you are addressing an existing problem, what are the limitations of current solutions? What are you adding that is novel? Why?
* Research question(s) and hypotheses 
    * What hypotheses do you make in formulating your solution? What are the questions you need to answer in order to solve the problem? Are there boundary cases you plan to exclude or assumptions you base on?
* Preliminary results 
    * What research methods did you follow in your proposal? Have you produced any results so far?
* Evaluation
    * How do you know you’ve answered your question(s)? What are the methods you apply to test your hypotheses? Have you identified criteria to measure the degree of success of your solution?
* Reflection and future work: Are there any limitations in your approach? What are your planned next steps to complete your investigation?

Hyhpothesis:
    Uniformity of onthology, only public data, trustfullness of KG metadata

Reacher question: How can semantic overlay over P2P network improve the expressiveness of files query on the web.

Evaluation 
-->
-->