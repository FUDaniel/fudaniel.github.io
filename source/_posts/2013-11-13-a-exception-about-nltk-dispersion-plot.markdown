---
layout: post
title: "NLTK 执行text4.dispersion_plot遇到的异常"
date: 2013-11-13 12:46
comments: true
categories: 
---
## 问题描述 ##
在学习NLTK时，按照书中的步骤开始，当执行  
语句
	``text4.dispersion_plot(['citizens','democracy','freedom','duties','America']) `` 
时抛出异常  


> Traceback (most recent call last):
  File "<pyshell#12>", line 1, in <module>
    text4.dispersion_plot(['citizens','democracy','freedom','duties','America'])
  File "C:\Python27\lib\site-packages\nltk\text.py", line 454, in dispersion_plot
    dispersion_plot(self, words)
  File "C:\Python27\lib\site-packages\nltk\draw\dispersion.py", line 25, in dispersion_plot
    raise ValueError('The plot function requires the matplotlib package (aka pylab).'
ValueError: The plot function requires the matplotlib package (aka pylab).See http://matplotlib.sourceforge.net/
## 解决方法 ##

1. 安装matploitlib库
matploitlib官网[http://matplotlib.org](http://matplotlib.org/)找到适合自己的版本。
我下载安装的是[matplotlib-1.3.1.win32-py2.7.exe](http://sourceforge.net/projects/matplotlib/files/matplotlib/matplotlib-1.3.1/matplotlib-1.3.1.win32-py2.7.exe/download?use_mirror=jaist)，但是问题没有解决，运行仍然出现上述异常。
1.在google上搜索问题，

> The plot function requires the matplotlib package (aka pylab)  
 
看了几篇，没有好的结果，最后看到[【原】Python NLP实战之一：环境预备](http://www.myexception.cn/perl-python/464414.html)在他的第一节中，安装Matplotlib的版本是[1.1.0](http://sourceforge.net/projects/matplotlib/files/matplotlib/matplotlib-1.1.0/)。我下载了相同的版本，安装以后执行就没有问题了。