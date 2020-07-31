# 中文文本摘要 (Text Summarization)

## 背景

文本摘要任务的输入是长的文本文档，任务的目标是将较长的文本转换成简短，流畅而准确的文本摘要。

## 示例

输入:

```
 较早进入中国市场的星巴克， 是不少小资钟情的品牌。相比在美国的平民形象，星巴克在中国就 显得“高端”得多。用料并无差别的一杯中杯美式咖 啡，在美国仅约合人民币12元，国内要卖21元，相当 于贵了75%。第一财经日报 
```

输出:

```
媒体称星巴克美式咖啡售价中国比美国 贵75%。
```

## 标准评价指标

ROUGE将自动生成的摘要与参考摘要进行比较, 其中ROUGE-1衡量unigram匹配情况，ROUGE-2衡量bigram匹配，ROUGE-L记录最长的公共子序列。ROUGE指标的计算可以以字符 (character) 为单位也能以字 (word) 为单位。

具体实现:
* [http://www.berouge.com/Pages/default.aspx](http://www.berouge.com/Pages/default.aspx) 
* [https://github.com/lancopku/superAE/blob/master/data/script/PythonROUGE.py](https://github.com/lancopku/superAE/blob/master/data/script/PythonROUGE.py) 



## <span class="t">LCSTS: A Large Scale Chinese Short Text Summarization Dataset</span>.
* [Hu et. al. (2015)](https://arxiv.org/pdf/1506.05865.pdf) 基于新闻媒体在微博上发布的新闻摘要创建了该数据集，每篇短文约100个字符，每篇摘要约20个字符。 

* 数据集下载说明: “如果想获取该数据集。 请填写申请表[申请表，中国大陆](http://pan.baidu.com/s/1eQCUL1K)  / [申请表，其他](https://www.dropbox.com/s/g9623j3hsx3yjij/Application%20form.pdf?dl=0)并发送至 [Qingcai Chen](qingcai.chen@hit.edu.cn) 或 [Baotian Hu](baotianchina@gmail.com)” ([数据简介](http://icrc.hitsz.edu.cn/Article/show/139.html))
  
| Test set  | # (text, summary) pairs | # (text, summary) pairs >= 3 score | 主题 (Genre) |
| --- | --- | --- | --- |
| Part II (validation) | 10,666 | 8,685 | 新闻，政治，经济，军事，电影，游戏等等 |
| Part III (test) | 1,106 | 725 | 新闻，政治，经济，军事，电影，游戏等等 |
  
### 结果

| System | ROUGE-1 | ROUGE-2 | ROUGE-L |
| --- | --- | --- | --- |
| [Duan et al. (2019)](https://www.aclweb.org/anthology/D19-1301) | 44.35 | 30.65 | 40.58 |
| [Wang et. al. (2018)](https://arxiv.org/pdf/1805.03616.pdf) | 39.9 | 21.5 | 37.9 |
| [Lin et. al. (2018)](https://arxiv.org/pdf/1805.03989.pdf) | 39.4 | 26.9 | 36.5 |
| [Ma et. al. (2018)](https://arxiv.org/pdf/1805.04869v1.pdf) | 39.2 | 26.0 | 36.2 |
| [Wei et. al. (2018)](https://arxiv.org/pdf/1805.04033v1.pdf) | 36.2 | 24.3 | 33.8 |
| Seq2Seq (baseline) | 32.1 | 19.9 | 29.2 |
 
### 相关资源

  | Train set | # (text, summary) pairs  | 主题 (Genre) |
  | --- | --- | --- |
  | Part I | 2,400,591  | 新闻 |


## 其他资源

* [中文文本摘要领域论文列表](https://github.com/mathsyouth/awesome-text-summarization#chinese-text-summarization) 
* [MAT-INF数据集](https://www.aclweb.org/anthology/2020.acl-main.330) (ACL 2020),文章提出了一个多任务学习的数据集,其中包括了一个100万文档摘要的语料集.文章同时证明通过多任务训练,文档摘要的质量能够得到提升.
* AAAI 2019的一篇论文 [Abstractive Text Summarization by Incorporating Reader Comments](https://arxiv.org/pdf/1812.05407.pdf) 没有使用LCSTS数据集，而是使用了他们自己收集的的新浪微博数据集。
* ACL 2018上的一篇论文 [Autoencoder as Assistant Supervisor: Improving Text Representation for Chinese Social Media Text Summarization](https://arxiv.org/pdf/1805.04869v1.pdf), 公开的代码实现: [https://github.com/lancopku/superAE](https://github.com/lancopku/superAE) 
* 一个用于抽象摘要 (abstractive summarization)的工具包: [https://github.com/lancopku/LancoSum](https://github.com/lancopku/LancoSum) 

---

**建议? 修改? 请发邮件到 [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**



