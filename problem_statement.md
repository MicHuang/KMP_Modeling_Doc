# 3. Problem statement

###3.1 Assumptions

    As we noted in section 2, the Four-layer possible security management framework for routing protocols will work based on two assumptions: 
    a. Security mechanisms in routing protocols are strong. So that the routers inside an autonomous system won’t be compromised in the first place.
    b. Key management protocol is strong enough. Since key management protocol manages all the shared keying materials and the parameters of security association that established among the group members. It will be a disaster if the KMP itself is not secure enough.
    
    For the first assumption, KARP and other working groups has put many efforts working on it to make the routing protocol security mechanisms more reliable. And many analysis reports and papers has been published aiming to the routing protocol security aspect, which gives us enough reasons to believe the security mechanisms in most routing protocols could be trusted.
    
     As the second assumption, KARP proposed the key management protocol framework in KARP-design-guideline RFC 6518 [7], later on RKMP[4] has been proposed to help secure the routing protocols that perform unicast exchange and MaRK[6] has been proposed to help secure routing protocols with multicast exchange. Since these proposals are working in progress now and have not been further analysed, the security of these KMPs is really a problem. Which we will discuss and analyse in the following sections.
     
###3.2 Security Definition and Properties   
####3.2.1 KMP security

    In order to better analyse the protocols and at last makes our conclusion convincible, the security defination of key management protocol should be clarified, and the security properties of those KMPs should be discussed as well.

    Due to the different usages of a protocol, the definition of security could be very wide. In order to find out a way to verify the security of the key management protocol, we need to understand what is the main purpose of a KMP.  In the documentation of ISAKMP (part of IKE)[11], it is noted that the key management protocol should be able to manage the security association and handle the establishment of cryptographic key for the Internet. So obviously, the security of a KMP is to make above procedure archive securely.


    The term “key management” refers to the establishment of cryptographic keying material for using with a cryptographic algorithm to provide protocol security services, especially integrity, authentication, and confidentiality[10]. As our main targets, RKMP and MaRK are all automated key management protocol, they derive one or more short-term session key by making use of long-term key (pre-shared symmetric secret value, RSA public key, DSA public key, and others). Apart from that, they also provide several other features such as against replay attack, authenticate each peers and ensure that short-term key is generated. 

####3.2.2 Security Properties

     (1)RKMP: As we discussed in section 2, RKMP is a modified version of IKEv2, that is to say, the properties are very similar to IKE. Such as automatically exchange keying material, set up a shared session secret from which cryptographic keys are derived. In all, the properties could be simplified as two things: First, authenticate the other peer during the exchange. Second, build a security channel between the two peers for secure communication.Unlike IKE only support devices which deploying IPsec, RKMP could be used integrated with TCP-AO, BFD or even RSVP-TE. Although the payload will certainly be different depending on the different authentication mechanism, but the properties will be the same


     (2)MaRK:


###3.3 Security Goals

     and a set of security goals should be made. Since RKMP and MaRK are proposed by KARP working group, the general routing protocol threats document [8] and KARP threads documents [9] could be used as a starting point for establishing our goals.