# Introduction

scikit-learn 是 Python 的一个开源机器学习模块，它建立在 NumPy，SciPy 和 matplotlib 模块之上。值得一提的是，scikit-learn 最先是由 David Cournapeau 在 2007 年发起的一个 Google Summer of Code 项目，从那时起这个项目就已经拥有很多的贡献者了，而且该项目目前为止也是由一个志愿者团队在维护着。scikit-learn 最大的特点就是，为用户提供各种机器学习算法接口，可以让用户简单、高效地进行数据挖掘和数据分析。scikit-learn 主页：[scikit-learn homepage](http://scikit-learn.org/dev/)

Numpy 是以矩阵为基础的数学计算模块，纯数学。

Scipy 基于 Numpy，科学计算库，有一些高阶抽象和物理模型。比方说做个傅立叶变换，这是纯数学的，用 Numpy；做个滤波器，这属于信号处理模型了，在 Scipy 里找。

Pandas 提供了一套名为 DataFrame 的数据结构，比较契合统计分析中的表结构，并且提供了计算接口，可用 Numpy 或其它方式进行计算。

sklearn 是机器学习的算法库

# Quick Start

## Installation

scikit-learn 的安装方法有很多种，而且也是适用于各种主流操作系统，scikit-learn 主页上也分别详细地介绍了在不同操作系统下的三种安装方法，具体安装详情请移步至 [installing scikit-learn](http://scikit-learn.org/dev/install.html)。　　在这里，首先向大家推荐一款学习 Python 的强大的开发环境 python(x,y)。python(x,y)是一个基于 python 的科学计算软件包，它包含集成开发环境 Eclipse 和 Python 开发插件 pydev、数据交互式编辑和可视化工具 spyder，而且还内嵌了 Python 的基础数据库 numpy 和高级数学库 scipy、3D 可视化工具集 MayaVi、Python 界面开发库 PyQt、Python 与 C/C++混合编译器 SWIG。除此之外，python(x,y)配备了丰富齐全的帮助文 档，非常方便科研人员使用。　　对于像楼主这样，在学校习惯了用 Matlab 仿真搞科研的学生而言，python(x,y)是学习 Python 的一个绝佳选择，其中内嵌的 spyder 提供了类似于 Matlab 的交互界面，可以很方便地使用。python(x,y)的下载请点击这里：[python(x,y)下载](http://www.softpedia.com/get/Programming/Other-Programming-Files/Python-x-y.shtml)。　　由于 scikit-learn 是基于 NumPy、SciPy 和 matplotlib 模块的，所以在安装 scikit-learn 之前必须要安装这 3 个模块，这就很麻烦。但是，如果你提前像楼主这样安装了 python(x,y)，它本身已经包含上述的模块，你只需下载与你匹配的 scikit-learn 版本，直接点击安装即可。　　 scikit-learn 各种版本下载：[scikit-learn 下载](https://pypi.python.org/pypi/scikit-learn/)。

### Anaconda

笔者推荐使用 Anaconda 进行安装，最方便的方式就是使用 Docker：

```
docker pull rothnic/anaconda-notebook
docker run -p 8888:8888 -i -t rothnic/anaconda-notebook
```

## Reference

### Tutorial & Docs

- [scipy_2015_sklearn_tutorial](https://github.com/amueller/scipy_2015_sklearn_tutorial)

# DataSets

## 内置数据集

scikit-learn 内包含了常用的机器学习数据集，比如做分类的[iris](https://en.wikipedia.org/wiki/Iris_flower_data_set)和[digit](http://archive.ics.uci.edu/ml/datasets/Pen-Based+Recognition+of+Handwritten+Digits)数据集，用于回归的经典数据集[Boston house prices](http://archive.ics.uci.edu/ml/datasets/Housing)。

### iris

数据都是以 n 维(n 个特征)矩阵形式存放和展现，iris 数据中每个实例有 4 维特征，分别为：sepal length、sepal width、petal length 和 petal width。显示 iris 数据：

```
[[ 5.1  3.5  1.4  0.2]
 [ 4.9  3.   1.4  0.2]
　　　　... ...
 [ 5.9  3.   5.1  1.8]]
```

如果是对于监督学习，比如分类问题，数据中会包含对应的分类结果，其存在.target 成员中：

```
print iris.target
```

对于 iris 数据而言，就是各个实例的分类结果：

```
[0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
 0, 0, 0, 0, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1,
 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1,
 1, 1, 1, 1, 1, 1, 1, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2,
 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2,
 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2]
```
