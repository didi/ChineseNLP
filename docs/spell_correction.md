# Chinese Spelling Correction

## Background

A spelling corrector finds and correct typographical errors in text. These errors often occur between characters that are similar in appearance, pronunciation, or both.



## Example

Input:

```
1986年毕业于国防科技大学计算机应用专业，获学时学位。
```

Output:

```
1986年毕业于国防科技大学计算机应用专业，获学士学位。
(时 -> 士)
```

## Standard Metrics

Spelling correction performance is typically evaluated using accuracy, precision, recall, and F1 score. These metrics can be computed at the character level or the sentence level. Detection and correction are typically evaluated separately.

* Detection: all locations of incorrect characters in a given passage should be completely identical with the gold standard.  
* Correction: all locations and corresponding corrections of incorrect characters should be completely identical with the gold standard.

## <span class="t">SIGHAN Bake-off: Chinese Spelling Check Task</span>.

* Versions: SIGHAN datasets have 3 versions ([2015](http://anthology.aclweb.org/W/W15/W15-3106.pdf), [2014](http://anthology.aclweb.org/W/W14/W14-6820.pdf), [2013](http://anthology.aclweb.org/W/W13/W13-4406.pdf))
* Shared task overview paper: [Tseng et. al. (2015)](http://anthology.aclweb.org/W/W15/W15-3106.pdf) 
* Licence: [http://nlp.ee.ncu.edu.tw/resource/csc_download.html](http://nlp.ee.ncu.edu.tw/resource/csc_download.html) (academic use only)
  
| test set | # sentence pairs | # characters | # spelling errors (chars) | character set | genre |
| --- | --- | --- | --- | --- | --- |
| SIGHAN 2015 ([Tseng et. al. 2015](http://aclweb.org/anthology/W15-3106))| 1,100 | 33,711 | 715 | traditional | second-language learning | 
| SIGHAN 2014 ([Yu et. al. 2014](https://www.aclweb.org/anthology/W14-6820))| 1,062 | 53,114 | 792 | traditional | second-language learning | 
| SIGHAN 2013 ([Wu et. al. 2013](https://www.aclweb.org/anthology/W13-4406))| 2,000 | 143,039 | 1,641 | traditional | second-language learning | 

  
  
  
### Metrics


* (1) False Positive Rate, (2) Detection Accuracy, (3) Detection Precision, (4) Detection Recall, (5) Detection F1, (6) Correction Accuracy, (7) Correction Precision, (8) Correction Recall, (9) Correction F1
* Implementation: http://nlp.ee.ncu.edu.tw/resource/csc_download.html 

### Results

| System | False Positive Rate | Detection Accuracy | Detection Precision | Detection Recall| Detection F1| Correction Accuracy | Correction Precision | Correction Recall | Correction F1| 
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | 
| Soft-Masked BERT ([Zhang et. al. 2020](https://www.aclweb.org/anthology/2020.acl-main.82))| - | 80.9 | 73.7 | 73.2 | 73.5 | 77.4 | 66.7 | 66.2 | 66.4 |
| Confusion-set ([Wang et. al. 2019](https://www.aclweb.org/anthology/P19-1578/))| - | - | 66.8 | 73.1 | 69.8 | - | 71.5 | 59.5 | 64.9 |
| FASPell ([Hong et. al. 2019](https://www.aclweb.org/anthology/D19-5522/))| - | 74.2 | 67.6 | 60.0 | 63.5 | 73.7 | 66.6 | 59.1 | 62.6 |
| CAS ([Zhang et. al. 2015](http://aclweb.org/anthology/W15-3107))| 11.6 | 70.1 | 80.3 | 53.3 | 64.0 | 69.2 | 79.7 | 51.5 | 62.5 |

Results above are all on the SIGHAN 2015 test set.

### Resources

  | Source | # sentence pairs | # chars | # spelling errors | character set | genre |
  | --- | --- | --- | --- | --- | --- |
  | SIGHAN 2015 Training data ([Tseng et. al. 2015](http://aclweb.org/anthology/W15-3106)) | 3,174 | 95,220 | 4,237 | traditional | second-language learning|
  | SIGHAN 2014 Training data ([Yu et. al. 2014](http://ir.itc.ntnu.edu.tw/lre/clp14csc.html)) | 6,526  | 324,342 | 10,087 | traditional | second-language learning|
  | SIGHAN 2013 Training data ([Wu et. al. 2013](http://ir.itc.ntnu.edu.tw/lre/sighan7csc.html)) | 350  | 17,220 | 350 | traditional | second-language learning|

## Other Resources

  | Source | # sentence pairs | # chars | # spelling errors | character set | genre |
  | --- | --- | --- | --- | --- | --- |
  | Synthetic training dataset ([Wang et. al. 2018](https://www.aclweb.org/anthology/P19-1578)) | 271,329 | 12M | 382,702 | simplified | news |

---

**Suggestions? Changes? Please send email to [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**



