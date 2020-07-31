# 中文音译 (Transliteration)

## 背景

音译任务通常在使用不同字母和声音系统的语言之间翻译专有名词和技术术语。

## 示例

输入:

```
约翰伍兹 (yue han wu zi)
```
输出:

```
John Woods
```

## 标准评价指标
- Word Accuracy in Top-1 (ACC)
- Fuzziness in Top-1 (Mean F-score)
- Mean Reciprocal Rank (MRR)
- MAP measures precision



## <span class="t">NEWS 2018 Dataset_03</span>.

Named Entity Workshop (NEWS)长期组织音译任务的评测，其中中文/英文是NEWS中参与度最广的子任务之一。NEWS 2018 相关信息:

- [开放任务信息](http://aclweb.org/anthology/W18-2409)
- [数据集相关信息](http://workshop.colips.org/news2018/dataset.html)

|  Test set name | Source | Target | Test set size (phrase pairs) |
| --- | --- | --- | --- |
|  NEWS 2018 Dataset_03 T-EnCh | English | Chinese | 1000 |
|  NEWS 2018 Dataset_03 B-ChEn | Chinese | English | 1000 |

### 结果

英文-中文

|   | ACC | F-score | MRR | MAP |
| --- | --- | --- | --- | --- |
|  EDI (University of Edinburgh) | 0.304 | 0.6791 | 0.4364 | 0.304 |

中文-英文

|   | ACC | F-score | MRR | MAP |
| --- | --- | --- | --- | --- |
|  UALB (University of Alberta) | 0.3 | 0.8 | 0.374 | 0.3 |
|  EDI (University of Edinburgh) | 0.276 | 0.83 | 0.386 | 0.276 |

### 相关资源
- NEWS 2018 提供了英文-中文音译和中文-英文音译任务的训练集和开发集。

|  Train set name | Source | Target | Train set size (phrase pairs) |
| --- | --- | --- | --- |
|  NEWS 2018 Dataset_03<br/>T-EnCh | English | Chinese | 41318 |
|  NEWS 2018 Dataset_03<br/>B-ChEn | Chinese | English | 32002 |

- TRANSLIT: 大规模名称音译资源
  - 数据集包含人名和地理位置的音译
  - 数据集收集了包括中文在内的180种语言共160万条目(entry),覆盖了大约3百万name variations.
  - [项目GitHub](https://github.com/fbenites/TRANSLIT) 
  - [论文](https://www.aclweb.org/anthology/2020.lrec-1.399.pdf)

---

**建议? 修改? 请发邮件到 [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**


