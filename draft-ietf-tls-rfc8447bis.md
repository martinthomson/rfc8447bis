---
title: IANA Registry Updates for TLS and DTLS
abbrev: (D)TLS IANA Registry Updates
docname: draft-ietf-tls-rfc8447bis-latest
category: std
updates: 3749, 5077, 4680, 5246, 5705, 5878, 6520, 7301, 8447
v: 3

ipr: trust200902
area: "Security"
workgroup: "Transport Layer Security"
keyword: Internet-Draft
venue:
  group: "Transport Layer Security"
  type: "Working Group"
  mail: "tls@ietf.org"
  arch: "https://mailarchive.ietf.org/arch/browse/tls/"
  github: "tlswg/rfc8447bis"

stand_alone: yes
smart_quotes: no
pi: [toc, sortrefs, symrefs]

author:
 -
    ins: J. Salowey
    name: Joe Salowey
    organization: Venafi
    email: joe@salowey.net
 -
    ins: S. Turner
    name: Sean Turner
    organization: sn3rd
    email: sean@sn3rd.com

normative:

informative:

--- abstract

This document updates the changes to TLS and DTLS IANA registries
made in RFC 8447. It adds a new value "D" for discouraged
to the recommended column of the selected TLS registries.

This document updates the following RFCs:
3749, 5077, 4680, 5246, 5705, 5878, 6520, 7301, and 8447.

--- middle

# Introduction

This document instructs IANA to make changes to a number of the IANA
registries related to Transport Layer Security (TLS) and Datagram
Transport Layer Security (DTLS). These changes update the changes made
in {{?RFC8447}}.

<aside markdown="block">
  NOTE for IANA: This document specifies changes to the registry to update
  the changes made in {{?RFC8447}}.
</aside>

This specification updates the "Recommended" column in TLS
registries to define a third value "D" for items that are discouraged.

# Terminology

{::boilerplate bcp14-tagged}

# Adding "Recommended" Column

The instructions in this document update the Recommended column,
originally added in {{?RFC8447}} to add a third value, "D",
indicating that a value is "Discouraged". The permitted values
are:

- Y: Indicates that the IETF has consensus that the
    item is RECOMMENDED. This only means that the associated
    mechanism is fit for the purpose for which it was defined.
    Careful reading of the documentation for the mechanism is
    necessary to understand the applicability of that mechanism.
    The IETF could recommend mechanisms that have limited
    applicability, but will provide applicability statements that
    describe any limitations of the mechanism or necessary constraints
    on its use.
- N: Indicates that the item has not been evaluated by
    the IETF and that the IETF has made no statement about the
    suitability of the associated mechanism. This does not necessarily
    mean that the mechanism is flawed, only that no consensus exists.
    The IETF might have consensus to leave an items marked as "N" on
    the basis of it having limited applicability or usage constraints.
- D: Indicates that the item is discouraged. This marking could be used to identify
    mechanisms that might result in problems if they are used, such as
    a weak cryptographic algorithm or a mechanism that might cause
    interoperability problems in deployment. Implementers SHOULD
    consult the linked references associated with the item to
    determine the conditions under which it SHOULD NOT or MUST NOT be used.

Setting a value to "Y" or "D" in the "Recommended" column requires IETF Standards
Action {{!RFC8126}}.  Any state transition to or from a "Y" or "D" value requires
IESG Approval. Not all items defined in Standards Track RFCs need to be set
to "Y" or "D". Any item not otherwise specified is set to "N". The column is
blank for values that are unassigned or reserved unless specifically set.

## Recommended Note {#rec-note}

Existing registries have a note on the meaning of the recommended column. For the
registries discussed in the subsequent sections this note is updated
with a sentence describing the 'D' vaue as follows:

Note:

: If "Recommended" column is set to "N", it does not necessarily mean
that it is flawed; rather, it indicates that the item either has not
been through the IETF consensus process, has limited applicability, or
is intended only for specific use cases.  If the "Recommended" column
is set to "D" the item is discouraged and SHOULD NOT or MUST NOT be used.

# TLS ExtensionType Values

In order to refect the changes in the Recommended column allocation,
IANA SHALL update the TLS ExtensionType Values registry as follows:

- Change the registration procedure to:

~~~
    Values with the first byte in the range 0-254 (decimal) are assigned
    via Specification Required [RFC8126].  Values with the first byte
    255 (decimal) are reserved for Private Use [RFC8126].  Setting a
    "Recommended" column value to Y or D requires Standards Action {{!RFC8126}}.
    Any state transition to or from a "Y" or "D" value requires
    IESG Approval.
~~~

- Add a reference to this document under the reference heading.

- Update the "Recommended" column with the changes as listed below.  Entries
  keep their existing "Y" and "N" entries except for the entries in following table.
  A reference to this document SHALL be added to these entries.

