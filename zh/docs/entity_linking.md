# 中文实体链接 (Entity Linking)

## 背景
实体链接识别文本片段并将它们与标准数据库，知识库，地名词典，维基百科页面等中的对应条目进行链接。

## 示例

输入:
```
美国国防部长马蒂斯说，与首尔举行的名为“秃鹫”的军事演习每年春天在韩国进行，但2019年将“缩小规模”。
```
输出:

```
[美国]wiki/United_States国防部长[马蒂斯]wiki/Jim_Mattis说，与[首尔]wiki/Seoul举行的名为“秃鹫”的军事演习每年春天在[韩国]wiki/South_Korea进行，但2019年将“缩小规模”。
```

## 标准评价指标

* F-score: 正确识别实体并链接到知识库中正确的概念。
* 在知识库中找不到对应概念的元素 (NIL mentions) 需要被聚类, 并用CEAF指标评价聚类效果。


## <span class="t">TAC-KBP / EDL 2017 Track</span>.

The NIST TAC Knowledge Base Population (KBP) Entity Discovery and Linking (EDL)包括5种类型的中文实体标注：人（PER），地缘政治实体（GPE），地点（LOC），组织（ORG）以及设施（FAC）。

实体链接到BaseKB (LDC2015E42: TAC KBP 2015 Tri-Lingual Entity Discovery and Linking Knowledge Base).

评估数据由Linguistic Data Consortium (LDC)发布.
* [Shared task site](http://nlp.cs.rpi.edu/kbp/2017)
* [Shared task writeup](http://nlp.cs.rpi.edu/paper/kbp2017.pdf)
* [Data writeup](https://tac.nist.gov/publications/2017/presentations/TAC2017.KBP.RESOURCES.overview.presentation.pdf)
* 数据仅供已注册用户使用。

评测数据可以通过Linguistic Data Consortium (LDC)获取.

|  Test set | 数量 (文件) | 主题(Genre) |
| --- | --- | --- |
|  TAC-KBP-EDL 2015 | 313 (train + eval) | 新闻 |
|  TAC-KBP-EDL 2016 | 166 | 新闻 |
|  TAC-KBP-EDL 2017 | 167 | 新闻 |

### 评价指标

NERC F-score
* 要求同时识别text-span以及对应的知识库ID
* 2016和2017年的任务包括name和nominal mentions.
* [Scoring code](http://nlp.cs.rpi.edu/kbp/2017/scoring.html) (likewise for 2015 ad 2016)


### 结果 

|  系统 | TAC-KBP / EDL 2015<br/>Names | TAC-KBP / EDL 2016<br/>Names and nominals | TAC-KBP / EDL 2017<br/>Names and nominals |
| --- | --- | --- | --- |
|  Best anonymous system in shared task writeup | 76.9 | 76.2 | 67.8 |

### 相关资源

训练集 (Train) 和测试集 (test)可以通过Linguistic Data Consortium (LDC)获取.

---

**建议? 修改? 请发邮件到[chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**


