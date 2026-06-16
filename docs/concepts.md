# Concepts

## The Challenge: Isolated Metabolomics Studies

Metabolomics studies generate rich data about small molecules in biological samples. However, most studies exist as isolated datasets:

- Each study uses different experimental designs
- Sample groups and conditions vary across studies
- Raw data formats and processing methods differ
- Results are difficult to compare directly

This limits the potential for reuse and discovery across studies.

## The Solution: Differential Profiles

integMET addresses this challenge by introducing the **Differential Profile (DiffProf)** as the fundamental unit of data.

### What is a Differential Profile?

A Differential Profile captures **how metabolites change between two biological conditions**.

For example:
- Disease vs. Control
- Before treatment vs. After treatment
- Mutant vs. Wild type
- Stressed vs. Normal

Each DiffProf contains:
- **Two comparison groups** (Group A vs. Group B)
- **Metabolite fold-changes** between the groups
- **Statistical significance** (p-values) for each change
- **Direction of change** (up or down)

### From Raw Data to Comparable Profiles

Traditional metabolomics produces a data matrix: rows of metabolites, columns of samples, cells containing abundance values.

integMET converts this into DiffProfs:

```
Traditional Data Matrix       →      Differential Profile

  Sample1  Sample2  ...              Group A vs Group B
  Met1: 100    150                   Met1: ratio=1.5, ↑
  Met2: 200     80                   Met2: ratio=0.4, ↓
  ...                                ...
```

By standardizing data into DiffProfs, integMET makes different studies comparable.

## Why DiffProfs Enable Integration

### 1. Universal Comparison Unit

Every biological comparison — regardless of species, tissue, or experimental platform — becomes a DiffProf. This creates a common language for metabolomics data.

### 2. Focus on Biological Contrast

A DiffProf represents a **biological event or contrast**, not just raw measurements. This captures the biologically meaningful signal: what changes when conditions differ.

### 3. Cross-Study Discovery

With thousands of DiffProfs in a standardized format, you can:

- Find studies with similar metabolic signatures
- Discover unexpected connections between different biological phenomena
- Identify metabolites that consistently change across related conditions

## Key Terminology

| Term | Definition |
|------|------------|
| **Study** | A metabolomics experiment from a public repository (e.g., MetaboLights) |
| **Differential Profile (DiffProf)** | A standardized record of metabolite changes between two conditions |
| **Metabolite** | A small molecule tracked across studies and DiffProfs |
| **iDMET** | A similarity metric that quantifies how similar two DiffProfs are based on shared metabolite changes |

## Next Steps

- Learn about the [Data Model](data_model/overview.md) to understand how Studies, DiffProfs, and Metabolites relate
- Explore the [Tutorial](tutorial/network_visualization.md) to see how DiffProf similarity networks work
