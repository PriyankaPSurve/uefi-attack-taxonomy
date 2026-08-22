# uefi-attack-taxonomy
# UEFI Attack Taxonomy

A structured taxonomy of adversary behaviour against UEFI firmware, organised in the
style of MITRE ATT&CK. It decomposes the pre-boot attack surface into 10 tactics,
42 techniques and 18 sub-techniques, each grounded in publicly documented attacks,
proofs of concept and disclosed vulnerabilities.

**Current version: v1.1** · [![DOI](https://zenodo.org/badge/DOI/[DOI].svg)](https://doi.org/[DOI])

---

## Why this exists

MITRE ATT&CK is an enterprise-wide framework in which the pre-boot environment is one
surface among many, represented by a small number of sub-techniques under Pre-OS Boot
(T1542). An analyst working in ATT&CK can record that a bootkit was installed, but not
the boot phase in which execution was obtained, the mechanism by which signature
enforcement was defeated, or the firmware component through which persistence was
achieved.

Those distinctions are immaterial to most enterprise detection engineering, which is why
ATT&CK does not draw them. They are precisely the distinctions that firmware-level
evidence supports and that firmware-level defences must act upon. This taxonomy is a
refinement of that region of ATT&CK for use in firmware security work, not a replacement
for it. Identifiers use a distinct range so the two can be cited together without
ambiguity.

## The ten tactics

| ID | Tactic | What the adversary is trying to do |
|----|--------|-----------------------------------|
| UEFI-TA9001 | Reconnaissance | Identify the platform, firmware version, components and supply chain |
| UEFI-TA9002 | Resource Development | Acquire access, infrastructure, credentials and exploit capability |
| UEFI-TA9003 | Delivery | Introduce the exploit or payload into the pre-OS attack surface |
| UEFI-TA9004 | Exploitation | Execute code or abuse native firmware capability |
| UEFI-TA9005 | Persistence | Survive reboot, and often reinstallation |
| UEFI-TA9006 | Defense Evasion | Subvert or bypass firmware security controls |
| UEFI-TA9007 | Discovery | Map the system from within the compromised firmware |
| UEFI-TA9008 | Privilege Escalation | Reach a more privileged firmware execution context |
| UEFI-TA9009 | Credential Access | Obtain passwords, certificates and key material |
| UEFI-TA9010 | Collection | Gather firmware-resident data for exfiltration or analysis |

Behaviour that appears in UEFI campaigns but is not firmware-specific — network scanning,
generic command and control — is deliberately excluded and left to ATT&CK.

## Repository layout

```
tactics/            one YAML file per tactic
techniques/         one YAML file per technique and sub-technique
countermeasures/    one YAML file per countermeasure, grouped by control family
CHANGELOG.md        what changed in each version, and why
GOVERNANCE.md       who maintains this, and how proposals are assessed
```

Each technique file records its identifier, name, parent tactic, description, the
documented attacks that evidence it, the ATT&CK techniques it refines, and the
countermeasures assessed as applicable.

## Proposing an addition or change

Open an issue. There are two forms and no need to fork, clone, or write YAML.

**[Report a new attack](../../issues/new?template=new-attack.yml)** — for a newly disclosed
attack, proof of concept or vulnerability that fits an existing technique. This is the
common case and takes about two minutes.

**[Propose a new technique](../../issues/new?template=new-technique.yml)** — for behaviour
you believe no existing technique captures. A candidate must be evidenced by at least one
publicly documented attack or proof of concept, and must be meaningfully specific to the
firmware attack surface rather than a general technique incidentally applied to it.

Proposals are reviewed in batches. Expect a response within a few weeks. See
[GOVERNANCE.md](GOVERNANCE.md) for how decisions are made and how versions are released.

## Versioning

Version numbers are stable reference points, so an analysis conducted against a given
version remains reproducible. New techniques or sub-techniques increment the minor
version; corrections and clarifications increment the patch version. Every release is
archived on Zenodo with its own DOI; the DOI above always resolves to the latest version.

See [CHANGELOG.md](CHANGELOG.md) for the full history.

## Citing this

If you use this taxonomy, please cite the paper:

> [AUTHORS]. Security Below the OS: A Security Analysis of UEFI.
> *Computers & Security*, [YEAR]. [DOI OR URL]

and, where the specific version matters, the archived release:

> [AUTHORS]. UEFI Attack Taxonomy (Version 1.1) [Data set]. Zenodo. https://doi.org/[DOI]

## Licence

Released under [Creative Commons Attribution 4.0 International](LICENSE) (CC BY 4.0).
You may share and adapt this material for any purpose, including commercially, provided
you give appropriate credit.

## Maintainer

Maintained by [NAME], [INSTITUTION] — [EMAIL].

Contributions are welcome, and I would be glad to see maintenance become a community
effort as the framework matures.