---
title: "IETF YANG Package Definitions"
abbrev: "Ietf Pkg Defns"
category: std

docname: draft-wilton-netmod-ietf-yang-pkg-defns-latest
submissiontype: IETF
number:
date:
consensus: true
v: 3
area: "Operations and Management"
workgroup: "Network Modelling"
keyword:
  - YANG Packages
venue:
  group: "Network Modelling"
  type: "Working Group"
  mail: "netmod@ietf.org"
  arch: "https://mailarchive.ietf.org/arch/browse/netmod/"
  github: "rgwilton/draft-ietf-package-definitions"
  latest: "https://rgwilton.github.io/draft-ietf-package-definitions/draft-wilton-netconf-ietf-package-definitions.html"

author:
 -
    fullname: Robert Wilton
    organization: Cisco Systems
    email: rwilton@cisco.com
    role: editor

normative:
  I-D.draft-netana-netconf-notif-envelope:
  RFC2474:

informative:
  RFC7950:
  I-D.draft-ietf-netconf-distributed-notif:


--- abstract

The document describe the overall process and approach for defining IETF YANG packages for IETF YANG modules.

--- middle

# Document Status

*RFC Editor: If present, please remove this section before publication.*

**Open issues are either now being tracked inline in the text or in {{OpenIssuesTracker}} for the higher level issues.**

# Conventions {#conventions}

{::boilerplate bcp14-tagged}

All *YANG tree diagrams* used in this document follow the notation defined in {{RFC7950}}.

# Introduction

{{I-D.draft-ietf-netconf-distributed-notif}} describes an architecture for how YANG datastore telemetry, e.g., {{RFC7950}}.


# Security Considerations {#security}

Not much to say here, other that saying that the YANG packages should be retrieved over a secure transport and from an authenticated end host because there is no other checks that the package definitions have not been tampered with.


# IANA Considerations

The proposed process in this document may have significant implications on IANA.  For example, if the process is accepted that we don't need to publish RFCs only the updated package definitions.

# Acknowledgments
{:numbered="false"}

TODO.

--- back

# Summary of Open Issues & Potential Enhancements {#OpenIssuesTracker}
