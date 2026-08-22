# Governance

This document sets out who maintains the UEFI Attack Taxonomy, how proposals are
assessed, and how versions are released. It exists so that the framework's
extensibility is a defined process rather than an invitation.

## Maintainer

Maintained by [NAME], [INSTITUTION] — [EMAIL].

Contributions are welcome. I would be glad to see maintenance become a community
effort as the framework matures; if you would like to help, open an issue saying so.

## What belongs in the taxonomy

A candidate technique or sub-technique is included if it satisfies both criteria:

1. **It is evidenced.** At least one publicly documented attack, proof of concept,
   or disclosed vulnerability demonstrates the behaviour. Embargoed or private
   findings cannot be included until public.
2. **It is firmware-specific.** The behaviour is meaningfully tied to the UEFI or
   firmware attack surface, rather than a general technique incidentally applied to
   it. Network scanning, credential phishing and generic command and control appear
   in UEFI campaigns but are not firmware behaviours; they are left to MITRE ATT&CK.

A candidate is placed as a **sub-technique** where it is a specific means of
achieving an existing technique's goal, and as a **technique** where it represents a
distinct goal within a tactic.

## How to propose a change

Open an issue using one of the two forms. No fork, clone or YAML is required.

- **Report a new attack** — a newly disclosed attack, proof of concept or
  vulnerability that fits an existing technique. This is the common case.
- **Propose a new technique** — behaviour you believe no existing technique captures.

You may also open a plain issue for a correction: a wrong identifier, a broken
reference, a description that misstates the mechanism.

## How proposals are assessed

Proposals are reviewed in batches rather than individually, so expect a response
within a few weeks rather than a few days.

Each proposal is assessed against the two criteria above. For a new technique, the
assessment also considers whether an existing technique already covers the behaviour
at an appropriate level of abstraction — the framework is intended to decompose the
firmware attack surface usefully, not exhaustively, and a proliferation of
near-identical techniques would reduce its value.

The outcome is recorded on the issue with reasoning, whether accepted or not. Where
a proposal is declined, the reasoning is part of the public record and may be cited
in later discussion.

## Versioning

Releases follow a `MAJOR.MINOR.PATCH` scheme:

- **PATCH** — corrections, clarified descriptions, added references. No structural
  change.
- **MINOR** — new techniques, sub-techniques or countermeasures; changes to how an
  existing entry is classified.
- **MAJOR** — restructuring of the tactic set, or renumbering of identifiers.
  Avoided wherever possible, since it breaks existing references.

Identifiers are never reused. A withdrawn technique is marked deprecated in place,
with the reason recorded, so that analyses citing it remain interpretable.

Every release is tagged on GitHub and archived on Zenodo with its own DOI. An
analysis conducted against a stated version therefore remains reproducible, and the
version can be cited precisely.

## Release cadence

There is no fixed schedule. Releases are cut when accumulated changes warrant one,
typically following a significant public disclosure or a batch of accepted
proposals. Committing to a cadence that is not met would be worse than committing to
none.
