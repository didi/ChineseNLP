# Chinese Entity Linking

## Background

Entity linking identifies pieces of text and links them with entries in a standard database, knowledge base, gazetteer, Wikipedia page, etc.  In addition to proper names (“Bob”), mentions may also include nominals (“the player”).

## Example input/output.

Input:

```
美国国防部长马蒂斯说，与首尔举行的名为“秃鹫”的军事演习每年春天在韩国进行，但2019年将“缩小规模”。
```
Output:

```
[美国]wiki/United_States国防部长[马蒂斯]wiki/Jim_Mattis说，与[首尔]wiki/Seoul举行的名为“秃鹫”的军事演习每年春天在[韩国]wiki/South_Korea进行，但2019年将“缩小规模”。
```

## Standard Metrics

* F-score for selecting correct piece of text and linking it to the correct concept from a knowledge base.
* Entity mentions that have no corresponding KB element (NIL mentions) must be clustered, with clusters evaluated by CEAF (successor to B-cubed).


## <span class="t">TAC-KBP / EDL 2017 Track</span>.

The NIST TAC Knowledge Base Population (KBP) Entity Discovery and Linking (EDL) track includes Chinese entity tagging for 5 types: person (PER), geo-political entity (GPE), location (LOC), organization (ORG) and facility (FAC).  

Entities are linked to BaseKB (LDC2015E42: TAC KBP 2015 Tri-Lingual Entity Discovery and Linking Knowledge Base).

Data for this evaluation was prepared by the Linguistic Data Consortium (LDC).
* [Shared task site](http://nlp.cs.rpi.edu/kbp/2017)
* [Shared task writeup](http://nlp.cs.rpi.edu/paper/kbp2017.pdf)
* [Data writeup](https://tac.nist.gov/publications/2017/presentations/TAC2017.KBP.RESOURCES.overview.presentation.pdf)
* Data are available to registrants only.

Data for this evaluation is available from the Linguistic Data Consortium (LDC).

|  Test set | Size (documents) | Genre |
| --- | --- | --- |
|  TAC-KBP-EDL 2015 | 313 (train + eval) | News |
|  TAC-KBP-EDL 2016 | 166 | News |
|  TAC-KBP-EDL 2017 | 167 | News |

### Metrics

NERC F-score
* Requires identifying both text-span and knowledge base ID (KB-id) of mention
* 2016 and 2017 tasks includes both name and nominal mentions
* [Scoring code](http://nlp.cs.rpi.edu/kbp/2017/scoring.html) (likewise for 2015 ad 2016)


### Results 

|  System | TAC-KBP / EDL 2015<br/>Names | TAC-KBP / EDL 2016<br/>Names and nominals | TAC-KBP / EDL 2017<br/>Names and nominals |
| --- | --- | --- | --- |
| [Sil et al (2018)](https://arxiv.org/abs/1712.01813) | 84.4 | | |
| [Pan et al (2020)](https://www.aclweb.org/anthology/D19-6107.pdf) | 84.2 | | |
| [Pan et al (2020)](https://www.aclweb.org/anthology/D19-6107.pdf) | 81.2 (unsup)| | |
| [Best anonymous system in shared task writeup | 76.9 | 76.2 | 67.8 |

### Resources

Train and test sets are available from the Linguistic Data Consortium (LDC).

---

**Suggestions? Changes? Please send email to [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**


