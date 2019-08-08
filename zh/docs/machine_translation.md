# 中文机器翻译 (Machine Translation)

## 背景

机器翻译（MT）将文本从一种语言转换翻译为另一种语言。这里, 我们专注于源语言(source language)或目标语言 (target language)为中文的任务。

## 示例

输入:

```
美中两国可能很快达成一个贸易协议。
```

输出:

```
The United States and China may soon reach a trade agreement.
```

## 标准评价指标

* 直接评估（人工评判）。Amazon Mechnical Turk上的标注人员会看到一个系统生成的翻译和一个人工翻译，然后回答这样一个问题：“系统翻译有多么精确的表达了人工翻译的含义？”
* Bleu score ([Papineni et al 02](https://www.aclweb.org/anthology/P02-1040.pdf)).
  * Bleu-n4r4: **词级别** {1,2,3,4}-gram 匹配, 与4条人工参考翻译译文比较
    * brevity penalty: 一个系数，用来惩罚长度短于参考翻译的机器翻译结果。
    * 标准的Bleu计算流程会先对参考译文和机器翻译结果进行符号化 (tokenizition)。
    * 如果中文是目标 (target) 语言, 则使用**字符级别** {1,2,3,4}-gram匹配。
    * 当只有1条人工参考翻译译文时使用Bleu-n4r1评估。
  * 标准Bleu有很多重要的变种:
    * 大小写敏感 vs. 大小写不敏感
    * Brevity penalty 触发条件: 当机器翻译结果短于最短的参考译文 (reference) 或者短于最接近的参考译文 (reference)。
* NIST. Bleu的一种变体，赋予少见的n-gram更高的权重。
* TER (Translation Edit Rate). 计算机器翻译与人工参考译文之间的编辑距离 (Edit distance)。
* BLEU-SBP ((Chiang et al 08)[http://aclweb.org/anthology/D08-1064]). 解决了Bleu的解耦（decomposability) 问题，在Bleu和单词错误率取得一个折中。 
* HTER. 修改为一个良好的翻译所需要的人工编辑次数 (the number of edits)。


## <span class="t">WMT</span>.

第二届机器翻译大会 (WMT17) 与CWMT 2017合作, 提供了中/英机器翻译的子任务.
* [网站](http://www.statmt.org/wmt17)
* [WMT17任务综述](http://www.statmt.org/wmt17/pdf/WMT17.pdf)
* 中英翻译测试集:

|  Test set | Size (sentences) | Genre |
| --- | --- | --- |
|  WMT17 Parallel English/Chinese test set | 2001 | News |

注意： WMT19 已在进行中 [详情](http://www.statmt.org/wmt19/translation-task.html).

### 评价指标

* 直接评估（人工评判）。
* [WMT Bleu 评分计算脚本](https://github.com/moses-smt/mosesdecoder/blob/master/scripts/generic/mteval-v13a.pl)

### 结果

中译英 (WMT17)

|  System | Direct Assessment (Ave z) | Bleu |
| --- | --- | --- |
|  [[Hany et al 18]](https://www.microsoft.com/en-us/research/uploads/prod/2018/03/final-achieving-human.pdf) |  | 27.4 |
|  [[Wang et al 17]](http://www.statmt.org/wmt17/pdf/WMT42.pdf) | 0.209 | 26.4 |
|  [[Sennrich et al 17]](http://www.aclweb.org/anthology/W17-4739) | 0.208 | 25.7 |
|  [[Tan et al 17]](http://www.statmt.org/wmt17/pdf/WMT40.pdf) | 0.184 | 26 |

英译中 (WMT17)

|  System | Direct Assessment (Ave z) | Bleu |
| --- | --- | --- |
|  [[Wang et al 17]](http://www.statmt.org/wmt17/pdf/WMT42.pdf) | 0.208 |  |
|  [[Sennrich et al 17]](http://www.aclweb.org/anthology/W17-4739) | 0.178 | 36.3 |
|  [[Tan et al 17]](http://www.statmt.org/wmt17/pdf/WMT40.pdf) | 0.165 | 35.8 |


### 相关资源


目前有许多英文/中文平行语料资源可以用来训练机器翻译(MT)系统。 以下是一些公开可获取的资源：

|  Train set | Size (words on English side) | 主题 (Genre) |
| --- | --- | --- |
|  UN | 327m | 政治 |
|  New Commentary v12 | 5m | 新闻 |
|  CWMT | 154m | 网络, 电影, 百科, 政府, 新闻对话, 小说, 技术文档 |
|  AI_Challenger | 120m | 电影字幕, 英语学习, 等等. |
|  WMT 2017 Dev | 54k | 新闻 |

The Linguistic Data Consortium (LDC) 还有其他资源，例如FBIS和NIST测试集。


## <span class="t">NIST</span>.


NIST在支持中英文机器翻译领域发展上有着很长的历史，许多模型都公布过在NIST测试集上的结果。在21世纪第一个十年间, NIST每年创建测试集并组织年度NIST OpenMT 测评 (evaluations)。

测试集包含中文句子，每个句子有四个不同的（人类参考）英语翻译。 四个参考翻译使NIST成为一个非常强大的测试集 (evaluation set).

训练 (Training) 和评估 (evaluation) 条件的不同使得系统之间的比较变得困难。

* 评测脚本方面(Evaluation script), 一些论文使用了 [mteval-v13a](https://github.com/moses-smt/mosesdecoder/blob/master/scripts/generic/mteval-v13a.pl), 也有另一些论文使用了 [multibleu](https://github.com/moses-smt/mosesdecoder/blob/master/scripts/generic/multi-bleu.perl) 脚本.  关于大小写敏感 (Case sensitivity) 的标准是一个问题, 当有多个参考翻译 (references) 的情况下, 在如何计算Bleu的brevity penalty系数上也有分歧.
* 训练集(Training data): 通常不同论文用于训练的平行语句数不相同.
* 开发集(Development data): 有些论文使用NIST 02进行开发与调试 (development/tuning)，而其他论文则将其用作测试数据(test data).

这篇[论文](http://www.lrec-conf.org/proceedings/lrec2018/pdf/678.pdf) 提供了一个基于NIST数据集的标准语料库和标准评测方法，同时也汇报了一个中翻英的更高的Bleu得分。 [Github](https://github.com/nusnlp/c2e-mt-benchmark)

|  Test set | Size (sentence pairs) | 主题 (Genre) |
| --- | --- | --- |
|  [NIST 02](https://catalog.ldc.upenn.edu/LDC2010T10) | 878 | 新闻 |
|  [NIST 03](https://catalog.ldc.upenn.edu/LDC2010T11) | 919 | 新闻 |
|  [NIST 04](https://catalog.ldc.upenn.edu/LDC2010T12) | 1788 | 新闻 |
|  [NIST 05](https://catalog.ldc.upenn.edu/LDC2010T14) | 1082 | 新闻 |
|  [NIST 06](https://catalog.ldc.upenn.edu/LDC2010T17) | 1664 | 新闻, 广播新闻, 广播对话, 网络新闻 |
|  [NIST 08](https://catalog.ldc.upenn.edu/LDC2010T21) | 1357 | 新闻, 广播新闻, 广播对话, 网络新闻 |

### 评价指标

[Bleu](ftp://jaguar.ncsl.nist.gov/mt/resources/mteval-v13a.pl)

### 结果

|  System | Training sentence pairs | 评价脚本 | NIST 02 | NIST 03 | NIST 04 | NIST 05 | NIST 06 | NIST 08 | 平均值 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  [[Zhang et al 2019]](https://arxiv.org/abs/1906.02448) | 1.25m | mteval-v11b |  | 48.31 | 49.40 | 48.72 | 48.45 |  | 48.72 |
|  [[Hadiwinoto & Ng, 2018]](http://www.lrec-conf.org/proceedings/lrec2018/pdf/678.pdf) | 7.65m | mteval-v13a | 46.94 | 47.58 | 49.13 | 47.78 | 49.37 | 41.48 | 47.05 |
|  [[Meng et al 2019]](https://arxiv.org/pdf/1901.10125.pdf) | 1.25m | unspecified | 40.56 (dev) | 39.93 | 41.54 | 38.01 | 37.45 | 29.07 | 37.76 |
|  [[Ma et al 2018c]](https://arxiv.org/abs/1805.04871) | 1.25m | unspecified | 39.77 (dev) | 38.91 | 40.02 | 36.82 | 35.93 | 27.61 | 36.51 |
|  [[Chen et al 2017]](http://aclweb.org/anthology/P17-1177) | 1.6m | multibleu | 36.57 | 35.64 | 36.63 | 34.35 | 30.57 |  |  |

### 相关资源

The Linguistic Data Consortium (LDC) 提供了用于NIST OpenMT任务的训练语料。


## <span class="t">IWSLT 2015</span>.

* TED演讲翻译
* 中/英翻译任务
* [开放任务综述](https://cris.fbk.eu/retrieve/handle/11582/303031/9811/main.pdf)

|  Test sets | Size (sentences) | # of talks | Genre |
| --- | --- | --- | --- |
|  tst2014 | 1068 | 12 | TED演讲 |
|  tst2015 | 1,080 | 12 | TED演讲 |

### 评价指标

* 自动化评价指标: Bleu, NIST, TER.
* 人工评测指标: HTER.

### 结果

中译英 (tst2015)

|  System | Bleu | NIST | TER |
| --- | --- | --- | --- |
| [MITLL-AFRL](https://www.ll.mit.edu/sites/default/files/publication/doc/2018-05/2015_Kazi_iwslt15.pdf) | 16.86 | 5.2565 | 67.31 |

英译中 (tst2015)

|  System | Bleu | NIST | TER |
| --- | --- | --- | --- |
| [Univ. Edinburgh](http://homepages.inf.ed.ac.uk/abmayne/publications/huck2015iwslt.pdf) | 25.39 | 6.3985 | 60.83 |
| [MITLL-AFRL](https://www.ll.mit.edu/sites/default/files/publication/doc/2018-05/2015_Kazi_iwslt15.pdf) | 24.31 | 6.4136 | 59.00 |

### 相关资源

|   | Size (sentences) | # of talks | 主题 (Genre) |
| --- | --- | --- | --- |
|  Train | 210k | 1718 | TED演讲 |



## <span class="t">TED corpus</span>.


该[网站](http://cs.jhu.edu/~kevinduh/a/multitarget-tedtalks/)包含一个最新的用于机器翻译研究的多语种TED talks语料库。同时该网站也提供了一个由Kevin Duh维护的排行榜 (leaderboard).

|  Test set | Size (sentences) | 主题 (Genre) |
| --- | --- | --- |
|  Chinese/English test | 1,982 | TED演讲 |
|  Chinese/English dev | 1,958 | TED演讲 |


此[网站](https://github.com/neulab/word-embeddings-for-nmt)包含更多的语言种类，但是train/test划分方式不同。

### 结果

中翻英

|  System | Bleu |
| --- | --- |
|  [Kevin Duh, 6-layer transformer (Sockeye)](http://cs.jhu.edu/~kevinduh/a/multitarget-tedtalks/) | 16.63 |

英翻中

|  System | Bleu |
| --- | --- |
|  Kevin Duh, coming | Not yet available |

### 相关资源

[The Multitarget TED Talks Task (MTTT)](http://cs.jhu.edu/~kevinduh/a/multitarget-tedtalks/)



## <span class="t">Workshop on Asian Translation</span>.

[The Workshop on Asian Translation](http://lotus.kuee.kyoto-u.ac.jp/WAT/) 从2014年开始举办, 在这里主要介绍2018年中文/日文评测任务。

### 评价指标
* BLEU.
* RIBES.  由NTT提出的一种基于rank correlation coefficients的方法([link](http://aclweb.org/anthology/D10-1092)).
* 评分代码.
  * 评估中文翻译结果: [link](http://lotus.kuee.kyoto-u.ac.jp/WAT/evaluation/automatic_evaluation_systems/automaticEvaluationZH.html)
  * 评估日文翻译结果: [link](http://lotus.kuee.kyoto-u.ac.jp/WAT/evaluation/automatic_evaluation_systems/automaticEvaluationJA.html)

ASPEC 中日翻译 (ASPEC Chinese-Japanese)

参与者须从该网站获取数据 [数据链接](http://lotus.kuee.kyoto-u.ac.jp/ASPEC/)

|  Test set | Size (sentences) | 主题 (Genre) |
| --- | --- | --- |
|  ASPEC Chinese-Japanese | 2107 | Scientific abstracts |
|  ASPEC Japanese-Chinese | 2107 | Scientific abstracts |

日本专利局专利数据 (JPO Patent Corpus 2)

参与者须从该网站获取数据 [数据链接](http://lotus.kuee.kyoto-u.ac.jp/WAT/patent/jpc2018.html)

|  Test set | Size (sentences) | 主题 (Genre) |
| --- | --- | --- |
|  JPCN Chinese-Japanese | 5,204 | 专利 |
|  JPCN Japanese-Chinese | 5204 | 专利 |
|  JPCN1 Chinese-Japanese | 2000 | 专利 |
|  JPCN1 Japanese-Chinese | 2000 | 专利 |
|  JPCN2 Chinese-Japanese | 3,000 | 专利 |
|  JPCN2 Japanese-Chinese | 3,000 | 专利 |
|  JPCN3 Chinese-Japanese | 204 | 专利 |
|  JPCN3 Japanese-Chinese | 204 | 专利 |
|  JPSEP Chinese-Japanese | 1151 | 专利表达模板 (Patent Expression Patterns) |

### 结果

* 详见[here](http://lotus.kuee.kyoto-u.ac.jp/WAT/evaluation/index.html)
* 请注意，引用其他人的结果只能通过匿名 (anonymization) 进行。

### 相关资源

|  Test set | Size (sentences) | 主题 (Genre)  |
| --- | --- | --- |
|  Japanese-Chinese train | 250,000 | 专利 |
|  Japanese-Chinese dev | 2000 | 专利 |
|  Japanese-Chinese devtest | 2000 | 专利 |



## <span class="t">CWMT</span>.

全国机器翻译研讨会 (China Workshop on Machine Translation) [CWMT 2017](http://ee.dlut.edu.cn/CWMT2017/index_en.html)
and [2018] (http://www.cipsc.org.cn/cwmt/2018/english/) 提出的6个任务:

|  Test set | Size (sentences) | 主题 (Genre)  |
| --- | ----: | ----: |
|  CWMT Chinese-English news | 1000 | 新闻 |
|  CWMT English-Chinese news | 1000 | 新闻 |
|  Mongolian-Chinese | 1001 | 日常用语 |
|  Tibetan-Chinese | 729 | 政府文件 |
|  Uyghur-Chinese | 1000 | 新闻 |
|  Japanese-Chinese | 1000 | 专利 |

2019年 CWMT 更名为全国机器翻译大会 (China Conference on Machine Translation) [CCMT](http://www.cipsc.org.cn/chcontent.php?&xuhao=2019031803)。



### 评价指标

[BLEU-SBP](http://aclweb.org/anthology/D08-1064) 是主要评价指标, 其他评价指标还包括 BLEU-NIST, TER, METEOR, NIST, GTM, mWER, mPER, and ICT.

### 结果

仍在编译中(Still being compiled).

### 相关资源

详情见[这里](http://nlp.nju.edu.cn/cwmt2017/guidelines.en.html)



## 其他资源

[Opus](http://opus.nlpl.eu/) 是一个非常好的寻找开源平行语料库的网站，提供搜索功能。


---

**建议? 修改? 请发邮件到[chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**






