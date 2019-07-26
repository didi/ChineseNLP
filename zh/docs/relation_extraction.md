# 中文关系提取 (Relation Extraction)


## 背景

给定两个实体 (entity)，识别它们的关系并对关系进行分类。

## 示例

输入:

```
[李晓华]和她的丈夫[王大牛]前日一起去[英国]旅行了。
```

输出:

```
(entity1: 李晓华, entity2: 王大牛, relation: 夫妻) 
````

## 标准评价指标

精确率 (Precision), 召回率 (Recall), F1

	   	
输入:

```
[李晓华]和她的丈夫[王大牛]前日一起去[英国]旅行了。
```

参考答案 (Reference):

```
(entity1: 李晓华, entity2: 王大牛, relation: 夫妻) 
(entity1: 李晓华, entity2: 英国, relation: Other) 
(entity1: 王大牛, entity2: 李晓华, relation: 夫妻) 
(entity1: 王大牛, entity2: 英国, relation: Other) 
(entity1: 英国, entity2: 李晓华, relation: Other) 
(entity1: 英国, entity2: 王大牛, relation: Other)
```

系统输出结果:

```
(entity1: 李晓华, entity2: 王大牛, relation: 夫妻) 
(entity1: 李晓华, entity2: 英国, relation: 夫妻) 
(entity1: 王大牛, entity2: 李晓华, relation: 夫妻) 
(entity1: 王大牛, entity2: 英国, relation: Other) 
(entity1: 英国, entity2: 李晓华, relation: Other) 
(entity1: 英国, entity2: 王大牛, relation: Other) 
```

评价指标:

```
Precision = 2 / 3 = 0.66
Recall = 2 / 2 = 1.0
```

## <span class="t">ACE 2005 Relation Extraction</span>.

* [数据链接](https://catalog.ldc.upenn.edu/LDC2006T06)
* [综述论文](https://pdfs.semanticscholar.org/3a9b/136ca1ab91592df36f148ef16095f74d009e.pdf)
* 不同的论文以不同的方式分割训练集和测试集。

ACE 2005包含6种关系类型和18种子关系类型 (subtypes), 具体类型如下所示:

|  Type | Subtypes |
| --- | --- |
|  ART (artifact) | User-Owner-Inventor-Manufacturer |
|  GEN-AFF (Gen-affiliation) | Citizen-Resident-Religion-Ethnicity, Org-Location |
|  * METONYMY | none |
|  ORG-AFF (Org-affiliation) | Employment, Founder, Ownership, Student-Alum, Sports-Affiliation, Investor-Shareholder, Membership |
|  P ART-WHOLE (part-whole) | Artifact, Geographical, Subsidiary |
|  * PER-SOC<br/>(person-social) | Business, Family, Lasting-Personal |
|  * PHYS (physical) | Located, Near |

### 结果

|   | F1 (6 relation types) | F1 (18 relation types) | Train/Test split |
| --- | --- | --- | --- |
|  [Zhang et al. (2018)](http://aclweb.org/anthology/L18-1077) | 87.87 | 83.40 | 80% / 20% |
|  [Chen et al. 2014](http://aclweb.org/anthology/P14-1054) | 90.35 | 75.44 | 未知 |

### 相关资源

| ACE 2005 Chinese Corpus | 字符数量 | 文件数量 |
| --- | --- | --- |
|  Newswire | 121797 | 238 |
|  Broadcast news | 120513 | 298 |
|  Web blogs | 65681 | 97 |
|  Total | 307991 | 633 |

---

**建议? 修改? 请发邮件到 [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**



