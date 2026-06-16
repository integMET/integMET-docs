# Differential Profile (DiffProf)

A **Differential Profile (DiffProf)** is the core data unit in integMET. It represents a biological contrast between two sample groups, together with the metabolite changes observed.

## What is a DiffProf?

A DiffProf captures a specific biological comparison:

- **Group A** (reference) vs. **Group B** (condition of interest)
- Which metabolites changed significantly
- The direction and magnitude of each change

Each DiffProf represents a **biological event or contrast** — such as disease onset, treatment effect, or developmental change — expressed through metabolite changes.

## DiffProf Fields

### Basic Information

| Field | Description |
|-------|-------------|
| **DiffProf ID** | Unique identifier (e.g., `MTBLS10_0001_00000005`) |
| **Study ID** | Parent study this DiffProf belongs to |
| **Title** | Comparison name (e.g., `Control_vs_HIAE`) |
| **Group A** | Reference group name and description |
| **Group B** | Condition group name and description |

### Statistical Parameters

| Field | Description |
|-------|-------------|
| **Total Features** | Number of metabolites tested |
| **Significant Features** | Number of metabolites showing significant change |
| **p-value Threshold** | Statistical significance cutoff (e.g., 0.05) |
| **Ratio Threshold** | Fold-change cutoff for significance (e.g., >1.5 or <1/1.5) |

### Significant Metabolites (Top Hits)

Each significant metabolite includes:

| Field | Description |
|-------|-------------|
| **Metabolite ID** | InChIKey identifier |
| **Ratio** | Fold-change between Group B and Group A |
| **p-value** | Statistical significance |
| **Direction** | `up` (increased in Group B) or `down` (decreased in Group B) |

## Example

```
DiffProf: MTBLS103_0001_00000001
Title: Control_vs_HIAE

Group A: Control group with no HIAE condition
Group B: Group with HIAE condition

Total Features: 9
Significant Features: 6
p-value Threshold: 0.05

Top Hits:
  - methionine sulfoxide: ratio=0.37, p=3.7e-06, down
  - glutamylglycine: ratio=0.51, p=1.2e-06, down
  - Valyl-Glutamate: ratio=0.45, p=4.2e-05, down
  - L-glutamate: ratio=0.62, p=3.7e-05, down
```

## Understanding Direction

- **up**: Metabolite level is higher in Group B than Group A
- **down**: Metabolite level is lower in Group B than Group A

The ratio indicates the magnitude:
- `ratio = 2.0` means Group B has 2× the level of Group A
- `ratio = 0.5` means Group B has half the level of Group A

## Relationship to Studies and Metabolites

```
Study (MTBLS103)
└── DiffProf (Control_vs_HIAE)
    ├── Metabolite: methionine sulfoxide (down)
    ├── Metabolite: glutamylglycine (down)
    └── ...
```

- Each DiffProf belongs to exactly one [Study](study.md)
- Each DiffProf contains multiple [Metabolites](metabolite.md) with their fold-changes
- The same Metabolite can appear in many DiffProfs across different Studies
