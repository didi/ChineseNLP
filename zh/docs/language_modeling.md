# 中文语言模型 (Language Modeling)


## 背景

语言模型 (language model) 可以对计算任何的文本字符串或语料库的概率。好的语言模型对于未观察过的流畅的文本应该能输出一个高概率或者低混淆度(perplexity),反之则输出低概率。

## 示例

输入:

```
我们体育界是有信心做到为北京2022年冬季奥运会提供坚实的人才基础
```

输出:

```
60.2 混淆度(perplexity)
```

## 标准评价指标

* 混淆度 (Perplexity) 用来衡量一个语言模型在未见过的的字符串S上的表现。对于一个长度为N的字符串S，语言模型给出概率P(S)，对应的混淆度 (Perplexity)为 2^{-(1/N) log2 P(S)}。其中字符串长度单位可以是字符 (characters) 也可以是单词 (words).
  * 语言模型通常以递增方式生成概率, 每个词 (token) 基于左侧的信息得到一个 P(S_i)，对每个P(S_i)取对数并求和即得到混淆度 (Perplexity)公式: 2^{-(1/N) sum_i log2 P(S_i)}.
* 另一个相关的评价指标是 bits-per-character (bpc)，当计算基于字符长度单位的混淆度 (Perplexity)时，Perplexity = 2^bpc.
* 英文语言模型有很成熟的榜单 (leaderboard) 可以追踪最新的结果[here](https://paperswithcode.com/task/language-modeling). 英文语言模型相关的标准数据集通常都遵循着以下规范:
  * 训练集 (Train)/开发集 (dev)/测试集 (test)的标准划分规范
  * 语言模型预测的单位（通常是单词而不是字符）
  * 固定的 word tokenization
  * 处理未在词表中出现的单词 (out-of-vocabulary (OOV))


常用于语言模型领域的英文数据集包括:

|   | Train (words) | Dev (words) | Test (words) | Genre |
| --- | --- | --- | --- | --- |
|  Penn Treebank | 888k | 70k | 79k | News |
|  WikiText-103 | 103m | 218k | 246k | Wikipedia |
|  Google 1B | 829m | 160k | 160k | News commentary |

总的来说，在中文语言模型领域，标准数据集还远没能达到这种级别的标准规范。

## <span class="t">Chinese Treebank</span>.

Chinese Treebank数据集由Linguistic Data Consortium (LDC)发布，然而该数据集并未提供一个用于语言模型的训练集 (Train)/开发集 (dev)/测试集 (test)的标准划分规范。

|   | Word tokens |
| --- | --- |
|  [Chinese Treebank (CBT) v9](https://catalog.ldc.upenn.edu/LDC2016T13) | 2m |

### 结果

考虑到基于不同的训练条件，以下结果并不具有可比性。

|   | Character ppl | Word ppl | Notes |
| --- | --- | --- | --- |
|  Glyce (glyph vectors). [We et al, 2019](https://arxiv.org/abs/1901.10125) | 51 | 176 | V6. 4,401个不同的字符。 数据划分 80/10/10. 分词工具: 结巴分词. 只出现过一次的次提出按为 UNK 。 |
|  RNNG [Dyer et al, 2016](https://arxiv.org/abs/1602.07776) | -- | 171.9 | V5.1. 31,000的词表. 测试机包含348行。训练集包含50k行 (LDC声称有19k行)。 |
|  Segmental NLMs [Kawakami et al, 2016](https://arxiv.org/pdf/1811.09353.pdf) | 4.8 bits per character (not ppl) | -- | V5.1 手工分词。 评分为bits per character (bpc). [数据](https://s3.eu-west-2.amazonaws.com/k-kawakami/seg.zip). |

## <span class="t">Chinese Gigaword</span>.

Chinese Gigaword也是由Linguistic Data Consortium (LDC)发布.

|  Corpora | Word tokens |
| --- | --- |
|  [Chinese Gigaword](https://catalog.ldc.upenn.edu/LDC2011T13) V5 (others exist) | 934k |

### 结果

考虑到基于不同的训练条件，以下结果并不具有可比性。

|  Chinese Gigaword | Character ppl | Word ppl | Notes |
| --- | --- | --- | --- |
|  [Liu et al, NTU 2016](https://arxiv.org/abs/1611.08656) [GW v1] | 86.9 | -- | 531k行训练集, 260k行测试集. 5k的词表. 不清楚是基于单词的还是基于字符的语言模型. |
|  [Huang et al, 2010 [GW v2]](http://www.imaging.org/site/PDFS/Reporter/Articles/2010_25/Rep25_2_EI2010_HUANG.pdf) | -- | 220.6 | 610M 的字符, 随机11m字符作为测试集， 使用MSR分词工具。 |
|  Neural Lattice Models [v5] [Buckman+Neubig, 2018](https://www.mitpressjournals.org/doi/pdf/10.1162/tacl_a_00036) | 32.19 | -- | *光明日报, 最高频的10k字符+UNK, 长度<150. 934k行训练集, 30k行测试集。 [数据](https://github.com/jbuckman/neural-lattice-language-models). |

---

**建议? 修改? 请发邮件到[chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**



