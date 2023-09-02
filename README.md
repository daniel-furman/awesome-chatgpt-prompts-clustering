# Text clustering: HDBSCAN is probably all you need

[![License](https://img.shields.io/badge/License-Apache_2.0-green.svg)](https://github.com/daniel-furman/Polyglot-or-Not/blob/main/LICENSE) 
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/release/python-390/) 
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black) 

---

## Resources 

<a target="_blank" href="https://colab.research.google.com/github/daniel-furman/awesome-chatgpt-prompts-clustering/blob/main/demo_text_clustering.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

* Dataset: [fka/awesome-chatgpt-prompts](https://huggingface.co/datasets/fka/awesome-chatgpt-prompts)
* Embedding Model: [sentence-transformers/all-mpnet-base-v2](https://huggingface.co/sentence-transformers/all-mpnet-base-v2)

## Experiments

`experiment_02_09_2023_16_54_32`

### Exemplar point analysis

![](assets/exemplars_experiment_02_09_2023_16_54_32.png)

**Figure 1**. Identifying the most persistent points in each leaf cluster - the "exemplars". These represent the cluster "hearts" around which the ultimate cluster formed.

* See [hdbscan docs](https://hdbscan.readthedocs.io/en/latest/soft_clustering_explanation.html#distance-based-membership) for more information