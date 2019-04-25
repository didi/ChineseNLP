# 中文词向量 (Word Embeddings)



## 背景

词向量 (Word Embeddings)通过对大量的文本语料进行训练，对每一个词 (word type) 返回一个n维的实数向量。向量表征了每个词的单词的句法和语义信息，这些信息可用于解决各种NLP任务。在中文任务中，词向量的单位除了词 (word) 以外也可以是字 (character) 或者 sub-character.
## 示例

输入:
```
大文本语料库
```

输出:

```
vec(“查询”) = [-0.059569, 0.126913, 0.273161, 0.225467, -0.185914, 0.018743, -0.18434, 0.083859, -0.115781, -0.216993, 0.063437, -0.005511, 0.276968,…, 0.254486]
```

## 标准评价指标

词向量的表现既可以进行内部任务 (intrinsically) 评估(比如观察相似的单词是否具有相近的词向量)，也可以通过外部任务 (extrinsically) 的方式评估，既通过使用新的词向量能为下游NLP任务(例如情感分析)的结果带来多少提升。

内部任务评估(intrinsic evaluation)主要关注:
* 词语相关性 (word relatedness)：在中文词汇相似性数据集wordsim-240和wordsim-296（英语相关资源的翻译）上，人类标记分数与词向量的內积之间的Spearman correlation (⍴)。

* 单词类比 (word analogy)：评估单词类比任务的准确率（例如：“男人：女人::父亲：X”，其中X由余弦相似性 (cosine distance) 选择）单词类比任务通常包括以下类型的词（1）国家首都（2）省份（3）家庭关系 (family relationships)

外部任务评估(extrinsic evaluation):  
* 在中文情感分析 (sentiment analysis) 任务上的准确率 (Accuracy)
* 在中文命名实体识别 (named entity recognition) 任务上的F1 score
* 在中文词性标注 (part-of-speech tagging) 任务上的准确率 (Accuracy)




## <span class="t">Chinese word similarity lists</span>.

