# 中文指代消歧 (Co-reference Resolution)

## 背景

指代消歧 (co-reference resolution) 是指标识一段文本以及将这些文本与其他具有相同指代内容的文本连接起来。有时这些文本片段的长度为0，表示省略了的代词 (pronouns) 或是名词 (nouns)。

## 示例

输入:
```
我的姐姐给我她的狗。很喜欢.
```

输出: 

```
[我]0的[姐姐]1给[我]0[她]1的[狗]2。[]0很喜欢[]2.

```

## 标准评价指标

以下三种精确率 (Precision) /召回率 (Recall) 得到的F1值 (F1-scores) 的平均值:
- MUC.  
- B-cubed.  
- Entity-based CEAF.  


## <span class="t">CoNLL 2012 指代消歧任务</span>.

CoNLL 2012 引入了一个中文的指代消歧任务.
- http://conll.cemantix.org/2012/introduction.html 

评估数据是OntoNotes项目的一部分, 由Linguistic Data Consortium (LDC)发布.
- https://catalog.ldc.upenn.edu/LDC2013T19 

|  Test set | 指代提及的次数 | 主题(Genre) |
| --- | --- | --- |
| CoNLL 2012 co-reference | 144k (包含了15k个长度为零的被省略的主语) | 新闻，广播新闻，广播对话 |


### 评价指标

MUC, B-cubed和CEAF三个指标各自的F1值 (F1-scores) 的平均值

评分代码: https://github.com/conll/reference-coreference-scorers 

### 结果

|  System | MUC, B-cubed和CEAF三个指标各自的F1值 (F1-scores) 的平均值 |
| --- | --- |
|  [[Clark & Manning, 2016](https://nlp.stanford.edu/static/pubs/clark2016deep.pdf)] | 63.88 |
|  [Kong & Jian (2019)](https://www.ijcai.org/Proceedings/2019/700) | 63.85 |
|  [[Clark & Manning, 2016](https://nlp.stanford.edu/static/pubs/clark2016improving.pdf)] | 63.66 |

### 资源

评估数据是OntoNotes项目的一部分, 由Linguistic Data Consortium (LDC)发布。
- https://catalog.ldc.upenn.edu/LDC2013T19 


## <span class="t">零指代消解子任务 (CoNLL 2012 / OntoNotes 5.0)</span>.


### 评价指标

F1 score, 详见[论文](https://www.aclweb.org/anthology/D07-1057.pdf).

### 结果

|  System | Overall F1 (w/ gold syntactic info) | Overall F1 (w/o gold syntactic info) |
| --- | --- | --- |
|  [Aloraini & Poesio (2020)](https://www.aclweb.org/anthology/2020.lrec-1.11/) | 63.5 | |
|  [Song et al. (2020)](https://www.aclweb.org/anthology/2020.acl-main.482/) | 58.5 | 26.1 |
|  [Yang et al. (2019)](https://www.aclweb.org/anthology/W19-4108/) | 58.1 | |
|  [Yin et al. (2018)](https://www.aclweb.org/anthology/C18-1002/) | 57.3 | |
|  [Liu et al. (2017)](https://www.aclweb.org/anthology/P17-1010/) | 55.3 | |
|  [Yin et al. (2017)](https://www.aclweb.org/anthology/D17-1135/) | 54.9 | 22.7 |


### 资源

更多关于数据集的具体数据详见 [Yin et al. (2018)](https://www.aclweb.org/anthology/C18-1002/)

| Split | Documents | Sentences | Words | Anaphoric Zero Pronouns | 
| --- | --- | --- | --- | --- |
|  Train | 1,391 | 36,487 | 756K | 12,111 |
|  Dev | 172 | 6,083 | 110K | 1,713 |


---

**建议? 修改? 请发邮件到 [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**