|Value | Extension                                | Recommended |
|:-----|:------------------------------------|------------:|
|4  |truncated_hmac                  |         D |
|53 |connection_id (deprecated)      |         D |
|40 |Reserved                        |         D |
|46 |Reserved                        |         D |

- Update note on the recommended column with text in {{rec-note}}.



# TLS Cipher Suites Registry

<aside markdown="block">
  Note: Review in light of {{!I-D.ietf-tls-deprecate-obsolete-kex}}.
</aside>

In order to refect the changes in the Recommended column allocation,
IANA SHALL update the TLS ExtensionType Values registry as follows:

- Change the registration procedure to:

~~~
    Values with the first byte in the range 0-254 (decimal) are
    assigned via Specification Required [RFC8126].  Values with the
    first byte 255 (decimal) are reserved for Private Use [RFC8126].
    Setting a "Recommended" column value to Y or D requires Standards
    Action {{!RFC8126}}. Any state transition to or from a "Y" or "D"
    value requires IESG Approval.
~~~

- Add a reference to this document under the reference heading.

- Update the "Recommended" column with the changes as listed below.  Entries
  keep their existing "Y" and "N" entries except for the entries in following table.
  A reference to this document SHALL be added to these entries.

| Value | Cipher Suite Name                             | Recommeded |
|:------|:---------------------------------------------|-----------:|
| 0x00,0x01	| TLS_RSA_WITH_NULL_MD5             |   D  |
| 0x00,0x02	| TLS_RSA_WITH_NULL_SHA            |   D  |
| 0x00,0x03	| TLS_RSA_EXPORT_WITH_RC4_40_MD5            |   D  |
| 0x00,0x04	| TLS_RSA_WITH_RC4_128_MD5            |   D  |
| 0x00,0x05	| TLS_RSA_WITH_RC4_128_SHA            |   D  |
| 0x00,0x06	| TLS_RSA_EXPORT_WITH_RC2_CBC_40_MD5            |   D  |
| 0x00,0x07	| TLS_RSA_WITH_IDEA_CBC_SHA            |   D  |
| 0x00,0x08	| TLS_RSA_EXPORT_WITH_DES40_CBC_SHA            |   D  |
| 0x00,0x09	| TLS_RSA_WITH_DES_CBC_SHA            |   D  |
| 0x00,0x0B | TLS_DH_DSS_EXPORT_WITH_DES40_CBC_SHA            |   D  |
| 0x00,0x0C	| TLS_DH_DSS_WITH_DES_CBC_SHA            |   D  |
| 0x00,0x0D	| TLS_DH_DSS_WITH_3DES_EDE_CBC_SHA            |   D  |
| 0x00,0x0E	| TLS_DH_RSA_EXPORT_WITH_DES40_CBC_SHA            |   D  |
| 0x00,0x0F | TLS_DH_RSA_WITH_DES_CBC_SHA    |  D  |
| 0x00,0x11	| TLS_DHE_DSS_EXPORT_WITH_DES40_CBC_SHA            |   D  |
| 0x00,0x12	| TLS_DHE_DSS_WITH_DES_CBC_SHA            |   D  |
| 0x00,0x13	| TLS_DHE_DSS_WITH_3DES_EDE_CBC_SHA            |   D  |
| 0x00,0x14	| TLS_DHE_RSA_EXPORT_WITH_DES40_CBC_SHA            |   D  |
| 0x00,0x15	| TLS_DHE_RSA_WITH_DES_CBC_SHA           |   D  |
| 0x00,0x17	| TLS_DH_anon_EXPORT_WITH_RC4_40_MD5          |   D  |
| 0x00,0x18	| TLS_DH_anon_WITH_RC4_128_MD5            |   D  |
| 0x00,0x19	| TLS_DH_anon_EXPORT_WITH_DES40_CBC_SHA            |   D  |
| 0x00,0x1A	| TLS_DH_anon_WITH_DES_CBC_SHA           |   D  |
| 0x00,0x1B	| TLS_DH_anon_WITH_3DES_EDE_CBC_SHA           |   D  |
| 0x00,0x19	| TLS_DH_anon_EXPORT_WITH_DES40_CBC_SHA            |   D  |
| 0x00,0x1E	| TLS_KRB5_WITH_DES_CBC_SHA            |   D  |
| 0x00,0x20	| TLS_KRB5_WITH_RC4_128_SHA            |   D  |
| 0x00,0x21	| TLS_KRB5_WITH_IDEA_CBC_SHA            |   D  |
| 0x00,0x22	| TLS_KRB5_WITH_DES_CBC_MD5            |   D  |
| 0x00,0x23	| TLS_KRB5_WITH_3DES_EDE_CBC_MD5           |   D  |
| 0x00,0x24	| TLS_KRB5_WITH_RC4_128_MD5            |   D  |
| 0x00,0x25	| TLS_KRB5_WITH_IDEA_CBC_MD5           |   D  |
| 0x00,0x26	| TLS_KRB5_EXPORT_WITH_DES_CBC_40_SHA  | D |
| 0x00,0x27	| TLS_KRB5_EXPORT_WITH_RC2_CBC_40_SHA | D |
| 0x00,0x28	| TLS_KRB5_EXPORT_WITH_RC4_40_SHA	| D |
| 0x00,0x29	| TLS_KRB5_EXPORT_WITH_DES_CBC_40_MD5	 | D |
| 0x00,0x2A	| TLS_KRB5_EXPORT_WITH_RC2_CBC_40_MD5	 | D |
| 0x00,0x2B	| TLS_KRB5_EXPORT_WITH_RC4_40_MD5 | D |
| 0x00,0x8A	| TLS_PSK_WITH_RC4_128_SHA | D |
| 0x00,0x8E	| TLS_DHE_PSK_WITH_RC4_128_SHA | D |
| 0x00,0x92	| TLS_RSA_PSK_WITH_RC4_128_SHA | D |
| 0xC0,0x02	| TLS_ECDH_ECDSA_WITH_RC4_128_SHA | D |
| 0xC0,0x07	| TLS_ECDHE_ECDSA_WITH_RC4_128_SHA | D |
| 0xC0,0x0C	| TLS_ECDH_RSA_WITH_RC4_128_SHA | D |
| 0xC0,0x11	| TLS_ECDHE_RSA_WITH_RC4_128_SHA | D |
| 0xC0,0x16	| TLS_ECDH_anon_WITH_RC4_128_SHA | D |
| 0xC0,0x33	| TLS_ECDHE_PSK_WITH_RC4_128_SHA | D |


