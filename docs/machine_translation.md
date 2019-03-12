# Machine Translation
---

## Background

Machine translation (MT) converts a text from one language to another.  Here, we focus on translation into and out of Chinese.

## Example

Input:

```
美中两国可能很快达成一个贸易协议。
```

Output:

```
The United States and China may soon reach a trade agreement.
```

## Standard Metrics

* Direct assessment (human judgment).  Amazon Mechanical Turk workers are supplied with a system translation and a human reference.  They are asked “How accurately does the candidate text convey the original semantics of the reference text?”
* Bleu score ([Papineni et al 02](https://www.aclweb.org/anthology/P02-1040.pdf)).
  * Bleu-n4r4: **word** {1,2,3,4}-gram matches, against four human reference translations
    * A brevity penalty additionally punishes translations that are shorter than the reference(s).
    * Standard Bleu scripts will tokenize translations and references before computing n-gram matches.
    * If Chinese is target language, **character** {1,2,3,4}-gram matches are used
    * Bleu-n4r1 is used when only one human reference is available.
  * There are important variations:
    * Case-sensitive vs. case-insensitive
    * Brevity penalty may kick in when the system translation is shorter than the shortest reference, or the “closest” reference.
* NIST.  A variation of BLEU that gives higher weight to rare n-grams.
* TER (Translation Edit Rate).  Automatically calculates the number of edits required to make a translation identical to a human reference.
* BLEU-SBP ((Chiang et al 08)[http://aclweb.org/anthology/D08-1064]).  Addresses decomposability problems with Bleu, proposing a cross between Bleu and word error rate.
* HTER.  Returns the number of edits performed by a human posteditor to get an automatic translation into good shape.

---

## WMT

The Second Conference on Machine Translation (WMT17) has a Chinese/English MT component, done in cooperation with CWMT 2017.
* [Website](http://www.statmt.org/wmt17)
* [Overview paper on WMT17 task](http://www.statmt.org/wmt17/pdf/WMT17.pdf)
* Chinese-English test set:

|  Test set | Size (sentences) | Genre |
| --- | --- | --- |
|  WMT17 Parallel English/Chinese test set | 2001 | News |

Note that the Conference on Machine Translation (WMT19) is announced [here](http://www.statmt.org/wmt19/translation-task.html).

### Metrics

* Direct assessment (human judgments).
* [WMT Bleu score script](https://github.com/moses-smt/mosesdecoder/blob/master/scripts/generic/mteval-v13a.pl)

### Results

Chinese to English (WMT17)

|  System | Direct Assessment (Ave z) | Bleu |
| --- | --- | --- |
|  [[Wang et al 17]](http://www.statmt.org/wmt17/pdf/WMT42.pdf) | 0.209 |  |
|  [[Sennrich et al 17]](http://www.aclweb.org/anthology/W17-4739) | 0.208 | 25.7 |
|  [[Tan et al 17]](http://www.statmt.org/wmt17/pdf/WMT40.pdf) | 0.184 | 26 |

English to Chinese (WMT17)

|  System | Direct Assessment (Ave z) | Bleu |
| --- | --- | --- |
|  [[Wang et al 17]](http://www.statmt.org/wmt17/pdf/WMT42.pdf) | 0.208 |  |
|  [[Sennrich et al 17]](http://www.aclweb.org/anthology/W17-4739) | 0.178 | 36.3 |
|  [[Tan et al 17]](http://www.statmt.org/wmt17/pdf/WMT40.pdf) | 0.165 | 35.8 |


### Resources

There are many parallel English/Chinese text resources to train MT systems on.  These are publicly available:

|  Train set | Size (words on English side) | Genre |
| --- | --- | --- |
|  UN | 327m | Political |
|  New Commentary v12 | 5m | News opinions |
|  CWMT | 154m | Web, movies, thesaurus, government, news conversation, novels, technical documents |
|  AI_Challenger | 120m | Movie subtitles, English learning, etc. |
|  WMT 2017 Dev | 54k | News |

The Linguistic Data Consortium has additional resources, such as FBIS and NIST test sets.

---

## NIST

NIST has a long history of supporting Chinese-English translation by creating annual test sets and running annual NIST OpenMT evaluations during the 2000s.  Many sites have reported results on NIST test sets.  

Test sets contain Chinese sentences with four distinct (human reference) English translations each.  Four references makes NIST an unusually strong evaluation set.

Variations in training and evaluation conditions can make it difficult to compare systems.  
* Evaluation script.  Some papers evaluate with [mteval-v13a](https://github.com/moses-smt/mosesdecoder/blob/master/scripts/generic/mteval-v13a.pl), while others evaluate with the [multibleu](https://github.com/moses-smt/mosesdecoder/blob/master/scripts/generic/multi-bleu.perl) script.  Case sensitivity can also be an issue, and with multiple references, there are variations in how to compute Bleu’s brevity penalty.
* Training data.  Papers vary in the number of training sentence pairs they restrict to.
* Development data.  Some papers use NIST 02 for development/tuning, while others use it as test data.

Note that this [paper](http://www.lrec-conf.org/proceedings/lrec2018/pdf/678.pdf) proposes a standard corpus and methodology around NIST sets, while reporting high Bleu scores. [Github](https://github.com/nusnlp/c2e-mt-benchmark)

|  Test set | Size (sentence pairs) | Genre |
| --- | --- | --- |
|  [NIST 02](https://catalog.ldc.upenn.edu/LDC2010T10) | 878 | News |
|  [NIST 03](https://catalog.ldc.upenn.edu/LDC2010T11) | 919 | News |
|  [NIST 04](https://catalog.ldc.upenn.edu/LDC2010T12) | 1788 | News |
|  [NIST 05](https://catalog.ldc.upenn.edu/LDC2010T14) | 1082 | News |
|  [NIST 06](https://catalog.ldc.upenn.edu/LDC2010T17) | 1664 | Newswire, broadcast news, broadcast conversations, web newgroups |
|  [NIST 08](https://catalog.ldc.upenn.edu/LDC2010T21) | 1357 | Newswire, broadcast news, broadcast conversations, web newgroups |

### Metrics

[Bleu](ftp://jaguar.ncsl.nist.gov/mt/resources/mteval-v13a.pl)

### Results

|  System | Training sentence pairs | Eval script | NIST 02 | NIST 03 | NIST 04 | NIST 05 | NIST 06 | NIST 08 | Average |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  [[Hadiwinoto & Ng, 2018]](http://www.lrec-conf.org/proceedings/lrec2018/pdf/678.pdf) | 7.65m | mteval-v13a | 46.94 | 47.58 | 49.13 | 47.78 | 49.37 | 41.48 | 47.05 |
|  [[Meng et al 2019]](https://arxiv.org/pdf/1901.10125.pdf) | 1.25m | unspecified | 40.56 (dev) | 39.93 | 41.54 | 38.01 | 37.45 | 29.07 | 37.76 |
|  [[Ma et al 2018c]](https://arxiv.org/abs/1805.04871) | 1.25m | unspecified | 39.77 (dev) | 38.91 | 40.02 | 36.82 | 35.93 | 27.61 | 36.51 |
|  [[Chen et al 2017]](http://aclweb.org/anthology/P17-1177) | 1.6m | multibleu | 36.57 | 35.64 | 36.63 | 34.35 | 30.57 |  |  |

### Resources

The Linguistic Data Consortium provides training materials typically used for NIST OpenMT tasks.

---

## IWSLT 2015

* Translation of TED talks
* Chinese-to-English track
* [Shared task overview](https://cris.fbk.eu/retrieve/handle/11582/303031/9811/main.pdf)

|  Test sets | Size (sentences) | # of talks | Genre |
| --- | --- | --- | --- |
|  tst2014 | 1068 | 12 | TED talks |
|  tst2015 | 1,080 | 12 | TED talks |

### Metrics

* Automatic metrics: Bleu, NIST, TER.
* Manual metrics: HTER.

### Results

Chinese to English (tst2015)

|  System | Bleu | NIST | TER |
| --- | --- | --- | --- |
|  MITLL-AFRL | 16.86 | 5.2565 | 67.31 |

English to Chinese (tst2015)

|  System | Bleu | NIST | TER |
| --- | --- | --- | --- |
|  Univ. Edinburgh | 25.39 | 6.3985 | 60.83 |
|  MITLL-AFRL | 24.31 | 6.4136 | 59 |

### Resources

|   | Size (sentences) | # of talks | Genre |
| --- | --- | --- | --- |
|  Train | 210k | 1718 | TED talks |

---

## TED corpus

This [site](http://cs.jhu.edu/~kevinduh/a/multitarget-tedtalks/) contains an up-to-date multi-way corpus of TED talks using for machine translation research. It also contains a leaderboard maintained by Kevin Duh.

|  Test set | Size (sentences) | Genre |
| --- | --- | --- |
|  Chinese/English test | 1,982 | TED talks |
|  Chinese/English dev | 1,958 | TED talks |

This [site](https://github.com/neulab/word-embeddings-for-nmt) contains more languages but a different train/test split.

### Results

Chinese to English

|  System | Bleu |
| --- | --- |
|  Kevin Duh, 6-layer transformer (Sockeye) | 16.63 |

English to Chinese

|  System | Bleu |
| --- | --- |
|  Kevin Duh, coming | Not yet available |

### Resources

[The Multitarget TED Talks Task (MTTT)](http://cs.jhu.edu/~kevinduh/a/multitarget-tedtalks/)

---

## Workshop on Asian Translation

[The Workshop on Asian Translation](http://lotus.kuee.kyoto-u.ac.jp/WAT/) has run since 2014.  Here, we include the 2018 Chinese/Japanese evaluations.

### Metrics
* BLEU.
* RIBES.  Method developed at NTT based on rank correlation coefficients ([link](http://aclweb.org/anthology/D10-1092)).
* Scoring code.
  * for evaluating Chinese outputs: [link](http://lotus.kuee.kyoto-u.ac.jp/WAT/evaluation/automatic_evaluation_systems/automaticEvaluationZH.html)
  * for evaluating Japanese outputs: [link](http://lotus.kuee.kyoto-u.ac.jp/WAT/evaluation/automatic_evaluation_systems/automaticEvaluationJA.html)

ASPEC Chinese-Japanese

Participants must get data from [here](http://lotus.kuee.kyoto-u.ac.jp/ASPEC/)

|  Test set | Size (sentences) | Genre |
| --- | --- | --- |
|  ASPEC Chinese-Japanese | 2107 | Scientific abstracts |
|  ASPEC Japanese-Chinese | 2107 | Scientific abstracts |

JPO Patent Corpus 2

Participants must get data from [here](http://lotus.kuee.kyoto-u.ac.jp/WAT/patent/jpc2018.html)

|  Test set | Size (sentences) | Genre |
| --- | --- | --- |
|  JPCN Chinese-Japanese | 5,204 | Patents |
|  JPCN Japanese-Chinese | 5204 | Patents |
|  JPCN1 Chinese-Japanese | 2000 | Patents |
|  JPCN1 Japanese-Chinese | 2000 | Patents |
|  JPCN2 Chinese-Japanese | 3,000 | Patents |
|  JPCN2 Japanese-Chinese | 3,000 | Patents |
|  JPCN3 Chinese-Japanese | 204 | Patents |
|  JPCN3 Japanese-Chinese | 204 | Patents |
|  JPSEP Chinese-Japanese | 1151 | Patent Expression Patterns |

### Results

* See [here](http://lotus.kuee.kyoto-u.ac.jp/WAT/evaluation/index.html)
* Note that citing others’ results should only be done with anonymization.

### Resources

|  Test set | Size (sentences) | Genre |
| --- | --- | --- |
|  Japanese-Chinese train | 250,000 | Patents |
|  Japanese-Chinese dev | 2000 | Patents |
|  Japanese-Chinese devtest | 2000 | Patents |

---

## CWMT

CWMT 2017 (China Workshop on Machine Translation) features six tasks:

|  Test set | Size (sentences) | Genre |
| --- | ----: | ----: |
|  CWMT Chinese-English news | 1000 | News |
|  CWMT English-Chinese news | 1000 | News |
|  Mongolian-Chinese | 1001 | Daily expressions |
|  Tibetan-Chinese | 729 | Government documents |
|  Uyghur-Chinese | 1000 | News |
|  Japanese-Chinese | 1000 | Patents |


### Metrics

[BLEU-SBP](http://aclweb.org/anthology/D08-1064) is the primary metric.  Other metrics include BLEU-NIST, TER, METEOR, NIST, GTM, mWER, mPER, and ICT.

### Results

Still being compiled.

### Resources

Detailed at [here](http://nlp.nju.edu.cn/cwmt2017/guidelines.en.html)

---

## Other Resources

[Opus](http://opus.nlpl.eu/) is an excellent site for open-source parallel corpora, with a nice language-pair search function.


---

**Suggestions? Changes? Please send email to [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**

[Return to Home](../index.md)




