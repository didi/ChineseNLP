# 中文情绪分类 (Emotion Classification)

## 背景

情绪分类 (Emotion Classification) 旨在识别叙述者的情绪状态。 与情感分析 (Sentiment Analysis) 不同的是，情感分析着重于叙述者对其叙述对象的观点。

## 示例

输入:

```
讨厌！你骗我！
```
输出:

```
生气
```

## 标准评价指标

- 分类准确率(Accuracy).
- F1值.


## <span class="t">Cheng emotion corpus</span>.

[Cheng et al 2017](https://dl.acm.org/citation.cfm?id=3132684) 引入了一个基于微博的情绪语料库。它由标有情感标签的短帖组成，其中各个情感标签的分布为：喜悦（11.3％），生气（3.5％），伤心（2.6％），恐惧（0.6％），积极（8.2％），中性（4.4％）， 消极（9.9％），非情绪（59.5％）。而且，该数据集标记了引发特定情绪的相关文本的范围 (sub-span)。

[Chen et al 2018](http://aclweb.org/anthology/D18-1066) 显示这个语料库共包括 ~3,000条微博, ~11,000个情绪分类 (emotion classification) 标注, 以及 ~13,000个情绪追因 (emotion cause detection) 标注。

|  测定集(Test set) | 流派 (Genre) |
| --- | --- |
|  Cheng emotion corpus | 微博 |

## 评价指标
- F1值.

## 结果

|  系统 | F1值 |
| --- | --- |
|  [[Chen et al 2018]](http://aclweb.org/anthology/D18-1066) | 62.4 |
|  [[Cheng et al 2017]](https://dl.acm.org/citation.cfm?id=3132684) | 58.2 |


---

**建议? 修改? 请发邮件到[chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**



