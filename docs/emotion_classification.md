# Chinese Emotion Classification

---

## Background

Emotion classification identifies the emotional state of a writer or speaker.  This is distinct from sentiment classification, which describes the viewpoint of writers toward their subjects.

## Example input/output

Input:

```
讨厌！你骗我！
```
Output:

```
Angry
```

## Standard metrics

- Accuracy of classification.
- F1 score.

---

## Cheng emotion corpus

[Cheng et al 2017](https://dl.acm.org/citation.cfm?id=3132684) introduce an emotion corpus for Chinese Microblogs.  It consists of short posts marked with the following distribution of emotion tags:  Joy (11.3%), Angry (3.5%), Sad (2.6%), Fearful (0.6%), Positive (8.2%), Neutral (4.4%), Negative (9.9%), Non-emotion (59.5%).  Furthermore, the corpus identifies the sub-span of the post that is the cause of the emotion.

[Chen et al 2018](http://aclweb.org/anthology/D18-1066) reports that the corpus includes “~3,000 subtweets, ~11,000 instances for EClass, and ~13,000 instances for ECause.”

|  Test set | Genre |
| --- | --- |
|  Cheng emotion corpus | Microblog |

## Metrics
- F1 score.

## Results

|  System | F1 |
| --- | --- |
|  [[Chen et al 2018]](http://aclweb.org/anthology/D18-1066) | 62.4 |
|  [[Cheng et al 2017]](https://dl.acm.org/citation.cfm?id=3132684) | 58.2 |




