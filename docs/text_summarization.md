# Chinese Text Summarization

## Background

Text summarization takes a long text document and creating a shorter text document that is a fluent and accurate summary of the longer text document.

## Example

Input:

```
 较早进入中国市场的星巴克， 是不少小资钟 情的品牌。相比在美国的平民形象，星巴克在中国就 显得“高端”得多。用料并无差别的一杯中杯美式咖 啡，在美国仅约合人民币12元，国内要卖21元，相当 于贵了75%。第一财经日报 
```

Output:

```
媒体称星巴克美式咖啡售价中国比美国 贵75%。
```

## Standard Metrics

ROUGE compares an automatically produced summary with human-produced, reference summaries.  ROUGE-1 records unigram overlap, ROUGE-2 bigram overlap, and ROUGE-L the longest common subsequence.   ROUGE can be computed over characters or words.

Implementations
* [http://www.berouge.com/Pages/default.aspx](http://www.berouge.com/Pages/default.aspx) 
* [https://github.com/lancopku/superAE/blob/master/data/script/PythonROUGE.py](https://github.com/lancopku/superAE/blob/master/data/script/PythonROUGE.py) 



## <span class="t">LCSTS: A Large Scale Chinese Short Text Summarization Dataset</span>.

* [Hu et. al. (2015)](https://arxiv.org/pdf/1506.05865.pdf) created a dataset of Weibo summaries posted by media organizations.  Short texts are about 100 characters, summaries are about 20 characters.
* Download instruction: “If you want to acquire the corpus. Please fill the application form and send to [Qingcai Chen](qingcai.chen@hit.edu.cn) or [Baotian Hu](baotianchina@gmail.com) [application form, Mainland China](http://pan.baidu.com/s/1eQCUL1K)   [application form, Other]((https://www.dropbox.com/s/g9623j3hsx3yjij/Application%20form.pdf?dl=0))” ([http://icrc.hitsz.edu.cn/Article/show/139.html](http://icrc.hitsz.edu.cn/Article/show/139.html))
  
| Test set  | # (text, summary) pairs | # (text, summary) pairs >= 3 score | Genre |
| --- | --- | --- | --- |
| Part II (validation) | 10,666 | 8,685 | News, politics, economic, military, movies, games, etc. |
| Part III (test) | 1,106 | 725 | News, politics, economic, military, movies, games, etc. |
  
### Results

| System | ROUGE-1 | ROUGE-2 | ROUGE-L |
| --- | --- | --- | --- |
| [Lin et. al. (2018)](https://arxiv.org/pdf/1805.03989.pdf) | 39.4 | 26.9 | 36.5 |
| [Ma et. al. (2018)](https://arxiv.org/pdf/1805.04869v1.pdf) | 39.2 | 26.0 | 36.2 |
| [Wei et. al. (2018)](https://arxiv.org/pdf/1805.04033v1.pdf) | 36.2 | 24.3 | 33.8 |
| [Wang et. al. (2018)](https://arxiv.org/pdf/1805.03616.pdf) | 39.9 | 21.5 | 37.9 |
| Seq2Seq (baseline) | 32.1 | 19.9 | 29.2 |
 
### Resources

  | Train set | # (text, summary) pairs  | Genre |
  | --- | --- | --- |
  | Part I | 2,400,591  | News |


## Other Resources

* [List of Chinese text summarization papers](https://github.com/mathsyouth/awesome-text-summarization#chinese-text-summarization) 
* Recent work [Abstractive Text Summarization by Incorporating Reader Comments](https://arxiv.org/pdf/1812.05407.pdf) (AAAI 2019), does not use the LCSTS dataset but their own version of SinaWeibo dataset  
* Recent work [Autoencoder as Assistant Supervisor: Improving Text Representation for Chinese Social Media Text Summarization](https://arxiv.org/pdf/1805.04869v1.pdf) (ACL 2018), code available at [https://github.com/lancopku/superAE](https://github.com/lancopku/superAE) 
* Toolkit for abstractive summarization: [https://github.com/lancopku/LancoSum](https://github.com/lancopku/LancoSum) 

---

**Suggestions? Changes? Please send email to [chinesenlp.xyz@gmail.com](mailto:chinesenlp.xyz@gmail.com)**



