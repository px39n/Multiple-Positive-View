# Multiple Positive View
 For Paper in ICLR


There are two ways to re-implement the experiment in Paper.



1. Fast Way

For any kind of paper, Just make sure, they have all same XX. And change multi-View

Just simply adjust the pseudo Code, like 

[Insert Psudeo code here]


For example, We have modified the All benchmark here
https://docs.lightly.ai/self-supervised-learning/getting_started/benchmarks.html#imagenet

Change to our multi-view version.


The Result in papers Please check

CIFAR100 Need Upload
CIFAR10 https://tensorboard.dev/experiment/I9NZuY9gSyeyS9qoNksAXg/#scalars
STL-10 Need Upload
TINYIMAGENET: https://tensorboard.dev/experiment/BcdkoHAkR8O1luRVTkULwA/#scalars 
ImageNette: Need Upload




2. Slow Way

We developed a auto pipeline call AutoSSL.

All model can be decomposed, so which means the only important thing is Configuration..

Please check config file.

