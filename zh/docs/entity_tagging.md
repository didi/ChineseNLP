# 中文实体标注 (Entity Tagging)

## 背景

实体标注 (Entity Tagging) 任务是识别实体概念在文本中的提及 (entity mention) 并且标注对应的类型，比如人（PER），组织（ORG），地缘政治实体（GPE），地点（LOC）等。文本提及除了专有名词 (proper noun) (例如"Bob") 外，还包括指代名词 (nominals)， 例如 "the player"。

## 示例

输入:

```
美国国防部长马蒂斯说，与首尔举行的名为“秃鹫”的军事演习每年春天在韩国进行，但2019年将“缩小规模”。
```

输出:

```
[美国]GPE国防部长[马蒂斯]PER说，与[首尔]GPE举行的名为“秃鹫”的军事演习每年春天在[韩国]GPE进行，但[2019年]TMP将“缩小规模”。
```

## 标准评价指标

F-score: 选择正确的文本提及（“mention”）并指定正确类型的。


## <span class="t">TAC-KBP / EDL Track (2015-2017)</span>.

The NIST TAC Knowledge Base Population (KBP) Entity Discovery and Linking (EDL) track 包括5种类型的中文实体标注：人（PER），地缘政治实体（GPE），地点（LOC），组织（ORG）以及设施（FAC）。
* 开放任务网站: [http://nlp.cs.rpi.edu/kbp/2017](http://nlp.cs.rpi.edu/kbp/2017) (与2015和 2016任务类似)
* 开放任务记录: [http://nlp.cs.rpi.edu/paper/kbp2017.pdf](http://nlp.cs.rpi.edu/paper/kbp2017.pdf) (与2015和 2016任务类似)
* KBP-EDL 2018包含来源于 YAGO ontology 的数千种实体类型，但测试数据 (Test) 为英语。

评估数据由Linguistic Data Consortium (LDC)发布.

| Test set | Size (documents) | 主题(Genre) | 
| --- | --- | --- |
| TAC-KBP-EDL 2015| 313 (train + eval) | 新闻 | 
| TAC-KBP-EDL 2016 | 166 | 新闻 |
| TAC-KBP-EDL 2017 | 167 | 新闻 |
  
  
  
### 评价指标

NERC F-score
* 要求同时识别文本片段 (text-span) 以及对应的实体概念的类型。
* 2016和2017年的任务包括名字 (name) 提及和指代 (nominal) 提及。
* 评分代码: [http://nlp.cs.rpi.edu/kbp/2017/scoring.html](http://nlp.cs.rpi.edu/kbp/2017/scoring.html) (与2015和 2016任务类似)


### 结果

| System | TAC-KBP / EDL 2015 Names | TAC-KBP / EDL 2016 Names and nominals | TAC-KBP / EDL 2017 Names and nominals |
| --- | --- | --- | --- |
| 开放任务记录中的最佳系统 | 79.9 | 80.8 | 72.2 |
 
### 相关资源

Ontonotes 5.0 ([https://catalog.ldc.upenn.edu/LDC2013T19](https://catalog.ldc.upenn.edu/LDC2013T19)) Linguistic Data Consortium中包含中文实体标注的资源.
* 698篇新华文章(1994-1998)
* 55篇香港特区政府新闻处的文章(1997)
* 132篇台湾光华杂志的文章(1996-1998 & 2000-2001)



## <span class="t">ACE 2005</span>.

ACE 2005任务评估七种实体类型：设施（FAC），地缘政治实体（GPE），位置（LOC），组织（ORG），人员（PER），车辆（VEH）和武器(WEA).

评估数据由Linguistic Data Consortium (LDC)发布.
* [https://catalog.ldc.upenn.edu/LDC2006T06](https://catalog.ldc.upenn.edu/LDC2006T06)

目前暂未发现任何一个训练集 (Train) /开发集 (dev) /测试集 (test) 的标准划分规范，较为常见的方式是8:1:1随机划分 ([Ju et. al. 2018](http://www.aclweb.org/anthology/N18-1131)).

  
| Train + test set| 数量 (字符) | 主题(Genre) |
| --- | --- | --- |
| ACE 2005| 325,834 | 新闻, 广播新闻, 博客 |
  

### 结果

| System | F-score |
| --- | --- |
| [Wang & Lu. (2018)](https://arxiv.org/pdf/1810.01808.pdf) | 73.00 | 
| [Ju et. al. (2018)](http://www.aclweb.org/anthology/N18-1131) | 72.25 | 



## <span class="t">SIGHAN bakeoff 2006 NER MSRA</span>.

该任务评估3种类型的中文实体标注：人（PER），地点（LOC）以及组织（ORG).

关于该任务(bakeoff)的综述论文:
* [Levow (2006)](http://acl-arc.comp.nus.edu.sg/archives/acl-arc-090501d4/data/pdf/anthology-PDF/W/W06/W06-0115.pdf) 
  
| Test set | Size (words) | 主题(Genre) | 
| --- | --- | --- |
| SIGHAN 2006 NER MSRA | 100,000 | 新闻, 广播新闻, 博客 |
  
### 结果

| System | F-score |
| --- | --- | 
| [Liu et. al. (2019)](https://www.aclweb.org/anthology/N19-1247) | 93.74 | 
| [Meng et. al. (2019)](https://arxiv.org/abs/1901.10125) | 93.89 | 
| [Zhang & Yang (2018)](http://aclweb.org/anthology/P18-1144) | 93.18 |
 
### 相关资源 

该任务限定参与者只能使用以下数据资源作为训练集:

| Train set | Size (words) | 主题(Genre) |
| --- | --- | --- |
| SIGHAN 2006 NER MSRA | 1.3M  | 新闻, 广播, 微博 |



## <span class="t">微博 NER</span>.

社交媒体领域的实体标注任务，类型包括地缘政治实体（GPE），组织（ORG），地点（LOC），以及人（PER）。该任务由与以下论文提出:
* [Peng & Dredze (2015)](https://aclweb.org/anthology/D15-1064)

数据集分隔方法: http://www.aclweb.org/anthology/E17-2113:
  
| Test set | Size (name mentions) | Size (nomial mentions) | 主题(Genre) |
| --- | --- | --- | --- |
| Weibo NER | 209 | 196 | 社交媒体 (微博) |
  

### 结果

| System | F-score (name mentions) | F-score (nominal mentions) | F-score (Overall) |
| --- | --- | --- | --- |
| [Liu et. al. (2019)](https://www.aclweb.org/anthology/N19-1247) | 52.55 | 67.41 | 59.84 |
|[Zhu (2019)](https://www.aclweb.org/anthology/N19-1342)|55.38 | 62.98 | 59.31 |
|[Zhang & Yang (2018)](http://aclweb.org/anthology/P18-1144)|53.04| 62.25 | 58.79 |
| [Peng & Dredze (2015)](https://www.cs.jhu.edu/~npeng/papers/golden_horse_supplement.pdf) | 55.28 | 62.97 | 58.99 |
 
### 相关资源

| Train & Dev data | Size (name mentions) | Size (nominal mentions) | 主题(Genre) |
| --- | --- | --- | --- |
| Weibo NER train | --  | -- | Social media (Weibo) |
| Weibo NER  dev | 153 | 226 | Social media (Weibo) |

里面同时还包括1.12亿万条未标注的微博文本。



## 其他资源

该论文介绍了一个关于社交媒体，人机交互和电子商务主题的带有NER标注语料库：
* [Lu et. al. (2018)](http://aclweb.org/anthology/L18-1706) 


---

**建议? 修改? 请发邮件到[chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**



