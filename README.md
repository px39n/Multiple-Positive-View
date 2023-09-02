 
# Multiple Positive Views in Self-Supervised Learning
**To be submitted to ICLR**

## Experiment Reproduction Methodologies

To verify the efficacy of our proposed approach, there are two distinct pathways for reimplementing the experiments presented in this paper. 

### 1. Plug-and-Play Integration

For a majority of view-invariant methods, our approach can be validated with minimal code adjustments. Below is the corresponding pseudo-code for the integration, ensuring all configurations such as stopping gradient, batch size, etc., remain consistent for a fair comparison.

![image](https://github.com/px39n/Multiple-Positive-View/assets/53490111/d0121c2e-290c-499a-b7c3-95066552e844)


#### Example Use-Case

In this paper, we demonstrate the applicability of our method by performing experiments on benchmark datasets using the Python library [Lightly](https://docs.lightly.ai/self-supervised-learning/getting_started/benchmarks.html#imagenet). Our method has been adapted for multi-view scenarios in these experiments.

### 2. Detailed Analysis and Diagnosis through [AutoSSL](https://autossl.gitbook.io/)

We introduce an automated pipeline, dubbed `AutoSSL`, that we intend to open-source upon the paper's publication. Below, we provide a concise description of its core functionalities and how it is utilized in our research.

#### 1. Configurable Modeling

The underlying principle behind AutoSSL is to decompose all models into a series of modular functions. This allows for high flexibility in experimental setup, requiring only a configuration file for specification. For instance, the primary difference between SimCLR and SimSiam can be attributed to the stopping gradient and the dimensions of specific layers, all of which can be specified in a configuration file.

#### 2. Metrics and Experimental Records

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


## Intermediate Data During Experiments

We provide access to the TensorBoard records for various datasets used in our experiments. Below is a table that enumerates these datasets along with their corresponding TensorBoard links.
These codes adopted in Section 'Results' under Table 2 and 3, and in the Appendix under Figure X and Tables 10 and 11.

### 1. 800 Epoches training over 5 Datasets, in Figure 2 

| Dataset      | TensorBoard Link |
|--------------|------------------|
| CIFAR100     | [View Experiment](https://tensorboard.dev/experiment/lBWExQayRpKIbuv5d0nA9Q/#scalars) |
| CIFAR10      | [View Experiment](https://tensorboard.dev/experiment/I9NZuY9gSyeyS9qoNksAXg/#scalars)  |
| STL-10       | [View Experiment](https://tensorboard.dev/experiment/j3SdHOk3QzOKKQksXVRxlQ/#scalars)  |
| TINYIMAGENET | [View Experiment](https://tensorboard.dev/experiment/BcdkoHAkR8O1luRVTkULwA/#scalars)  |
| ImageNette   | [View Experiment](https://tensorboard.dev/experiment/hon7xMTqR7W3NIQ4YIlBLg/#scalars)  |

These TensorBoard records can be useful for gaining insights into the intermediate stages of the experiments, aiding in the fine-tuning and analysis of the model's performance.


### 2. CSV File: Process Analysis
This file contains a comprehensive record of the accuracies obtained from various methods applied across the datasets. It pinpoints the instances when 90% and 95% total accuracy milestones are achieved. Notably, there's a detailed assessment of each method's performance specifically when trained on the ImageNette dataset. Relevant references from this analysis are incorporated in Section 'Results' (Table 2 and 3) and the Appendix (Table 10 and 11).