- Update note on the recommended column with text in {{rec-note}}.


# TLS Supported Groups

In order to refect the changes in the Recommended column allocation,
IANA SHALL update the TLS Supported Groups registry as follows:

- Update the registration policy to include:

~~~
    Setting a "Recommended" column value to Y or D requires Standards
    Action {{!RFC8126}}. Any state transition to or from a "Y" or "D"
    value requires IESG Approval.
~~~

- Add a reference to this document under the reference heading.

- Entries keep their existing Recommended column "Y" and "N" entries.
<aside markdown="block">
  Note: Review in light of {{!I-D.ietf-tls-deprecate-obsolete-kex}}
  also there are some weaker elliptic curves in this list.
</aside>

- Update note on the recommended column with text in {{rec-note}}.

# TLS Exporter Labels Registry

This document updates the registration procedure for the TLS Exporter
registry and updates the Recommended column allocation.
IANA SHALL update the TLS Exporter Labels Registry as follows:

- Change the registration procedure from Specification Required to
  Expert Review and update it to include:

~~~
    Setting a "Recommended" column value to Y or D requires Standards
    Action {{!RFC8126}}. Any state transition to or from a "Y" or "D"
    value requires IESG Approval.
~~~

- Add a reference to this document under the reference heading.

- Entries keep their existing Recommended column "Y" and "N" entries

- Update note on the recommended column with text in {{rec-note}}.

- update the note on the role of the expert reviewer as follows.

Note:
: The role of the designated expert is described in {{!RFC8447}}.
Even though this registry does not require a specification, the
designated expert {{!RFC8126}} will highly encourage registrants
to provide a link to a publicly available specification. An
Internet-Draft (that is posted and never published as an RFC)
or a document from another standards body, industry consortium,
university site, etc. are suitable for these purposes.
The expert may provide more in-depth reviews, but their approval
should not be taken as an endorsement of the exporter label.  The
expert also verifies that the label is a string consisting of
printable ASCII characters beginning with "EXPORTER".  IANA MUST
also verify that one label is not a prefix of any other label.
For example, labels "key" or "master secretary" are forbidden.


# TLS Certificate Types

In order to refect the changes in the Recommended column allocation,
IANA SHALL update the the TLS Certificate Types registry as follows:

- Change the registration procedure to:

~~~
    Values in the range 0-223 (decimal) are assigned via Specification
    Required [RFC8126]. Values in the range 224-255 (decimal) are
    reserved for Private Use [RFC8126]. Setting a "Recommended" column
    value to Y or D requires Standards
    Action {{!RFC8126}}. Any state transition to or from a "Y" or "D"
    value requires IESG Approval.
~~~

- Add a reference to this document under the reference heading.

- Entries keep their existing Recommended column "Y" and "N" entries.

- Update note on the recommended column with text in {{rec-note}}.


# TLS HashAlgorithm Registry

