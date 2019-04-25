# 中文拼写纠错 (Spell Correction)

## 背景
拼写纠错 (Spell Correction)任务的目标是在文本中查找并更正拼写错误 (typographical errors).

## 示例

输入:
```
1986年毕业于国防科技大学计算机应用专业，获学时学位。
```

输出:

```
1986年毕业于国防科技大学计算机应用专业，获学士学位。
(时 -> 士)
```

## 标准评价指标

* 识别(Detection): 识别一段文字中所有拼写错误字符的位置，应该做到与正确参考 (gold standard) 相同.
* 纠正(Correction): 识别的错误字符以及纠正错误字符，应与正确参考 (gold standard)相同.



## <span class="t">SIGHAN Bake-off: Chinese Spelling Check Task</span>.

* 版本: SIGHAN 数据集有3个版本 ([2015](http://anthology.aclweb.org/W/W15/W15-3106.pdf), [2014](http://anthology.aclweb.org/W/W14/W14-6820.pdf), [2013](http://anthology.aclweb.org/W/W13/W13-4406.pdf))
* 综述论文: [Tseng et. al. (2015)](http://anthology.aclweb.org/W/W15/W15-3106.pdf) 
* Licence: [http://nlp.ee.ncu.edu.tw/resource/csc_download.html](http://nlp.ee.ncu.edu.tw/resource/csc_download.html) (academic use only)
  
| test set | # sentence pairs | # characters | #拼写错误 (chars) | 字符集 | 主题 (Genre)  |
| --- | --- | --- | --- | --- | --- |
| SIGHAN 2015 ([Tseng et. al. 2015](http://aclweb.org/anthology/W15-3106))| 1,100 | 33,711 | 715 | 繁体 | 第二语言学习 (second-language learning) | 

  
  
  
### 评价指标


* (1) 误报率 (False Positive Rate), (2) 识别正确率 (Accuracy), (3) 识别精确率 (precision), (4) 识别召回率 (recall), (5) 识别F1, (6) 纠正正确率 (Accuracy), (7) 纠正精确率 (precision), (8) 纠正 召回率 (recall), (9) 纠正 F1
* 具体实现: http://nlp.ee.ncu.edu.tw/resource/csc_download.html 

### 结果

| System | False Positive Rate | Detection Accuracy | Detection Precision | Detection Recall| Detection F1| Correction Accuracy | Correction Precision | Correction Recall | Correction F1| 
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | 
| CAS ([Zhang et. al. 2015](http://aclweb.org/anthology/W15-3107))| 0.11 | 0.68 | 0.80 | 0.49 | 0.61 | 0.68| 0.80 | 0.47 | 0.59 |
 
### 其他资源

  | Source | # sentence pairs | # chars | #拼写错误 | 字符集 | 主题 (Genre)  |
  | --- | --- | --- | --- | --- | --- |
  | SIGHAN 2015 Training data ([Tseng et. al. 2015](http://aclweb.org/anthology/W15-3106)) | 2,334  | 146,076 | 2,594 | 繁体 | 第二语言学习 (second-language learning) |

---

**建议? 修改? 请发邮件到 [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**



