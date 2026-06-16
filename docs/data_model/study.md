# Study

A **Study** represents a metabolomics experiment from a public data repository or published research.

## What is a Study?

Each Study in integMET corresponds to a research project that generated metabolomics data. Studies are typically derived from:

- Entries in metabolomics data repositories (e.g., MetaboLights)
- Open access publications with available data

From each Study, integMET extracts sample information and data matrices to create [Differential Profiles (DiffProfs)](diffprof.md).

## Metadata Annotation

integMET independently annotates each Study with structured metadata using natural language processing (NLP) tools. This allows users to search and filter studies by:

- Disease terms
- Gene names
- Chemical compounds
- Species
- Gene Ontology terms

## Study Fields

| Field | Description |
|-------|-------------|
| **Study ID** | Unique identifier (e.g., `MTBLS10`) |
| **Source** | Link to original repository entry |
| **Title** | Original study title |
| **Summary** | Brief description of the study |
| **Observation** | What was measured or observed |
| **Findings** | Key results from the study |

### Annotated Metadata

| Field | Description | Example |
|-------|-------------|---------|
| **Disease** | MeSH disease terms | hyperinsulinaemic androgen excess, metabolic syndrome |
| **Gene** | Gene names | apo-A1, apolipoprotein-A1 |
| **Chemical** | Chemical compounds mentioned | nitrogen |
| **Species** | NCBI Taxonomy species | Homo sapiens, Nicotiana attenuata |
| **GO Terms** | Gene Ontology annotations | — |

## Example

```
Study: MTBLS103
Title: Metabolomics reveals impaired maturation of HDL particles
       in adolescents with hyperinsulinaemic androgen excess
Summary: HDL maturation impaired in HIAE adolescents.
Observation: Serum levels of methionine sulfoxide in HIAE girls
Findings: Impaired HDL maturation linked to methionine-148 oxidation in apo-A1

Annotated diseases: hyperinsulinaemic androgen excess, metabolic syndrome,
                    hypertriglyceridemia, type 2 diabetes
Annotated genes: apo-A1
```

## Relationship to DiffProfs

One Study can contain multiple DiffProfs. Each DiffProf represents a specific biological comparison made within the Study.

For example, a study comparing disease vs. control across multiple time points might generate several DiffProfs:

```
Study: MTBLS103
├── DiffProf: Control vs HIAE (comparison 1)
├── DiffProf: Control vs HIAE (comparison 2)
└── ...
```

→ Learn more about [Differential Profiles](diffprof.md)
