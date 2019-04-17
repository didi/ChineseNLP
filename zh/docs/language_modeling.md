# Chinese Language Modeling


## Background

A language model (LM) assigns a probability to any text string or corpus.  Its goal is to assign high probability (or low perplexity) to fluent text strings it has never observed before, and low probability to others.

## Example

Input:

```
我们体育界是有信心做到为北京2022年冬季奥运会提供坚实的人才基础
```

Output:

```
60.2 perplexity
```

## Standard metric:

* Perplexity (ppl) measures how well the LM performs on previously-unseen text S.  If an LM assigns probability P(S) to S of length N, the perplexity is 2^{-(1/N) log2 P(S)}.  Length may be measured in characters or words.  
  * Language models typically assign probability incrementally, in which case perplexity sums up log probabilities of individual tokens given their left contexts: 2^{-(1/N) sum_i log2 P(S_i)}
* An related metric is bits-per-character (bpc).  If perplexity is measured on a character basis, then ppl = 2^bpc.
* Performance in English language modeling is tracked in places such as [here](https://paperswithcode.com/task/language-modeling).  Standard datasets come with a shared specification for:
  * Train/dev/test corpora splits
  * Units of prediction (typically words rather than characters)
  * Fixed word tokenization
  * Handling of out-of-vocabulary (OOV) items


Common English datasets include:

|   | Train (wds) | Dev (wds) | Test (wds) | Genre |
| --- | --- | --- | --- | --- |
|  Penn Treebank | 888k | 70k | 79k | News |
|  WikiText-103 | 103m | 218k | 246k | Wikipedia |
|  Google 1B | 829m | 160k | 160k | News commentary |

Generally speaking, Chinese LM datasets do not yet have this level of shared specification.

## Chinese Treebank

The Chinese Treebank is available from the Linguistic Data Consortium.  It does not come with a standard train/dev/test split for language modeling.

|   | Word tokens |
| --- | --- |
|  [Chinese Treebank (CBT) v9](https://catalog.ldc.upenn.edu/LDC2016T13) | 2m |

### Results

These numbers are not comparable, given different training conditions!

|   | Character ppl | Word ppl | Notes |
| --- | --- | --- | --- |
|  Glyce (glyph vectors). [We et al, 2019](https://arxiv.org/abs/1901.10125) | 51 | 176 | V6. 4,401 distinct characters.. Data split 80/10/10. For word-level: Jieba segmentation. Singletons → UNK. |
|  RNNG [Dyer et al, 2016](https://arxiv.org/abs/1602.07776) | -- | 171.9 | V5.1. 31k vocab. Maybe singletons → UNK? Test is just 348 lines, so standard split. Claim train is 50k (LDC says 19k). |
|  Segmental NLMs [Kawakami et al, 2016](https://arxiv.org/pdf/1811.09353.pdf) | 4.8 bits per character (not ppl) | -- | V5.1 manual segmentation. Score as bits per character (bpc). Data [here](https://s3.eu-west-2.amazonaws.com/k-kawakami/seg.zip). |

## Chinese Gigaword

Chinese Gigaword is also available from the Linguistic Data Consortium.

|  Corpora | Word tokens |
| --- | --- |
|  [Chinese Gigaword](https://catalog.ldc.upenn.edu/LDC2011T13) V5 (others exist) | 934k |

### Results

These numbers are not comparable, given different training conditions.

|  Chinese Gigaword | Character ppl | Word ppl | Notes |
| --- | --- | --- | --- |
|  [Liu et al, NTU 2016](https://arxiv.org/abs/1611.08656) [GW v1] | 86.9 | -- | 531k lines train, 260k test. 5k vocab. Unclear if character or word-based LM. |
|  [Huang et al, 2010 [GW v2]](http://www.imaging.org/site/PDFS/Reporter/Articles/2010_25/Rep25_2_EI2010_HUANG.pdf) | -- | 220.6 | 610m chars, random 11m for test. MSR segmenter. |
|  Neural Lattice Models [v5] [Buckman+Neubig, 2018](https://www.mitpressjournals.org/doi/pdf/10.1162/tacl_a_00036) | 32.19 | -- | *Guangming Daily subset, top 10k chars + UNK, length <150. 934k lines train, 30k line test. Data [here](https://github.com/jbuckman/neural-lattice-language-models). |

---

**Suggestions? Changes? Please send email to [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**



