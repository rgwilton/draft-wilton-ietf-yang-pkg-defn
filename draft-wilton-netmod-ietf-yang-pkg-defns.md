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
  I-D.draft-ietf-netmod-yang-semver:
  RFC2474:

informative:
  RFC2026:
  RFC6991:
  RFC7950:
  RFC8199:
  RFC8299:
  RFC8309:
  RFC8343:
  RFC8345:
  RFC9182:
  I-D.draft-ietf-netconf-distributed-notif:

--- abstract

The document describe the overall IETF process and approach for defining and maintaining YANG packages for IETF YANG modules.

--- middle

# Document Status

*RFC Editor: If present, please remove this section before publication.*

**Open issues are either now being tracked inline in the text or in {{OpenIssuesTracker}} for the higher level issues.**

# Conventions {#conventions}

{::boilerplate bcp14-tagged}

XXX All *YANG tree diagrams* used in this document follow the notation defined in {{RFC7950}}.  *TODO - This probably won't be required, and should be deleted.*

# Introduction

This document does not specify the exact YANG packages that are defined by defines the categories and naming conventions for packages that may be defined and stored in IANA.

## General IETF YANG Package Guidance



## Goals for managing and maintaining IETF packages

The procedure and tools described in this document are aiming to achieve the following goals:

- to provide appropriate YANG Package definitions for all IETF protocols that define YANG models

- provide updated package definitions when new IETF module versions are published.

- ensure that the YANG packages compile cleanly and the included modules and sub-packages work together.

- have the ability to have new working package definitions alongside verified stable pakage definitions.

- to coexist with the IETF consensus process.

- allow new packages

  *ISSUE - Should new IETF packages be published immediately, or perhaps on a 1, 3, 6, or 12 month cadence?  Publishing newer versions quickly allow implementations to pick up those changes immediately, but has the downside that there ends up being more variant in the published YANG packages in the wild, which may reduce interop.  There could be different rules depending on whether the changes are cosmetic, backwards compatible, or backwards compatible changes.*

# Terminology

TODO - Reference/import appropriate terminology here:

- Revision vs Version

- SemVer

- YANG Packages

- Instance data file.

# IETF YANG Package Lifecycle

All IETF YANG packages MUST be versioned using versioning rules defined in IETF Semver {{I-D.draft-ietf-netmod-yang-semver}}.

This document specifies an IETF process for creating and versioning IETF YANG packages that MUST be followed for all IETF maintained YANG packages.  The aims (requirements) for this process are three fold:

- To allow updated YANG package definitions to be provided relatively quickly to pick up fixes and new backwards compatible functionality.

- To provide long term stability for YANG packages.  E.g., perhaps particular YANG package versions are labelled as being the equivalent of long-term-support.

- To ensure that the package definitions have a level of IETF consensus from those in the Network Management Area.  It is not necessarily a requirement that the package definitions (effectively code APIs) have full IETF consensus, or follow the complete process defined in {{RFC2026}}.

## Process for creating new IETF YANG packages

TODO

- Where are IETF YANG package definitions stored?

- Are LTS versions of YANG packages stored somewhere else.  E.g., IANA vs Github.

## Process for updating existing IETF YANG packages

This section describes the process for IETF package definitions that have already been published, and hence maintenance for those packages

Thoughts:

- WG already owns the package definitions, and should have an agreed plan of how the packages should evolve.

  - There MUST be WG rough consensus before making significant changes to a package definition, e.g., adding/remove YANG modules or included packages.  Noting that it is always possible create temporary packages with different names.

- The tooling e.g., should automatically suggest/generate pre-release versions of the packages (e.g., with dev-yyyy-mm-dd(-x)), if any new sub-package or module versions are published (either released, or pre-release).


- Does the IETF define a minimum regular cadence for updating new YANG packages?

- Need to think about if/when IETF YANG modules are maintained in a more agile fashion.

