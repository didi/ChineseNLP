# 中文分词 (Word Segmentation)


## 背景

中文里每个汉字即为一个字符 (character)。 一个单词通常由一个或多个字符 (character) 组成。 单词之间没有空格。分词 (segmentation) 是将一系列无空格间隔字符串分割成一系列单词的过程。

## 示例

输入:

```
亲 请问有什么可以帮您的吗？
```

输出:

```
亲 请问 有 什么 可以 帮 您 的 吗 ？
```

## 标准评价指标

单词级别的 F1-score:

> Gold: 共同  创造  美好  的  新  世纪  ——  二○○一年  新年  贺词

> Hypothesis: 共同  创造  美  好  的  新  世纪  ——  二○○一年  新年  贺词

Precision = 9 / 11 = 0.818

Recall = 9 / 10 = 0.9

F1 = 0.857


## <span class="t">The Second International Chinese Word Segmentation Bakeoff in SIGHAN 2005 Workshop (Emerson, 2005)</span>.

* [网站](http://sighan.cs.uchicago.edu/bakeoff2005/) 
* [详细介绍](http://sighan.cs.uchicago.edu/bakeoff2005/data/instructions.php.html)
* [综述文章](http://aclweb.org/anthology/I05-3017)
* 包含4个数据集，繁体中文数据集2个：AS, CityU; 简体中文数据集2个：PK, MSR.

| Corpus | Abbrev. | Encoding | Test Size (Tokens/Types) |
| ---: | ---: | ---: | ---: |
| **Traditional Chinese** |
|Academia Sinica(Taipei)|AS|Unicode/Big Five Plus|122K / 19K|
|City University of Hong Kong|CityU|HKSCS Unicode/Big Five|104K / 13K|
| **Simplified Chinese** |
|Peking University|PK|CP936/Unicode|41K / 9K|
|Microsoft Research|MSR|CP936/Unicode|107K / 13K|

### 结果

|  Model | AS | CITYU | MSR | PKU |
| --- | --- | --- | --- | --- |
|  [Yang et al. (2017)](http://aclweb.org/anthology/P17-1078) | 95.7 | 96.9 | 97.5 | 96.3 |
|  [Zhou et al. (2017)](https://www.aclweb.org/anthology/D17-1079) |  |  | 97.8 | 96 |
|  [Ma et al. (2018)](http://aclweb.org/anthology/D18-1529) | 96.2 | 97.2 | 97.4 | 96.1 |
|  [Meng et al. (2019)](https://arxiv.org/pdf/1901.10125.pdf) |  |  |  | 96.3 |

### 相关资源

|  Train set | Training Size(Words) |
| --- | ----: |
|  AS | 5.45M |
|  CityU | 1.46M |
|  MSR | 2.37M |
|  PKU | 1.1M |


## <span class="t">Chinese Penn Treebank</span>.

* [网站](https://verbs.colorado.edu/chinese/ctb.html)
* 包含2个数据集:
  * [CTB6](https://catalog.ldc.upenn.edu/LDC2007T36): 包括78,000个词 (word), 超过128万个中文字符。 
  * [CTB7](https://catalog.ldc.upenn.edu/LDC2010T07): 包括2448个文档，51447句子，1,196,329个词 (word)以及超过190万个中文字符。 


|Data set|Test set (Tokens)|
| ---: | ---: |
|CTB6|81,578|
|CTB7|81,578|

### 结果

|  Model | CTB6 | CBT7 |
| --- | --- | --- |
| [Yang et al. (2017)](http://aclweb.org/anthology/P17-1078) | 96.2 |  |
| [Zhou et al. (2017)](https://www.aclweb.org/anthology/D17-1079) | 96.2 |  |
| [Ma et al. (2018)](http://aclweb.org/anthology/D18-1529) | 96.7 | 96.6 |
| [Meng et al. (2019)](https://arxiv.org/pdf/1901.10125.pdf) | 96.6 |  |


### 相关资源

|  Train set | Training Size(Words) |
| --- | ----: |
|  CTB6 | 641,368 |
|  CTB7 | 950,138 |


## <span class="t">Chinese Universal Treebank (UD)</span>.

* [网站](https://universaldependencies.org/)
* [Github](https://github.com/UniversalDependencies/UD_Chinese-GSD)

|Data set|Test set(Tokens)|
| ---: | ---: |
|UD|12,012|

### 结果

|  Model | UD |
| --- | --- | 
| [Ma et al. (2018)](http://aclweb.org/anthology/D18-1529) | 96.9 |

### 相关资源

|  Train set | Training Size(Words) |
| --- | ----: |
|  UD | 98,608 |


## <span class="t">NLPCC2016 WordSeg Weibo</span>.

* [Github](https://github.com/FudanNLP/NLPCC-WordSeg-Weibo)
* [数据集介绍论文](https://link.springer.com/chapter/10.1007/978-3-319-50496-4_84)

|   | # Sentences | # Words | # Characters |
| --- | --- | --- | --- |
| Weibo | 8,592 | - | 315,857 |

### 结果

|  Model | Weibo |
| --- | --- | 
| [Yang et al. (2017)](http://aclweb.org/anthology/P17-1078) | 95.5 | 
| [Meng et al. (2019)](https://arxiv.org/pdf/1901.10125.pdf) | 96.0 |  

### 相关资源

|   | # Sentences | # Words | # Characters |
| --- | --- | --- | --- |
|  Train | 20,135 | 421,166 | 688,734 |
|  Dev | 2,052 | 43,697 | 73,244 |


## 其他资源

* [Chinese Word Segmentation: Another Decade Review (2007-2017)](https://arxiv.org/pdf/1901.06079.pdf)

---

**建议? 修改? 请发邮件到 [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**


