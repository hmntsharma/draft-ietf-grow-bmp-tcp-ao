---
title: "TCP-AO Protection for BGP Monitoring Protocol (BMP)"
category: info

docname: draft-hmntsharma-bmp-tcp-ao-latest
submissiontype: independent  # also: "independent", "editorial", "IAB", or "IRTF"
number:
date:
consensus: true
v: 3
# area: Ops & Management
# workgroup: GROW
keyword:
 - BMP Security
 - TCP-AO for BMP

author:
 -
    fullname: Hemant Sharma
    organization: Vodafone
    email: hemant.sharma@vodafone.com

normative:
informative:
 RFC5925:
 RFC7854:

--- abstract

This document outlines the utilization of the Transmission Control Protocol - Authentication Option (TCP-AO), as prescribed in RFC5925, for the authentication of Border Gateway Protocol Monitoring Protocol (BMP) sessions, as specified in RFC7854. The intent is to heighten security within the underlying Transmission Control Protocol (TCP) transport layer, ensuring the authentication of BMP sessions established between routers and BMP stations.


--- middle

# Introduction

The BGP Monitoring Protocol (BMP), as specified in RFC7854, recommends employing Internet Protocol Security (IPSec) from RFC4303 to mitigate security concerns related to the Transmission Control Protocol (TCP) session between routers and the BMP station managing BGP route collection. Recognizing the practical limitations of IPSec, this document underscores the preference for the use of Transmission Control Protocol - Authentication Option (TCP-AO) as the authentication method of choice for TCP-based network protocols such as BGP and LDP. A comprehensive discussion of TCP-AO is provided in RFC5925.

# TCP-AO Protection for BGP Monitoring Protocol (BMP)

The BGP Monitoring Protocol (BMP) outlined in RFC7854 plays a crucial role in network management by allowing routers to share information about their BGP tables, helping operators monitor and troubleshoot their networks effectively. However, the security considerations associated with BMP have become increasingly critical in light of evolving cyber threats. This document proposes that these concerns be addressed by introducing a framework that utilizes the Transmission Control Protocol - Authentication Option (TCP-AO), specified in RFC5925, to safeguard BMP sessions.

Extending this security measure to BMP helps mitigate risks associated with unauthorized access, tampering, and other potential security vulnerabilities. By integrating TCP-AO into BMP implementations, network operators can establish a more resilient and trustworthy foundation for BGP monitoring activities.


# Security Considerations

The security of the BMP session gets a boost with TCP-AO, seamlessly implemented over the existing TCP transport, ensuring heightened protection without any additional load.

# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments
{:numbered="false"}

This document is a result of BMP integration into the network. While TCP-AO safeguards other TCP protocols, BMP lacks the same level of protection within this context.