* 采用的评测文件是wordsim-240和wordsim-296, 提供了中文词汇对以及人工标注的相似性分数。具体细节见论文[Chen et. al. (2015)](http://nlp.csai.tsinghua.edu.cn/~lzy/publications/ijcai2015_character.pdf), [SemEval Task 4: Evaluating Chinese Word Similarity](http://ixa2.si.ehu.es/starsem/proc/pdf/STARSEM-SEMEVAL049.pdf).
* 该数据集是由对应的英文数据集翻译至中文。
* 数据集获取链接: [https://github.com/Leonard-Xu/CWE/tree/master/data](https://github.com/Leonard-Xu/CWE/tree/master/data) 
  
| Test set | # 带有人工标注的相似性分数的词汇对 |
| --- | --- |
| [wordsim-240](https://github.com/Leonard-Xu/CWE/blob/master/data/240.txt) | 240 |
| [wordsim-296](https://github.com/Leonard-Xu/CWE/blob/master/data/297.txt) | 297 |
  
  
  
### 评价指标

* 人工标注的相似性分数和词向量得到的相似性分数之间的Spearman correlation (⍴). 
* 具体实现: [https://github.com/HKUST-KnowComp/JWE/blob/master/src/word_sim.py](https://github.com/HKUST-KnowComp/JWE/blob/master/src/word_sim.py) 


### 结果

* 当前最佳的系统 VCWE 发表于NAACL 2019。 VCWE通过结合字符内 (intra-character) 组合性（通过卷积神经网络计算）和字符间组合性（通过具有自注意力 (self-attention) 的递归神经网络 (recurrent neural network) 计算）计算得到词向量。

| System | wordsim-240 (⍴) | wordsim-296 (⍴) |
| --- | --- | --- |
| [Sun et. al. (2019)](https://arxiv.org/pdf/1902.08795.pdf) (VCWE) | 57.81 | 61.29 |
| [Yu et. al. (2017)](https://www.aclweb.org/anthology/D17-1027) (JWE) | 51.92 | 59.84 |
 


## <span class="t">Chinese word analogy lists</span>.

例如当给出 “法国 : 巴黎 :: 中国 : ?”这样的例子时, 系统应该返回正确答案"北京".
* Chen et. al. (2015) 收集了3个领域的1225个单词类比(analogies)。
   * 3个领域分别是 (1）国家首都（2）城市省份（3）家庭关系 (family relationships).
* 数据集下载链接: [https://github.com/Leonard-Xu/CWE/blob/master/data/analogy.txt](https://github.com/Leonard-Xu/CWE/blob/master/data/analogy.txt) 
  
| Test set | 类比数量 |
| --- | --- |
| 国家首都 | 687 |
| 城市省份 | 175 |
| 家庭关系 | 240 |
  
### 评价指标

* Accuracy
* 具体实现: [https://github.com/HKUST-KnowComp/JWE/blob/master/src/word_analogy.py](https://github.com/HKUST-KnowComp/JWE/blob/master/src/word_analogy.py) 


### 结果

| System | Accuracy (国家首都) | Accuracy (城市省份) | Accuracy (家庭关系) | Accuracy (总体) | 
| --- | --- | --- | --- | ---|
| [Yu et. al. (2017)](https://www.aclweb.org/anthology/D17-1027) (JWE)| 0.91 | 0.93 | 0.62 | 0.85 |
| [Yin et. al. (2016)](https://www.aclweb.org/anthology/D16-1100) (MGE) | 0.89 | 0.88 | 0.39 | 0.76 |
| CBOW (baseline) | 0.84 | 0.88 | 0.60 | 0.79 |
 


## <span class="t">中文情感分析 (sentiment analysis)</span>.

* 通过评估词向量对情感分析 (sentiment analysis) 任务的提升来间接评测词向量。
* 目前并没有统一的baseline方法及代码实现，因此很难比较各论文的结果。
* 数据集链接 [http://sentic.net/chinese-review-datasets.zip](http://sentic.net/chinese-review-datasets.zip) ([Peng et. al. (2018)](https://www.sciencedirect.com/science/article/abs/pii/S0950705118300972)) 
   * 包括了属于4个领域的中文评论：笔记本电脑，汽车，相机和手机。
   * 二分类任务：评论属于正向的/负向的。
   * 缺乏标准的train/dev/test数据集划分规范.


| Test set | # 正向评论 | # 负向评论 |
| --- | --- | --- |
| 笔记本电脑 | 417 | 206 |
| 汽车 | 886 | 286 |
| 相机 | 1,558 | 673 |
| 手机 | 1,713 | 843 |

### 结果

| System | Accuracy (笔记本电脑) | Accuracy (汽车) | Accuracy (相机) | Accuracy (手机) | Accuracy (总体) | 
| --- | --- | --- | --- | ---| ---|
| [Sun et. al. (2019)](https://arxiv.org/pdf/1902.08795.pdf) (VCWE) | 80.95 | 85.59 | 83.93 | 84.38 | 88.92 |
| [Yu et. al. (2017)](https://www.aclweb.org/anthology/D17-1027) (JWE) | 77.78 | 78.81 | 81.70 | 81.64 | 85.13 | 
| Baseline (skip-gram) | 69.84 | 77.12 | 80.80 | 81.25 | 86.65 |



## <span class="t">中文实体标记 (name tagging)</span>.

* 该测试集通过评估词向量对实体标记 (name tagging) 任务的提升来间接评测词向量。
* 目前并没有统一的baseline方法及代码实现，因此很难比较各论文的结果。
* 评估三种类型的实体标记：人（PER），位置（LOC）和组织（ORG）: [Levow (2006)](http://acl-arc.comp.nus.edu.sg/archives/acl-arc-090501d4/data/pdf/anthology-PDF/W/W06/W06-0115.pdf)
   
| Test set | Size (words) | 主题 (Genre) |
| --- | --- | --- |
| SIGHAN 2006 NER MSRA | 100,000 | 新闻，广播新闻，博客 |
  
### 结果

| System | F1 score | 
| --- | --- |
| [Sun et. al. (2019)](https://arxiv.org/pdf/1902.08795.pdf) (VCWE) | 85.77 | 
| [Yu et. al. (2017)](https://www.aclweb.org/anthology/D17-1027) (JWE)  | 85.30 |
 
### 相关资源

| Train set | Size (words) | 主题 (Genre) |
| --- | --- | --- |
| SIGHAN 2006 NER MSRA | 1.3M  | 新闻，广播新闻，博客 |



## 其他资源

| Corpus | Size (words) | Size (vocabulary) | 主题 (Genre) |
| --- | --- | --- | --- |
| Wikipedia dump | 153,278,000 | 66,856 | 开放主题 |
| People’s Daily| 31,000,000 | 105,000 | 新闻 |

---

**建议? 修改? 请发邮件到 [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**



