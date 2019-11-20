# Chinese Entity Tagging

## Background

Entity tagging identifies pieces of text (“mentions”) and marks them with types such as Person, Organization, Geo-political Entity, Location, etc.  In addition to proper names (“Bob”), mentions may also include nominals (“the player”).

## Example

Input:

```
美国国防部长马蒂斯说，与首尔举行的名为“秃鹫”的军事演习每年春天在韩国进行，但2019年将“缩小规模”。
```

Output:

```
[美国]GPE国防部长[马蒂斯]PER说，与[首尔]GPE举行的名为“秃鹫”的军事演习每年春天在[韩国]GPE进行，但[2019年]TMP将“缩小规模”。
```

## Standard Metrics

F-score for selecting correct piece of text (“mention”) and assigning the correct type.



## <span class="t">TAC-KBP / EDL Track (2015-2017)</span>.

The NIST TAC Knowledge Base Population (KBP) Entity Discovery and Linking (EDL) track includes Chinese entity tagging for 5 types: person (PER), geo-political entity (GPE), location (LOC), organization (ORG) and facility (FAC).
* Shared task sites: [http://nlp.cs.rpi.edu/kbp/2017](http://nlp.cs.rpi.edu/kbp/2017) (likewise for 2015 and 2016)
* Shared task writeups: [http://nlp.cs.rpi.edu/paper/kbp2017.pdf](http://nlp.cs.rpi.edu/paper/kbp2017.pdf) (likewise for 2015 and 2016)
* Note that KBP-EDL 2018 includes thousands of entity types, from the YAGO ontology, but test data is provided only in English.

Data for this evaluation is available from the Linguistic Data Consortium (LDC).

| Test set | Size (documents) | Genre | 
| --- | --- | --- |
| TAC-KBP-EDL 2015| 313 (train + eval) | News 
| TAC-KBP-EDL 2016 | 166 | News |
| TAC-KBP-EDL 2017 | 167 | News |
  
  
  
### Metrics

NERC F-score
* Requires identifying both text-span and type of entity mention
* 2016 and 2017 tasks includes both name and nominal mentions
* Scoring code: [http://nlp.cs.rpi.edu/kbp/2017/scoring.html](http://nlp.cs.rpi.edu/kbp/2017/scoring.html) (likewise for 2015 ad 2016)


### Results

| System | TAC-KBP / EDL 2015 Names | TAC-KBP / EDL 2016 Names and nominals | TAC-KBP / EDL 2017 Names and nominals |
| --- | --- | --- | --- |
| Best anonymous system in shared task writeup| 79.9 | 80.8 | 72.2 |
 
### Resources

Ontonotes 5.0 ([https://catalog.ldc.upenn.edu/LDC2013T19](https://catalog.ldc.upenn.edu/LDC2013T19)) from the Linguistic Data Consortium includes Chinese entity tagging.
* 698 articles Xinhua (1994-1998)
* 55 articles Information Services Department of HKSAR (1997)
* 132 articles Sinorama magazine, Taiwan (1996-1998 & 2000-2001)



## <span class="t">ACE 2005</span>.

ACE 2005 evaluates on seven entity types: Facility (FAC), Geopolitical Entity (GPE), Location (LOC), Organization (ORG), Person (PER), Vehicle (VEH), and Weapon (WEA).

Data for this evaluation was prepared by the Linguistic Data Consortium (LDC).
* [https://catalog.ldc.upenn.edu/LDC2006T06](https://catalog.ldc.upenn.edu/LDC2006T06)

A standard train/dev/test split does not seem to be available.  Authors frequently split randomly 8:1:1 ([Ju et. al. 2018](http://www.aclweb.org/anthology/N18-1131)).

  
| Train + test set| Size (characters) | Genre |
| --- | --- | --- |
| ACE 2005| 325,834 | Newswire, Broadcast News, Weblog |
  

### Results

| System | F-score |
| --- | --- |
| [Wang & Lu. (2018)](https://arxiv.org/pdf/1810.01808.pdf) | 73.00 | 
| [Ju et. al. (2018)](http://www.aclweb.org/anthology/N18-1131) | 72.25 | 



## <span class="t">SIGHAN bakeoff 2006 NER MSRA</span>.

This bakeoff evaluates entity taggers on three types of entities: Person (PER), Location (LOC), and Organization (ORG).

Paper summarizing the bakeoff:
* [Levow (2006)](http://acl-arc.comp.nus.edu.sg/archives/acl-arc-090501d4/data/pdf/anthology-PDF/W/W06/W06-0115.pdf) 
  
| Test set | Size (words) | Genre | 
| --- | --- | --- |
| SIGHAN 2006 NER MSRA | 100,000 | Newswire, Broadcast News, Weblog |
  
### Results

| System | F-score |
| --- | --- | 
| [Meng et. al. (2019)](https://arxiv.org/abs/1901.10125) | 93.89 | 
| [Liu et. al. (2019)](https://www.aclweb.org/anthology/N19-1247) | 93.74 |
| [Sui et al. (2019)](https://www.aclweb.org/anthology/D19-1396/) | 93.47 | 
| [Gui et al. (2019)](https://www.aclweb.org/anthology/D19-1096/) | 93.46 |
| [Zhang & Yang (2018)](http://aclweb.org/anthology/P18-1144) | 93.18 |
 
### Resources 

The “closed” task restricts participants to use only the following training material:

| Train set | Size (words) | Genre |
| --- | --- | --- |
| SIGHAN 2006 NER MSRA | 1.3M  | Newswire, Broadcast News, Weblog |



## <span class="t">Weibo NER</span>.

This social media entity tagging task includes GPE, ORG, LOC, and PER.  It was introduced by
* [Peng & Dredze (2015)](https://aclweb.org/anthology/D15-1064)

Using the test split by http://www.aclweb.org/anthology/E17-2113:
  
| Test set | Size (name mentions) | Size (nomial mentions) | Genre |
| --- | --- | --- | --- |
| Weibo NER | 209 | 196 | Social media (Weibo) |
  

### Results

| System | F-score (name mentions) | F-score (nominal mentions) | F-score (Overall) |
| --- | --- | --- | --- |
| [Sui et al. (2019)](https://www.aclweb.org/anthology/D19-1396/) | 56.45 | 68.32 | 63.09 |
| [Gui et al. (2019)](https://www.aclweb.org/anthology/D19-1096/) | 55.34 | 64.98 | 60.21 |
| [Liu et. al. (2019)](https://www.aclweb.org/anthology/N19-1247) | 52.55 | 67.41 | 59.84 |
|[Zhu (2019)](https://www.aclweb.org/anthology/N19-1342)|55.38 | 62.98 | 59.31 |
|[Zhang & Yang (2018)](http://aclweb.org/anthology/P18-1144)|53.04| 62.25 | 58.79 |
| [Peng & Dredze (2015)](https://www.cs.jhu.edu/~npeng/papers/golden_horse_supplement.pdf) | 55.28 | 62.97 | 58.99 |
 
### Resources

| Train & Dev data | Size (name mentions) | Size (nominal mentions) | Genre |
| --- | --- | --- | --- |
| Weibo NER train | --  | -- | Social media (Weibo) |
| Weibo NER  dev | 153 | 226 | Social media (Weibo) |

Also included are 112M unlabeled text Weibo messages.



## Other Resources

This paper presents an NER-annotated corpus in the genres of social media, human-computer interaction, and e-commerce:
* [Lu et. al. (2018)](http://aclweb.org/anthology/L18-1706) 


---

**Suggestions? Changes? Please send email to [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**



