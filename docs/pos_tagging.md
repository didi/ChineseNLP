# Part-of-Speech (POS) tagging

---

## Background

Part-of-speech tagging is the task of assigning a part-of-speech tag (from a given tag set) to every word in a given sentence. 

## Example

Input:

```
快速 的 棕色 狐狸 跳过 了 懒惰 的 狗
```

Output:

```
[快速] VA [的] DEC [棕色] NN [狐狸] NN [跳过] VV [了] AS [懒惰] VA [的] DEC [狗] NN
```

## Standard Metrics

F1 score calculated from word-level precision and word-level recall computed from the joint segmentation and tagging task. 


---

## Chinese Tree Bank Datasets 

* Task originally defined in [Ng and Low (2004)](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.477.8384&rep=rep1&type=pdf)
* Released by LDC. Requires LDC licence to acquire the datasets
* Link: [https://verbs.colorado.edu/chinese/ctb.html](https://verbs.colorado.edu/chinese/ctb.html) 
* Tag set has 33 POS tags

  
| Test set| # words (dev)  | # words (test) | Genre |
| --- | --- | --- | --- |
| CTB5| 6,821 | 8,008 | News |  
  
### Metrics

* Implementation: [https://github.com/yanshao9798/tagger/blob/master/evaluation.py](https://github.com/yanshao9798/tagger/blob/master/evaluation.py) 

### Results

| System | F1 score |
| --- | --- |
| [Meng et. al. (2019)](https://arxiv.org/pdf/1901.10125.pdf) (Glyce)| 95.61 |
| [Shao et. al. 2017](http://www.aclweb.org/anthology/I17-1018) | 94.38 |
 
### Resources

  | Train set| # words | Genre |
  | --- | --- | --- |
  | CTB5 | 493,935  | News |
 
---

## Universal Dependencies Datasets 

* Available freely (GPL or equivalent licence)
* [https://universaldependencies.org/](https://universaldependencies.org/) 
* Paper describing the dataset: [Nivre et. al. (2016)](http://www.petrovi.de/data/lrec16.pdf)
* Tagset has 15 POS tags

  
| Test set| # words (dev) | # words (test) | Genre |
| --- | --- | --- | --- |
| UD Chinese | 12,663 | 12,012 | Learner essays, news, spoken language, Wiki |
  
### Metrics

* Implementation: [https://github.com/yanshao9798/tagger/blob/master/evaluation.py](https://github.com/yanshao9798/tagger/blob/master/evaluation.py) 

### Results

| System | F1 score|
| --- | --- |
| [Meng et. al. (2019)](https://arxiv.org/pdf/1901.10125.pdf) (Glyce)| 90.77 |
| [Shao et. al. (2017)](http://www.aclweb.org/anthology/I17-1018) | 89.75 |
 
### Resources

|Train set | # words | Genre |
| --- | --- | --- |
| UD Chinese | 98,608  | Learner essays, news, spoken language, Wiki |

---


**Suggestions? Changes? Please send email to [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**

[Return to Home](../index.md)

