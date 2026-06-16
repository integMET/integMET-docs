# Data Model Overview

integMET organizes data into three core entities: **Study**, **Differential Profile (DiffProf)**, and **Metabolite**.

## Entity Relationships

```
Study (e.g., MTBLS10)
└── DiffProf (e.g., Control_0h vs Wounding_72h)
    └── Metabolite (e.g., nicotine — ratio=0.62, down)
```

- One **Study** contains one or more **DiffProfs** (biological contrasts)
- One **DiffProf** captures a biological event with its metabolite changes
- One **Metabolite** can appear across multiple DiffProfs and Studies

## Relationships Summary

| From | To | Relationship |
|------|----|--------------|
| Study | DiffProf | One Study contains one or more DiffProfs |
| DiffProf | Study | Each DiffProf belongs to exactly one Study |
| DiffProf | Metabolite | One DiffProf contains many Metabolites (with fold-changes) |
| Metabolite | DiffProf | One Metabolite can appear in many DiffProfs |
| Metabolite | Study | One Metabolite can appear in many Studies |

## Entity Overview

### Study

A Study represents a metabolomics experiment from a public repository such as MetaboLights.

- **Identifier**: MetaboLights accession (e.g., `MTBLS10`)
- **Contains**: Title, summary, observations, findings
- **Linked metadata**: Disease terms, gene names, species, chemicals

→ [Learn more about Study](study.md)

### Differential Profile (DiffProf)

A DiffProf represents a **biological contrast or event** — a comparison between two sample groups that captures a specific biological phenomenon.

Examples of biological contrasts:
- Disease vs. Healthy
- Treated vs. Untreated
- Regenerating tissue vs. Intact tissue
- Stressed vs. Normal

Each DiffProf carries biological meaning: it describes *what changed* at the metabolite level when a specific condition or treatment was applied.

- **Identifier**: Study ID + comparison index (e.g., `MTBLS10_0001_00000005`)
- **Contains**: Two comparison groups, metabolite fold-changes, p-values, direction of change
- **Biological meaning**: Each DiffProf represents a distinct biological event with its metabolic signature

→ [Learn more about DiffProf](diffprof.md)

### Metabolite

A Metabolite is a small molecule tracked across the database.

- **Identifier**: InChIKey (e.g., `SNICXCGAKADSCV-UHFFFAOYSA-N`)
- **Contains**: Chemical identifiers (ChEBI, IUPAC name, synonyms)
- **Tracks**: Which Studies and DiffProfs this metabolite appears in

→ [Learn more about Metabolite](metabolite.md)

## Navigation Example

A typical exploration path:

1. **Start with a Study** — browse studies by keyword or condition
2. **View its DiffProfs** — see what biological comparisons were made
3. **Examine Metabolites** — find which metabolites changed significantly
4. **Trace Metabolite across DiffProfs** — discover other conditions where the same metabolite changes
