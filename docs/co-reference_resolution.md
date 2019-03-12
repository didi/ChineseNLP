# Chinese Co-reference Resolution

## Background

Co-reference identifies pieces of text and links them with other pieces of text that refer to the same thing.  Sometimes pieces of text have zero-length, where an overt pronoun or noun is omitted.

## Example input/output

Input:
```
我的姐姐给我她的狗。很喜欢.
```

Output: 

```
[我]0的[姐姐]1给[我]0[她]1的[狗]2。[]0很喜欢[]2.

```

## Standard Metrics.
Average of F1-scores returned by these three precision/recall metrics:
- MUC.  
- B-cubed.  
- Entity-based CEAF.  

---

## CoNLL 2012 Co-reference task

CoNLL 2012 introduced a co-reference task in Chinese.
- http://conll.cemantix.org/2012/introduction.html 

Data for this evaluation is part of Ontonotes, distributed by the Linguistic Data Consortium (LDC).
- https://catalog.ldc.upenn.edu/LDC2013T19 

|  Test set | # of co-referring mentions | Genre |
| --- | --- | --- |
|  CoNLL 2012 co-reference | 144k (including 15k zero-length “dropped” subjects) | Newswire, broadcast news, broadcast conversation |

### Metrics

Average F1 of MUC, B-cubed, and CEAF

Scoring code: https://github.com/conll/reference-coreference-scorers 

### Results

|  System | Average F1 of MUC, B-cubed, CEAF |
| --- | --- |
|  [Clark & Manning, 2016] | 63.66 |

### Resources

Data for this evaluation is part of Ontonotes, distributed by the Linguistic Data Consortium (LDC).
- https://catalog.ldc.upenn.edu/LDC2013T19 

