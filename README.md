[![License](https://img.shields.io/badge/license-apache%20v2-brightgreen.svg)](https://github.com/CycloneDX/cyclonedx-property-taxonomy/blob/master/LICENSE)
[![Website](https://img.shields.io/badge/https://-cyclonedx.org-blue.svg)](https://cyclonedx.org/)
[![Slack Invite](https://img.shields.io/badge/Slack-Join-blue?logo=slack&labelColor=393939)](https://cyclonedx.org/slack/invite)
[![Group Discussion](https://img.shields.io/badge/discussion-groups.io-blue.svg)](https://groups.io/g/CycloneDX)
[![Twitter](https://img.shields.io/twitter/url/http/shields.io.svg?style=social&label=Follow)](https://twitter.com/CycloneDX_Spec)

# CycloneDX Property Taxonomy

This is the official CycloneDX property namespace and name taxonomy.

## Introduction

With the v1.3 release of the specification, custom properties have been added.

Although the specification doesn't impose restrictions on the property names used,
standardization can assist tool implementors and BOM consumers.

The authoritative source of official namespaces and property names is this repository.

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD",
"SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be
interpreted as described in [RFC2119](http://www.ietf.org/rfc/rfc2119.txt).

## Namespace Syntax

Namespaces are hierarchical and delimeted with a `:`.

As such, `:` MUST NOT be used in property namespaces and names except as a delimeter.

The only characters that SHALL be used in official property namespaces and names are alpanumerical characters, "-", "_" and " ".

### Examples

```
local:classification:CLASSIFIED
local:classification:UNCLASSIFIED
local:maintained_by:team a
local:maintained_by:team b
```

### ABNF for Official CycloneDX Property Names

```
property-name  = namespace ":" name

namespace      = namespace-part | namespace-part ":" namespace

namespace-part = *pchar

name           = *pchar

pchar          = ALPHA / DIGIT / "-" / "_" / " "
```

## Registered Top Level Namespaces

| Namespace | Description | Administered By | Taxonomy |
| --- | --- | --- | --- |
| `cdx` | Namespace for official CycloneDX namespaces and properties. Unofficial namespaces and properties MUST NOT be used under the `cdx` namespace. | CycloneDX Core Working Group | [cdx taxonomy](cdx.md) |
| `internal` | Namespace for internal use only. BOMs shared with 3rd parties SHOULD NOT include properties in the local namespace. | CycloneDX Core Working Group | N/A |

## Registering New Top Level Namespaces

It is RECOMMENDED that anyone creating custom properties outside of the `internal`
namespace SHOULD register a new top level namespace.

The process for registering a new top level namespace is to
[create a new issue requesting it](https://github.com/CycloneDX/cyclonedx-property-taxonomy/issues/new/choose).

Before requesting a new top level namespace registration you should have
publicly available documentation for the taxonomy of the namespace.

An example is the [cdx taxonomy](cdx.md).
