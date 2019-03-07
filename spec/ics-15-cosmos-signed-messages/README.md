---
ics: 15
title: Cosmos Signed Messages
stage: draft
category: misc
author: Aleksandr Bezobchuk <alex@tendermint.com>
created: 2019-03-07
modified: 2019-03-07
---

## Synopsis

Having the ability to sign messages off-chain has proven to be a fundamental aspect
of nearly any blockchain. The notion of signing messages off-chain has many
added benefits such as saving on computational costs and reducing transaction
throughput and overhead. Within the context of the Cosmos, some of the major
applications of signing such data includes, but is not limited to, providing a
cryptographic secure and verifiable means of proving validator identity and
possibly associating it with some other framework or organization. In addition,
having the ability to sign Cosmos messages with a Ledger or similar HSM device.

A standardized protocol for hashing, signing, and verifying messages that can be
implemented by the Cosmos SDK and other third-party organizations is needed.

## Specification

### Desired Properties

The Cosmos message signing standardized protocol subscribes to the following:

* Use of a secure cryptographic hash function (e.g. resistance to collision and second
pre-image attacks)
* Hash and sign over human-readable and machine-parsable messages
* Is invulnerable to chosen ciphertext attacks
* Allow for signing over structured data
* Contains a framework for deterministic and injective encoding of structured data
* Have builtin framework and support for domain separation and replay protection
* Has protection against potentially signing transactions a user did not intend to

### Technical Specification

The Cosmos message signing protocol will be parameterized over a secure
cryptographic hash function `H(x) → y` and a public key DSA `S → (sk, pk)`, where
`H` satisfies the desired properties such as having resistance to collision and
second pre-image attacks, as well as being
[deterministic](https://en.wikipedia.org/wiki/Hash_function#Determinism) and
[uniform](https://en.wikipedia.org/wiki/Hash_function#Uniformity) and where
`S` contains the operations <code>sign<sub>sk</sub>(x) → y</code> and
<code>verify<sub>pk</sub>(x, H) → true|false</code> which provide digital
signatures over a set of bytes and verification of signatures respectively.

### Backwards Compatibility

(discussion of compatibility or lack thereof with previous standards)

### Forwards Compatibility

(discussion of compatibility or lack thereof with expected future standards)

### Example Implementation

(link to or description of concrete example implementation)

## History

2019-03-07: Initial ICS 1 draft finished and submitted as a PR

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).