- When does the consensus check occur?  Who is involved?  Do we use pre-release versions of new packages?

## IETF YANG Packaging team

*TODO - We need input from the OPS/Mgmt AD(s) on the best way to achieve this.  This document proposes a particular solution to promote discussion, before listing some potential alternatives.*

The proposal here is that a new YANG Modules & Packages Working Group (YAMP) should be created that is responsible for:



Key questions: Are there enough folks willing to work/help on this?  Does this need a BOF?

### Alternatives Considered:

1. Create a new dedicated Directorate (or expand the scope of YANG Doctors to cover this functionality).

   - At first glance, some aspects of this work may fit reasonably well with the directorate model, e.g., the task of updating package definitions when new YANG modules are proposed.

   - However, other aspects of the work, i.e., needing to update package definitions, fix issues, have more collaboration, agenda discussion time, may fit better into the WG format.

1. Use an existing WG, e.g. NETMOD, OPSAWG, or NMOP.

   - This may overload an existing WG and pull it in too many different directions, such that it wouldn't achieve sufficient focus.

1. Create a short lived WG for the initial package definitions and to ensuring that the IETF YANG modules work together, but once that task is complete, the WG closes, and future maintenance is moved to another WG, e.g., OPSAWG, NETMOD, NMOP, perhaps with YANG Doctors picking up the work for the reviews.

   - This choice hasn't been considered at this time, since the initial steps are effectively the same as creating a new WG.  If this was the desirable approach then it may affect how the charter for a new WG is written, but otherwise the decision can be deferred depending on what progress the WG makes.

1. Distribute the packaging work out to existing WGs, and then have a directorate review team (e.g., YANG Doctors) to validate that they are correct.

   - This approach has arguably been very slow for standardizing IETF YANG data models and having a more obvious central team for curating and maintaining them (i.e., a working group), may be better.

   - Obviously, the knowledge/energy for creating good YANG data models and YANG package definitions needs to come from two places: The subject matter experts and a central team to coordinate the quality of the definitions.

## IETF YANG Package Versioning

At YANG modules are updated with new functionality, or to fix bugs, and as new protocols are standardized within the IETF, with corresponding YANG data models, it is necessary to update IETF YANG package definitions with new versions.

This section describes the rules around creating new versions of IETF YANG Package definitions:

1. YANG packages MUST be versioning using YANG Semver {{I-D.draft-ietf-netmod-yang-semver}}.

1. IETF YANG packages MUST be versioned using a linear development flow for all new functionality and modified behavior.

1. Any bugfixes, whether backwards-compatible or non-backwards-compatible MUST initially be committed to the main linear development branch.

