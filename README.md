
![image](https://i.imgur.com/7XNcyMF.png)

- This is for "Multi-Positive-Views in Self-Supervised Learning" (As Supplementary)

- To be submitted to ICML 2024 (Review Stage)
  
------------------------------------------------

## Materials 1: Re-implementation Code

**Pathway1: Lightly library (for benchmark comparision)**

![image](https://i.imgur.com/R8lgMoc.png)

**Lightly** is a python package for self-supervised learning, making training more efficient, which provides with [benchmarks](https://docs.lightly.ai/self-supervised-learning/getting_started/benchmarks.html#imagenet) comparision on public datasets. 

This unified comparison paved the way for our batch experiments. Thus we present a method for code implementation (as shown in following table). Our code draws inspiration from the simplicity and continuity of Lightly, and it has been tailored specifically for multi-view scenarios in these experiments. This allows anyone to easily replicate and propose enhancements.


| Dataset      | TensorBoard Link |
|--------------|------------------|
| CIFAR100     | [Jupyter Notebook](https://github.com/px39n/Multiple-Positive-View/blob/main/Fast_Reimplement/CIFAR10.ipynb) |
| CIFAR10      | [Jupyter Notebook](https://github.com/px39n/Multiple-Positive-View/blob/main/Fast_Reimplement/CIFAR100.ipynb)  |
| STL-10       | [Jupyter Notebook](https://github.com/px39n/Multiple-Positive-View/blob/main/Fast_Reimplement/ImageNette.ipynb)  |
| TINYIMAGENET | [Jupyter Notebook](https://github.com/px39n/Multiple-Positive-View/blob/main/Fast_Reimplement/STL10.ipynb)  |
| ImageNette   | [Jupyter Notebook](https://github.com/px39n/Multiple-Positive-View/blob/main/Fast_Reimplement/TinyImageNet.ipynb)  |


**Pathway2: AutoSSL (for efficiency,ablation experiment section)**

We provide an in-depth analysis and diagnostic tool via an automated pipeline that we have dubbed AutoSSL. We plan to open-source this tool upon the paper's publication. Below, we outline its core functionalities and its utilization in our research.

[Documentation](https://autossl.gitbook.io/autossl/getting-started/configuration-supported) (Doc only for blind review)

1. Configurable Modeling
AutoSSL is designed with modularity in mind, allowing for the decomposition of models into a series of modular functions. This offers a high degree of flexibility in the experimental setup and requires only a single configuration file for specification. For instance, the primary differences between SimCLR and SimSiam—such as the stopping gradient and dimensions of specific layers—can all be specified via this configuration file.
2. Metrics and Experimental Records

Upon the completion of training, AutoSSL automatically records a comprehensive set of metrics useful for assessing the quality of self-supervised learning models. These include:

- Standard Deviation (STD) of views
- STD of batches
- STD of feature representations
- K-Nearest Neighbors (KNN) accuracy
- Linear classification accuracy
- Running time
- Forward propagation time
- Backward propagation time
- GPU utilization
---

By following the aforementioned methodologies, the experiments presented in this paper can be reliably replicated and further extended for in-depth analyses.

---

## Materials 2: Intermediate Data During Experiments


We uploaded all raw data involved in paper.


1. Intermediate/Metrics, Meta, Records_of_Experiment
2. Intermediate/CheckPoint_of_Result_in_Tensorboard 
3. Intermediate/YAML_Config_of_Model
4. Intermediate/Calculation_for_Benchmark_Comparision.csv
5. Intermediate/Calculation_for_Transfer_Learning.xlsx
 
### 1. Raw data Records using AutoSSL

The original data without process, including all detailed data training meta information, log, metrics, checkpoints, configuration etc,. All results are extracted and processed from them.

### 2. Benchmark Comparision (Accessible via tensorboard services)

We provide collated TensorBoard records for various datasets used in our experiments. Below is a table that enumerates these datasets along with their corresponding TensorBoard links.
These codes adopted in Section 'Results' under Table 3 and 4, and in the Appendix under Tables 10 and 11.

| Dataset      | TensorBoard Link |
|--------------|------------------|
| CIFAR100     | [Tensorboard](https://github.com/px39n/Multiple-Positive-View/tree/main/Traininglogs) |
| CIFAR10      | [Tensorboard](https://github.com/px39n/Multiple-Positive-View/tree/main/Traininglogs)  |
| STL-10       | [Tensorboard](https://github.com/px39n/Multiple-Positive-View/tree/main/Traininglogs)  |
| TINYIMAGENET | [Tensorboard](https://github.com/px39n/Multiple-Positive-View/tree/main/Traininglogs)  |
| ImageNette   | [Tensorboard](https://github.com/px39n/Multiple-Positive-View/tree/main/Traininglogs)  |

These TensorBoard records can be useful for gaining insights into the intermediate stages of the experiments, aiding in the fine-tuning and analysis of the model's performance.

### 3. Intermediate Data of Calculate the Performance and Efficiency
This file contains a comprehensive record of the accuracies obtained from various methods applied across the datasets. It pinpoints the instances when 90% and 95% total accuracy milestones are achieved. Notably, there's a detailed assessment of each method's performance specifically when trained on the ImageNette dataset. Relevant references from this analysis are incorporated in Section 'Results' (Table 3 and 4) and the Appendix (Table 10 and 11).

Please Check [Directory Intermediate](https://github.com/px39n/Multiple-Positive-View/tree/main/Intermediate) for more details
### 4. Calculation of Transfer Learning
collated data in form of csv.
Please Check [Transfer_Learning.csv](https://github.com/px39n/Multiple-Positive-View/blob/main/Intermediate/Calculation_for_Transfer_Learning.xlsx) for more details

## Materials 3: Experimental Configurations
Can be found in the appendix section.
 

