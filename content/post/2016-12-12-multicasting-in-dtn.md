---
title: Multicasting in Delay Tolerant Networks
date: 2016-12-12
description: "A class networks where intermittent connections between nodes makes it difficult to communicate"
tags: [
    "Java",
    "Protocol",
    "development",
    "Computer Networks"
]
---

Delay tolerant networks are named so since the connections between nodes are intermittent and hence lack instantaneous end-to-end sender-to-receiver paths. This is particularly applicable to systems that suffer disruption in infrastructure leading to huge delays in message delivery. There can be many real-life applications of delay tolerant networking like emergency response, military systems, vehicular systems and deep-space communication.

In such scenarios, there is no network infrastructure to establish an end-to-end communication path between two nodes. The messages have to be relayed via intermediate nodes that hold on to the message till they meet another node. Distribution of a message to a group of recipients can be useful in such an environment. For example, in a disaster recovery scene, it is vital to disseminate information about the victims and potential hazards among the rescue workers where there is no central arbiter. In battlefield, soldiers in a squad need to inform each other about their surrounding environment.

To disseminate messages in an efficient manner, various protocols are defined for unicast routing in DTNs. This paper studies a subset of various protocols for delay tolerant networks: First Contact, Direct Delivery, Epidemic, Spray-and-Wait and PRoPHET. A property that sets these routing protocols apart from the ones widely applicable in connected networks is that they use a store and forward approach to transmit the message to the intended end recipient. These protocols have been chosen in such a manner that few of them are single copy protocols - first contact and direct delivery, epidemic uses flooding as the underlying approach, spray and wait can be classified as controlled flooding and PRoPHET is the probability based protocol that uses delivery predictability as a metric.

Various approaches can be taken to enable and implement multicasting in the protocols discussed. A unicast based multicast is the most straightforward way of doing it, but can have potential issues. Other approaches include having an Oracle or a logical group based identifier. Based on the advantages offered by the logical unique identifier approach, it was chosen and multicast in delay tolerant networks was implemented for various protocols. Implementation was done using the ONE(Opportunistic Network Environment) simulator which has been designed for emulating delay tolerant networks and provides support for various protocols and mobility models. Leveraging the power of ONE, we analyzed and evaluated various scenarios to measure the performance of the protocols based on different parameters.

Effective group based communication in real time scenarios can be utilized in various applications in delay tolerant networks.
Having implemented the multicast functionality for various protocols in ONE simulator has helped us analyze the results of the simulations in various scenarios under varying movement models and carrier nodes. The results are highly dependent on the scenario in which particular protocol runs and there is no one single protocol which stands out in terms of all performance metrics mentioned in the evaluation section.

Probability based protocols can be very effective in scenarios where the knowledge base of each node to determine the probability of meeting every other node is accurate. PRoPHET exhibited overall decreased latency when it was given sufficient warm up time to establish the accurate knowledge. In many scenarios where there is no sufficient time to establish this knowledge base the performance of PRoPHET exhibits no significant added advantage. Scenarios like that of emergency where there is no sufficient time to establish knowledge base this protocol may not work optimally. However, in cases where this knowledge base can be established, like in case of battalion of Army, PRoPHET’s performance could be utilized for effective communication.

Flood based protocols are highly reliant methods that make sure the message goes through but they can highly overwhelm a network and in real life scenarios this can lead to congestion and eventually communication failure for all the nodes. Controlled flooding can be an optimization over such an approach to control the network traffic. Direct Delivery and First Contact can also be used depending on the need of the application and urgency of the message to get delivered.

As a part of what can be done next, one may consider incorporating the dynamic nature of node for the purpose of analysis. A node can changes its nature (group id) within a single simulation. This may affect the performance metric severely specially in cases of probability based protocols which determine their knowledge with a single target node group in mind. Also one could imagine scenarios where few nodes belong to more than one group and its effects could be observed by simulating such scenarios once implementation support for the same has been provided.