Though TLS 1.0 and TLS 1.1 were deprecated {{!RFC8996}}, TLS 1.2 will
be in use for some time. In order to refect the changes in the Recommended
column allocation, IANA SHALL update the TLS HashAlgorithm Registry
registry as follows:

- Update the registration procedure to include:

~~~
    Setting a "Recommended" column value to Y or D requires Standards
    Action {{!RFC8126}}. Any state transition to or from a "Y" or "D"
    value requires IESG Approval.
~~~

- Add a reference to this document under the reference heading.

- Update the TLS HashAlgorithm registry to add a "Recommended" column
  as follows:

| Value | Descsription | Recommended |
|:----  |:-------------|------------:|
| 0 | none | Y |
| 1 | md5  | D |
| 2 | sha1 | D |
| 3 | sha224 | D |
| 4 | sha256 | Y |
| 5 | sha384 | Y |
| 6 | sha512 | Y |
| 8 | Intrinsic | Y |

- Add note on the recommended column with text in {{rec-note}}.


# TLS SignatureAlgorithm registry

Though TLS 1.0 and TLS 1.1 were deprecated {{!RFC8996}}, TLS 1.2 will
be in use for some time. In order to refect the changes in the Recommended
column allocation, IANA SHALL update the TLS SignatureAlgorithm registry
registry as follows:

- Update the registration procedure to include:

~~~
    Setting a "Recommended" column value to Y or D requires Standards
    Action {{!RFC8126}}. Any state transition to or from a "Y" or "D"
    value requires IESG Approval.
~~~

- Add a reference to this document under the reference heading.

- Update the TLS SignatureAlgorithm registry to add a "Recommended"
  column as follows:

|Value | Descsription | Recommended |
|:-----|:-------------|------------:|
| 0 | anonymous| N |
| 1 | rsa | Y |
| 2 | dsa | N |
| 3 | ecdsa | Y |
| 7 | ed25519 | Y |
| 8 | ed448 | Y |
| 64 | gostr34102012_256 | N |
| 65 | gostr34102012_512 | N |

- Add note on the recommended column with text in {{rec-note}}.

# TLS ClientCertificateTypes registry

Though TLS 1.0 and TLS 1.1 were deprecated {{!RFC8996}}, TLS 1.2 will
be in use for some time. In order to refect the changes in the Recommended
column allocation, IANA SHALL update the  TLS ClientCertificateTypes
registry as follows:

- Update the registration procedure to include:

~~~
    Setting a "Recommended" column value to Y or D requires Standards
    Action {{!RFC8126}}. Any state transition to or from a "Y" or "D"
    value requires IESG Approval.
~~~

- Add a reference to this document under the reference heading.

- Update the TLS ClientCertificateTypes registry to add a "Recommended"
column as follows:

| Value | Descsription | Recommended |
|:------|:-------------|------------:|
| 1 | rsa_sign | Y |
| 2 | dss_sign | N |
| 3 | rsa_fixed_dh | N |
| 4 | dss_fixed_dh | N |
| 5 | rsa_ephemeral_dh_RESERVED | D |
| 6 | dss_ephemeral_dh_RESERVED | D |
| 20 | fortezza_dms_RESERVED | D |
| 64 | ecdsa_sign | Y |
| 65 | rsa_fixed_ecdh | N |
| 66 | ecdsa_fixed_ecdh | N |
| 67 | gost_sign256 | N |
| 68 | gost_sign512 | N |

- Add note on the recommended column with text in {{rec-note}}.

# TLS PskKeyExchangeMode registry

In order to refect the changes in the Recommended column allocation,
IANA SHALL update the TLS PskKeyExchangeMode registry as follows:

- Update the registration procedure to include:

~~~
    Setting a "Recommended" column value to Y or D requires Standards
    Action {{!RFC8126}}. Any state transition to or from a "Y" or "D"
    value requires IESG Approval.
~~~

- Add a reference to this document under the reference heading.

- Entries keep their existing recommended column "Y" and "N" entries.

- Update note on the recommended column with text in {{rec-note}}.

# Security Considerations

The change to Specification Required from IETF Review lowers the amount
of review provided by the WG for cipher suites and supported groups.
This change reflects reality in that the WG essentially provided no
cryptographic review of the cipher suites or supported groups.  This
was especially true of national cipher suites.

Recommended algorithms are regarded as secure for general use at the
time of registration; however, cryptographic algorithms and parameters
will be broken or weakened over time.  It is possible that the
"Recommended" status in the registry lags behind the most recent advances
in cryptanalysis.  Implementers and users need to check that the
cryptographic algorithms listed continue to provide the expected level
of security.

Designated experts ensure the specification is publicly available.  They may
provide more in-depth reviews.  Their review should not be taken as an
endorsement of the cipher suite, extension, supported group, etc.


# IANA Considerations

This document is entirely about changes to TLS-related IANA registries.


--- back
