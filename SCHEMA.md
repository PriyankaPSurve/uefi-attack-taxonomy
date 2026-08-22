# File schema

Every entry is one YAML file. Filenames are the identifier: `UEFI-T0025.005.yml`.

## `tactics/`

| Field | Required | Notes |
|-------|----------|-------|
| `id` | yes | `UEFI-TA9001` .. `UEFI-TA9010` |
| `name` | yes | |
| `version_added` | yes | Version in which the entry first appeared |
| `description` | yes | What the adversary is trying to achieve |
| `attack_mapping` | no | Corresponding MITRE ATT&CK tactic IDs |

## `techniques/`

| Field | Required | Notes |
|-------|----------|-------|
| `id` | yes | `UEFI-T0001`, or `UEFI-T0016.004` for a sub-technique |
| `name` | yes | |
| `type` | yes | `technique` or `sub-technique` |
| `tactic` | yes | Parent tactic ID |
| `parent` | sub-techniques only | Parent technique ID |
| `version_added` | yes | |
| `description` | yes | The behaviour, not a specific attack |
| `evidence` | yes | One or more documented instances, each with references |
| `attack_mapping` | no | ATT&CK techniques this refines |
| `countermeasures` | no | Applicable countermeasures, scored 1-3 |
| `risk` | no | Impact, likelihood, effectiveness and resulting level |
| `deprecated` | no | Set with a reason if withdrawn. Identifiers are never reused. |

## `countermeasures/`

| Field | Required | Notes |
|-------|----------|-------|
| `id` | yes | `PM-01-14`: family, then position within the family |
| `name` | yes | |
| `family` / `family_name` | yes | e.g. `PM-01`, UEFI Hardening |
| `category` | yes | Preventive, Detective, Mitigation, Remediation |
| `version_added` | yes | |
| `description` | yes | |
| `references` | yes | |
| `addresses` | no | Technique IDs this countermeasure applies to |

## Applicability scale

Countermeasure applicability is scored on the scale used in the paper:

| Score | Meaning |
|-------|---------|
| 0 | Does not apply to this technique |
| 1 | Useful, indirect contribution |
| 2 | Important and quite effective |
| 3 | Highly effective, direct and critical role |
