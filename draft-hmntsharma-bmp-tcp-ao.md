---
###
# Internet-Draft Markdown Template
#
# Rename this file from draft-todo-yourname-protocol.md to get started.
# Draft name format is "draft-<yourname>-<workgroup>-<name>.md".
#
# For initial setup, you only need to edit the first block of fields.
# Only "title" needs to be changed; delete "abbrev" if your title is short.
# Any other content can be edited, but be careful not to introduce errors.
# Some fields will be set automatically during setup if they are unchanged.
#
# Don't include "-00" or "-latest" in the filename.
# Labels in the form draft-<yourname>-<workgroup>-<name>-latest are used by
# the tools to refer to the current version; see "docname" for example.
#
# This template uses kramdown-rfc: https://github.com/cabo/kramdown-rfc
# You can replace the entire file if you prefer a different format.
# Change the file extension to match the format (.xml for XML, etc...)
#
###
title: "TCP-AO Protection for BGP Monitoring Protocol (BMP)"
category: info

docname: draft-hmntsharma-bmp-tcp-ao.md
submissiontype: independent  # also: "independent", "editorial", "IAB", or "IRTF"
number:
date:
consensus: true
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

normative: 

informative: 
[RFC 5925] The TCP Authentication Option
[RFC 7854] BGP Monitoring Protocol (BMP)

--- abstract

This document outlines the utilization of the Transmission Control Protocol - Authentication Option (TCP-AO), as prescribed in RFC 5295, for the authentication of Border Gateway Protocol Monitoring Protocol (BMP) sessions, as specified in RFC 7854. The intent is to heighten security within the underlying Transmission Control Protocol (TCP) transport layer, ensuring the authentication of BMP sessions conducted between routers and BMP stations.


--- middle

# Introduction

The BGP Monitoring Protocol (BMP), as specified in RFC 7854, recommends employing Internet Protocol Security (IPSec) from RFC 4303 to mitigate security concerns related to the Transmission Control Protocol (TCP) session between routers and the BMP station managing BGP route collection. Recognizing the practical limitations of IPSec, this document underscores the preference for the use of Transmission Control Protocol - Authentication Option (TCP-AO) as the authentication method of choice for TCP-based network protocols such as BGP and LDP. A comprehensive discussion of TCP-AO is provided in RFC 5295.

# TCP-AO Protection for BGP Monitoring Protocol (BMP)

The BGP Monitoring Protocol (BMP) outlined in RFC 7854 plays a crucial role in network management by allowing routers to share information about their BGP tables, helping operators monitor and troubleshoot their networks effectively. However, the security considerations associated with BMP have become increasingly critical in light of evolving cyber threats. This document addresses these concerns by introducing a framework that utilizes the Transmission Control Protocol - Authentication Option (TCP-AO), specified in RFC 5295, to safeguard BMP sessions.

Extending this security measure to BMP helps mitigate risks associated with unauthorized access, tampering, and other potential security vulnerabilities. By integrating TCP-AO into BMP implementations, network operators can establish a more resilient and trustworthy foundation for BGP monitoring activities.



# Security Considerations

The security of the BMP session gets a boost with TCP-AO, seamlessly implemented over the existing TCP transport, ensuring heightened protection without any additional load.

# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments
{:numbered="false"}

This document is a result of BMP integration into the network. While TCP-AO safeguards other TCP protocols, BMP lacks the same level of protection within this context.