1. For fixing significant flaws, or where there is deployment demand, then bugfixes MAY also be back ported and double committed on bugfix branches for recent stable versions of a YANG package.  These branches MAY use the COMPAT modifier (section 4.3 of {{I-D.draft-ietf-netmod-yang-semver}}, if required because the next linear development version has already be used.

## Process for deprecating or removing IETF YANG packages

## Procedure for defining new package sub-groups

The procedure for defining new package sub-groups is defined in (*TODO - Add ref to sub-module registry in the IANA considerations chapter*)

## Introducing IETF 'Agile' Consensus

IETF has a well defined and well established standardization process, documented in BCP XXX.  This process works particularly well for features that are implemented in hardware (and hence have a long and expensive development cycle), and for protocols that are expected to be very stable over a long period.

Instead, the document introduces a

The process defined in this document.

# IETF Yang Module Abstraction Layers

As per section 2 of {{RFC8199}} and {{RFC8309}}, YANG modules can be classified into different abstraction layers.  In some cases, YANG packages, e.g., for common types definitions may span multiple abstraction layers.  In other cases, YANG modules are predominantly expected to be used at a single layer, although there are scenarios where a device-layer YANG modules may be mounted into a network wide abstraction layer.

This document proposes that packages be classified into the following abstraction layers:

- common - these packages contain YANG modules that span multiple abstraction layers, e.g., common YANG type definitions, {{RFC6991}}

- device - these packages contain YANG modules designed for network devices, e.g., ietf-interfaces.yang, {{RFC8343}}

- network - these packages contain YANG modules for network wide abstractions, e.g., ietf-l3vpn-ntw.yang, {{RFC9182}}

- service - these packages contain YANG modules for customer network service abstractions, e.g., ietf-l3vpn-svc.yang, {{RFC8299}}

## Common Packages



This document does not define any sub-groups for packages in the *common* package group.

## Device Packages

Device packages include sub-groups for:
- Network Mgmt protocols and features
- Routing Protocols


### Network Management Protocols and features

The devices package includes a sub-group for

### Routing Packages

#### Routing Protocol Packages

Each IETF routing protocol that defines YANG modules for the management of the protocol SHOULD define a YANG package using the naming convention *ietf-dev-routing-\<protocol-name\>-all-pkg*, that contains all protocol related YANG modules and any dependencies.

Each IETF routing protocol that defines YANG modules for the management of the protocol SHOULD define a YANG package using the naming convention *ietf-routing-\<protocol-name\>-base-pkg*, that contains only the minimal protocol specification and any dependencies.  This package SHOULD NOT include any extensions or optional functionality.

Additional routing protocol packages MAY be defined to choose different subsets of functionality.

## Network Packages

Network packages defines sub-groups for: L2VPN Services, L3VPN Services, Topology, Inventory.

## Service Packages

Service packages defined sub-groups for: L2VPN Services, L3VPN Services.

# Naming Convention for IETF package names {#IetfPackageNaming}

Using a consistent naming convention for IETF YANG package definitions is expected to help consumers more easily navigate package definitions.  IETF YANG package uses the following naming convention:

    ietf-<group>-<sub-group>-<content>-<scope>-pkg.json

In some cases, sub-groups, content and scope labels could overlap with similar meaning.  groups, sub-groups, and scopes should all be well known, so any tooling that is attempting to parse label names should be able to optimistically match group, then sub-group and scope labels with what's left being assigned to the content label (which could be empty).

Note, for the moment, all IETF package definitions are specified to end with *-pkg.json*, that helps indicate that the file is JSON and represents a YANG package on the filesystem.

- *ISSUE - It has been suggested that it might be better to register a mime type (e.g., 'ypkg') for a YANG package JSON file to avoid needing a '-pkg' in every package definition name and saving a few characters.  The other case to potential consider is when packages are referenced, is the -pkg suffix needed/helpful there.  Also worth noting that RFC 9195 has a SHOULD for ending the filename with '.json' because the package definitions end up being YANG instance data documents.*

Please see {{PackageNameExamples}} for some examples of IETF package names that follow the naming conventions.

Explanations of the labels follow:

## *group* label

| *group* label | Explanation |
| *cmn* | YANG packages that are common across all abstraction layers, e.g., common types |
| *dev* | YANG packages to be used on network devices and networked hosts |
| *ntw* | YANG packages for specifying a network wide abstraction |
| *svc* | YANG packages for specifying service wide abstractions |

The *group* labels are not expected to change frequently, hence they are specified in this document without an IANA registry, thus requiring a update to this draft if new labels are ever needed. (*RFC Editor - Please change 'draft' to 'RFC'*).

## *sub-group* label

Each *group* be optionally be further split into separate *sub-groups*, and more sub-groups may be added over time.  Thus, IANA registries are defined to allow new sub-groups to be allocated without the unnecessary overhead of publishing new RFCs.

The following table lists some example (non-normative) sub-group labels:

| group(s) label |sub-group label | Description |
| dev | rtg | Device packages related to routing protocols and associated functionality |
| ntw | topo | Network packages related to topology YANG modules |
| ntw, svc | l2vpn | Network and Service packages related to L2VPN functionality |
| dev, ntw, svr | te | Traffic Engineering related packages |

*ISSUE - This document should define some initial sub-groups categories to populate the IANA sub-group registry with.  E.g., traffic-engineering, forwarding, routing, routing-protocols, inventory.*


## *content* label

The *content* label identifies the specific contents of the package definition and are not restricted beyond the standard conventions for a valid package identifier.  The package content could represent some common types, an individual protocol or feature (e.g., BGP, OSPF, QoS, ACLs), or a set of related protocols and features (e.g., a set of Routing Protocols, or the YANG modules required for management of a basic network device).  The description field within the package should provide more details on the specification of the package contents.

The content label may be elided for a package that applies to a subgroup in its entirety.  This can seen in some of example package names in {{PackageNameExamples}}.

## *scope* label

Package scope indication is an optional label and may be elided from the package name if not useful.

| Package Scope | Explanation |
| *types* | Package definitions that only contains types, grouping and identities and does not define any instantiable data nodes, RPCs, notifications or actions. |
| *base* | Package definitions that defines minimal basic functionality and excluding less common optional functionality. |
| *all* | Complete package definitions that includes all module definitions including less common optional functionality.  |

The *scope* labels are not expected to change frequently, hence they are specified in this document without an IANA registry, thus requiring a update to this draft if new labels are ever needed. (*RFC Editor - Please change 'draft' to 'RFC'*).

# Package Definitions

This document does not contain any package definitions, because new package definitions are expected to be created and updated with a more agile process.



# Security Considerations {#security}

Not much to say here, other that saying that the YANG packages should be retrieved over a secure transport and from an authenticated end host because there is no other checks that the package definitions have not been tampered with.


# IANA Considerations

The proposed process in this document may have significant implications on IANA.  For example, if the process is accepted that we don't need to publish RFCs only the updated package definitions.

TODO - Define *sub-group* registries for labels, along with guidance (e.g., keep them short and concise).

| Package group | Sub-group | Explanation |
| *dev* | *rtg* | Routing Protocol related device packages |
| *dev* | *mgmt* | YANG Mgmt protocol and feature related device packages |
| *ntw* | *l2vpn* | L2VPN related network functionality |
| *ntw* | *l3vpn* | L3VPN related network functionality |
| *ntw* | *topo* | Topology related functionality |
| *ntw* | *te* | Traffic engineering related functionality |
| *svc* | *l2vpn* | L3VPN related network functionality |
| *svc* | *l3vpn* | L3VPN related network functionality |

*ISSUE - Should these packages be L2VPN, L3VPN or should they be L2 or L3?*

# Acknowledgments
{:numbered="false"}

TODO.

--- back

# Summary of Open Issues & Potential Enhancements {#OpenIssuesTracker}

# Example YANG Package Names {#PackageNameExamples}

The following table contains some example IETF YANG package names that follow the naming conventions in {{IetfPackageNaming}}:

| Package Name | Description |
| ietf-cmn-base-types-pkg | A package containing common YANG type definitions, e.g., like those specified in RFC 6991. |
| ietf-dev-basic-networking-pkg | A package specifying basic networking functionality for a basic router or end host. |
| ietf-dev-rtg-isis-pkg | A package for the IS-IS protocol YANG models on network devices. |
| ietf-dev-rtg-protocols-all-pkg | A package for all IETF routing protocol YANG models, to check compilation and dependencies |
| ietf-dev-all-pkg | A package for all IETF device YANG models, to check compilation and dependencies |
| ietf-ntw-l2vpn-pkg | A package for representing L2VPN network YANG models |
| ietf-ntw-all-pkg | A package for representing all network YANG models |
| ietf-svc-l3vpn-pkg | A package for representing L3VPN service YANG models |
| ietf-svc-all-pkg | A package for representing all service YANG models |

*TODO - Update the actual package definitions to follow these naming conventions, if they are agreed.*
