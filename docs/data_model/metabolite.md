# Metabolite

A **Metabolite** is a small molecule tracked across the integMET database. Each metabolite records where it was observed and where it showed significant changes.

## What is a Metabolite in integMET?

integMET tracks metabolites across all Studies and DiffProfs. For each metabolite, you can find:

- Which Studies detected this metabolite
- Which DiffProfs show significant changes in this metabolite
- Chemical identifiers for external database lookup

This allows you to trace a metabolite back to its biological contexts — discovering which conditions, treatments, or diseases affect its levels.

## Metabolite Fields

### Chemical Identifiers

| Field | Description |
|-------|-------------|
| **InChIKey** | Unique structural identifier (e.g., `SNICXCGAKADSCV-UHFFFAOYSA-N`) |
| **ChEBI ID** | ChEBI database identifier |
| **IUPAC Name** | Systematic chemical name |
| **Synonym** | Common name (e.g., "Rutin", "Reserpin") |
| **Reactome IDs** | Links to Reactome pathways |

### Observation Tracking

| Field | Description |
|-------|-------------|
| **Studies Observed** | List of Studies where this metabolite was detected |
| **DiffProfs Observed** | List of DiffProfs where this metabolite appears |
| **Studies with Variation** | Studies where this metabolite showed significant change |
| **DiffProfs with Variation** | DiffProfs where this metabolite showed significant change |

## Example

```
Metabolite: Reserpin
InChIKey: QEVHRUUCFGRFIF-MDEJGZGSSA-N
ChEBI ID: 28487

Observed in 9 studies:
  MTBLS10, MTBLS3750, MTBLS3963, MTBLS4463, ...

Significant variation in 3 DiffProfs:
  MTBLS3750_0002_00000006
  MTBLS4463_0001_00000001
  MTBLS5195_0001_00000001
```

## Tracing Metabolites to Biological Contexts

A key feature of integMET is the ability to ask: *"Where does this metabolite change?"*

Starting from a metabolite, you can:

1. Find all DiffProfs where it shows significant variation
2. Examine the biological contrasts in those DiffProfs
3. Discover patterns across different conditions

```
Metabolite: Rutin
└── Significant in DiffProfs:
    ├── MTBLS1191: Disease vs Control (liver condition)
    ├── MTBLS2384: Treated vs Untreated (drug response)
    └── MTBLS3518: Stressed vs Normal (environmental stress)
```

This reveals that Rutin levels change across diverse biological contexts — potentially indicating shared metabolic responses.

## Relationship to Studies and DiffProfs

```
Metabolite (Rutin)
├── Observed in Study: MTBLS1191
│   └── Significant in DiffProf: MTBLS1191_0001_00000001
├── Observed in Study: MTBLS2384
│   └── Significant in DiffProf: MTBLS2384_0002_00000003
└── ...
```

- One Metabolite can appear in many [Studies](study.md)
- One Metabolite can show significant changes in many [DiffProfs](diffprof.md)
- This cross-referencing enables discovery of shared metabolic patterns
