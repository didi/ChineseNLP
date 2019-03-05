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

* [Website](http://sighan.cs.uchicago.edu/bakeoff2005/), [Detailed Instruction](http://sighan.cs.uchicago.edu/bakeoff2005/data/instructions.php.htm), [Overview Paper](http://aclweb.org/anthology/I05-3017)
* Includes 4 datasets: AS, CityU in traditional Chinese, PK, MSR in simplified Chinese.
