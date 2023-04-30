# SikuGPT

[TOC]

# 中文版

## 引言 

刚刚过去的2022年是生成式AI大放异彩的一年，自动生成图像的扩散模型，一键生成视频的跨模态模型，震惊世人的chatGPT，都彰显着AIGC(AI自动生成内容)的魅力。人工智能产品作为一种能够切实提升生产力的工具，正在悄然走进人们的生活，给行业发展带来变革。古籍文献、古代汉语与生成式AI的碰撞给古籍智能处理工作注入了新的活力，使用预训练模型生成文本，可以辅助古籍文本的对外翻译和知识组织工作。虽然当前以chatGPT为代表的超大规模语言模型已经能够实现与人类的无障碍交互，可以依照人类指令完成不同的自然语言处理任务，但在解答某些垂直领域的问题上，由于语料的缺乏，大语言模型有可能给出错误率较高的答案，而使用学科知识进行微调或编写提示进行上下文学习的成本又过于高昂，在真实场景中的部署仍然是一个不小的挑战。中小规模模型的应用价值主要体现在此类问题的解决上，使用领域数据预训练参数在数十亿范围的模型，可以显著提升低资源环境下的数据挖掘与生成能力。我们的研究团队在GPT2模型的基础上，开发了用于古籍文本自动生成的sikuGPT预训练模型，通过文本翻译和文本理解两类任务验证了生成式模型的性能，并开源了使用双语平行语料微调的古白翻译模型，以帮助古汉语研究者和爱好者快速阅读并掌握古籍文献的主要内容。 


## 性能验证

机器翻译任务

|  预训练模型pretrained models  |BLUE-1 | BLUE-2| BLUE-3 | BLUE-4 |
| :----------------: | :----------: | :---------: | :---------: | :---------: |
| sikuBERT+unilm | 0.6521  | 0.5291  | 0.4446 | 0.3755|
| ancientGPT | 0.7701 | 0.6143 | 0.5133 | 0.4342 |
|sikuGPT | 0.7655 |0.6172 |0.5196 | 0.4425 |

文本分类任务

|  预训练模型pretrained models  |精确率（%） |召回率（%）|F值（%） |
| :----------------: | :----------: | :---------: | :---------: |
| gpt2_chinese |86.00  | 84.02  |84.31 |
| ancientGPT |88.34 |88.38 | 88.29 |
|sikuGPT | 90.19|90.15 |90.09 |


## 使用方法

### Huggingface Transformers

基于[Huggingface Transformers](https://github.com/huggingface/transformers)的`from_pretrained`方法可以直接在线获取SikuGPT模型。

```python

from transformers import AutoTokenizer, AutoModelForCausalLM

tokenizer = AutoTokenizer.from_pretrained("JeffreyLau/SikuGPT2")

model = AutoModelForCausalLM.from_pretrained("JeffreyLau/SikuGPT2")

```

## 古文生成、古诗词生成、古白翻译预训练模型

古文生成预训练模型 **SikuGPT2**：https://huggingface.co/JeffreyLau/SikuGPT2

古诗词生成预训练模型 **SikuGPT2-poem**：https://huggingface.co/JeffreyLau/SikuGPT2-poem

古白翻译预训练模型 **SikuGPT2-translation**：https://huggingface.co/LC748NLP/SikuGPT2-translation

# English

## Introduction

In 2022, generative AI has made remarkable achievements in various fields. The diffusion models that automatically generate images, cross-modal models that generate videos with one click, and the astounding ChatGPT all showcase the charm of AIGC (AI-Generated Content). The China Academy of Information and Communications Technology pointed out in its "White Paper on Artificial Intelligence-Generated Content (AIGC) that AIGC will become a unique information production method in the web3.0 era, following PGC (Professionally Generated Content) and UGC (User Generated Content). Large-scale pre-trained models have officially entered people's lives as productivity tools, bringing about tremendous changes to the industry.In this study, we developed a SikuGPT pre-trained model based on the GPT2 model for the automatic generation of ancient texts. We verified the performance of the generative model in two categories of tasks: text translation and text comprehension. In this article, we also released an open-source Ancient Chinese-Modern Chinese translation model fine-tuned with a bilingual parallel corpus, with the twofold aim of promoting research efficiency for scholars working in Chinese ancient texts and boosting the international dissemination of Chinese ancient culture. 

## Performance verification

Machine translation task

|  pretrained models  |BLUE-1 | BLUE-2| BLUE-3 | BLUE-4 |
| :----------------: | :----------: | :---------: | :---------: | :---------: |
| sikuBERT+unilm | 0.6521  | 0.5291  | 0.4446 | 0.3755|
| ancientGPT | 0.7701 | 0.6143 | 0.5133 | 0.4342 |
|sikuGPT | 0.7655 |0.6172 |0.5196 | 0.4425 |

Text classification task

|  pretrained models  |P（%） |R（%）|F（%） |
| :----------------: | :----------: | :---------: | :---------: |
| gpt2_chinese |86.00  | 84.02  |84.31 |
| ancientGPT |88.34 |88.38 | 88.29 |
|sikuGPT | 90.19|90.15 |90.09 |

## How to use

### Huggingface Transformers

```python

from transformers import AutoTokenizer, AutoModelForCausalLM

tokenizer = AutoTokenizer.from_pretrained("JeffreyLau/SikuGPT2")

model = AutoModelForCausalLM.from_pretrained("JeffreyLau/SikuGPT2")

```

## Pre-trained model of ancient text generation, ancient poetry generation and ancient chinese - modern chinese translation

ancient text generation **SikuGPT2**：https://huggingface.co/JeffreyLau/SikuGPT2

ancient poetry generation **SikuGPT2-poem**：https://huggingface.co/JeffreyLau/SikuGPT2-poem

ancient chinese - modern chinese translation **SikuGPT2-translation**：https://huggingface.co/LC748NLP/SikuGPT2-translation



