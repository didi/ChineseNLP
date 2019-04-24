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

* 识别(Detection): 识别一段文字中所有拼写错误字符的位置应该做到与gold standard相同.
* 纠正(Correction): 识别的错误字符以及相应纠正应与gold standard相同.



## <span class="t">SIGHAN Bake-off: Chinese Spelling Check Task</span>.

* 版本: SIGHAN 数据集有3个版本 ([2015](http://anthology.aclweb.org/W/W15/W15-3106.pdf), [2014](http://anthology.aclweb.org/W/W14/W14-6820.pdf), [2013](http://anthology.aclweb.org/W/W13/W13-4406.pdf))
* 综述论文: [Tseng et. al. (2015)](http://anthology.aclweb.org/W/W15/W15-3106.pdf) 
* Licence: [http://nlp.ee.ncu.edu.tw/resource/csc_download.html](http://nlp.ee.ncu.edu.tw/resource/csc_download.html) (academic use only)
  
| test set | # sentence pairs | # characters | # spelling errors (chars) | character set | genre |
| --- | --- | --- | --- | --- | --- |
| SIGHAN 2015 ([Tseng et. al. 2015](http://aclweb.org/anthology/W15-3106))| 1,100 | 33,711 | 715 | traditional | second-language learning | 

  
  
  
### 评价指标


* (1) False Positive Rate, (2) Detection Accuracy, (3) Detection Precision, (4) Detection Recall, (5) Detection F1, (6) Correction Accuracy, (7) Correction Precision, (8) Correction Recall, (9) Correction F1
* 具体实现: http://nlp.ee.ncu.edu.tw/resource/csc_download.html 

### 结果

| System | False Positive Rate | Detection Accuracy | Detection Precision | Detection Recall| Detection F1| Correction Accuracy | Correction Precision | Correction Recall | Correction F1| 
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | 
| CAS ([Zhang et. al. 2015](http://aclweb.org/anthology/W15-3107))| 0.11 | 0.68 | 0.80 | 0.49 | 0.61 | 0.68| 0.80 | 0.47 | 0.59 |
 
### 其他资源

  | Source | # sentence pairs | # chars | # spelling errors | character set | genre |
  | --- | --- | --- | --- | --- | --- |
  | SIGHAN 2015 Training data ([Tseng et. al. 2015](http://aclweb.org/anthology/W15-3106)) | 2,334  | 146,076 | 2,594 | traditional | second-language learning|

---

**建议? 修改? 请发邮件到 [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**



