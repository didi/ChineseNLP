# Chinese Relation Extraction


## Background

Given two entity mentions, identify relations and classify them into predefined types.

## Example

Input:

```
[李晓华]和她的丈夫[王大牛]前日一起去[英国]旅行了。
```

Output:

```
(entity1: 李晓华, entity2: 王大牛, relation: 夫妻) 
````

## Standard Metrics

Precision, Recall and F1.

	   	
Input:

```
[李晓华]和她的丈夫[王大牛]前日一起去[英国]旅行了。
```

Reference:

```
(entity1: 李晓华, entity2: 王大牛, relation: 夫妻) 
(entity1: 李晓华, entity2: 英国, relation: Other) 
(entity1: 王大牛, entity2: 李晓华, relation: 夫妻) 
(entity1: 王大牛, entity2: 英国, relation: Other) 
(entity1: 英国, entity2: 李晓华, relation: Other) 
(entity1: 英国, entity2: 王大牛, relation: Other)
```

System Output:

```
(entity1: 李晓华, entity2: 王大牛, relation: 夫妻) 
(entity1: 李晓华, entity2: 英国, relation: 夫妻) 
(entity1: 王大牛, entity2: 李晓华, relation: 夫妻) 
(entity1: 王大牛, entity2: 英国, relation: Other) 
(entity1: 英国, entity2: 李晓华, relation: Other) 
(entity1: 英国, entity2: 王大牛, relation: Other) 
```

Metric:

```
Precision = 2 / 3 = 0.66
Recall = 2 / 2 = 1.0
```

## <span class="t">ACE 2005 Relation Extraction</span>.

* [Data link](https://catalog.ldc.upenn.edu/LDC2006T06)
* [Description paper](https://pdfs.semanticscholar.org/3a9b/136ca1ab91592df36f148ef16095f74d009e.pdf)
* Different papers split the training and testing set in a different manner. 

ACE 2005 employs 6 relation types and 18 subtypes as listed below.

|  Type | Subtypes |
| --- | --- |
|  ART (artifact) | User-Owner-Inventor-Manufacturer |
|  GEN-AFF (Gen-affiliation) | Citizen-Resident-Religion-Ethnicity, Org-Location |
|  * METONYMY | none |
|  ORG-AFF (Org-affiliation) | Employment, Founder, Ownership, Student-Alum, Sports-Affiliation, Investor-Shareholder, Membership |
|  P ART-WHOLE (part-whole) | Artifact, Geographical, Subsidiary |
|  * PER-SOC<br/>(person-social) | Business, Family, Lasting-Personal |
|  * PHYS (physical) | Located, Near |

### Results

|   | F1 (6 relation types) | F1 (18 relation types) | Train/Test split |
| --- | --- | --- | --- |
|  [Zhang et al. (2018)](http://aclweb.org/anthology/L18-1077) | 87.87 | 83.40 | 80% / 20% |
|  [Li et. al. (2019)](https://www.aclweb.org/anthology/P19-1430.pdf) | - | 78.17 | 75% / 25% |  
|  [Chen et al. 2014](http://aclweb.org/anthology/P14-1054) | 90.35 | 75.44 | - |

### Resources

| ACE 2005 Chinese Corpus | chars | files |
| --- | --- | --- |
|  Newswire | 121797 | 238 |
|  Broadcast news | 120513 | 298 |
|  Web blogs | 65681 | 97 |
|  Total | 307991 | 633 |

## <span class="t">Chinese-Literature-NER-RE-Dataset </span>.
* [Data link](https://github.com/lancopku/Chinese-Literature-NER-RE-Dataset)
* [Description paper](https://arxiv.org/pdf/1711.07010.pdf)
* Well defined train, development and test data splits. 
* Contains 9 types of relations (Located, Part-Whole, Family, General-Special, Social, Ownership, Use, Create, Near)

### Results

|   | F1 |
| --- | --- |
|  [Li et. al. (2019)](https://www.aclweb.org/anthology/P19-1430.pdf) | 65.61 | 
|  [Zhang et. al. (2020)](https://dl.acm.org/doi/abs/10.1145/3395260.3395276) | 63.13 |
|  [Xu et. al. (2020)](https://ieeexplore.ieee.org/abstract/document/9085019) | 57.43 |

---

**Suggestions? Changes? Please send email to [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**



