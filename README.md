---
config_name: tcm_mkg
task_categories:
- question-answering
- named-entity-recognition
- knowledge-graph-extraction
- text-generation
language:
- zh
- en
license: mit
size_category: 1K-10K
---

# HealthLens TCM-MKG Structured Corpus

Curated Traditional Chinese Medicine knowledge graph corpus for LLM training, RAG
retrieval and knowledge-graph research.

**Upstream**: [TCM-MKG (GraphAI-for-TCM)](https://github.com/ZENGJingqi/GraphAI-for-TCM) ·
[Zenodo 10.5281/zenodo.13763953](https://doi.org/10.5281/zenodo.13763953)
**Curator**: [HealthLens](https://healthlens.cc) · MIT

- **6,207 herb entities**, all `evidence_level: high`
- **~23,500 medicinal property records** (五味 / 归经 / 四气, each with an `x_rank × y_rank` coordinate)
- Aligned to **ICD-11 / UMLS / MeSH / DOID**
- 701 classical-text entries + 120 evidence-graded case records

Full schema, statistics and citation: [DATASET_CARD.md](./DATASET_CARD.md)

```python
from datasets import load_dataset

ds = load_dataset("lm203688/tcm-mkg", data_files="data/chp_entities.json", split="train")
print(ds)          # 6207 rows
print(ds[0])       # one herb entity
```
