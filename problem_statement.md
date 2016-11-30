# Problem statement

    As we noted in section 2, the Four-layer possible security management framework for routing protocols will work based on two assumptions: 
    a. Security mechanisms in routing protocols are strong. So that the routers inside an autonomous system won’t be compromised in the first place.
    b. Key management protocol is strong enough. Since key management protocol manages all the shared keying materials and the parameters of security association that established among the group members. It will be a disaster if the KMP itself is not secure enough.
    
    For the first assumption, KARP and other working groups has put many efforts working on it to make the routing protocol security mechanisms more reliable. And many analysis reports and papers has been published aiming to the routing protocol security aspect, which gives us enough reasons to believe the security mechanisms in most routing protocols could be trusted.
    
     As the second assumption, KARP proposed the key management protocol framework in KARP-design-guideline RFC 6518 [7], later on RKMP[4] has been proposed to help secure the routing protocols that perform unicast exchange and MaRK[6] has been proposed to help secure routing protocols with multicast exchange. Since these proposals are working in progress now and have not been further analysed, the security of these KMPs is really a problem. Which we will discuss and analyse in the following sections.
     
     In order to better analyse the protocols and at last makes our conclusion convincible, the definition of secure should be clarified, and a set of security goals should be made. Since RKMP and MaRK are proposed by KARP working group, the general routing protocol threats document [8] and KARP threads documents [9] could be used as a starting point for establishing our goals.