# Previous work

    From this section, we shall get some better understanding of the background pertaining the security problem we are going to analyse. What relevant works that has been done and where we need to improve. Also with the concepts and terms we are going to use in the following sections.

a. **Routing Protocol Security**

    The wide use of Internet in nowadays has make a great challenge to the information security. Routing protocols are used to exchange the topology information among routers within a single network or between different networks. According to the topology information, routers are able to selecting the best paths to forward packets that associated with the least cost. Without the correct routing information, forwarding of packets will be inefficient, unreachable and sometimes  causing meltdown to the whole network,  which makes the security of routing protocol the crucial problem that we have to deal with. 
    
    For routing security, a routing protocol needs to make sure the authenticity of each peer routers and also the integrity of the packets they exchange. In order to achieve that, most routing protocols using keys (or a shared secret) to authenticate its peers and using different kinds of security mechanisms to protect the packets from being modified. 
    
    Each routing protocol has one or more security mechanisms to achieve the security purpose. These security mechanisms are either build-in or varies from their transport subsystem. 
    
b. **Routing Protocol Framework**

     A Four-layer possible security management framework for routing protocols was introduced in [Nitin’s Paper].  Figure 1 shows the basic structure of these four layers.

    Layer1 is the routing protocols layer, all routing protocol that out there used exist in this layer. Routers running routing protocols to disseminating network information and maintain the routing table. Layer 2 has different kinds of security mechanisms that depends on what routing protocol the network is running. And all the associated keys/SA configurations, all kinds of security parameters are managed on Layer 3, although there are some Key Management Protocols (KMP), currently, most configurations are managed manually. We will discuss about all the KMPs later. Layer 4 represents the security configuration of all the routing and management information then automatically distribute them to every individual router.
    
c. **Key Management**

    The key/SA (stands for Security Association) management not only manage the keys, it includes various security parameters, such as the cryptographic algorithms, the lifetime of the keys and what shared materials are used to derive the key. Those parameters should not be generated manually, otherwise the network operator will have to go to each devices and configure the parameters on them, which have very high cost with low efficiency and make it very hard to maintain. In order to make key management more flexible and scalable, it is a good solution to use the Four-layer secure management framework with appropriate Key Management Protocol (KMP).

    There are large amount of routing protocols that are used in different areas, but the key management protocols are relatively fewer. Basically they can be classified into to two categories, which are unicast (IKE, IKEv2) and multicast (GDOI, G-IKEv2).

    1) **Well-Developed KMP**
    
     IKE (either IKE or IKEv2) is the protocol used to set up a security association (known as SA) in the IPsec protocol suite, it is widely used to set up a shared session secret and manage the cryptographic keys in the unicast communications. Compared to the first version, IKEv2 has a number of improvements. The need and intent of an overhaul was described in RFC 4306 so we are not going to further discuss about it.
     
     While IKE is run between two peers to establish a “pair-wise security association”, GDOI protocol is run between a group member and a "group controller/key server" (controller) and establishes a security association among two or more group members[1]. Because GDOI uses the IKEv1 Phase 1 to authenticate a group member to the group controller, when IKEv1 is obsoleted by IKEv2, it is no longer secure anymore to use GDOI. To solve the problem, there is a way to replace IKEv1 Phase to IKEv2 in GDOI to make it stronger and it is basically how G-IKEv2 comes up. Strictly speaking, G-IKEv2 is still working in progress, but the technology it used is very straightforward, therefore we are not going to further discuss about it neither, check the document[2] for more details if necessary. 

    2) **Work in Progress**
    
    The KARP[3] (Keying and Authentication for Routing Protocols) working group of IETF also working on their ways to improve security for key management of routing protocols. They have developed several proposals for KMPs that manage SA for routing protocol exchange which are still work in progress.
    
    The KARP[3] (Keying and Authentication for Routing Protocols) working group of IETF also working on their ways to improve security for key management of routing protocols. They have developed several proposals for KMPs that manage SA for routing protocol exchange which are still work in progress.
    
    G-IKEv2-MRKM: Which stands for G-IKEv2 for Multicast Router Key Management. It describes a mode of using G-IKEv2 to protect routing protocols (e.g., OSPF, PIM). The standard document is in[5]. 
    
    MaRK[6]: MaRK protocol is very similar to G-IKEv2, as we discussed before, GDOI establishes a security association among group members and a "group controller/key server" (short as GC/KS), and the GC/KS is assigned manually. In this case, if the current GC/KS crashes and the network administrator could not assign another new GC/KC, then the whole network will have huge problems. To solve the problem, instead of assigning a GC/KS, MaRK defines an election procedure to allow the network members can have the ability to elect the GC/KS by themselves. Which gives the network more fault tolerance and self-healing ability.
