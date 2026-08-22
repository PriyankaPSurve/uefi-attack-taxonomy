# Changelog

All notable changes to the UEFI Attack Taxonomy are recorded here.
This project follows the versioning scheme described in [GOVERNANCE.md](GOVERNANCE.md).

## [1.1] — [DATE]

Extension following review of publicly disclosed attacks from 2023 to 2026. Nine
attacks were added to the evidence base; six mapped onto existing techniques without
modification, and two exposed gaps that the taxonomy did not previously capture.

### Added
- `UEFI-T0016.004` **Boot Resource Parsing Exploitation** — exploitation of firmware
  routines that parse attacker-supplied data files during boot. Distinguished from
  Malicious Payload Injection in that the injected artefact is data, not code.
  Evidenced by LogoFAIL.
- `UEFI-T0025.005` **Vulnerable Signed Binary Abuse** — execution of unsigned code
  under enabled Secure Boot by invoking an already-trusted signed binary containing a
  defect. Requires no compromised key material, distinguishing it from
  `UEFI-T0025.003` and `UEFI-T0035`. Evidenced by CVE-2024-7344, CVE-2025-3052, and
  the unrevoked legacy shim binaries disclosed in 2026.
- Countermeasure **Validate and restrict parsing of boot resources** under UEFI
  Hardening (PM-01), addressing the gap exposed by `UEFI-T0016.004`.

### Evidence added to existing techniques
- LogoFAIL (2023), Glupteba UEFI bootkit (2023), Bootkitty (2024),
  PKfail / CVE-2024-8105 (2024), CVE-2024-7344 (2025), HybridPetya (2025),
  Hydroph0bia / CVE-2025-4275 (2025), CVE-2025-3052 (2025), and the legacy UEFI shim
  vulnerabilities CVE-2026-8863 and CVE-2026-10797 (2026).

## [1.0] — [DATE]

Initial release: the taxonomy as described in the accompanying paper. Ten tactics,
42 techniques and 16 sub-techniques, derived from publicly documented UEFI attacks
and proofs of concept disclosed up to 2022.
