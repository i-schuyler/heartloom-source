# Source to Identity Relationship Contract v1.0

This contract defines how `heartloom-source` and `heartloom-identity` relate without collapsing their roles.

## Layer Roles

### `heartloom-source` (upstream meaning-bearing layer)

- Holds the closest currently available source texts for Heartloom’s meaning, law, and orientation.
- Preserves canonical constraints and source-level distinctions.
- Functions as the quieter north-star layer for downstream repos.
- Does not own all implementation mechanics, workflow orchestration, pack wiring, or export operations.

### `heartloom-identity` (downstream shaping/inheritance layer)

- Inherits from source and translates source into repo/ecosystem structures.
- Owns implementation-facing composition: workflows, packs, exports, operational glue, and environment-specific shaping.
- May specialize and operationalize source in bounded ways for practical use.
- Does not own upstream source meaning or canonical law.

## Inheritance and Referencing

- `heartloom-identity` inherits from `heartloom-source` by explicitly referencing source documents (path, title, and version where available).
- Source references should remain traceable so downstream translations can be audited against upstream meaning.
- When translation layers reinterpret structure, they should preserve semantic fidelity to source intent and constraints.

## Bounded Translation Rule

Allowed downstream translation in `heartloom-identity` includes:

- packaging and workflow structure
- operational sequencing and implementation framing
- repo/ecosystem mapping and integration patterns

Not allowed downstream without upstream proposal:

- changing source meaning
- changing canonical law
- redefining core ontology distinctions

## Change Flow (Governance Loop)

1. `heartloom-identity` discovers a needed change.
2. If the change affects source meaning, law, or core orientation, propose upstream in `heartloom-source` via issue/PR.
3. Source stewards review and merge (or decline) at the source layer.
4. `heartloom-identity` then updates downstream translations/references to match the accepted upstream state.
5. Implementation-specific workflow/export/pack logic remains downstream unless it changes source meaning.

## Placement Test: Source vs Identity

Put a change in `heartloom-source` when it changes:

- canonical law
- source meaning
- ontology-level distinctions
- north-star textual orientation

Put a change in `heartloom-identity` when it changes:

- workflows and automation
- pack/repo structure
- implementation choreography
- operational tooling and downstream execution patterns

When uncertain, keep source text stable, document the downstream interpretation, and open an upstream proposal if semantic change appears necessary.
