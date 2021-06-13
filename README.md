# Multiple Generation Based Knowledge Distillation for Neural Networks: A Roadmap

Shangmin Guo, University of Edinburgh, s.guo@ed.ac.uk

----

## Preface

Knowledge distillation (KD) was originally proposed to compress the large models. Although the modern deep neural networks obtained very good generalisation performance on various of "artificial intelligence" tasks, their size is very large thus the inference speed is quite slow. Thus, researchers proposed to distil knowledge from a large model ("teacher") trained on a specific task to a smaller model ("student"). Since the student model is much smaller than the teacher model, the inference cost is drastically reduced. Meanwhile, the student model could obtain a very similar performance to the teacher. This sounds quite good, and people achieved their purpose. So, why should we care about the multi-generation based KD?

Well, it has been by some works that distilling knowledge can not only help to compress the size of models, but **improves** the generalisation performance of students with generation-based methods. Or, just to say, we can train students to outperform their teachers. This makes quite a lot sense, right? At least in human society, we accumulate knowledges over generations and (more efficiently) deliver them to next generation, thus every generation could know more than their parents. 

However, we may ask the following questions: 
1. why KD could work for neural networks?
2. why generation-based distillation could help student outperform teachers? 
3. what happened during the training over generations?

There is no answer yet. But, please do not be disappointed, we may could solve the above questions in the future. It is quite exciting to discove the answer of these problems.

So, let's see what progress we have made yet,

Citation:
```
@article{shangmin2021,
  title   = "Multiple Generation Based Knowledge Distillation for Neural Networks: A Roadmap",
  author  = "Shangmin Guo",
  year    = "2021",
  url     = "https://github.com/Shawn-Guo-CN/Multiple-Generation-Based-Knowledge-Distillation"
}
```

## Pre-requisites

To better understand the paper listed in the following sections, we may need some basic understanding of machine learning and probabilistic models: 
-	Pattern Recognition and Machine Learning. Christopher M. Bishop. 2006
-	Machine Learning: A Probabilistic Perspective. Kevin P. Murphy. 2012
-	Probabilistic Graphical Models : Principles and Techniques. Daphne Koller and Nir Friedman. 2009

## Theoritical Analysis of KD

### Foundamental KD

> In this section, we would list the works that proposed or tried to understand KD. This is the core works that study KD for neural networks.

- Model Compression. Cristian Bucila, Rich Caruana and Alexandru Niculescu-Mizil. 2006.
- Distilling the Knowledge in a Neural Network. Geoffrey Hinton, Oriol Vinyal and Jeff Dean. 2015.
- Born Again Neural Networks. Tommaso Furlanello, Zachary C. Lipton,  Michael Tschannen, Laurent Itti and Anima Anandkumar. 2018.
- An Embarrassingly Simple Approach for Knowledge Distillation. Mengya Gao, Yujun Shen, Quanquan Li, Junjie Yan, Liang Wan, Dahua Lin, Chen Change Loy, Xiaoou Tang. 2018.
- Distillation ≈ Early Stopping? Harvesting Dark Knowledge Utilizing Anisotropic Information Retrieval for Overparameterized Neural Network. Bin Dong, Jikai Hou, Yiping Lu, Zhihua Zhang. 2019.
- On the Efficacy of Knowledge Distillation. Jang Hyun Cho, Bharath Hariharan. 2019.
- Why Distillation Helps: a Statistical Perspective. Aditya Krishna Menon, Ankit Singh Rawat, Sashank J. Reddi, Seungyeon Kim, Sanjiv Kumar. 2020.
- Understanding and Improving Knowledge Distillation. Jiaxi Tang, Rakesh Shivanna, Zhe Zhao, Dong Lin, Anima Singh, Ed H.Chi and Sagar Jain. 2021.
- Knowledge Evolution in Neural Networks. Ahmed Taha, Abhinav Shrivastava and Larry Davis. 2021.

### Label Smoothing

> It has been shown that part of the KD derivative is equivalent to the effect brought by label smoothing. So, we also need to understand label smoothing.



### Pesudo Labels

> [TODO: explain why Pesudo Labels is related to understanding of KD]

-	Pseudo-Label : The Simple and Efficient Semi-Supervised Learning Method for Deep Neural Networks. Dong-Hyun Lee. 2013.
-	Meta Pseudo Labels. Hieu Pham, Zihang Dai, Qizhe Xie, Minh-Thang Luong, Quoc V. Le. 2020.

## Application of KD


### KD for Natural Language Processing

> Since the calculation of probability of all possible sequences in intractable, we cannot directly apply the above methods to sequence-level KD. In this section, we would first on the application in NLP. We could also treat the trajectories in reinforcement learning (RL) as sequences, but we will discuss them later since RL has different factorisation assumption.

-	Sequence-Level Knowledge Distillation. Yoon Kim and Alexander M. Rush. 2016.
-	BAM! Born-Again Multi-Task Networks for Natural Language Understanding. Kevin Clark, Minh-Thang Luong, Urvashi Khandelwal, Christopher D. Manning and Quoc V. Le. 2019.

### KD for Reinforcement Learning

> Since the key element of RL is the distribution of trajectories and their corresponding returns, the standard KD methods can not be directly applied in RL as well. Besides, the fact that RL follows the Markov property also introduces new challenges into the KD for RL.

-	Policy Distillation. Andrei A. Rusu, Sergio Gomez Colmenarejo, Caglar Gulcehre, Guillaume Desjardins, James Kirkpatrick, Razvan Pascanu, Volodymyr Mnih, Koray Kavukcuoglu, Raia Hadsell. 2016
-	Exploration by Random Network Distillation. Yuri Burda, Harrison Edwards, Amos Storkey, Oleg Klimov. 2018.