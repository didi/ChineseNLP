# Chinese Word Segmentation


## Overview

Chinese is written using characters (hanzi), where each character represents a syllable. A word is usually taken to consist of one or more character tokens.  There are no spaces between words. Less than 3500 distinct characters are normally encountered. Word segmentation (or tokenization) is the process of dividing up  a sequence of characters into a sequence of words.

## Example

Input:

```
亲 请问有什么可以帮您的吗？
```

Output:

```
亲 请问 有 什么 可以 帮 您 的 吗 ？
```

## Metrics

Word F1 score:

> Gold: 共同  创造  美好  的  新  世纪  ——  二○○一年  新年  贺词

> Hypothesis: 共同  创造  美  好  的  新  世纪  ——  二○○一年  新年  贺词

Precision = 9 / 11 = 0.818

Recall = 9 / 10 = 0.9

F1 = 0.857


## <span class="t">The Second International Chinese Word Segmentation Bakeoff in SIGHAN 2005 Workshop (Emerson, 2005)</span>.

* [Website](http://sighan.cs.uchicago.edu/bakeoff2005/), [Detailed Instruction](http://sighan.cs.uchicago.edu/bakeoff2005/data/instructions.php.html), [Overview Paper](http://aclweb.org/anthology/I05-3017)
* Includes 4 datasets: AS, CityU in traditional Chinese, PK, MSRA in simplified Chinese.

| Corpus | Abbrev. | Encoding | Test Size (Tokens/Types) |
| ---: | ---: | ---: | ---: |
| **Traditional Chinese** |
|Academia Sinica(Taipei)|AS|Unicode/Big Five Plus|122K / 19K|
|City University of Hong Kong|CityU|HKSCS Unicode/Big Five|104K / 13K|
| **Simplified Chinese** |
|Peking University|PK|CP936/Unicode|41K / 9K|
|Microsoft Research|MSRA|CP936/Unicode|107K / 13K|

### Results

|  Model | AS | CITYU | MSRA | PKU |
| --- | --- | --- | --- | --- |
|  [Ke et al. (2021)](https://aclanthology.org/2021.naacl-main.436/) | 97.0 | 98.2 | 98.5 | 96.9 |
|  [Tian, Song, Xia, Zhang, Wang (2020)](https://www.aclweb.org/anthology/2020.acl-main.734/) | 96.6 | 97.9 | 98.4 | 96.5 |
|  [Qiu, Pei, Yan, Huang (2020)](https://aclanthology.org/2020.findings-emnlp.260/) | 96.4 | 96.9 | 98.1 | 96.4 |
|  [Meng et al. (2019)](https://arxiv.org/abs/1901.10125) | 96.7<sup>*</sup> | 97.9<sup>*</sup> | 98.3 | 96.7 |
|  [Huang et al. (2019)](https://arxiv.org/abs/1903.04190)| 96.6 | 97.6 | 97.9 | 96.6 |
|  [Ma et al. (2018)](http://aclweb.org/anthology/D18-1529) | 96.2 | 97.2 | 97.4 | 96.1 |
|  [Yang et al. (2017)](http://aclweb.org/anthology/P17-1078) | 95.7 | 96.9 | 97.5 | 96.3 |
|  [Zhou et al. (2017)](https://www.aclweb.org/anthology/D17-1079) |  |  | 97.8 | 96.0 |

<sup>*</sup> Unlike others, [Meng et al. (2019)](https://arxiv.org/pdf/1901.10125.pdf) do not report converting traditional Chinese to simplified Chinese.

### Resources

|  Train set | Training Size(Words) |
| --- | ----: |
|  AS | 5.45M |
|  CityU | 1.46M |
|  MSRA | 2.37M |
|  PKU | 1.1M |


## <span class="t">Chinese Penn Treebank</span>.

* [Website](https://www.cs.brandeis.edu/~clp/ctb/)
* Includes 3 datasets:
  * [CTB6](https://catalog.ldc.upenn.edu/LDC2007T36): consisting of 780,000 words (over 1.28 million Chinese characters)
  * [CTB7](https://catalog.ldc.upenn.edu/LDC2010T07): consists of 2,448 text files, 51,447 sentences, 1,196,329 words and 1,931,381 hanzi (Chinese characters)
  * [CTB9](https://catalog.ldc.upenn.edu/LDC2016T13): consists of 3,726 text files, 132,076 sentences, 2,084,387 words, 3,247,331 characters (hanzi or foreign)

|Data set|Test set (Tokens)|
| ---: | ---: |
|CTB6|82K|
|CTB7|245K|
|CTB9|242K|

### Results

|  Model | CTB6 | CTB7 | CTB9 |
| --- | --- | --- | --- |
|  [Ke et al. (2021)](https://aclanthology.org/2021.naacl-main.436/) | 97.9 |  |  |
| [Tian, Song, Ao, Xia, Quan, Zhang, Wang (2020)](https://www.aclweb.org/anthology/2020.acl-main.735/) | 97.5 | 97.3 | 97.8 |
| [Tian, Song, Xia, Zhang, Wang (2020)](https://www.aclweb.org/anthology/2020.acl-main.734/) | 97.3 | |
| [Yan et al. (2020)](https://transacl.org/ojs/index.php/tacl/article/view/1876) | | 97.1| 97.6 |
| [Huang et al. (2019)](https://arxiv.org/abs/1903.04190)|97.6| | |
| [Ma et al. (2018)](http://aclweb.org/anthology/D18-1529) | 96.7 | 96.6<sup>**</sup> | |
| [Yang et al. (2017)](http://aclweb.org/anthology/P17-1078) | 96.2 |  | |
| [Zhou et al. (2017)](https://www.aclweb.org/anthology/D17-1079) | 96.2 | | |

<sup>**</sup> [Ma et al. (2018)](http://aclweb.org/anthology/D18-1529) report different statistics for their CTB7 split (950K/60K/82K), so the results might not be comparable.


### Resources

|  Train set | Training Size (Words) |
| --- | ----: |
|  CTB6 | 641K |
|  CTB7 | 718K |
|  CTB9 | 1,696K |


## <span class="t">Chinese Universal Treebank (UD)</span>.

* [Website](https://universaldependencies.org/), [Github](https://github.com/UniversalDependencies/UD_Chinese-GSD)

|Data set|Test set(Tokens)|
| ---: | ---: |
|UD|12,012|

### Results

|  Model | UD |
| --- | --- | 
|  [Ke et al. (2021)](https://aclanthology.org/2021.naacl-main.436/) | 98.6 |
| [Tian, Song, Ao, Xia, Quan, Zhang, Wang (2020)](https://www.aclweb.org/anthology/2020.acl-main.735/) | 98.3 |
| [Huang et al. (2019)](https://arxiv.org/abs/1903.04190)|97.3 |
| [Ma et al. (2018)](http://aclweb.org/anthology/D18-1529) | 96.9 |

### Resources

|  Train set | Training Size(Words) |
| --- | ----: |
|  UD | 98,608 |


## <span class="t">NLPCC2016 WordSeg Weibo</span>.

* [Github](https://github.com/FudanNLP/NLPCC-WordSeg-Weibo)
* [Paper describe the dataset](https://link.springer.com/chapter/10.1007/978-3-319-50496-4_84)

|   | # Sentences | # Words | # Characters |
| --- | --- | --- | --- |
| Weibo | 8,592 | - | 315,857 |

### Results

|  Model | Weibo |
| --- | --- | 
| [Yang et al. (2017)](http://aclweb.org/anthology/P17-1078) | 95.5 | 


### Resources

|   | # Sentences | # Words | # Characters |
| --- | --- | --- | --- |
|  Train | 20,135 | 421,166 | 688,734 |
|  Dev | 2,052 | 43,697 | 73,244 |


## Other Resources

* [Chinese Word Segmentation: Another Decade Review (2007-2017)](https://arxiv.org/pdf/1901.06079.pdf)

---

**Suggestions? Changes? Please send email to [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**


