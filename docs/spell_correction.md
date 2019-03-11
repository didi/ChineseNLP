# Spell Correction

---

## Background

A spell corrector finds and correct typographical errors in text.


## Example

Input:

```
1986年毕业于国防科技大学计算机应用专业，获学时学位。
```

Output:

```
1986年毕业于国防科技大学计算机应用专业，获学士学位。
```

## Standard Metrics
The criteria for judging spelling correction systems are determined at two levels: 
* Detection level: all locations of incorrect characters in a given passage should be completely identical with the gold standard.  
* Correction level: all locations and corresponding corrections of incorrect characters should be completely identical with the gold standard


---

## SIGHAN Bake-off: Chinese Spelling Check Task

* Versions: SIGHAN datasets have 3 versions ([2015](http://anthology.aclweb.org/W/W15/W15-3106.pdf), [2014](http://anthology.aclweb.org/W/W14/W14-6820.pdf), [2013](http://anthology.aclweb.org/W/W13/W13-4406.pdf))
* Shared task overview paper: http://anthology.aclweb.org/W/W15/W15-3106.pdf 
* Licence: http://nlp.ee.ncu.edu.tw/resource/csc_download.html (academic use only)
  
| test set | # sentence pairs | # characters | # spelling errors (chars) | character set | genre |
| --- | --- | --- | --- | --- | --- |
| SIGHAN 2015 ([Tseng+'15](http://aclweb.org/anthology/W15-3106))| 1,100 | 33,711 | 715 | traditional | second-language learning | 

  
  
  
### Metrics


* (1) False Positive Rate, (2) Detection Accuracy, (3) Detection Precision, (4) Detection Recall, (5) Detection F1, (6) Correction Accuracy, (7) Correction Precision, (8) Correction Recall, (9) Correction F1
* Implementation: http://nlp.ee.ncu.edu.tw/resource/csc_download.html 

### Results

| System | False Positive Rate | Detection Accuracy | Detection Precision | Detection Recall| Detection F1| Correction Accuracy | Correction Precision | Correction Recall | Correction F1| 
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | 
| CAS ([Zhang+'15](http://aclweb.org/anthology/W15-3107))| 0.11 | 0.68 | 0.80 | 0.49 | 0.61 | 0.68| 0.80 | 0.47 | 0.59 |
 
### Resources

  | Source | # sentence pairs | # chars | # spelling errors | character set | genre |
  | --- | --- | --- | --- | --- | --- |
  | SIGHAN 2015 Training data ([Teseng+'15](http://aclweb.org/anthology/W15-3106)) | 2,334  | 146,076 | 2,594 | traditional | second-language learning|

---

**Suggestions? Changes? Please send email to [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**

[Return to Home](../index.md)

