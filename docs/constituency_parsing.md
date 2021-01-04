# Chinese Constituency Parsing

## Background

Given a sentence, consituency parsing produces a parse tree whose internal nodes are constituents and whose leaf nodes are words.

## Example

Input:

```
柴犬是一种像精灵一样的犬种。
```

Output:

```
(IP (NP-SBJ (NN 柴犬)) (VP (VC 是) (NP-PRD (QP (CD 一) (CLP (M 种))) (DVP (IP (VP (PP (P 像) (NP (NN 精灵))) (VP (VA 一样)))) (DEV 的)) (VP (VA 犬种)))) (PU 。))
```

## Standard Metrics

* Exact match (EM): the percentage of predicted parse trees that match the ground truth exactly.
* F1 score of constituents in the predicted parse tree.
* Labeled precision (LP): precision of constituents in the predicted parse tree.
* Labeled precall (LR): recall of constituents in the predicted parse tree.


## <span class="t">Chinese Tree Bank Datasets</span>.

* Released by LDC. Requires LDC licence to acquire the datasets
* Link: [https://verbs.colorado.edu/chinese/ctb.html](https://verbs.colorado.edu/chinese/ctb.html) 
* First used for consituency parsing by [Liu and Zhang (2017)](https://www.aclweb.org/anthology/Q17-1029/).
* Prior works have adopted the preprocessing in [distance-parser](https://github.com/hantek/distance-parser), which selects a subset of CTB 8.0 that corresponds to CTB 5.1.
  
| Dataset | # sentences (train)  | # sentences (dev) | # sentences (test) |
| --- | --- | --- | --- |
| CTB 5.1 | 17,544 | 352 | 348 |  
  
  
### Metrics

EM, F1, LP and LR can be calculated using the [Evalb](https://nlp.cs.nyu.edu/evalb/) tool.


### Results

| System | EM | F1 | LP | LR | code |
| --- | --- | --- | --- | --- | --- |
| [Liu and Zhang (2017)](https://www.aclweb.org/anthology/Q17-1029/) | 44.94 | 91.81 | - | - | [Github](https://github.com/dpfried/rnng-bert) |
| [Zhou and Zhao (2019)](https://www.aclweb.org/anthology/P19-1230/) | - | 92.18 | 92.33 | 92.03 | [Github](https://github.com/DoodleJZ/HPSG-Neural-Parser) |
| [Mrini et al. (2020)](https://arxiv.org/abs/1911.03875) | - | 92.64 | 93.45 | 91.85 | [Github](https://github.com/KhalilMrini/LAL-Parser) |
| [Yang and Deng (2020)](https://arxiv.org/abs/2010.14568) | 49.72 | 93.59 | 93.80 | 93.40 | [Github](https://github.com/princeton-vl/attach-juxtapose-parser) |


---

**Suggestions? Changes? Please send email to [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**

