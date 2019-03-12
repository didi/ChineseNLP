# Chinese Sentiment Analysis

---

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



---

## SemEval-2016 Task 5

-   SemEval-2016 Task 5: contains 2 test sets with over reviews 5000 reviews in total from digital camera and mobile phone area.

    - [Link](http://alt.qcri.org/semeval2016/task5/index.php?id=data-and-tools#)


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

---

## NLP&CC 2012

-   NLP&CC 2012 Test: Chinese Weibo sentiment analysis evaluation data.
    - [Link](http://tcci.ccf.org.cn/conference/2012/pages/page04_eva.html)

| Source | Genre | # Classes | Size(sentences)|Size(words) |
| --- | --- | --- | --- | --- |
| NLP&CC 2012 Test | Weibo reviews(Chinese) | 2 | 442 | ~32k |

### Metrics
- F1-score
- Accuracy

### Results
|   | F1 | Accuracy |
| --- | --- | --- |
| [Chen, et al 2018](https://ieeexplore.ieee.org/abstract/document/8386495)| |88.35%|
| [Wang, et al 2013](https://link.springer.com/chapter/10.1007/978-1-4614-6880-6_31) | 63.60% | 74.00% |

### Resources

| Source | Genre | # Classes | Size(sentences)|Size(words) |
| --- | --- | --- | --- | --- |
| NLP&CC 2012 Train | Weibo reviews(Chinese) | 2 | 1765 | ~116k |

---
## ChnSentiCorp
-   ChnSentiCorp: It contains 1021 documents in three domains: education, movie and house. Meanwhile, Hotel review dataset which contains 5000 positive and 5000 negative short texts.

| Source | Genre | # Classes | Size(sentences)|Size(words) |
| --- | --- | --- | --- | --- |
| ChnSentiCorp Test | Hotel reviews(Chinese) | 2 | 1999 | ~725k |

### Metrics
- Accuracy
- F1-score

### Results

|   | F1 | Accuracy |
| --- | --- | --- |
| fastText | 0.9218 | 0.9218 |
| MCCNN | 0.9208 | 0.9208 |


### Resources

| Source | Genre | # Classes | Size(sentences)|Size(words) |
| --- | --- | --- | --- | --- |
| ChnSentiCorp Train | Hotel reviews(Chinese)|2|8000|~2.9M|

---

## IT168TEST
-   IT168TEST: A product review dataset presented by Zagibalov and Carroll in [30]. This dataset contains over 20000 reviews, in which 78% were manually labeled as positive and 22% labeled as negative.

| Source | Genre | # Classes | Size(sentences)|Size(words) |
| --- | --- | --- | --- | --- |   
| IT168Test | Product review | 2 | 29531 |  |

### Metrics
- Accuracy
- F1-score

### Results

|   | F1 | Accuracy |
| --- | --- | --- |
| fastText | 0.9261 | 0.9261 |
| [MCCNN](https://arxiv.org/pdf/1808.02961.pdf#page=8&amp;zoom=100,0,648) | 0.9302 | 0.9304 |
| [Zhang, P., &amp; He, Z. (2013)](https://journals.sagepub.com/doi/10.1177/0165551513480330) | 0.9402 | 0.9500 |


### Resources




---
## Dianping
-   Dianping: Chinese restaurant reviews were evenly split as follows: 4 and 5 star reviews were assigned to the positive class while 1-3 star reviews were in the negative class.
  -   [Link](https://github.com/zhangxiangxiao/glyph)

| Source | Genre | # Classes | Size(sentences)|Size(words) |
| --- | --- | --- | --- | --- |   
| Dianping | restaurant reviews | 2 | 500,000 |  |

### Metrics
- Accuracy

### Results

|   | Accuracy |
| --- | --- |
| [Sun, Baohua, et al](https://arxiv.org/abs/1810.07653) | 77.8% |
|  [Zhang and Lecun 2017](https://arxiv.org/abs/1708.02657) | 77.7% |



### Resources

| Source | Genre | # Classes | Size(sentences)|Size(words) |
| --- | --- | --- | --- | --- |
| Dianping | restaurant reviews | 2 | 2,000,000 |   |


---
## JD Full
-   JD Full: Chinese shopping reviews were evenly split for predicting full five stars.
  -   [Link](https://github.com/zhangxiangxiao/glyph)

| Source | Genre | # Classes | Size(sentences)|Size(words) |
| --- | --- | --- | --- | --- |
| JD Full | shopping reviews | 5 | 250,000 |  |

### Metrics
- Accuracy

### Results

|   | Accuracy |
| --- | --- |
| [Sun, Baohua, et al](https://arxiv.org/abs/1810.07653) | 54.1% |
|  [Zhang and Lecun 2017](https://arxiv.org/abs/1708.02657) | 52.0% |



### Resources

| Source | Genre | # Classes | Size(sentences)|Size(words) |
| --- | --- | --- | --- | --- |
| JD Full | shopping reviews | 5 | 3,000,000 |   |

---
## JD Binary
-   JD Binary: Chinese shopping reviews are evenly split into positive (4-and-5 star reviews)and negative (1-and-2 star reviews) sentiments, ignoring 3-star reviews.

| Source | Genre | # Classes | Size(sentences)|Size(words) |
| --- | --- | --- | --- | --- |
| JD Binary | shopping reviews | 2 | 360,000 |  |

### Metrics
- Accuracy

### Results

|   | Accuracy |
| --- | --- |
| [Sun, Baohua, et al](https://arxiv.org/abs/1810.07653) | 92.2% |
|  [Zhang and Lecun 2017](https://arxiv.org/abs/1708.02657) | 91.3% |


### Resources

| Source | Genre | # Classes | Size(sentences)|Size(words) |
| --- | --- | --- | --- | --- |
| JD Binary | shopping reviews | 2 | 4,000,000 |   |


---

## Other Resources

* Overview paper in this area: 
    * [chinese-sentiment-analysis-review](http://sentic.net/chinese-sentiment-analysis-review.pdf)

---

Suggestions? Changes? Please send email to [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)

[Return to Home](../index.md)




