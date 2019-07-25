# 中文问答 (Question Answering)


## 背景

问答 (question answering) 任务试图回答自然语言形式提出的问题. 答案有可能来自结构化的数据库中，也可能来自非结构化的文本片段。

## 示例

输入:

```
世界上最大的国家是什么?
```

输出:

```
俄国
```

## 标准评价指标

* 典型的指标包括了准确性 (accuracy), 完全匹配 (exact match) 以及F1-score。
* 有些任务要求系统能在提供的文本中定位答案，而不是返回一个包含答案的字符串。
* 某些任务的测试集中包括了一些无法从提供的数据库或者文本中给出答案的问题，模型需要返回“不存在答案”才能得分。


## <span class="t">NLPCC KBQA shared task</span>.


NLPCC 2017 KBQA shared task 要求系统能够从提供事实三元组 (factual triples) 的知识库 (knowledge base) 中检索出答案。知识库包含大约8.7百万的实体 (entity)以及 47.9百万的三元组 (triple).

* [开放任务指南](http://tcci.ccf.org.cn/conference/2017/dldoc/taskgline05.pdf)
* [综述论文](http://tcci.ccf.org.cn/conference/2017/papers/2052.pdf)

测试集由人工标注生成。对于每一个三元组，标注者写下一个自然语言形式的问题 (natural-language question)，其答案是三元组的对象 (object).测试集中只提供对应的问题/答案对，但是不提供对应的三元组。


|  Test set | Size (Q/A pairs) | 主题 (Genre)  |
| --- | --- | --- |
|  NLPCC-ICCPOL KBQA 2016 | 9870 | 开放领域 |
|  NLPCC KBQA 2017 | 7631 | 开放领域 |


### 评价指标

平均 F1 (Averaged F1).

### 结果

有14支队伍参与。

|  System | Averaged F1 |
| --- | --- |
|  匿名汇报的最佳成绩 | 0.47 |

### 相关资源

|  Train set | Size (Q/A pairs) | 主题 (Genre)  |
| --- | --- | --- |
|  NLPCC KBQA 2016/2017 | 14,609 | 开放领域 |


## <span class="t">NLPCC DBQA shared task</span>.

The DBQA shared task at NLPCC 2017 任务要求:

* [Shared task guideline](http://tcci.ccf.org.cn/conference/2017/dldoc/taskgline05.pdf)
* [Overview paper](http://tcci.ccf.org.cn/conference/2017/papers/2052.pdf)

测试集由人工标注生成。标注者从给定的文章 (document) 中挑选出一个句子，并写出一个自然语言形式的问题，该问题的答案就是标注者选出的句子。

|  Test set | Size (document/sentence pairs) | 主题 (Genre)  |
| --- | --- | --- |
|  NLPCC-ICCPOL DBQA 2016 | 5779 | 开放领域 |
|  NLPCC DBQA 2017 | 2500 | 开放领域 |


### 评价指标

* MRR.
* MAP.
* Accuracy @ N.
* F1

### 结果

NLPCC DBQA 2016

|  System | MRR | F1 |
| --- | --- | --- | --- |
|  [ERNIE(baidu)](https://arxiv.org/pdf/1904.09223.pdf) | 95.1 | 82.7 |
|  [BERT](https://arxiv.org/pdf/1810.04805.pdf) | 94.6 | 80.8 |

NLPCC DBQA 2017

|  System | MRR | MAP | Accuracy @ 1 |
| --- | --- | --- | --- |

|  匿名汇报的最佳成绩 | 72.0 | 71.7 | 59.2 |

### 相关资源

|  Train set | Size (document/sentence pairs) | 主题 (Genre)  |
| --- | --- | --- |
|  NLPCC DBQA 2016/2017 | 8772 | 开放领域 |



## 其他资源

* WebQA (百度) 数据集包含 42k 问题和答案。 [链接](https://arxiv.org/pdf/1607.06275.pdf)
* DuReader (Baidu) 200k提问来自在线query日志. [链接](https://arxiv.org/pdf/1711.05073.pdf)
* [Zhang and Zhao (2018)](http://aclweb.org/anthology/C18-1038) 提供了1929组来源于高考历史考卷试题的问题/答案对 (Q/A pairs).


---

**建议? 修改? 请发邮件到 [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**


