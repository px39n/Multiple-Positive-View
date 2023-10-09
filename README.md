
![image](https://github.com/px39n/Multiple-Positive-View/assets/53490111/5d64a2b0-e607-4320-997c-ab7252ac8fe6)

This document serves as a guide for reproducing the results presented in our paper titled as "Multi-Positive-Views in Self-Supervised Learning"

**To be submitted to ICLR 2024 (Review Stage)**

------------------------------------------------
**Overview of all Supplementary Materials in Paper**

### Hyperparameters: Experimental Configurations
Can be found in the appendix section.

### Code: Re-implementation

#### Pathway1: Lightly library (Benchmark and Efficiency)
![image](https://github.com/px39n/Multiple-Positive-View/assets/53490111/c081c408-eacc-497d-bd38-46dc2b460696)

**Lightly** is a python package for self-supervised learning, making training more efficient.

**Lighly** provides with [benchmarks](https://docs.lightly.ai/self-supervised-learning/getting_started/benchmarks.html#imagenet) comparision on public datasets. 

This unified comparison paved the way for our batch experiments. Thus we present a method for code implementation (as shown in following table). Our code draws inspiration from the simplicity and continuity of Lightly, and it has been tailored specifically for multi-view scenarios in these experiments. This allows anyone to easily replicate and propose enhancements.

| Dataset      | TensorBoard Link |
|--------------|------------------|
| CIFAR100     | [Jupyter Notebook](https://tensorboard.dev/experiment/lBWExQayRpKIbuv5d0nA9Q/#scalars) |
| CIFAR10      | [Jupyter Notebook](https://github.com/px39n/Multiple-Positive-View/blob/main/Fast_Reimplement/CIFAR10.ipynb)  |
| STL-10       | [Jupyter Notebook](https://tensorboard.dev/experiment/j3SdHOk3QzOKKQksXVRxlQ/#scalars)  |
| TINYIMAGENET | [Jupyter Notebook](https://tensorboard.dev/experiment/BcdkoHAkR8O1luRVTkULwA/#scalars)  |
| ImageNette   | [Jupyter Notebookt](https://tensorboard.dev/experiment/hon7xMTqR7W3NIQ4YIlBLg/#scalars)  |




#### Pathway2: AutoSSL
We provide an in-depth analysis and diagnostic tool via an automated pipeline that we have dubbed AutoSSL. We plan to open-source this tool upon the paper's publication. Below, we outline its core functionalities and its utilization in our research.

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


### Intermediate Data During Experiments


We uploaded all raw data involved in paper.


1. Intermediate/Metrics, Meta, Records_of_Experiment
2. Intermediate/CheckPoint_of_Result_in_Tensorboard 
3. Intermediate/YAML_Config_of_Model
4. Intermediate/Calculation_for_Benchmark_Comparision.csv
5. Intermediate/Calculation_for_Transfer_Learning.xlsx
 
#### 1. Raw data Records using AutoSSL

The original data without process, including all detailed data training meta information, log, metrics, checkpoints, configuration etc,. All results are extracted and processed from them.

#### 2. Benchmark Comparision (Accessible via tensorboard services)

We provide collated TensorBoard records for various datasets used in our experiments. Below is a table that enumerates these datasets along with their corresponding TensorBoard links.
These codes adopted in Section 'Results' under Table 3 and 4, and in the Appendix under Tables 10 and 11.


| Dataset      | TensorBoard Link |
|--------------|------------------|
| CIFAR100     | [View Experiment](https://tensorboard.dev/experiment/lBWExQayRpKIbuv5d0nA9Q/#scalars) |
| CIFAR10      | [View Experiment](https://tensorboard.dev/experiment/I9NZuY9gSyeyS9qoNksAXg/#scalars)  |
| STL-10       | [View Experiment](https://tensorboard.dev/experiment/j3SdHOk3QzOKKQksXVRxlQ/#scalars)  |
| TINYIMAGENET | [View Experiment](https://tensorboard.dev/experiment/BcdkoHAkR8O1luRVTkULwA/#scalars)  |
| ImageNette   | [View Experiment](https://tensorboard.dev/experiment/hon7xMTqR7W3NIQ4YIlBLg/#scalars)  |

These TensorBoard records can be useful for gaining insights into the intermediate stages of the experiments, aiding in the fine-tuning and analysis of the model's performance.

#### 3. Configuration File for each Architecture

Please check  [AutoSSL](https://autossl.gitbook.io/) for further information.

#### 4. Intermediate Data of Calculate the Performance and Efficiency
This file contains a comprehensive record of the accuracies obtained from various methods applied across the datasets. It pinpoints the instances when 90% and 95% total accuracy milestones are achieved. Notably, there's a detailed assessment of each method's performance specifically when trained on the ImageNette dataset. Relevant references from this analysis are incorporated in Section 'Results' (Table 3 and 4) and the Appendix (Table 10 and 11).

#### 5. Calculation of Transfer Learning

collated data in form of csv.

