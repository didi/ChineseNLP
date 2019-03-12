# Dialogue State Management
---

## Background

In task-oriented dialogue systems, a dialogue state management (DM) system takes a user intent as input, interacts with a knowledge base, and predicts the next system actions. The user intent is analysed by a Natural Language Understanding component (NLU),  which is sometimes combined with DM as a single component for end-to-end training. The next system actions usually consist two type of actions: Dialogue act type and Slot-value pairs. Given the next system actions, a Natural Language Generation component (NLG) will generate a response to the user.

## Examples

An example taken from [Zhang et al. (2018)](https://arxiv.org/pdf/1805.00150.pdf) and translated into Chinese:

|   | Input | Output |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
|   |  | Slot-value pairs |  |  |  |  |
|   | 语句 | 美食类别 | 价格 | 人数 | 地点 | Dialogue Act Type |
|  用户 | 早上好 |  |  |  |  | 问候 |
|  系统 | 你好，有什么可以帮助你的 | - | - | - | - | - |
|  用户 | 能帮忙预定一个在伦敦价格比较便宜的餐厅么？ |  | 便宜 |  | 伦敦 | 确认 |
|  系统 | 好的 | - | - | - | - | - |
|  用户 | <沉默> |  | 便宜 |  | 伦敦 | 询问美食类别 |
|  系统 | 请问想要预定那种类型的餐厅？ | - | - | - | - | - |
|  用户 | 法国餐厅 | 法式 | 便宜 |  | 伦敦 | 询问人数 |
|  系统 | 请问有多少人？ | - | - | - | - | - |
|  用户 | 4人 | 法式 | 便宜 | 4 | 伦敦 | 确认 |
|  系统 | 好的，让我来看看 | - | - | - | - | - |
|  用户 | <沉默> | 法式 | 便宜 | 4 | 伦敦 | 查询 |
|  系统 | API(法式，便宜，4，伦敦) | - | - | - | - | - |

The output is generated before system's turn.

## Standard Metrics

Classification Accuracy: 
* Sentence level.
* Session level. A session is correct only if all the sentences in the session are predicted correctly.

---

## Alibaba Dialogue Management Dataset
* Not public
* It consists of real conversations from the flight-booking domain, in which the system is supposed to acquire departure city, arrival city, and departure date information from the user to book a flight ticket.
* 5 dialogue act types and 3 slot types


Dialogue act types:

|  Dialogue act type |
| --- |
|  ask_dep_loc |
|  ask_arr_loc |
|  ask_dep_date |
|  offer |
|  end |

Slot types:

|  Slot names | # Values |
| --- | --- |
|  Dep_city | 174 |
|  Arr_city | 174 |
|  Date | 100 |

Dataset stats:

|  Test | 3,832 sessions |
| --- | --- |
|  Average turns per session | 5 |
|  Average sentence length | 4 |

### Metrics

Accuracy

### Results

|   | Dialogue Act Type | Slot-Value | Mask | All |
| --- | --- | --- | --- | --- |
|  [Zhang et al. (2018)](https://arxiv.org/pdf/1805.00150.pdf) | 76.7 (16.3) | 100.0 (100.0) | 100.0 (100.0) | 76.7 (16.3) |

The numbers in parenthesis are session level accuracy.

### Resources

|  Train | 15,330 sessions |
| --- | --- |
|  Dev | 7,665 sessions |

---

## Dialog State Tracking Challenge 5 (DSTC5)

This task aims at tracking the dialog state defined as a frame structure filled with slot-value pairs representing the subject of each sub-dialog in human-human dialogs. 
* [Challenge paper](http://workshop.colips.org/dstc5/papers/0000511.pdf)
* The dialogue is divided into sub-dialogues, and the frame structure is annotated at sub-dialogue level.
* This is a cross-language task, where the training set is in English, whereas dev and test set are in Chinese. 

|   | Language | # dialogs | # utterances |
| --- | --- | --- | --- |
|  Test | Chinese | 10 | 14,878 |

### Results

|   | Accuracy | Precision | Recall | F1 |
| --- | --- | --- | --- | --- |
|  [Shi et al. (2017)](https://arxiv.org/pdf/1701.06247.pdf) | 0.0956 | 0.5643 | 0.3769 | 0.4519 |

### Resources


|   | Language | # dialogs | # utterances |
| --- | --- | --- | --- |
|  Train | English | 35 | 31,304 |
|  Dev | Chinese | 2 | 3,130 |

---

**Suggestions? Changes? Please send email to [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**

[Return to Home](../index.md)
