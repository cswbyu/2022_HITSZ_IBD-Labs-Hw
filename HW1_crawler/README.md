# HW1: crawler

## 作业简介

第一次作业的内容为网页爬虫。本次作业我们需要爬取至少一万个网页，然后解析其中内容、进行分词处理并存储到txt文件中（作为之后实验课的实验材料）。

## 作业要求

- 爬取至少10000个网页（老师的意思是越多越好）
- 需要进行分词处理，最终存储在一个txt文件中
- 编程语言、实现手段不限

## 技术方案

- **实现语言：** Python生态向来以各种类库齐全而闻名，因此我毫不犹豫地选择了Python。
- **爬取方案：** 虽然有现成的Python爬虫框架Scrapy，但是我并没有使用。我的做法是通过requests库发送请求，然后通过BeautifulSoup解析网页内容，同时获取当前网页所链接到的子网页，并将其存入待访问队列中。这样，就能实现对新网页源源不断的访问了。
- **数据存储方案：** 由于~~此时还没学到数据库不会MySQL~~文件存储操作简便，且本次作业涉及到的数据量并不算大、对数据的操作并不复杂，所以我直接使用txt文件存储数据。
- **所依赖的第三方库：** 总共有bs4、jieba、lxml、requests、zhon这5个。其中bs4、lxml和requests用于爬取、解析网页，jieba用于分词处理，zhon用于去除中文标点符号。

## 文件说明

- .gitignore：git忽略文件
- README.md：本文档
- crawler.py：实现爬虫功能的Python模块
- main.py：对crawler.py进行调用
- preprocess.py：对result.txt进行预处理
- requirements.txt：工程依赖包清单
- result.txt：进行分词后的爬取结果（main.py执行时自动生成）
- seed_url.txt：存放种子网页地址（选取了清华、北大、复旦等高校的官方网站）
- stop_words.txt：停用词表