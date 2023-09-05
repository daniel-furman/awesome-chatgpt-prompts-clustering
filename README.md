# Text clustering: HDBSCAN is probably all you need

[![License](https://img.shields.io/badge/License-Apache_2.0-green.svg)](https://github.com/daniel-furman/Polyglot-or-Not/blob/main/LICENSE) 
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/release/python-390/) 
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black) 

## Goal

Segment common items in a text dataset to pinpoint core themes and their distribution. 

* Clusters cover the main topics/subtopics in the dataset
* Clusters backed by [gpt-3.5-turbo-16k](https://platform.openai.com/docs/models/gpt-3-5) generated summaries

## Background

We employ [HDBSCAN](https://hdbscan.readthedocs.io/en/latest/index.html) for probabilistic clustering. This algorithm is advantageous in many ways, including:

* Don’t be wrong: Cluster can have varying densities, don’t need to be globular, and won’t include noise
* Intuitive parameters: Choosing a minimum cluster size is very reasonable, and the number of *k* clusters does not need to be specified (HDBSCAN finds the optimal *k* for you)
* Stability: HDBSCAN is stable over runs and subsampling and has good stability over parameter choices
* Performance: When implemented well HDBSCAN can be very efficient; the current implementation has similar performance to fastcluster’s agglomerative clustering

## Citations

* Datasets
    * [fka/awesome-chatgpt-prompts](https://huggingface.co/datasets/fka/awesome-chatgpt-prompts)
    * [gustavosta/stable-diffusion-prompts](https://huggingface.co/datasets/Gustavosta/Stable-Diffusion-Prompts)  
* Embedding models
    * [sentence-transformers/all-mpnet-base-v2](https://huggingface.co/sentence-transformers/all-mpnet-base-v2)

## Experiments

<br>

### 1. Visualizing core themes in [fka/awesome-chatgpt-prompts](https://huggingface.co/datasets/fka/awesome-chatgpt-prompts)

These figures correspond to [`experiments/02_09_2023_16_54_32`](https://github.com/daniel-furman/awesome-chatgpt-prompts-clustering/tree/main/experiments/02_09_2023_16_54_32)

<a target="_blank" href="https://colab.research.google.com/github/daniel-furman/awesome-chatgpt-prompts-clustering/blob/main/notebooks/awesome-chatgpt-prompts-clustering.ipynb"> <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>

![](experiments/02_09_2023_16_54_32/assets/clusters_viz_1.png)

**Figure 1**. The clustering algorithm splits the data into three segments, "cluster 0" with 44 prompts (orange), "cluster 1" with 105 prompts (blue), and "outliers" with 4 prompts (gray). See the HDBSCAN docs on [comparing clustering algorithms](https://hdbscan.readthedocs.io/en/latest/comparing_clustering_algorithms.html#hdbscan) and [how hdbscan works](https://hdbscan.readthedocs.io/en/latest/how_hdbscan_works.html) for more information.

![](experiments/02_09_2023_16_54_32/assets/exemplars_viz_1.png)

**Figure 2**. The most persistent prompts in each leaf cluster are known as "exemplars". These represent the hearts around which the ultimate cluster formed. See the HDBSCAN docs on [soft clustering explanation](https://hdbscan.readthedocs.io/en/latest/soft_clustering_explanation.html#distance-based-membership) for supporting information and functions.

![](experiments/02_09_2023_16_54_32/assets/exemplars_viz_2.png)

**Figure 3**. Additional clustering is conducted around the exemplars to identify sub-topics in the dataset. The cases in each sub-cluster then serve as context for the [gpt-3.5-turbo-16k](https://platform.openai.com/docs/models/gpt-3-5) calls below.

![](experiments/02_09_2023_16_54_32/assets/cluster0_subcluster0.png)
![](experiments/02_09_2023_16_54_32/assets/cluster0_subcluster1.png)
![](experiments/02_09_2023_16_54_32/assets/cluster1_subcluster2.png)
![](experiments/02_09_2023_16_54_32/assets/cluster1_subcluster3.png)
![](experiments/02_09_2023_16_54_32/assets/cluster1_subcluster4.png)
![](experiments/02_09_2023_16_54_32/assets/cluster1_subcluster5.png)

**Figure 4**. A visualization of the dataset's core themes, which were generated by [gpt-3.5-turbo-16k](https://platform.openai.com/docs/models/gpt-3-5). The above was created with [jsoncrack.com/editor](https://jsoncrack.com/editor).

<br>

### 2. Drift detection for [gustavosta/stable-diffusion-prompts](https://huggingface.co/datasets/Gustavosta/Stable-Diffusion-Prompts)

![](experiments/04_09_2023_03_02_25/assets/selected_5_themes.png)

**Figure 5**. A visualization of 5 selected themes of interest. The summaries were generated by [claude-2](https://claude.ai/chats). The above was created with [jsoncrack.com/editor](https://jsoncrack.com/editor).


**More Coming**
