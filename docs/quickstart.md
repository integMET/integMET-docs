# Quick Start

This guide helps you get started with integMET in a few minutes.

## What You Can Do

- **Explore Differential Profiles** — Browse biological comparisons (e.g., control vs. disease) together with metabolic changes
- **Find Metabolites** — Search for specific metabolites and trace their changes across studies
- **Browse Studies** — Find metabolomics studies by condition, disease, or species

## Navigation Overview

```
Home
├── Studies → click a study → see its DiffProfs
├── Diff Profiles → click a DiffProf → see metabolite changes
└── Metabolites → click a metabolite → see where it changes
```

## Example Workflows

### Workflow A: Start from a Condition

*"I'm interested in a disease or condition — what metabolites change?"*

1. Go to **Studies**
2. Browse or search for studies related to your condition
3. Click a study to see its details
4. View the **Differential Profiles** from that study
5. Examine the **Top Hits** — metabolites with significant changes

### Workflow B: Start from a Metabolite

*"I have a metabolite of interest — where does it change?"*

1. Go to **Metabolites**
2. Find your metabolite by name or identifier
3. Click to view its detail page
4. See **Studies Observed** — where this metabolite was detected
5. See **DiffProfs with Variation** — where this metabolite changed significantly

### Workflow C: Find Similar Phenomena

*"I found an interesting DiffProf — are there similar ones?"*

1. Go to **Diff Profiles**
2. Find a DiffProf of interest
3. Note the metabolites that change
4. Use the network visualization to find DiffProfs with similar metabolic signatures

## Understanding the Data

### Reading a DiffProf

When you view a Differential Profile, you'll see:

| Field | Meaning |
|-------|---------|
| **Group A vs Group B** | The two conditions being compared |
| **Significant Features** | Number of metabolites with significant changes |
| **Top Hits** | List of changed metabolites |
| **Ratio** | Fold-change (>1 = increased, <1 = decreased in Group B) |
| **Direction** | `up` or `down` in Group B relative to Group A |

### Reading a Metabolite Page

When you view a Metabolite, you'll see:

| Field | Meaning |
|-------|---------|
| **InChIKey** | Unique chemical identifier |
| **Studies Observed** | All studies where this metabolite was detected |
| **DiffProfs with Variation** | DiffProfs where this metabolite changed significantly |

## Tips

- **Start broad, then narrow down** — Browse studies first, then drill into specific DiffProfs
- **Use metabolites as links** — A metabolite connects multiple studies and conditions
- **Look for patterns** — If a metabolite changes across multiple DiffProfs, it may indicate a common biological response

## Next Steps

- Read [Concepts](concepts.md) to understand Differential Profiles in depth
- Explore the [Data Model](data_model/overview.md) to understand how data is organized
- Learn about [Network Visualization](tutorial/network_visualization.md) to find similar DiffProfs

---

TODO: Add screenshots of the integMET interface
