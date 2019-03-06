# Word Segmentation

---

## Overview

Chinese is written using characters (hanzi), where each character represents a syllable. There are no spaces between words, unlike English. There are 25-50k characters, but less than 3500 are normally encountered. Words can be composed of multiple characters, so the reader needs to determine where one word ends and the next begins in order to understand the sentence. Deciding where the word boundaries are in a text (and optionally inserting a space or some other separator) is called tokenization, or **Word Segmentation**. 

## Example

Input:

> 亲 请问有什么可以帮您的吗？

Output:

> ["亲", "请问", "有", "什么", "可以", "帮", "您", "的", "吗", "？"]

## Problem History

Word segmentation to separate complete words is primarily a task designed for Chinese and Japanese, as those are the largest languages that do not use whitespace. There is other work on word segmentation for morphologically richer languages such as Arabic, where the goal is to split complete words into morphemic units. Similarly, there is ‘compound splitting’ for German, separating compound nouns into more-frequently-seen components  and reduce the number of distinct word types. Word segmentation for Vietnamese is different in that all the syllables are separated by whitespace, and the challenge is to identify which syllables should be combined into a single token.

## Progress on Chinese

It’s been a character-level sequence labelling task since the 1990’s. Human annotators agreement seems pretty low: 70%  [Sproat et al, 1996].

## Metrics

Word F1 score:

> Gold: 共同  创造  美好  的  新  世纪  ——  二○○一年  新年  贺词

> Hypothesis: 共同  创造  美  好  的  新  世纪  ——  二○○一年  新年  贺词

Precision = 9 / 11 = 0.818

Recall = 9 / 10 = 0.9

F1 = 0.857

## Standard test sets

### The Second International Chinese Word Segmentation Bakeoff in SIGHAN 2005 Workshop (Emerson, 2005)

* [Website](http://sighan.cs.uchicago.edu/bakeoff2005/), [Detailed Instruction](http://sighan.cs.uchicago.edu/bakeoff2005/data/instructions.php.html), [Overview Paper](http://aclweb.org/anthology/I05-3017)
* Includes 4 datasets: AS, CityU in traditional Chinese, PK, MSR in simplified Chinese.

| Corpus | Abbrev. | Encoding | Test Size (Tokens/Types) |
| ---: | ---: | ---: | ---: |
| **Traditional Chinese** |
|Academia Sinica(Taipei)|AS|Unicode/Big Five Plus|122K / 19K|
|City University of Hong Kong|CityU|HKSCS Unicode/Big Five|104K / 13K|
| **Simplified Chinese** |
|Peking University|PK|CP936/Unicode|41K / 9K|
|Microsoft Research|MSR|CP936/Unicode|107K / 13K|

### Chinese Penn Treebank

* [Website](https://verbs.colorado.edu/chinese/ctb.html)
* Includes 2 datasets:
  * [CTB6](https://catalog.ldc.upenn.edu/LDC2007T36): consisting of 780,000 words (over 1.28 million Chinese characters)
  * [CTB7](https://catalog.ldc.upenn.edu/LDC2010T07): consists of 2,448 text files, 51,447 sentences, 1,196,329 words and 1,931,381 hanzi (Chinese characters)


|Data set|Test set (Tokens)|
| ---: | ---: |
|CTB6|81,578|
|CTB7|81,578|

### Chinese Universal Treebank (UD)

* [Website](https://universaldependencies.org/), [Github](https://github.com/UniversalDependencies/UD_Chinese-GSD)

|Data set|Test set(Tokens)|
| ---: | ---: |
|UD|12,012|

## Baselines and state-of-art results

Systems

|  Model | description | paper | code |
| --- | --- | --- | --- |
|  Ma et al. (2018) | Bidirectional LSTM + Pre-trained Embedding + Dropout + Hyperparameter tuning | [EMNLP 2018](http://aclweb.org/anthology/D18-1529) |  |

Performance

|  Model | AS | CITYU | CTB6 | CBT7 | MSR | PKU | UD |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
|  Ma et al. (2018) | 96.2 | 97.2 | 96.7 | 96.6 | 97.4 | 96.1 | 96.9 |

## Resources

There are several datasets in this area. Many of them are free for download except CTB7 ($300)

|  Train set | Training Size(Tokens) |
| --- | ----: |
|  AS | 5.45M |
|  CityU | 1.46M |
|  MSR | 2.37M |
|  CTB6 | 641,368 |
|  CTB7 | 950,138 |
|  PKU | 1.1M |
|  UD | 98,608 |
