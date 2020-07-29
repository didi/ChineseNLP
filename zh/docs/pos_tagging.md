# 中文词性标注 (Part-of-speech tagging)


## 背景

词性标注任务是将给定句子中的每个单词从给定标签组 (tag set)中赋予一个词性标签 (part-of-speech tag)。

## 示例

输入:

```
快速 的 棕色 狐狸 跳过 了 懒惰 的 狗
```

输出:

```
[快速] VA [的] DEC [棕色] NN [狐狸] NN [跳过] VV [了] AS [懒惰] VA [的] DEC [狗] NN
```

## 标准评价指标

在联合分割标注的任务 (the joint segmentation and tagging task) 中， 计算基于词级别 (word-level) 的精确率 (Precision)和召回率 (Recall)，以及F1-score.



## <span class="t">Chinese Tree Bank Datasets</span>.

* 该任务最早由[Ng and Low (2004)](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.477.8384&rep=rep1&type=pdf)提出。
* 数据集由LDC发布, 需要LDC许可证 (LDC licence) 才能获取数据集。
* 链接: [https://verbs.colorado.edu/chinese/ctb.html](https://verbs.colorado.edu/chinese/ctb.html) 
* 标签组 (tag set) 包含有33种词性标签 (POS tags).

  
| Test set| # words (dev)  | # words (test) | 主题 (Genre) |
| --- | --- | --- | --- |
| CTB5| 6,821 | 8,008 | 新闻 |  
  
### 评价指标

* 代码实现: [Github](https://github.com/yanshao9798/tagger/blob/master/evaluation.py) 

### 结果

| System | F1 score |
| --- | --- |
| [Tian el. al. (2020)](https://www.aclweb.org/anthology/2020.acl-main.735.pdf) | 96.92 | 
| [Meng et. al. (2019)](https://arxiv.org/pdf/1901.10125.pdf) (Glyce + BERT)| 96.61 |
| [Meng et. al. (2019)](https://arxiv.org/pdf/1901.10125.pdf) (BERT)| 96.06 |
| [Shao et. al. 2017](http://www.aclweb.org/anthology/I17-1018) | 94.38 |
 
### 相关资源

  | Train set| # words | 主题 (Genre)  |
  | --- | --- | --- |
  | CTB5 | 493,935  | 新闻 |
 

## <span class="t">Universal Dependencies Datasets</span>.

* 数据集可免费获取 (GPL or equivalent licence)
* [https://universaldependencies.org/](https://universaldependencies.org/) 
* 数据集详情: [Nivre et. al. (2016)](http://www.petrovi.de/data/lrec16.pdf)
* 标签组 (tag set) 包含有15种词性标签 (POS tags).

  
| Test set| # words (dev) | # words (test) | 主题 (Genre)  |
| --- | --- | --- | --- |
| UD Chinese | 12,663 | 12,012 | Learner essays, 新闻, 口语, Wiki百科 |
  
### 评价指标

* 代码实现: [https://github.com/yanshao9798/tagger/blob/master/evaluation.py](https://github.com/yanshao9798/tagger/blob/master/evaluation.py) 

### 结果

| System | F1 score|
| --- | --- |
| [Meng et. al. (2019)](https://arxiv.org/pdf/1901.10125.pdf) (Glyce + BERT)| 96.14 |
| [Tian el. al. (2020)](https://www.aclweb.org/anthology/2020.acl-main.735.pdf) | 95.69 | 
| [Meng et. al. (2019)](https://arxiv.org/pdf/1901.10125.pdf) (BERT)| 94.79 |
| [Shao et. al. (2017)](http://www.aclweb.org/anthology/I17-1018) | 89.75 |
 
### 相关资源

|Train set | # words | 主题 (Genre)  |
| --- | --- | --- |
| UD Chinese | 98,608  | Learner essays, 新闻, 口语, Wiki百科 |

---


**建议? 修改? 请发邮件到 [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**



