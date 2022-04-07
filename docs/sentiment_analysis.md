# Chinese Sentiment Analysis


## Background

Sentiment Analysis detects identifies and extracts subjective information from text.

## Example

Input:

```
总的感觉这台机器还不错，实用的有：阴阳历显示，时间与日期快速转换, 记事本等。
```

Output:

```
Positive
```

## Standard Metrics

Accuracy
  * The percentage of correctly classified samples on test set.

F1-score
  * Combination of precision and recall.
  * [Wiki Page](https://en.wikipedia.org/wiki/F1_score)




## <span class="t">SemEval-2016 Task 5</span>.

[SemEval-2016 Task 5](http://alt.qcri.org/semeval2016/task5/index.php?id=data-and-tools#) contains 2 test sets with over 5000 reviews in total from digital camera and mobile phone area.


| Source | Genre | # Classes | Size(sentences) |Size(words) |
| --- | --- | --- | --- | --- |
| SemEval 2016 Task 5 – CAM Test | Digital Camera reviews (Chinese) | 3 | 2256 | ~25k |
| SemEval 2016 Task 5 – PHNS Test | Mobile Phone reviews (Chinese) | 3 | 3191 | ~34k |

### Metrics
- Accuracy

### Results

|   | Accuracy(PHNS Test) | Accuracy(CAM Test) |
| --- | --- | --- |
|  [SenHint](http://www.wowbigdata.com.cn/main/paper/www2018wang.pdf) | 0.7958 | 0.8711 |


### Resources

| Source | Genre | # Classes | Size(sentences)|Size(words) |
| --- | --- | --- | --- | --- |
| SemEval 2016 Task 5 – CAM  Train | Digital Camera reviews (Chinese) | 3 | 5784 | ~61k |
| SemEval 2016 Task 5 – PHNS Train | Mobile Phone reviews (Chinese) | 3 | 6330 | ~62k |


## <span class="t">NLP&CC 2012</span>.

[NLP&CC 2012 Test](http://tcci.ccf.org.cn/conference/2012/pages/page04_eva.html): Chinese Weibo sentiment analysis evaluation data.

| Source | Genre | # Classes | Size(sentences)|Topics |
| --- | --- | --- | --- | --- |
| [NLP&CC 2012 Test](https://link.springer.com/chapter/10.1007/978-1-4614-6880-6_29) | Weibo reviews | 2 | 1908 | 10 |

### Metrics
- F1-score
- Accuracy

### Results

|   | F1 | Accuracy |
| --- | --- | --- |
| [Chen, et al 2018](https://ieeexplore.ieee.org/abstract/document/8386495)|-- |88.35|
| [Wang, et al 2013](https://link.springer.com/chapter/10.1007/978-1-4614-6880-6_31) | 63.60 | 74.00 |

### Resources

| Source | Genre | # Classes | Size(sentences)|Size(words) |
| --- | --- | --- | --- | --- |
| NLP&CC 2012 Train | Weibo reviews(Chinese) | 2 | 1765 | ~116k |


## <span class="t">ChnSentiCorp</span>.


[ChnSentiCorp](https://www.sciencedirect.com/science/article/pii/S0957417407001534): It contains 1021 documents in three domains: education, movie and house.


| Source | Genre | # Classes | Size(sentences)|Size(words) |
| --- | --- | --- | --- | --- |
| ChnSentiCorp Test | Hotel reviews(Chinese) | 2 | 1999 | ~725k |

### Metrics
- Accuracy
- F1-score

### Results

|   | F1 | Accuracy |
| --- | --- | --- |
| [Chen et al., 2020: 3SiBert](https://www.aclweb.org/anthology/2020.lrec-1.293.pdf) | | 0.967 | https://www.aclweb.org/anthology/2020.lrec-1.293.pdf
| [ZEN 2.0](https://arxiv.org/abs/2105.01279) | | 0.965 |
| [ZEN](https://aclanthology.org/2020.findings-emnlp.425/) | | 0.961 |
| [ERNIE 2.0](https://arxiv.org/pdf/1907.12412.pdf) | | 0.958 |
| [ERNIE](https://arxiv.org/pdf/1904.09223.pdf) |  | 0.954 |
| BERT * |  | 0.943 |
| fastText **| 0.9218 | 0.9218 |
| [MCCNN](https://arxiv.org/pdf/1808.02961.pdf) | 0.9208 | 0.9208 |

*Bert accuracy result is cited from [ERNIE paper](https://arxiv.org/pdf/1904.09223.pdf).

**fastText accuracy result is cited from [MCCNN paper](https://arxiv.org/pdf/1808.02961.pdf).

### Resources

| Source | Genre | # Classes | Size(sentences)|Size(words) |
| --- | --- | --- | --- | --- |
| ChnSentiCorp Train | Hotel reviews(Chinese)|2|8000|~2.9M|


## <span class="t">IT168TEST</span>.

[IT168TEST](http://www.aclweb.org/anthology/I08-1040): A product review dataset presented by Zagibalov and Carroll. This dataset contains over 20000 reviews, in which 78% were manually labeled as positive and 22% labeled as negative.

| Source | Genre | # Classes | Size(sentences)|
| --- | --- | --- | --- |
| IT168Test | Product review | 2 | 29531 |

### Metrics
- Accuracy
- F1-score

### Results

|   | F1 | Accuracy |
| --- | --- | --- |
| fastText* | 0.9261 | 0.9261 |
| [MCCNN](https://arxiv.org/pdf/1808.02961.pdf) | 0.9302 | 0.9304 |
| [Zhang, P., &amp; He, Z. (2013)](https://journals.sagepub.com/doi/10.1177/0165551513480330) | 0.9402 | 0.9500 |


\*Accuracy result is cited from [MCCNN paper](https://arxiv.org/pdf/1808.02961.pdf).



## <span class="t">Dianping</span>.

[Dianping](https://github.com/zhangxiangxiao/glyph): Chinese restaurant reviews were evenly split as follows: 4 and 5 star reviews were assigned to the positive class while 1-3 star reviews were in the negative class.

| Source | Genre | # Classes | Size(sentences)|
| --- | --- | --- | --- |
| Dianping | restaurant reviews | 2 | 500,000 |

### Metrics
- Accuracy

### Results

|   | Accuracy |
| --- | --- |
| [Sun, Baohua, et al](https://arxiv.org/abs/1810.07653) | 77.8 |
| [Zhang and Lecun 2017](https://arxiv.org/abs/1708.02657) | 77.7 |


### Resources

| Source | Genre | # Classes | Size(sentences)|
| --- | --- | --- | --- |
| Dianping | restaurant reviews | 2 | 2,000,000 |



## <span class="t">JD Full</span>.
[JD Full](https://github.com/zhangxiangxiao/glyph): Chinese shopping reviews were evenly split for predicting full five stars.

| Source | Genre | # Classes | Size(sentences)|
| --- | --- | --- | --- |
| JD Full | shopping reviews | 5 | 250,000 |

### Metrics
- Accuracy

### Results

|   | Accuracy |
| --- | --- |
| [Sun, Baohua, et al](https://arxiv.org/abs/1810.07653) | 54.1 |
| [Zhang and Lecun 2017](https://arxiv.org/abs/1708.02657) | 52.0 |


### Resources

| Source | Genre | # Classes | Size(sentences)|
| --- | --- | --- | --- |
| JD Full | shopping reviews | 5 | 3,000,000 |

---
## <span class="t">JD Binary</span>.
-   [JD Binary](https://github.com/zhangxiangxiao/glyph): Chinese shopping reviews are evenly split into positive (4-and-5 star reviews)and negative (1-and-2 star reviews) sentiments, ignoring 3-star reviews.

| Source | Genre | # Classes | Size(sentences)|
| --- | --- | --- | --- |
| JD Binary | shopping reviews | 2 | 360,000 |

### Metrics
- Accuracy

### Results

|   | Accuracy |
| --- | --- |
| [Sun, Baohua, et al](https://arxiv.org/abs/1810.07653) | 92.2 |
| [Zhang and Lecun 2017](https://arxiv.org/abs/1708.02657) | 91.3 |

### Resources

| Source | Genre | # Classes | Size(sentences)|
| --- | --- | --- | --- |
| JD Binary | shopping reviews | 2 | 4,000,000 |


## Other Resources

* Overview paper in this area:
    * [chinese-sentiment-analysis-review](http://sentic.net/chinese-sentiment-analysis-review.pdf)

* An incomplete list of new corpora (as of 2020)

| Name | Description | Domain/ Source | Size (positive/ negative where applicable) | Accuracy |  F1 | Link |
| --- | --- | --- | --- | --- | --- | --- |
| Chinese Sarcasm Dataset | Text manually labelled as sarcastic or not | news | 2500 / 90 000 | 0.7611 | 0.7368 | [Gong et al., 2020](https://www.aclweb.org/anthology/2020.lrec-1.619.pdf)
| CH-SIMS | Individually labelled multi-modal (text, video, audio) | movies, TV shows | 2281 video segments | - | 0.827 | [Yu et al., 2020](https://www.aclweb.org/anthology/2020.acl-main.343.pdf)
| FiTSA | Aspect-based sentiment analysis for financial news | news | 8314 sentences, 647 000 characters | - | 0.798 | [Yuan et al., 2020](https://www.aclweb.org/anthology/2020.lrec-1.620.pdf)
| MPDD | Emotion in multi-party dialogs | TV shows | 25 500 utterances | 0.595 | - | [Cheng et al., 2020](https://www.aclweb.org/anthology/2020.lrec-1.76.pdf)
| MIMN | Multimodal (text, image) and aspect-based analysis | zol.com (shopping site) | 5200 reviews | 0.616 | 0.605 | [github](https://github.com/xunan0812/MIMN)


---

Suggestions? Changes? Please send email to [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)


