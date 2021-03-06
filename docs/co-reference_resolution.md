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
- BLANC.
- Link-Based Entity-Aware metric (LEA).

## <span class="t">CoNLL 2012 Co-reference task</span>.

CoNLL 2012 introduced a co-reference task in Chinese.
- http://conll.cemantix.org/2012/introduction.html 

Data for this evaluation is part of OntoNotes, distributed by the Linguistic Data Consortium (LDC).
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
|  [Clark & Manning (2016b)](https://nlp.stanford.edu/static/pubs/clark2016deep.pdf) | 63.88 |
|  [Kong & Jian (2019)](https://www.ijcai.org/Proceedings/2019/700) | 63.85 |
|  [Clark & Manning (2016a)](https://nlp.stanford.edu/static/pubs/clark2016improving.pdf) | 63.66 |

### Resources

Data for this evaluation is part of OntoNotes, distributed by the Linguistic Data Consortium (LDC).
- https://catalog.ldc.upenn.edu/LDC2013T19 

---

## <span class="t">Subtask: zero pronoun resolution (CoNLL 2012 / OntoNotes 5.0) </span>.

### Metrics

F1 score computed on resolution hits ([Zhao & Ng 2007](https://www.aclweb.org/anthology/D07-1057.pdf)).

### Results

|  System | Overall F1 (w/ gold syntactic info) | Overall F1 (w/o gold syntactic info) |
| --- | --- | --- |
|  [Aloraini & Poesio (2020)](https://www.aclweb.org/anthology/2020.lrec-1.11/) | 63.5 | |
|  [Song et al. (2020)](https://www.aclweb.org/anthology/2020.acl-main.482/) | 58.5 | 26.1 |
|  [Yang et al. (2019)](https://www.aclweb.org/anthology/W19-4108/) | 58.1 | |
|  [Yin et al. (2018)](https://www.aclweb.org/anthology/C18-1002/) | 57.3 | |
|  [Liu et al. (2017)](https://www.aclweb.org/anthology/P17-1010/) | 55.3 | |
|  [Yin et al. (2017)](https://www.aclweb.org/anthology/D17-1135/) | 54.9 | 22.7 |

### Resources

Training and testing is performed on the train and dev splits of OntoNotes 5.0 respectively (statistics reported by [Yin et al. (2018)](https://www.aclweb.org/anthology/C18-1002/))

| Split | Documents | Sentences | Words | Anaphoric Zero Pronouns | 
| --- | --- | --- | --- | --- |
|  Train | 1,391 | 36,487 | 756K | 12,111 |
|  Dev | 172 | 6,083 | 110K | 1,713 |


**Suggestions? Changes? Please send email to [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**


