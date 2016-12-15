# 1.3 安装说明

本章的说明涵盖了所有Robot Framework安装和卸载的方法，以及在不同操作系统上安装的前提条件。如果你本地安装有```pip```,那么就很容易安装Robot Framework。如下：

```
    pip install robotframework 
```

## 1.3.1 介绍

Robot Framework是用Python实现的，同时支持Jython(JVM)和IronPython(.NET)。在安装框架之前，前提条件就是安装其中一种Python解释器。

下面列出了安装Robot Framework不同的方式，并在后续的章节中加以详细的说明。

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

一般来说，选择哪种解释器通常根据你的测试库和测试环境决定。一些测试库使用的工具和模块仅仅在Python下工作，而另一些测试库需要使用Java工具，这就需要有Jython环境，或者需要.NET环境，那就需要安装IronPython。
也有一些测试库和工具能够在所有解释器平台上正常运行。

如果你没有特殊的环境要求，那么推荐使用Python解释器来运行Robot Framework。因为Robot Framework是用原生Python实现的，所以运行的自然比Jython和IronPython要快(特别是在启动时间上)。
同时在类Unix系统上，Python解释器是自带的，随时可用。还有一个替代方案就是，运行独立的JAR发布包，它仅仅依赖Java环境作为前提条件。

**Python 2 or Python 3**

