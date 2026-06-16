# Network Visualization

integMET provides a network visualization that reveals similarities between Differential Profiles based on their metabolite changes.

## Concept

When two biological conditions cause similar metabolite changes, their DiffProfs are likely related — even if they come from different studies, species, or experimental contexts.

integMET quantifies this similarity using **iDMET** (integrated Differential Metabolite) scores and visualizes the relationships as a network.

## How the Network Works

### Nodes

Each **node** represents a DiffProf — a biological contrast with its associated metabolite changes.

### Edges

An **edge** connects two DiffProfs when they share similar metabolic changes. The similarity is calculated based on:

- Overlapping metabolites that change significantly in both DiffProfs
- Similar direction of change (both up or both down)
- Magnitude of the changes

### iDMET Score

The **iDMET** score quantifies how similar two DiffProfs are based on their shared metabolite patterns. Higher scores indicate stronger metabolic similarity.

## Exploring the Network

The network visualization allows you to:

1. **Find related phenomena** — Discover DiffProfs with similar metabolic signatures
2. **Identify clusters** — Groups of connected DiffProfs may represent related biological processes
3. **Generate hypotheses** — Unexpected connections between conditions may suggest shared mechanisms

## Example

```
Network cluster example:

    [Diabetes vs Control]
           |
           | (high iDMET)
           |
    [Obesity vs Lean] -------- [Metabolic Syndrome vs Healthy]
                      (high iDMET)
```

In this example, three DiffProfs from different studies cluster together because they share similar metabolite changes — suggesting related metabolic disruptions across these conditions.

## Use Cases

### Finding Similar Conditions

Starting from a DiffProf of interest, find other conditions with similar metabolic profiles:

1. Select your DiffProf in the network
2. Examine connected nodes (high iDMET edges)
3. Explore the biological contexts of similar DiffProfs

### Cross-Species Discovery

The network can reveal conserved metabolic responses across species:

- A stress response in plants may connect to a similar response in animals
- Drug effects in model organisms may link to human disease states

### Meta-Analysis

Use the network to identify groups of related DiffProfs for combined analysis, increasing statistical power and generalizability.

## Limitations

- Similarity is based on detected metabolites; undetected metabolites are not compared
- Different analytical platforms may detect different metabolite subsets
- High iDMET scores suggest similarity but do not prove mechanistic relationships

---

TODO: Add screenshots of the network visualization interface
