# 如何参与贡献


当前有两种方式参与贡献：
* **在Github中直接编辑**. 适合在现有的markdown文件上做小量的修改。
* **Fork然后提交pull request**. 适合做大量的修改，比如添加新的任务。

## 在Github中直接编辑

假设你想修改 `docs/word_segmentation.md`.

* 首先点击右上角的 `edit` 按钮。

![点击edit按钮](img/edit.png)

* Github会自动按照提示fork当前的代码仓库，你可以在Github的markdown编辑器中进行修改。

![进行编辑](img/fork.png)

* 当修改完毕后，请预览你的修改。 **请提供有意义的提交信息 (commit message)**然后点击`Propose file change`。

![提交修改](img/commit.png)

## Fork然后提交pull request

假设你想添加一个新的任务 `docs/new_task.md`

* Fork本代码仓库
* 克隆(clone)fork下来的的代码仓库到本地

  ```	
  git clone https://github.com/YOUR_GITHUB_NAME/ChineseNLP.git	
  ```

* 快速搭建Web服务
  ```
  cd ChineseNLP
  python3 -m http.server
  ```
  如果你使用的是python 2
  ```
  cd ChineseNLP
  python -m SimpleHTTPServer
  ```
  
  * 在浏览器中查看网站[http://localhost:8000](http://localhost:8000)

* 添加一个新的文件`docs/new_task.md`.
  * 新的文件应该遵循这个[模板](docs/template.md)
  * 在`index.html`中的`sidebar`中添加相关链接
* 提交你的修改到fork的代码仓库.
* 创建一个到`chinesenlpxyz/ChineseNLP:master`的pull request.

## 相关工具
* [Docute](https://docute.org/)
* [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
* [Google Sheet Table to Markdown Converter](https://chrome.google.com/webstore/detail/markdowntablemaker/cofkbgfmijanlcdooemafafokhhaeold?hl=en)
