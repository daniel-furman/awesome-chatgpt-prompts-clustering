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

* The below figures correspond to `experiment_02_09_2023_16_54_32`

### Exemplars

**Figure 1**. The most persistent prompts in each leaf cluster are known as "exemplars". These represent the hearts around which the ultimate cluster formed.

![](assets/experiment_02_09_2023_16_54_32/exemplars_viz_1.png)

* See [hdbscan docs](https://hdbscan.readthedocs.io/en/latest/soft_clustering_explanation.html#distance-based-membership) for more information on the above figure

### Sub-Clustering

**Figure 2**. Sub-clustering of exemplars helps uncover sub-topics across the dataset. The cases in each sub-cluster are then used to generate themes below.

![](assets/experiment_02_09_2023_16_54_32/exemplars_viz_2.png)

### Themes Summarization

**Figure 3**. A visualization of the dataset's themes (see leftmost elements, "core theme") and exemplars (see rightmost elements, "exemplars"). The sub-clusters are arranged in descending order by count (most frequent to least). Themes were generated by `gpt-3.5-turbo-16k`.

![](assets/experiment_02_09_2023_16_54_32/cluster1_subcluster4.png)
![](assets/experiment_02_09_2023_16_54_32/cluster1_subcluster2.png)
![](assets/experiment_02_09_2023_16_54_32/cluster1_subcluster5.png)
![](assets/experiment_02_09_2023_16_54_32/cluster0_subcluster1.png)
![](assets/experiment_02_09_2023_16_54_32/cluster1_subcluster3.png)
![](assets/experiment_02_09_2023_16_54_32/cluster0_subcluster0.png)

* The above figure was created with https://jsoncrack.com/editor
