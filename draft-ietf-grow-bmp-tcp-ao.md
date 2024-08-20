---
v: 3
title: "TCP-AO Protection for BGP Monitoring Protocol (BMP)"
abbrev: TCP-AO for BMP
category: standard

docname: draft-ietf-grow-bmp-tcp-ao-latest
updates: 7854
submissiontype: independent  # also: "independent", "editorial", "IAB", or "IRTF"
number:
date:
consensus:
v: 3
area: Ops & Management
workgroup: GROW
keyword:
 - BMP Security
 - TCP-AO for BMP

author:
 -
    fullname: Hemant Sharma
    organization: Vodafone
    email: hemant.sharma@vodafone.com
 -
    fullname: Jeffrey Haas
    organization: Juniper Networks
    email: jhaas@juniper.net

normative:
 RFC2119:
 RFC8174:
 RFC5925:
 RFC7854:

informative:
 RFC1122:
 RFC4303:
 RFC6978:

--- abstract

This document outlines the utilization of the TCP Authentication Option (TCP-AO), as specified in RFC5925, for the authentication of BGP Monitoring Protocol (BMP) sessions, as specified in RFC7854. TCP-AO provides for the authentication of BMP sessions established between routers and BMP stations at the TCP layer.


--- middle

# Requirements Language

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL",
"SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT
RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be
interpreted as described in BCP 14 {{RFC2119}}
{{RFC8174}} when, and only when, they appear in
all capitals, as shown here.

# Introduction

The BGP Monitoring Protocol (BMP), as specified in {{RFC7854}}, recommends the use of IPsec {{RFC4303}} to address security considerations concerning the BMP session between a router and the BMP station managing BGP route collection. This document suggests the use of the TCP Authentication Option (TCP-AO) as an authentication mechanism to ensure end-to-end authentication of BMP sessions between the routers and the BMP stations. TCP-AO is also the choice of authentication for TCP-based network protocols such as BGP and LDP. A comprehensive discussion of TCP-AO is provided in {{RFC5925}}.

# TCP-AO Protection for BGP Monitoring Protocol (BMP)

The BGP Monitoring Protocol (BMP), defined in {{RFC7854}}, plays a crucial role in network management by allowing routers to share information about their BGP RIBs.  This helps operators monitor and troubleshoot their networks effectively. However, the security considerations associated with BMP have become increasingly critical in light of evolving threats. This document proposes that these threats be addressed by utilizing TCP-AO to safeguard BMP sessions.

TCP-AO provides protection against spoofed TCP segments and helps protect the integrity of the TCP session.  Further, it provides for the authentication of session endpoints.  Similar to BGP, BMP can benefit from these security properties.

TCP-AO helps protect the integrity of BMP session liveness at the TCP layer.  As outlined in {{Section 3.2 of RFC7854}}, BMP operates as a unidirectional protocol, meaning no BMP messages are transmitted from the monitoring station to the monitored router.  BMP relies on the underlying TCP session, supported by TCP keepalives {{RFC1122}}, to prevent session timeouts from the station to the monitored router.

## Operational Recommendations for BMP

The implementation and use of TCP-AO to protect BMP session is RECOMMENDED in circumstances where the session might not otherwise be protected by alternative mechanisms such as IPsec.

# Security Considerations

TCP-AO is not intended as a direct substitute for IPsec, nor is it suggested as such in this document.  The Security Considerations for TCP-AO in {{Section 11 of RFC7854}} all apply to its application for BMP.

TCP-AO may inhibit connectionless resets when session keys have been lost or changed.  This may cause BMP sessions to linger in some circumstances; however, BGP shares this consideration.

In the presence of NAT, TCP-AO requires additional support as defined in {{RFC6978}}.

TCP-AO does not provide for privacy for the BMP protocol's contents.  When this is desired, IPsec with Encapsulating Security Payload (ESP) can help provide for such privacy.

# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments
{:numbered="false"}

This document is an outcome of the experiences gained through implementing BMP. While TCP-AO safeguards other TCP protocols, BMP currently lacks the same level of protection.
