# 中文话题分类 (Topic Classification)


## 背景

话题分类 (Topic Classification) 根据其主题内容为文本分配标签或类别。主题 (topic) 有时广泛，类似于流派（新闻，体育，艺术），但有时也会像标签 (hashtag) 一样细粒度。

## 示例

输入:

```
[国足]有信心了 中国国奥队取得热身赛三连胜
```
输出:

```
体育
```


## 标准评价指标
- 准确率 (Accuracy): 正确分类的样本的百分比。


## <span class="t">THUCNews</span>.


新浪新闻RSS订阅频道数据，数据时间范围从2005年到2011年，其中包含7400万条新闻文件（2.19 GB），14个主题，全部采用UTF-8纯文本格式。

  - [Website](http://thuctc.thunlp.org/#%E4%B8%AD%E6%96%87%E6%96%87%E6%9C%AC%E5%88%86%E7%B1%BB%E6%95%B0%E6%8D%AE%E9%9B%86THUCNews)

| Source  | # Classes | Size(sentences)|
| --- |  --- | --- |
| THUCNews |  14 | 740,000 |

### 评价指标
- Accuracy

### 结果

|   | Accuracy |
| --- | --- |
| [Sun, Baohua, et al](https://arxiv.org/abs/1810.07653) | 94.85% |



## <span class="t">SogouCS</span>.

数据来源于2012年6月至7月间搜狐18个频道 (channel) 的新闻。

  - [Website](http://www.sogou.com/labs/resource/cs.php)

| Source  | # Classes | Size(sentences)|
| --- |  --- | --- |
| [Sougou news dataset](https://www.sciencedirect.com/science/article/abs/pii/S0952197619300090) |  5 | 86,597 |

### 评价指标
- Accuracy

### 结果

|   | Error rate |
| --- | --- |
| [Chung, Tonglee, et al](https://www.sciencedirect.com/science/article/abs/pii/S0952197619300090) | 3.37% |

### 相关资源

| Dataset | Classes | Train(samples size) |
| --- | --- | --- |
| [Sougou news dataset](https://github.com/koalaGreener/Character-level-Convolutional-Network-for-Text-Classification-Applied-to-Chinese-Corpus) | 5 | 490,717 |


## <span class="t">Fudan corpus</span>.

包括20个类别的一共9804个文档。


| Source  | # Classes | Size(sentences)|
| --- |  --- | --- |
| [Fudan corpus](https://www.semanticscholar.org/paper/cw2vec%3A-Learning-Chinese-Word-Embeddings-with-Cao-Lu/57b57e88edcc9a20c78388e847b42e088b451c55) |  5 | 1836 |

### 评价指标
- Accuracy

### 结果

|   | Accuracy |
| --- | --- |
| [Sun, Baohua, et al](https://arxiv.org/abs/1810.07653) | 97.8% |
| [[Meng et al, 2019]](https://arxiv.org/pdf/1901.10125.pdf) | 96.3% |

### 相关资源

| Source  | # Classes | Size(sentences)|
| --- |  --- | --- |
| [Fudan corpus](https://www.semanticscholar.org/paper/cw2vec%3A-Learning-Chinese-Word-Embeddings-with-Cao-Lu/57b57e88edcc9a20c78388e847b42e088b451c55) |  5 | 4284 |

## <span class="t">Ifeng</span>.

2006-2016年间凤凰网上的新闻文章，每篇选取前几个段落，数据集有5个新闻频道 (channel),每个频道(channel) 包含的文章数相等。

  - [Github link](https://github.com/zhangxiangxiao/glyph)

| Source  | # Classes | Size(sentences)|
| --- |  --- | --- |
| [Ifeng](https://github.com/zhangxiangxiao/glyph) |  5 | 50,000 |

### 评价指标
- Accuracy

### 结果

|   | Accuracy |
| --- | --- |
| [[Meng et al, 2019]](https://arxiv.org/pdf/1901.10125.pdf) | 85.8% |
| [Sun, Baohua, et al](https://arxiv.org/abs/1810.07653) | 84.4% |
| [[Zhang and Lecun 2017]](https://arxiv.org/abs/1708.02657) | 83.7% |

### 相关资源

| Dataset | Classes | Train(samples size) |
| --- | --- | --- |
| Ifeng | 5 | 800,000 |

## <span class="t">Chinanews</span>.

数据来自2008年至2016年的中文新闻文章(已去重)，文章属于7个新闻频道(channel)，每个频道(channel) 包含的文章数相等。

- [Github link](https://github.com/zhangxiangxiao/glyph)

| Source  | # Classes | Size(sentences)|
| --- |  --- | --- |
| [Chinanews](https://github.com/zhangxiangxiao/glyph) |  7 | 112,000 |

### 评价指标
- Accuracy

### 结果

|   | Accuracy |
| --- | --- |
| [Sun, Baohua, et al](https://arxiv.org/abs/1810.07653) | 92.0% |
| [[Meng et al, 2019]](https://arxiv.org/pdf/1901.10125.pdf) | 91.9% |
| [[Zhang and Lecun 2017]](https://arxiv.org/abs/1708.02657) | 90.9% |

### 相关资源

| Dataset | Classes | Train(samples size) |
| --- | --- | --- |
| China news | 7 | 1,400,000 |


---

**建议? 修改? 请发邮件到 [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**







