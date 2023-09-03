# Text clustering: HDBSCAN is probably all you need

[![License](https://img.shields.io/badge/License-Apache_2.0-green.svg)](https://github.com/daniel-furman/Polyglot-or-Not/blob/main/LICENSE) 
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/release/python-390/) 
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black) 

---

## Resources

<a target="_blank" href="https://colab.research.google.com/github/daniel-furman/awesome-chatgpt-prompts-clustering/blob/main/awesome-chatgpt-prompts-clustering.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>


## Citations 

* Dataset: [fka/awesome-chatgpt-prompts](https://huggingface.co/datasets/fka/awesome-chatgpt-prompts)
* Embedding Model: [sentence-transformers/all-mpnet-base-v2](https://huggingface.co/sentence-transformers/all-mpnet-base-v2)

## Experiments

* The below results correspond to `experiment_02_09_2023_16_54_32`

### Exemplars analysis

**Figure 1**. Identifying the most persistent prompts in each leaf cluster - the "exemplars". These represent the **hearts** around which the ultimate cluster forms and can be leveraged to pinpoint sub-topics in the dataset. 

![](assets/experiment_02_09_2023_16_54_32/exemplars_viz_1.png)

* See [hdbscan docs](https://hdbscan.readthedocs.io/en/latest/soft_clustering_explanation.html#distance-based-membership) for more information on exemplars

### Theme summarization

**Figure 2**. A knowledge graph visualizing each sub-cluster's core theme and exemplar prompts. The "core themes" were **automatically generated** by prompting `gpt-3.5-turbo-16k`. The figures were generated via https://jsoncrack.com/editor. 

![](assets/experiment_02_09_2023_16_54_32/cluster0_subcluster0.png)
![](assets/experiment_02_09_2023_16_54_32/cluster0_subcluster1.png)
![](assets/experiment_02_09_2023_16_54_32/cluster1_subcluster2.png)
![](assets/experiment_02_09_2023_16_54_32/cluster1_subcluster3.png)
![](assets/experiment_02_09_2023_16_54_32/cluster1_subcluster4.png)
![](assets/experiment_02_09_2023_16_54_32/cluster1_subcluster5.png)

**Figure 3**. Sub-cluster analysis through exemplar clustering and minimum distance mapping. With such outputs, the overall coverage of each theme is measurable.

![](assets/experiment_02_09_2023_16_54_32/exemplars_viz_2.png)

