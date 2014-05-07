---
layout: post
title: "R语言简介"
date: 2014-05-07 14:58
comments: true
categories: 
---
##什么是R语言
 Robert I. Kabacoff（2013）在其R语言实战一书中是这样介绍R语言的：
>“R是一种用于统计计算和绘图的语言和环境，是一套开源的数据分析解决方案，由一个庞大且活跃的全球性研究型社区维护”  

直观地理解是，通过R软件可以将一堆原始数据进行处理、运算，以得到我们想要的数值结果或者图形。
##名称由来
R本来是由来自新西兰奥克兰大学的Ross Ihaka和Robert Gentleman开发。因两人名字都是以R 开头 所以也因此形象称为R
##开源、跨平台
R的源代码可以下载自由使用，符合GNU通用公共许可证  
多平台运行，可以在UNIX、Linux、Mac OS和 X OS运行
##代码库
CRAN为Comprehensive R Archive Network的简称。它除了收藏了R的执行档下载版、源代码和说明文件，也收彔了各种用户撰写的软件包。目前有5412个包，[http://cran.r-project.org/](http://cran.r-project.org/)
##行业应用
统计分析，应用数学，计量经济，金融分析，财经分析，人文科学，数据挖掘，人工智能，生物信息学，生物制药，全球地理科学，数据可视化等行业应用
##R能干什么
1. 擅长统计分析方面的工作  
它提供了各种各样的数据处理和分析技术，几乎任何数据分析过程都可以在R中完成。与此相比较，SPSS、MINITAB、MATLAB等数据分析软件更加适合于已经处理好的、规范的数据，而对于还未完成处理过程，或者在分析中仍需大量与处理过程的数据而言，它们可能会显得繁琐一些。
2. R具有专业级的绘图功能  
对于复杂数据的可视化问题，R的优势更加明显；可以很快得到jpg、png、bmp、tiff、gif或postscript等格式的图形结果。 
3. R的交互式数据分析功能强大且灵活  
一个完整的数据分析过程可以大体包括以下几个步骤：  
（1）导入数据；  
（2）数据准备、探索和清洗；  
（3）拟合一个统计模型；  
（4）得到结果并进行评估；  
（5）如果结果的评估不理想，重新完成（3）步骤；  
（6）得到多个模型的结果，并进行交叉检验；  
（7）根据模型结果进行预测、分析等；  
（8）形成报告。  
R中每个步骤的所有“输出”都可以直接作为下一个步骤的“输入”，可以批量完成以上所有的八个步骤。
4. R可以轻松地从多个数据源导入数据，包括文本文件、数据库、其他统计软件等  
这一点成为R处理大数据的基础。
##开发环境
以windows为例，直接下载[安装包](http://mirror.bjtu.edu.cn/cran/)安装。  
由于本身界面简单丑陋、不易用。可以安装同样是跨平台的集成开发环境[RStudio](https://www.rstudio.com/)。
##R与其它软件的接口
- 可通过相应接口连接数据库，例如Oracle、DB2、MySQL。
- 同Python、Java、C、C++等语言进行互调。
- 提供API接口均可以调用，例如Google、Twitter、Weibo。
- 其他统计软件大部分均可调用R，例如SAS、SPSS、Statistica等。
- 一些商业应用，例如Oracle R Enterprise、R add-on for Teradata、Sybase RAP等。

---

#R+Hadoop
##RHIPE
RHIPE(R and Hadoop Integrated Programming Environment)是整合R和Hadoop的开发环境。  
RHIPE合并了R和Hadoop。

- 开源软件 datadr
- 需要安装配置相应的环境，没有完全的安装手册
- 思想 分治 Divide and Recombine  
- [简单教程](http://ml.stat.purdue.edu/rhafen/rhipe/) 

---

##RHadoop

###简介
RHadoop是由Revolution Analytics发起的一个开源项目，它可以将统计语言R与Hadoop结合起来。该项目主要包括四个R packages，分别为支持用R来编写MapReduce应用的rmr、用于R语言访问HDFS的rhdfs以及用于R语言访问 HBASE的rhbase，还有发布近半年的plyrmr，是一个深层的了解R语言运行机制的工具，可以帮助我们更加贴近R语言的核心。

###rmr
用R编写MapReduce程序  
- 提供编程人员更容易、简便的方式写map-reduce程序  
- 提供从大数据的角度用R去进行数据分析  
- 在每一个结点均需要安装rmr2包

###rhdfs
提供R与HDFS的连接与基本操作  
- 文件操作 hdfs.copy, hdfs.move, hdfs.rename, hdfs.delete, hdfs.rm, hdfs.del, hdfs.chown, hdfs.put, hdfs.get  
- 文件读写 hdfs.file, hdfs.write, hdfs.close, hdfs.flush, hdfs.read, hdfs.seek, hdfs.tell, hdfs.line.reader, hdfs.read.text.file  
- 目录操作 hdfs.dircreate, hdfs.mkdir  
- 其他命令 hdfs.ls, hdfs.list.files, hdfs.file.info, hdfs.exists  
- 初始化 hdfs.init, hdfs.defaults
###rhbase
提供与HBASE操作的接口
###plyrmr
帮助我们了解R语言运行机制的工具，可以更容易地接触R的核心。
安装于每个结点上。

## RHive
一款通过R语言直接访问Hive的工具包，是由NexR一个韩国公司研发的
##重写Mahout
用R语言重写Mahout的实现也是一种结合的思路
##Hadoop调用R
打通Java和R的连接通道，还没有商家做出成型的产品

---

#R与Hadoop结合做统计和大数据分析
参考了张丹的博客[R语言为Hadoop注入统计血脉](http://blog.fens.me/r-hadoop-intro/)
##问题1 Hadoop的家族如此强大，为什么还要结合R语言？
- Hadoop家族的强大之处在于对大数据的处理
- R语言的强大之处在于统计分析，在没有Hadoop之前，对大数据的处理是采样、假设检验和回归
- Hadoop重点是全量数据分析，而R语言重点是样本数据分析，两种技术取长补短

##问题2 Mahout同样可以做数据挖掘和机器学习，和R语言的区别是什么？
- Mahout是基于Hadoop的数据挖掘和机器学习算法框架，重点是解决大数据计算问题
- Mahout目前已支持的算法包括，协同过滤，推荐算法，聚类算法，分类算法，LDA(Latent Dirichlet Allocation)，朴素Bayes，随机森林
- Mahout的空白是很多的数据挖掘算法很难实现MapReduce并行化
- R语言可以提供Mahout的绝大多数算法且有很多Mahout不支持的算法
- R和Mahout擅长的领域并不重合，在适合的领域选合适的技术

#R与数据挖掘
##聚类
- 常用的包 **cluster** **fpc**
- 基于划分的方法: kmeans, pam, pamk, clara
- 基于层次的方法: hclust, pvclust, agnes, diana
- 基于模型的方法: mclust
- 基于密度的方法: dbscan
- 基于画图的方法: plotcluster, plot.hclust
- 基于验证的方法: cluster.stats

##分类
- 常用的包 **party** **rpart** **randomForest** **ROCR** **survival** **maptree**
- 决策树: rpart，ctree
- 随机森林: cforest，randomForest
- 回归: Logistic回归，Poisson回归: glm，predict，residuals
- 生存分析: survfit，survdiff，coxph

##关联规则与频繁项集
- 常用的包 **arules**
- arules 支持挖掘频繁项集，最大频繁项集，频繁闭项目集和关联规则
- arules包含两个算法Apriori和Eclat

##序列模式
- 常用的包 **arulesSequences**
- SPADE算法 **cSPADE**

##时间序列
- 常用的包 **timsac** **forecast** **dtw**

##文本挖掘
- 常用的包 **tm** **topicmodels** **wordcloud**

##社交网络分析和图挖掘
- 常用的包 **igraph** network analysis and visualization

##统计分析
- **nlme** linear and nonlinear mixed effects models

##画图及数据操作
- **ggplot2** an implementation of the Grammar of Graphics
- **reshape** flexibly restructure and aggregate data

##并行计算
- **snowfall** usability wrapper around snow for easier development of parallel R programs
- **snow** simple parallel computing in R
- **multicore** parallel processing of R code on machines with multiple cores or CPUs

##RWeka
- Package **RWeka** is an R interface to Weka.

---

#R面向对象编程
现在的R像8年前的Javascript一样，需要大公司和牛人推动，引入面向对象思路。  
R主要面向统计计算，而且代码量一般不会很大，几十行，几百行，使用面向过程的方法就可以很好的完成任务。
随着R向更多的领域发展，产生了R的面向对象编程。  
对于R语言的面向对象编程，不同于其他编程语言，R语言提供了3种底层对象类型，一种是S3类型，一种是S4类型，还有一种是RC类型。
- S3对象简单、具有动态性、结构化特征不明显
- S4对象结构化、功能强大
- RC对象是2.12版后使用的新类型，用于解决S3，S4很难实现的对象
## S3对象
在R语言中，基于S3对象的面向对象编程，是一种基于泛型函数的实现方式。泛型函数是一种特殊的函数, 根据传入对象的类型决定调用哪个具体的方法。基于S3对象实现的面向对象编程，不同其他语言的面向对象编程，是一种动态函数调用的模拟实现。S3对象被广泛应用于R的早期的开发包中。
## S4对象
S4对象系统是一种标准的R语言面向对象实现方式，S4对象有明确的类定义，参数定义，参数检查，继承关系，实例化等的面向对象系统的特征。
## RC对象
RC对象系统从底层上改变了原有S3和S4对象系统的设计，去掉了泛型函数，真正地以类为基础实现面向对象的特征。  
RC是Reference classes的简称，又被称为R5，在R语言的2.12版本被引入的，是最新一代的面向对象系统。
RC不同于原来的S3和S4对象系统，RC对象系统的方法是在类中自定的，而不是泛型函数。
RC对象的行为更相似于其他的编程语言，实例化对象的语法也有所改变。

---
#参考文献
1. [http://dapengde.com/archives/14802](http://dapengde.com/archives/14802)
2. [http://blog.fens.me/series-rhadoop/](http://blog.fens.me/series-rhadoop/)
3. [http://www.xiaowanxue.com/r/aboutr/files/201310/20131004195648706.html](http://www.xiaowanxue.com/r/aboutr/files/201310/20131004195648706.html)
4. [http://www.datadr.org/](http://www.datadr.org/)
5. [http://datapig.diandian.com/post/2012-06-13/R-Datamining01](http://datapig.diandian.com/post/2012-06-13/R-Datamining01)
6. [http://www.36dsj.com/archives/6468](http://www.36dsj.com/archives/6468)

#推荐博客
张丹 [http://blog.fens.me/](http://blog.fens.me/)  
统计之都[http://cos.name/](http://cos.name/)