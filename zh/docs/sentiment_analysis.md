# 中文情感分析 (Sentiment Analysis)


## 背景

情感分析 (Sentiment Analysis) 从文本中识别提取文本的主观态度信息。

## 示例

输入:

```
总的感觉这台机器还不错，实用的有：阴阳历显示，时间与日期快速转换, 记事本等。
```

输出:

```
正向 (Positive)
```

## 标准评价指标

准确度 (Accuracy) 
  * 在测试集上正确分类的样本的百分比。

F1-score
  * 准确率和召回率的一种加权平均指标。
  * [Wiki百科](https://en.wikipedia.org/wiki/F1_score)




## <span class="t">SemEval-2016 Task 5</span>.

[SemEval-2016 Task 5](http://alt.qcri.org/semeval2016/task5/index.php?id=data-and-tools#) 包含2个测试集，超过5000条数码相机和手机领域的评论。


| Source | 主题 (Genre)  | # Classes | Size(sentences) |Size(words) |
| --- | --- | --- | --- | --- |
| SemEval 2016 Task 5 – CAM Test | 电子相机评论（中文） | 3 | 2256 | ~25k |
| SemEval 2016 Task 5 – PHNS Test | 手机评论（中文） | 3 | 3191 | ~34k |

### 评价指标
- Accuracy

### 结果

|   | Accuracy(PHNS Test) | Accuracy(CAM Test) |
| --- | --- | --- |
|  [SenHint](http://www.wowbigdata.com.cn/main/paper/www2018wang.pdf) | 0.7958 | 0.8711 |

 
### 相关资源

| Source | 主题 (Genre)  | # Classes | Size(sentences)|Size(words) |
| --- | --- | --- | --- | --- |
| SemEval 2016 Task 5 – CAM  Train | 电子相机评论（中文） | 3 | 5784 | ~61k |
| SemEval 2016 Task 5 – PHNS Train | 手机评论（中文） | 3 | 6330 | ~62k |


## <span class="t">NLP&CC 2012</span>.

[NLP&CC 2012 Test](http://tcci.ccf.org.cn/conference/2012/pages/page04_eva.html): 中文微博情感分析评测数据。

| Source | 主题 (Genre)  | # Classes | Size(sentences)|Topics |
| --- | --- | --- | --- | --- |
| [NLP&CC 2012 Test](https://link.springer.com/chapter/10.1007/978-1-4614-6880-6_29) | 微博 | 2 | 1908 | 10 |

### 评价指标
- F1-score
- Accuracy

### 结果

|   | F1 | Accuracy |
| --- | --- | --- |
| [Chen, et al 2018](https://ieeexplore.ieee.org/abstract/document/8386495)|-- |88.35|
| [Wang, et al 2013](https://link.springer.com/chapter/10.1007/978-1-4614-6880-6_31) | 63.60 | 74.00 |

### 相关资源

| Source | 主题 (Genre)  | # Classes | Size(sentences)|Size(words) |
| --- | --- | --- | --- | --- |
| NLP&CC 2012 Train | 微博 | 2 | 1765 | ~116k |


## <span class="t">ChnSentiCorp</span>.


[ChnSentiCorp](https://www.sciencedirect.com/science/article/pii/S0957417407001534) 包含教育，电影和住房三个领域共计1021个文档。


| Source | 主题 (Genre)  | # Classes | Size(sentences)|Size(words) |
| --- | --- | --- | --- | --- |
| ChnSentiCorp Test | 酒店评论（中文） | 2 | 1999 | ~725k |

### 评价指标
- Accuracy
- F1-score

### 结果

|   | F1 | Accuracy |
| --- | --- | --- |
| fastText *| 0.9218 | 0.9218 |
| [MCCNN](https://arxiv.org/pdf/1808.02961.pdf#page=8&amp;zoom=100,0,648) | 0.9208 | 0.9208 |

*准确度 (Accuracy) 结果引用自 [MCCNN paper](https://arxiv.org/pdf/1808.02961.pdf#page=8&amp;zoom=100,0,648).

### 相关资源

| Source | 主题 (Genre)  | # Classes | Size(sentences)|Size(words) |
| --- | --- | --- | --- | --- |
| ChnSentiCorp Train | 酒店评论（中文）|2|8000|~2.9M|


## <span class="t">IT168TEST</span>.

[IT168TEST](http://www.aclweb.org/anthology/I08-1040): 一个由Zagibalov and Carroll提供的产品评论领域的数据集。 该数据集包含超过20000条评论，其中78％评论被人工标记为正向 (positive), 22％被标记为负向(negative).

| Source | 主题 (Genre)  | # Classes | Size(sentences)|
| --- | --- | --- | --- |
| IT168Test | 产品评论 | 2 | 29531 |

### 评价指标
- Accuracy
- F1-score

### 结果

|   | F1 | Accuracy |
| --- | --- | --- |
| fastText* | 0.9261 | 0.9261 |
| [MCCNN](https://arxiv.org/pdf/1808.02961.pdf#page=8&amp;zoom=100,0,648) | 0.9302 | 0.9304 |
| [Zhang, P., &amp; He, Z. (2013)](https://journals.sagepub.com/doi/10.1177/0165551513480330) | 0.9402 | 0.9500 |


*准确度 (Accuracy) 结果引用自 [MCCNN paper](https://arxiv.org/pdf/1808.02961.pdf#page=8&amp;zoom=100,0,648).



## <span class="t">Dianping</span>.

[Dianping](https://github.com/zhangxiangxiao/glyph): 一个二分类的餐厅点评数据集，4星和5星评价被归为正向评价类，1-3星的评价被归为负向评价类。

| Source | 主题 (Genre)  | # Classes | Size(sentences)|
| --- | --- | --- | --- |
| Dianping | 饭店评价 | 2 | 500,000 |

### 评价指标
- Accuracy

### 结果

|   | Accuracy |
| --- | --- |
| [Sun, Baohua, et al](https://arxiv.org/abs/1810.07653) | 77.8 |
|  [Zhang and Lecun 2017](https://arxiv.org/abs/1708.02657) | 77.7 |



### 相关资源

| Source | 主题 (Genre)  | # Classes | Size(sentences)|
| --- | --- | --- | --- |
| Dianping | 饭店评价 | 2 | 2,000,000 |



## <span class="t">JD Full</span>.
[JD Full](https://github.com/zhangxiangxiao/glyph): 京东购物评分数据集，评价范围1-5星，每个类别样本数量相同。

| Source | 主题 (Genre)  | # Classes | Size(sentences)|
| --- | --- | --- | --- |
| JD Full | 购物评论 | 5 | 250,000 |

### 评价指标
- Accuracy

### 结果

|   | Accuracy |
| --- | --- |
| [Sun, Baohua, et al](https://arxiv.org/abs/1810.07653) | 54.1 |
|  [Zhang and Lecun 2017](https://arxiv.org/abs/1708.02657) | 52.0 |



### 相关资源

| Source | 主题 (Genre)  | # Classes | Size(sentences)|
| --- | --- | --- | --- |
| JD Full | 购物评论 | 5 | 3,000,000 |

---
## <span class="t">JD Binary</span>.
-   [JD Binary](https://github.com/zhangxiangxiao/glyph): 二分类的京东购物评论数据集，去掉评分为3星的评价，将4-5星的评论归为正向评价，1-2星的评价被归为负向评价。 

| Source | 主题 (Genre)  | # Classes | Size(sentences)|
| --- | --- | --- | --- |
| JD Binary |  购物评论 | 2 | 360,000 |

### 评价指标
- Accuracy

### 结果

|   | Accuracy |
| --- | --- |
| [Sun, Baohua, et al](https://arxiv.org/abs/1810.07653) | 92.2 |
|  [Zhang and Lecun 2017](https://arxiv.org/abs/1708.02657) | 91.3 |


### 相关资源

| Source | 主题 (Genre)  | # Classes | Size(sentences)|
| --- | --- | --- | --- |
| JD Binary |  购物评论 | 2 | 4,000,000 |



## 其他资源

* 中文情感分析综述论文: 
    * [chinese-sentiment-analysis-review](http://sentic.net/chinese-sentiment-analysis-review.pdf)

---

**建议? 修改? 请发邮件到 [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**


