---
eip: <to be assigned>
title: Explicit Canonical Spec
author: Brooklyn Zelenka (@expede)
discussions-to: https://ethereum-magicians.org/t/jello-paper-as-canonical-evm-spec/2389
status: Draft
type: Meta
created: 2019-01-11
---

## Simple Summary

Specify the Jello Paper as the canonical specification for the Ethereum Virtual Machine

Should this be for the entire client? Most likely. Put that off for a future EIP

A single source of truth produced by some formal methods and validated

## Abstract
<!--A short (~200 word) description of the technical issue being addressed.-->
A short (~200 word) description of the technical issue being addressed.

There is currently no explicit EVM spec, though it is implied to be the Yellow Paper with the concrete implementations for clarity. Many of these do not agree.


## Motivation
<!--The motivation is critical for EIPs that want to change the Ethereum protocol. It should clearly explain why the existing protocol specification is inadequate to address the problem that the EIP solves. EIP submissions without sufficient motivation may be rejected outright.-->

At time of writing:

* The Yellow Paper has holes
  * Unclear semantics
    * Some described here: https://jellopaper.org/issues/#issues-with-description-of-evm
  * [Dense, hard to follow](https://github.com/ethereum/pm/blob/master/All%20Core%20Devs%20Meetings/Meeting%2049.md#on-the-yellow-paperjello-paper-spec)

* Beige Paper is woefully incomplete

* Jello Paper
  * Formalized the semantics
  * Has identified many areas of ambiguity in the Yellow Paper
  * K generates code -- this is an executable spec

## Specification
<!--The technical specification should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations for any of the current Ethereum platforms (go-ethereum, parity, cpp-ethereum, ethereumj, ethereumjs, and [others](https://github.com/ethereum/wiki/wiki/Clients)).-->

Explicit assumptions

Such a spec should have explicit assumptions

## Rationale
<!--The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.-->

Why only EVM spec? A formally verified client spec does not (yet?) exist. A future EIP should be filed once that is available.

### Opposing Views

The primary opposing views can be summed up as follows:

* Previous investment
* Notational preferences
* Multiple specs

#### Previous Investment

#### Notational Preferences

* Some people have already invested in learning the Yellow Paper's idiomatic notation

Also discuss Multiple Specs RE notation briefly.

K has a nice feature where it can generate multiple notations

As we've seen, maintainance of any one spec has been challenging.

Mult

#### Multiple Specs (TMR)

Multiple specs


##### Scenario 1: Overlapping Feature Drift with Majority

Assume that we have specs A, B, and C, and features x and y.

If x e A and B, y e B and C, but x !e C and y !e A, we now assume that features x and y are both available. _Now none of these specs are complete._ In effect, there is a spec, but it is abstract. An implementer will have to compare all three specs, make comparisons, and discover all subelties and weights between them.

Make overlapping circle graphics

##### Scenario 2: Feature Variant

This is a special case of Scenario 1.

Assume that we have specs A and B and feature x, which is specified as variants xa and xb. This is strictly a type of Scenario 1, but will explain here as it's a nice explanitory case.

Now A and B both think that they have x, but the details differ. We really have features y and z, but it's subtle.

## Backwards Compatibility
<!--All EIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The EIP must explain how the author proposes to deal with these incompatibilities. EIP submissions without a sufficient backwards compatibility treatise may be rejected outright.-->

The Jello Paper Since the Jello Paper is more precise, client implementers may have interpreted portions of the spec differently. The Jello Paper, being a complete formal semantics, contains more information about how an implementation should behave. This does not break backwards compatability with the Yellow Paper, but it is possible that some clients will need to update their implementations.

## Test Cases
<!--Test cases for an implementation are mandatory for EIPs that are affecting consensus changes. Other EIPs can choose to include links to test cases if applicable.-->

## Implementation
<!--The implementations must be completed before any EIP is given status "Final", but it need not be completed before the EIP is accepted. While there is merit to the approach of reaching consensus on the specification and rationale before writing code, the principle of "rough consensus and running code" is still useful when it comes to resolving many discussions of API details.-->

* https://github.com/kframework/evm-semantics#installingbuilding

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
