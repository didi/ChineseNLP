# Chinese Question Answering


## Background

Question answering (QA) automatically provides answers to questions posed in natural language.  Answers may be contained in structured databases or unstructured text collections.

## Example

Input:

```
世界上最大的国家是什么?
```

Output:

```
俄国
```

## Standard Metrics

* Typical metrics are accuracy, exact match, and F1.
* Some tests require systems to locate answers in provided text, rather than return a string.
* Some tests include questions for which no answer exists in the provided database or text collection, in which case systems must return “no answer exists” to get credit.


## <span class="t">NLPCC KBQA shared task</span>.

The KBQA shared task at NLPCC 2017 asks systems to retrieve answers from a provided knowledge base (KB) of factual triples.  The knowledge base consists of 8.7m entities and 47.9m triples.
* [Shared task guideline](http://tcci.ccf.org.cn/conference/2017/dldoc/taskgline05.pdf)
* [Overview paper](http://tcci.ccf.org.cn/conference/2017/papers/2052.pdf)

The test set was formed by human annotators who selected triples.  For each triple, the annotator wrote down a natural-language question whose answer is the object of the triple.  Q/A pairs are provided, but the triple is not provided.

|  Test set | Size (Q/A pairs) | Genre |
| --- | --- | --- |
|  NLPCC-ICCPOL KBQA 2016 | 9870 | Open domain |
|  NLPCC KBQA 2017 | 7631 | Open domain |


### Metric

Averaged F1.

### Results

14 teams participated.

|  System | Averaged F1 |
| --- | --- |
|  Best anonymous score reported | 0.47 |

### Resources

|  Train set | Size (Q/A pairs) | Genre |
| --- | --- | --- |
|  NLPCC KBQA 2016/2017 | 14,609 | Open domain |


## <span class="t">NLPCC DBQA shared task</span>.

The DBQA shared task at NLPCC 2017 asks systems to 

* [Shared task guideline](http://tcci.ccf.org.cn/conference/2017/dldoc/taskgline05.pdf)
* [Overview paper](http://tcci.ccf.org.cn/conference/2017/papers/2052.pdf)

The test set was formed by human annotators who were given documents.  For each document, an annotator selected a sentence, then constructed a natural-language question whose answer is that sentence.

|  Test set | Size (document/sentence pairs) | Genre |
| --- | --- | --- |
|  NLPCC-ICCPOL DBQA 2016 | 5779 | Open domain |
|  NLPCC DBQA 2017 | 2500 | Open domain |


### Metrics

* MRR.
* MAP.
* Accuracy @ N.
* F1

### Results

NLPCC DBQA 2016

|  System | MRR | F1 |
| --- | --- | --- |
| [ERNIE 2.0](https://arxiv.org/pdf/1907.12412.pdf) | 95.8 | 85.8 |
| [Meng et. al. (2019)](https://arxiv.org/pdf/1901.10125.pdf) (Glyce + BERT) | - | 83.4 |
| [ERNIE(baidu)](https://arxiv.org/pdf/1904.09223.pdf) | 95.1 | 82.7 |
| [BERT](https://arxiv.org/pdf/1810.04805.pdf) | 94.6 | 80.8 |

NLPCC DBQA 2017

|  System | MRR | MAP | Accuracy @ 1 |
| --- | --- | --- | --- |
|  Best anonymous score reported | 72.0 | 71.7 | 59.2 |

### Resources

|  Train set | Size (document/sentence pairs) | Genre |
| --- | --- | --- |
|  NLPCC DBQA 2016/2017 | 8772 | Open domain |



## <span class="t">Machine Reading Comprehension (MRC) tasks from CLUE benchmark</span>.

[CLUE](https://github.com/CLUEbenchmark/CLUE) is a Chinese Language Understanding Evaluation benchmark. 
Machine Reading Comprehension (MRC) is a task to teach machine to read and understand unstructured text and then answer questions about it.
MRC corpus in CLUE consists of three datasets: **CMRC 2018** [(Cui et al.)](https://www.aclweb.org/anthology/D19-1600.pdf), **ChID** [(Zheng et al.)](https://www.aclweb.org/anthology/P19-1075.pdf), and **C<sup>3</sup>** [(Sun et al.)](https://arxiv.org/pdf/1904.09679.pdf).



### Metrics
* Exact Match (CMRC 2018)
* Accuracy (ChID and C<sup>3</sup>)

### Results
|  System | CMRC 2018 | ChID | C<sup>3</sup> |
| --- | --- | --- | --- |
| [HUMAN (CLUE origin)](https://github.com/CLUEbenchmark/CLUE) | 92.40 | 87.10 | 96.00 |
| [RoBERTa-wwm-ext-large (CLUE origin)](https://github.com/CLUEbenchmark/CLUE) | 76.58 | 85.37 | 72.32 |
| [BERT-base (CLUE origin)](https://github.com/CLUEbenchmark/CLUE) | 69.72 | 82.04 | 64.50 |

### Resources

[CLUE benchmark](https://www.cluebenchmarks.com/)

## Other resources.

* WebQA (Baidu) has 42k questions and answers. [link](https://arxiv.org/pdf/1607.06275.pdf)
* DuReader (Baidu) has 200k questions from online query logs. [link](https://arxiv.org/pdf/1711.05073.pdf)
* [Zhang and Zhao (2018)](http://aclweb.org/anthology/C18-1038) provide 1929 Q/A pairs in the domain of Gaokao history exam questions.


---

**Suggestions? Changes? Please send email to [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**


