# 中文指代消歧(Co-reference Resolution)

## 背景

Co-reference (指代)是标识文本以及将这些文本与其他具有相同指代内容的文本连接起来。这些片段可以很短，甚至可以省略代词(pronouns)或是普通名词(common nouns)。

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

由以下三个指标的精确率 (Precision), 召回率 (Recall)综合得到的平均F1值(F1-scores):
- MUC.  
- B-cubed.  
- Entity-based CEAF.  


## <span class="t">CoNLL 2012 指代消歧任务</span>.

CoNLL 2012 引入了一个中文的指代消歧任务.
- http://conll.cemantix.org/2012/introduction.html 

评估数据是Ontonotes项目的一部分, 由Linguistic Data Consortium (LDC)发布.
- https://catalog.ldc.upenn.edu/LDC2013T19 

|  Test set | 指代提及的次数 | 主题(Genre) |
| --- | --- | --- |
|  CoNLL 2012 co-reference | 144k (包含了15k长度为零被省略的主语) | 新闻，广播 |

### 评价指标

MUC, B-cubed和CEAF的平均F1值(F1-scores)

评分代码: https://github.com/conll/reference-coreference-scorers 

### 结果

|  System | MUC, B-cubed和CEAF的平均F1值(F1-scores) |
| --- | --- |
|  [[Clark & Manning, 2016](http://alt.qcri.org/semeval2016/task5/index.php?id=data-and-tools#)] | 63.66 |

### 其他资源

评估数据是Ontonotes项目的一部分, 由Linguistic Data Consortium (LDC)发布。
- https://catalog.ldc.upenn.edu/LDC2013T19 

---

**建议? 修改? 请发邮件到 [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**


