# 6.2 所有命令行选项

附录列出了在执行测试用例和后处理输出时的所有命令行参数选项。同时也列出了影响执行和后处理过程中的环境变量。


## 6.2.1 测试执行的命令行选项

|  选项          | 选项全名  |  介绍   | 
|:-------------|:-------------:|--------:|
| -N | --name <name> | 设置顶层测试套件的名字 |
| -D | --doc <document> | 设置顶层测试套件的文档内容 |
| -M | --metadata <name:value> | 设置顶层测试套件的元数据 |
| -G | --settag <tag> | 设置所有执行中测试用例的tag |
| -t | --test <name> | 根据名称选择指定测试用例 |
| -s | --suite <name> | 根据名称选择指定测试套件 |
| -R | --rerunfailed <file> | 根据早先产生的output文件，选择失败的测试重新执行一遍 |
|    | --runfailed <file> | 从Robot Framework 2.8.4开始不再推荐使用，用`--rerunfailed`代替 |
| -i | --include <tag> | 根据tag选择指定测试用例 |
| -e | --exclude <tag> | 根据tag选择指定测试用例 |
| -c | --critical <tag> | 设置带指定tag的测试为critical |
| -n | --noncritical <tag> | 设置带指定tag的测试为非critical |
| -v | --variable <name:value> | 设置独立的变量 |
| -V | --variablefile <path:args> | 使用变量文件来设置变量 |
| -d | --outputdir <dir> | 定义创建output文件的目录 |
| -o | --output <file> | 设置生成output文件的路径 |
| -l | --log <file> | 设置生成log文件的路径 |
| -r | --report <file> | 设置生成report文件的路径 |
| -x | --xunit <file> | 设置生成xUnit兼容结果文件的路径 |
|    | --xunitskipnoncritical | 标志在xUnit兼容结果文件中跳过非critical的测试用例 |
| -b | --debugfile <file> | 设置执行期间的debug文件路径 |
| -T | --timestampoutputs | 添加时间戳到所有的output文件 |
|    | --splitlog |


## 6.2.2 后处理输出的命令行选项

## 6.2.3 执行和后处理时的环境变量