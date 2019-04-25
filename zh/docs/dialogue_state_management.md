# 中文对话状态管理 (Dialogue State Management)

## 背景

在面向任务的对话系统中，对话状态管理（dialogue state management）系统将用户意图 (user intent) 作为输入，与知识库交互，并预测系统的下一个动作 (action)。 自然语言理解组件（NLU）负责分析用户意图，该组件有时与对话状态管理（DM）系统结合成为一个单一的端到端学习组件。 系统的下一个动作 (action) 通常包括两种类型：对话动作类型 (dialogue act type) 和插槽值对 (slot-value pairs)。 给定下一个系统动作，自然语言生成组件（NLG）将生成对用户的回复。

## 示例

示例为[Zhang et al. (2018)](https://arxiv.org/pdf/1805.00150.pdf)中所举例子的中文翻译。

|   | 输入 | 输出 |  |  |  |  |
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

以上每一轮输出是在生成系统下一轮回复之前生成的。

## 标准评价指标

分类准确率 (Accuracy): 
* 句子级别.
* 对话级别。 一个对话是正确的当且仅当该对话中的所有句子都被准确的预测了。


## <span class="t">阿里巴巴对话管理数据集</span>.
* 非公开
* 数据来自航班预订领域的真实对话，其中系统应该从用户获得出发城市，到达城市和出发日期的信息来完成预订机票的任务。 
* 其中包含5种对话动作类型 (Dialogue act type) 和3种插槽类型 (Slot type)。


对话动作类型 (Dialogue act type):

|  对话动作类型 |
| --- |
|  ask_dep_loc |
|  ask_arr_loc |
|  ask_dep_date |
|  offer |
|  end |

插槽类型 (Slot type):

|  插槽类型 | 数量 |
| --- | --- |
|  Dep_city | 174 |
|  Arr_city | 174 |
|  Date | 100 |

数据集统计:

|  测试集 (Test) | 3,832 会话(session) |
| --- | --- |
|  每个会话(session)的平均轮数 | 5 |
|  每个句子的平均长度 | 4 |

### 评价指标

准确率 (Accuracy)

### 结果

|   | Dialogue Act Type | Slot-Value | Mask | All |
| --- | --- | --- | --- | --- |
|  [Zhang et al. (2018)](https://arxiv.org/pdf/1805.00150.pdf) | 76.7 (16.3) | 100.0 (100.0) | 100.0 (100.0) | 76.7 (16.3) |

括号中的数字表示会话级的准确率。

### 相关资源

|    | 会话数量 |
| --- | --- |
|  训练集 (Train) | 15,330 会话 (session) |
|  开发集 (dev) | 7,665个 会话 (session) |


## <span class="t">Dialog State Tracking Challenge 5 (DSTC5)</span>.

DSTC5任务旨在跟踪对话状态。
* [任务介绍论文](http://workshop.colips.org/dstc5/papers/0000511.pdf)
* 每个对话被分成若干个子对话 (sub-dialogues), 并且在子对话层面上标注了frame structure。
* DSTC5是一个跨语种的任务，训练集是英文，而开发集 (dev) 和测试集 (Test) 是中文的。

|   | 语言 | 对话(dialogs)数量 | 语句(utterances)数量 |
| --- | --- | --- | --- |
|  测试集 (Test) | 中文 | 10 | 14,878 |

### 结果

|   | 准确率 (Accuracy) | 精确率 (Precision) | 召回率 (Recall) | F1 |
| --- | --- | --- | --- | --- |
|  [Shi et al. (2017)](https://arxiv.org/pdf/1701.06247.pdf) | 0.0956 | 0.5643 | 0.3769 | 0.4519 |

### 相关资源


|   | 语言 | 对话(dialogs)数量 | 语句(utterances)数量 |
| --- | --- | --- | --- |
|  训练集 (Train) | 英语 | 35 | 31,304 |
|  开发集 (dev) | 中文 | 2 | 3,130 |

---

**建议? 修改? 请发邮件到[chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**


