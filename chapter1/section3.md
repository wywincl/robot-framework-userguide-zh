# 1.3 安装说明

本章的说明覆盖了所有Robot Framework安装和卸载的方法，以及在不同操作系统上安装的前提条件。如果你本地安装有```pip```,那么就很容易安装Robot Framework。如下：

```
    pip install robotframework 
```

## 1.3.1 介绍

Robot Framework是用Python实现的，同时支持Jython(JVM)和IronPython(.NET)。在安装框架之前，前提条件就是安装其中一种Python解释器。

下面列出了安装Robot Framework不同的方式，并在后面的章节中加以详细的解释。

**用pip安装** 

用`pip`安装Robot Framework是官方推荐的方式。在最新的Python, Jython和IronPython版本中已经包含了这种标准的包管理器。
如果你已经安装了`pip`, 你可以简单的执行以下这句命令:

```
    pip install robotframework
```

**用源码安装**

这种方式独立于操作系统和Python解释器。你可以从PyPI网站上下载源码发布包进行解[压亦或是从[Github](https://github.com/robotframework/robotframework)上克隆Robot Framework仓库。

**独立的JAR发布包**

如果你用Jython执行测试就足够的话，最简单的方式就是从[Maven中央仓库](http://search.maven.org/#search%7Cga%7C1%7Ca%3Arobotframework)上下载独立的JAR包`robotframework-[version].jar`
JAR发布包同时包含了Jython和Robot Framework，因此仅仅需要安装[Java](http://java.com/)就可以了。

**手动安装**

如果你有特殊需求或者其他的方式都不起作用，那么你可以手动安装。

>注意  
>在Robot Framework 3.0以前，也有Python 32位版本和64位版本两个单独的Windows安装程序。但是在Windows上自带`pip`的Python2.7.9和更新的版本以及Python 3则需要更多的安装程序。
>因此我们决定不在提供Windows安装程序了。在Windows系统上我们同样推荐`pip`安装方式。


## 1.3.2 前提条件

Robot Framework支持[Python](http://python.org/)(包括Python 2和Python 3), [Jython](http://jython.org/)(JVM), [IronPython](http://ironpython.net/)(.NET)以及[PyPy](http://pypy.org/). 
在安装Robot Framework之前，必须先安装你选择的Python解释器。

一般来说，选择哪种解释器通常根据你的测试库和测试环境决定。

## 1.3.3 用pip安装
## 1.3.4 用源码安装
## 1.3.5 独立的JAR发行包
## 1.3.6 手动安装
## 1.3.7 验证安装
## 1.3.8 卸载
## 1.3.9 升级
## 1.3.10 执行Robot Framework