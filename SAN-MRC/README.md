# Stochastic Answer Networks for Machine Reading Comprehension

这个 代码实现了用于机器阅读理解的随机答案网络 (SAN)，：

Xiaodong Liu, Yelong Shen, Kevin Duh, Jianfeng Gao<br/>
Stochastic Answer Networks for Machine Reading Comprehension<br/>
Proceedings of the 56th Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers)<br/>
[arXiv version](https://arxiv.org/abs/1712.03556)

## Quickstart 

### 配置环境
1. python3.6
2. install requirements:
   
   > pip install panda==0.22.0
   >
   > pip install spadecy==2.0.12
   >
   > pip install torch==0.4.1 torchvision==0.2.1 -f https://download.pytorch.org/whl/torch_stable.html
   >
   > pip install tqdm
   >
   > pip install colorlog
3. download data/word2vec 
   
   > sh download.sh
4. You might need to download the en module for spacy
   > python -m spacy download en              # default English model (~50MB) <br/>
   > python -m spacy download en_core_web_md  # larger English model (~1GB)

### 在SQuAD v1.1上训练一个SAN模型
1. preprocess data
   
   > python prepro.py
2. train a model
   
   > python train.py

### （选择）使用ELMO
1. download ELMo resource from AllenNLP
2. train a Model with ELMo
   
   > python train.py --elmo_on

注意我们仅需要在SQuAD v1.1上进行验证的实验结果

## Notes and Acknowledgments
Some of code are adapted from: https://github.com/hitvoice/DrQA <br/>

## Results
我们对该模型产生的结果报告如下。

| Dataset | EM/F1 on Dev |
| ------- | ------- |
| `SQuAD v1.1` (Rajpurkar et al., 2016) | **76.8**/**84.6** (vs 76.2/84.1 SAN paper) |


