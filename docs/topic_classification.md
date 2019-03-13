# Chinese Topic Classification

---

## Background

Text classification assigns tags or categories to text according to its topical content, typically training on labeled documents. Topics are sometimes broad and akin to genre (news, sports, arts) but sometimes as fine-grained as hashtags.

## Example input/output

Input:

```
[国足]有信心了 中国国奥队取得热身赛三连胜
```
Output:

```
Sports
```


## Standard Metrics
- Accuracy: the percentage of correctly classified samples.


### THUCNews
---
Sina News RSS subscription channel data from 2005 to 2011, which contains 74 million news documents (2.19 GB), 14 topics, all in UTF-8 plain text format.
  - [Website](http://thuctc.thunlp.org/#%E4%B8%AD%E6%96%87%E6%96%87%E6%9C%AC%E5%88%86%E7%B1%BB%E6%95%B0%E6%8D%AE%E9%9B%86THUCNews)

| Source  | # Classes | Size(sentences)|
| --- |  --- | --- |
| THUCNews |  14 | 740,000 |

#### Metrics
- Accuracy

#### Results

|   | Accuracy |
| --- | --- |
| [Sun, Baohua, et al](https://arxiv.org/abs/1810.07653) | 94.85% |



### SogouCS 
---

Sohu News from June to July 2012 in 18 channels.
  - [Website](http://www.sogou.com/labs/resource/cs.php)

| Source  | # Classes | Size(sentences)|
| --- |  --- | --- |
| [Sougou news dataset](https://www.sciencedirect.com/science/article/abs/pii/S0952197619300090) |  5 | 86,597 |

#### Metrics
- Accuracy

#### Results

|   | Error rate |
| --- | --- |
| [Chung, Tonglee, et al](https://www.sciencedirect.com/science/article/abs/pii/S0952197619300090) | 3.37% |

#### Resources

| Dataset | Classes | Train(samples size) |
| --- | --- | --- |
| [Sougou news dataset](https://github.com/koalaGreener/Character-level-Convolutional-Network-for-Text-Classification-Applied-to-Chinese-Corpus) | 5 | 490,717 |


### Fudan corpus
---

contains 9804 documents of long sentences and paragraphs in 20 categories.


| Source  | # Classes | Size(sentences)|
| --- |  --- | --- |
| [Fudan corpus](https://www.semanticscholar.org/paper/cw2vec%3A-Learning-Chinese-Word-Embeddings-with-Cao-Lu/57b57e88edcc9a20c78388e847b42e088b451c55) |  5 | 1836 |

#### Metrics
- Accuracy

#### Results

|   | Accuracy |
| --- | --- |
| [Sun, Baohua, et al](https://arxiv.org/abs/1810.07653) | 97.8% |
| [[Meng et al, 2019]](https://arxiv.org/pdf/1901.10125.pdf) | 96.3% |

#### Resources

| Source  | # Classes | Size(sentences)|
| --- |  --- | --- |
| [Fudan corpus](https://www.semanticscholar.org/paper/cw2vec%3A-Learning-Chinese-Word-Embeddings-with-Cao-Lu/57b57e88edcc9a20c78388e847b42e088b451c55) |  5 | 4284 |

### Ifeng 
---
First paragraphs of Chinese news articles from 2006-2016 were evenly split into 5 news channels.
  - [Github link](https://github.com/zhangxiangxiao/glyph)

| Source  | # Classes | Size(sentences)|
| --- |  --- | --- |
| [Ifeng](https://github.com/zhangxiangxiao/glyph) |  5 | 50,000 |

#### Metrics
- Accuracy

#### Results

|   | Accuracy |
| --- | --- |
| [[Meng et al, 2019]](https://arxiv.org/pdf/1901.10125.pdf) | 85.8% |
| [Sun, Baohua, et al](https://arxiv.org/abs/1810.07653) | 84.4% |
| [[Zhang and Lecun 2017]](https://arxiv.org/abs/1708.02657) | 83.7% |

#### Resources

| Dataset | Classes | Train(samples size) |
| --- | --- | --- |
| Ifeng | 5 | 800,000 |

### Chinanews
---
Chinese news articles from 2008- 2016 were evenly split into 7 news channels, removing duplicates.
- [Github link](https://github.com/zhangxiangxiao/glyph)

| Source  | # Classes | Size(sentences)|
| --- |  --- | --- |
| [Chinanews](https://github.com/zhangxiangxiao/glyph) |  7 | 112,000 |

#### Metrics
- Accuracy

#### Results

|   | Accuracy |
| --- | --- |
| [Sun, Baohua, et al](https://arxiv.org/abs/1810.07653) | 92.0% |
| [[Meng et al, 2019]](https://arxiv.org/pdf/1901.10125.pdf) | 91.9% |
| [[Zhang and Lecun 2017]](https://arxiv.org/abs/1708.02657) | 90.9% |

#### Resources

| Dataset | Classes | Train(samples size) |
| --- | --- | --- |
| China news | 7 | 1,400,000 |


---

**Suggestions? Changes? Please send email to [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**

[Return to Home](../index.md)





