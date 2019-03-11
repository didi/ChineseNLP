# Chinese Transliteration

## Background

Transliteration translates proper names and technical terms across languages that use different alphabets and sound systems.

## Example input/output

Input: 约翰伍兹 (yue han wu zi)
Output: John Woods

## Standard Metrics
- Word Accuracy in Top-1 (ACC)  measures correctness of the first transliteration candidate in a candidate list produced by a transliteration system.
- Fuzziness in Top-1 (Mean F-score).
- Mean Reciprocal Rank (MRR).
- MAP measures precision in the n-best candidates for i-th source name, for which reference transliterations are available.
For more information about the above metrics, please refer this paper.

## Standard Test Set

### NEWS 2018 Dataset_03
Named Entity Workshop (NEWS) is a long-running transliteration evaluation campaign.  Chinese/English is one of the most popular NEWS language pairs.  For NEWS 2018:
- The shared-task report is in http://aclweb.org/anthology/W18-2409.
- The data is described http://workshop.colips.org/news2018/dataset.html.

|  Test set name | Source | Target | Test set size (phrase pairs) |
| --- | --- | --- | --- |
|  NEWS 2018 Dataset_03 T-EnCh | English | Chinese | 1000 |
|  NEWS 2018 Dataset_03 B-ChEn | Chinese | English | 1000 |

### Results

English-Chinese
|   | ACC | F-score | MRR | MAP |
| --- | --- | --- | --- | --- |
|  EDI (University of Edinburgh) | 0.304 | 0.6791 | 0.4364 | 0.304 |

Chinese-English
|   | ACC | F-score | MRR | MAP |
| --- | --- | --- | --- | --- |
|  UALB (University of Alberta) | 0.3 | 0.8 | 0.374 | 0.3 |
|  EDI (University of Edinburgh) | 0.276 | 0.83 | 0.386 | 0.276 |

### Resources
NEWS 2018 also releases training and development data for English-Chinese and Chinese-English.

|  Train set name | Source | Target | Train set size (phrase pairs) |
| --- | --- | --- | --- |
|  NEWS 2018 Dataset_03<br/>T-EnCh | English | Chinese | 41318 |
|  NEWS 2018 Dataset_03<br/>B-ChEn | Chinese | English | 32002 |