Python 2 和Python 3通常来说是同一种编程语言，但是它们之间却不是完全的相互兼容。两者之间主要的区别是Python 3中所有的字符串都是Unicode编码的，而在Python 2中默认是字节编码。
但是也有其他几个向后兼容的改变。最后一个Python 2版本是Python 2.7, 于2010年发布, 将会支持到2020年。点击链接[Should I use Python 2 or 3?](https://wiki.python.org/moin/Python2orPython3)查看更多关于两者之间的异同，该使用哪个版本，
以及如何写出兼容两个版本的代码等等。

Robot Framework 3.0 是第一个支持Python 3的版本， 当然，它也支持Python 2版本。同时我们也计划一直支持到Python 2官方的结束支持时间。我们希望开发Robot Framework生态系统的测试库和测试工具的开发者能够考虑支持Python 3, 像我们的核心框架一样。

**Python 安装**

在大部分类Unix系统，如Linux和OS X已经默认自带了Python解释器了，所以无需安装。如果你是在Windows系统或者自己需要安装Python, 可以去官方网站http://python.org，这里可以下载合适的版本以及了解更多关于Python的相关信息。

Robot Framework 3.0支持Python 2.6, 2.7, 3.3和更新的版本。但是RF3.1 已经计划不支持Python 2.6了。如果你需要使用老版本Python的话，Robot Framework 2.5-2.8支持Python 2.5, Robot Framework 2.0-2.1 支持Python 2.3和2.4。

在安装完Python以后，你可能需要设置PATH环境变量, 以使Python本身以及`robot` 和`rebot`执行器能够在命令行中执行。

>小贴士  
>最新的Python Windows安装程序在安装过程中允许设置PATH路径。这个功能默认是禁用的, 但可以通过在自定义安装Python界面中添加`python.exe`到Path中来启动。

**Jython 安装**
 
使用Java实现的测试库或者工具需要Robot Framework运行在Jython上。反过来又需要有Java运行时环境(JRE)或者Java开发工具集(JDK)。安装这两种Java发行包已经超出了本章的范围了，但是你可以通过http://java.com来获取更多信息。

安装Jython是很容易的，第一步就是在网站http://jython.org获取安装程序。安装程序是可执行的JAR包，可以在命令行中执行,如`java -jar jython_installer-<version>.jar`。依赖于系统设置，你或许可以通过双击文件来运行安装程序。

Robot Framework 3.0 支持Jython 2.7, 因此需要Java 7或更新的运行时环境。如果需要旧的Jython或者Java版本，那么Robot Framework 2.5-2.8支持Jython 2.5(需要Java 5以及更新版本)；
Robot Framework 2.0-2.1支持Jython 2.2。

安装完Jyhton之后，你可能仍需要配置PATH环境变量，以使Jython本身以及`robot` 和`rebot`执行器能够在命令行中执行。

**IronPython 安装**

IronPython 运行Robot Framework运行在.NET平台,可以与C#或者其他.NET语言和API进行交互。仅支持IronPython 2.7。

当使用IronPython，需要额外安装`elementtree`模块1.2.7预览版本。这是因为`elementtree`模块利用IronPython发布出现了问题。
你可以下载源码安装包到本地，解压，然后在解压目录下打开终端，执行`ipy setup.py install`进行安装。

安装完IronPyhton之后，你可能仍需要配置PATH环境变量，以使Jython本身以及`robot` 和`rebot`执行器能够在命令行中执行。

**配置PATH**

PATH环境变量列出了操作系统执行命令的位置，为了确保可以从终端上执行Robot Framework, 推荐将Robot Framework的执行器路径添加到PATH环境变量中去。通常也将解释器本身添加到PATH中，以使Python执行方式更加简单。

当在类Unix系统使用Python时，Python本身和它的相关脚本会自动地添加到PATH路径中去，无需额外操作。但在Windows系统和其他解释器的情况下，还需要分别设置PATH环境变量。

>小贴士  
>最新的Python Windows安装程序在安装过程中允许设置PATH路径。这个功能默认是禁用的, 但可以通过在自定义安装Python界面中添加`python.exe`到Path中来启动。
>这样会同时将Python安装路径和脚本目录添加到PATH环境变量中去。
>

**添加什么目录到PATH**

添加什么目录到PATH环境变量中取决于你本地的操作系统和解释器类型。首要位置就是解释器的安装目录(如，C:\Python27)，其次就是解释器安装执行脚本的目录。
在Windows系统上，Python和IronPython均将脚本安装到自身安装目录的Scripts子目录下。无论在什么系统上，Jython统一安装到bin目录下(如，C:\jython2.7.0\bin)。

注意Scripts和bin目录并不是在解释器自身安装的时候创建的，在安装Robot Framework和Python第三方模块的时候，才会创建该目录。

**在Windows系统上配置PATH**

在Windows系统上你可以根据以下步骤来配置PATH环境变量。注意具体的设置名称可能在不同的Windows版本上会出现不一致，但基本的方法是一样的。

* 打开控制面板>系统>高级>环境变量。有系统环境变量和用户环境变量，它们的区别是用户环境变量仅仅对当前的用户生效，而系统环境变量则对所有的用户起作用。
* 编辑已存在的PATH值，选择`编辑`，然后添加`;<InstallationDir>;<ScriptsDir>`到已存在的值的末尾去(如. ;C:\Python27;C:\Python27\Scripts)。
注意分号(;)很重要, 它用于分隔不同的值项。添加一个新的PATH值，选择`新增`，然后同时设置变量名和值, 只一次前面不需要分号了。
* 点击`确定`按钮,保存修改并退出对话框。
* 启动新的命令行终端使修改生效。



**在类Unix系统上配置PATH**

在类Unix系统上，你可能需要编辑系统层面或者用户层面的配置文件。至于编辑何种文件则依据于具体的操作系统。你需要查询操作系统文档来获取更多信息。

**配置`https_proxy`**

如果你是用pip安装，并且使用代理的话，你需要设置`https_proxy`环境变量。`https_proxy`环境变量在安装pip本身和使用pip安装Robot Framework以及其他Python包的时候都需要。

和配置PATH类似，配置`https_proxy`环境变量，根据不同的系统，方式也不尽相同。但是`https_proxy`变量的值必须是代理的URL地址，如http://10.0.0.42:8080。

## 1.3.3 用pip安装

Python标准的包管理方式是pip, 但是也有其他的替代方案如[Buildout](http://buildout.org/)和[easy_install](http://peak.telecommunity.com/DevCenter/EasyInstall)。
本节只覆盖了pip安装的部分，其他的包管理方式也能安装Robot Framework。

最新的Python, Jython和IronPython版本已经内置了pip模块。后续的章节我们详细讨论那些版本包含pip以及如何使用pip。如果你需要安装pip，可查看[pip](http://pip-installer.org/)项目主页以了解最新的安装说明.

>小贴士  
>只有Robot Framework 2.7和更新的版本可以用pip安装。如果你需要用旧的版本，你必须选择其他的安装方式。

**为Python安装pip**

从Python 2.7.9开始，标准的Windows安装程序就默认安装和激活了pip了。假设你已经设置好PATH或者HTTP代理了，你可以在安装完Python后执行命令
`pip install robotframework`。

对于非Windows系统或者是早期的Python版本，你需要自己手动安装pip。你可以利用系统的包管理工具，在linux上使用apt或者是yum来进行安装。
同时你也可以在[pip](http://pip-installer.org/)主页上找到手动安装的说明。

如果你安装有多个包含pip模块的Python版本的话，那么优先执行PATH环境变量中第一个在搜索路径发现的pip命令。一个替代的方式是直接在执行pip命令的时候选择Python的版本：

```
    python -m pip install robotframework
    python3 -m pip install robotframework
```

**为Jython安装pip**

Jython 2.7已经自带了pip，但是需要先执行下面的命令启用它：

```
    jython -m ensurepip
```

Jython将pip安装到\<JythonInstallation>/bin目录下。
执行运行`pip install robotframework`有可能会使用其他的pip版本, 这取决于PATH环境变量中pip命令的路径地址顺序。
一个替代的方式是直接用Jython运行pip模块:

```
    jython -m pip install robotframework
```

**为IronPython安装pip**

IronPython 从2.7.5版本开始自带pip。和Jython类似，需要先进行激活：

```
    ipy -X:Frames -m ensurepip
```

注意命令行选项 `-X:Frames`在激活和使用pip的时候都需要。

IronPython将pip安装到\<IronPythonInstallation>/Scripts目录下。
执行运行`pip install robotframework`有可能会使用其他的pip版本, 这取决于PATH环境变量中pip命令的路径地址顺序。
一个替代的方式是直接用IronPthon运行pip模块:

```
    ipy -X:Frames -m pip install robotframework
```

IronPython 2.7.5以前的版本，官方不支持pip。

**使用pip**

一旦安装好了pip，设置好https代理以后，在命令行使用pip就非常简单了。最简单的方式就是使用pip从Python Package Index (PyPI)上来查找和下载包。
它也可以安装已经下载的安装包。最常用的使用方法如下所示，pip官方文档提供了更多详细的信息：

```
    # Install the latest version
    pip install robotframework

    # Upgrade to the latest version
    pip install -upgrade robotframework

    # Install a specific version 
    pip install robotframework==2.9.2

    # Install separately downloaded package (no network connection needed.)
    pip install robotframework-3.0.tar.gz

    # Uninstall
    pip uninstall robotframework
```
注意pip1.4和更新的pip版本默认情况下只会安装稳定的包版本。如果你需要安装alpha,beta或者rc版本,你需要特别指定，或者使用`--pre`选项。

```
    # Install 3.0 beta 1
    pip install robotframework==3.0b1

    # Upgrade to the latest version even if it is a pre-release
    pip install --pre --upgrade robotframework
```

## 1.3.4 用源码安装

这种安装方法可以在所有系统和解释器环境下使用。从源码安装可能有一点可怕，但是过程其实是非常简单明了的。

**获取源码**

你通常可以下载`.tar.gz`格式的源码发布包来获取源码。在[PyPI](https://pypi.python.org/pypi/robotframework)上可以获取更新的包。
但是Robot Framework 2.8.1和更早的版本只能从旧的[Google Code](https://code.google.com/p/robotframework/downloads/list?can=1)下载页面获取了。
一旦你下载了源码包以后，你就需要解压到某个路径，完成后，创建了目录为`robotframework-<verion>`。这个目录包含了安装的源码和脚本。

另一种获取源码的方式是直接从[Github](https://github.com/robotframework/robotframework)仓库中克隆该项目。
默认情况下，获取的是最新的代码, 但是你可以很容易切换到不同的发布版本和Tag标签。

**安装**

Robot Framework源码安装是采用标准的Python `setup.py`安装脚本。安装脚本在解压后的源码目录中, 你可以在命令行下使用任意一种解释器进行安装：

```
    python setup.py install 
    jython setup.py install
    ipy setup.py install
```

`setup.py`安装脚本允许接收多个参数。例如，安装到非默认路径不需要管理员权限。它也可以用于创建不同的发行包。 
执行`python setup.py  --help`来获取更多信息。

## 1.3.5 独立的JAR发行包

Robot Framework也提供了独立的JAR发行包，包含了Jython和Robot Framework，仅仅依赖Java环境。这种方式不需要进行安装，只需要一个包就可以了。
但是一个缺点就是在通常的Python解释器下不能工作。

这个包的命名是`robotframework-<version>.jar`, 在[Maven](http://search.maven.org/#search%7Cga%7C1%7Ca%3Arobotframework)中央仓库上可以获得。
下载完包以后，你可以以下的方式执行测试：

```
    java -jar robotframework-3.0.jar mytests.robot
    java -jar robotframework-3.0.jar --variable name:value mytests.robot
```

如果你想使用后处理命令或者使用其他内置工具的话，你需要将命令名作为第一个参数传递给JAR文件：

```
    java -jar robotframework-3.0.jar rebot output.xml
    java -jar robotframework-3.0.jar libdoc MyLibrary list
```

可以通过不带任何参数执行JAR文件来获取更多信息。

除了Python标准库和Robot Framework模块外，这个独立的JAR发行包从2.9.2版本开始，也包含了依赖项PyYAML来处理yaml格式的变量文件。

## 1.3.6 手动安装

如果你不想采用任何自动化的方式来安装Robot Framework的话，你也可以按照以下步骤来手动安装：

* 获取源码, 所有的源码在`robot`目录下, 如果你从源码发布或者版本控制系统检出的话，你可以从`src`目录找到源码, 你也可以从早先安装路径制获取源码。
* 拷贝源码到你想要的路径。
* 按照自己的方式执行测试。

## 1.3.7 验证安装

在成功安装以后，可以通过在命令行中终端上用`--version`选项来运行执行器去获取Robot Framework版本以及Python解释器版本：

```
    $robot --version
    Robot Framework 3.0 (Python 2.7.10 on linux2)

    $rebot --version
    Rebot 3.0 (Python 2.7.10 on linux2)
```

如果运行执行器脚本失败的话，提示错误信息是命令没找到或者不识别的话，最好先检查一下PATH环境变量是否配置正确。如果PATH没有问题的话，
再去阅读相关章节的说明, 如果还是没有解决的话，可以通过因特网或者是robotframework-users邮件组等方式来寻求帮助。

## 1.3.8 卸载

最简单的卸载Robot Framework的方式就是使用pip命令:

```
    pip uninstall robotframework
```

用pip卸载的好处就是即使你是用源码安装的，也同样可以卸载。如果你没有安装pip的话，或者是手动安装到自定义的路径，那么你需要知道你的文件安装到哪里，然后手动删除它们。

如果你在PATH环境变量中设置了相关路径，你需要撤销这些操作。

## 1.3.9 升级

如果你使用pip的话，升级新版本，可以使用参数`--upgrade`选项或者是指定的版本:

```
    pip install --upgrade robotframework
    pip install -U robotframework
    pip install robotframework==2.9.2
```

但使用pip安装时，它会自动卸载先前安装的版本。如果你是源码安装的话，覆盖安装通常也是安全的。
如若遇到了问题，请再安装之前先卸载旧的版本可能会解决。

当升级Robot Framework时，可能会遇到新版本对旧版本不兼容的情况，从而影响到已存在的测试或者是测试设施。但是这些问题在临近的小版本之间影响微乎其微，
如2.8.7或2.9.2, 而在大版本之间如2.9和3.0之间可能会比较常见。向后不兼容的影响以及不推荐的特性在发行说明中已经详细说明了。
在升级到新的里程碑版本的时候，了解它的新特性和一些改变会是很好的方式。

## 1.3.10 执行Robot Framework

**使用`robot`和`rebot`脚本**

从Robot Framework 3.0开始，用脚本命令`robot`来执行测试,用`rebot`脚本来执行结果的后处理。

```
    robot tests.robot
    rebot output.xml
```
这两个脚本命令都是随着Robot Framework安装程序一起被安装的。如果PATH配置正确的话，可以直接从命令行终端上执行。
它们是用Python实现的，但是在Windows上，它们是批处理脚本。

旧的Robot Framework版本不含`robot`命令，而`rebot`命令只在Python解释器中。
在其他解释器中替代的是`pybot`，`jybot`, `ipybot`来执行测试, `jyrebot`, `ipyrebot`来处理结果。这些脚本目前仍然可以运行，但是不推荐使用，不排除在将来会将它们移除。

**执行已安装的`robot`模块**

还有一种替代的方式运行测试是用Python的` -m command line option`命令行方式直接执行`robot`模块或者其子模块`robot.run`。
这种方式在多版本Python并存的环境中很有用。

```
    python -m robot tests.robot
    python3 -m robot.run tests.robot
    jython -m robot tests.robot
    /opt/jython/jython -m robot tests.robot
```

对`python -m robot`方式的支持是Robot Framework 3.0的新功能，在旧的版本中只支持`python -m robot.run`。后者必须在Python 2.6的环境下运行。

结果后处理使用相同的方式。模块改为`robot.rebot`。

```
    python -m robot.rebot output.xml
```

**执行已安装的`robot`目录**

如果你知道robot安装目录的话，你可以在安装目录中直接执行`robot`命令或者是`run.py`文件:

```
    python path/to/robot/ tests.robot
    jython path/to/robot/run.py tests.robot
```

执行`robot`目录是Robot Framework 3.0的新功能。旧版本功能仅仅支持执行`robot/run.py`文件。

结果后处理使用同样的方式`robot/rebot.py`执行:

```
    python path/to/robot/rebot.py output.xml
```

如果你是手动安装的，这种执行方式非常方便。
