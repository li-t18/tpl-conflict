# conflict

## 问题背景

天才少年爱迪生顺利地进入了华大学。开学时，他迎来了紧张而刺激的选课阶段。由于华大学人均单身十年的手速，爱迪生感觉到强烈的抢课压力。爱迪生是现充，手速不过关，他就想，如果自己能够快速过滤无效课程，是不是就可以弥补这个缺陷了，于是他找到了你。

## 问题描述

你需要修改目录下的conflict.py，实现如下功能：

1. 从命令行第二个参数代表的文件中，读入两个数字n和m，分别表示已选课数目以及候选课数目
2. 在该文件接下来的n+m行中，课程会被逐行读入，格式参见样例（example.in,），对于已选课与侯选课，已选课的各个域表示为“选课属性 课程号 课程名 课序号 上课时间 任课教师 学分 是否二级选课”，候选课的各个域表示为“课程号 课序号 课程名 课余量 队列人数 上课时间 任课教师 课程特色 选课文字说明 开课系 是否二级选课”
3. 对于每个课程，其开课时间与持续周数可能不同，你需要找到候选课中与已经选课**时间上**冲突的课（不考虑其他冲突类型），并将候选课名与冲突课名及相关信息输出到命令行第三个参数代表的文件中，格式参见样例。值得注意的是，冲突的课之前使用的是tab字符，并非普通空格。

需要注意的是，如果有多个课与一节候选课冲突，其输出顺序按照课程号排序。候选课冲突列表的输出顺序与候选课的输入顺序相同。

由于现有选课系统的文字复杂较高，为了简便，我们自行生成数据，生成器为 gen.py，**建议**同学们在写程序时参考，以便处理所有可能的情况；也建议自行生成数据来检测自己的程序是否正确。

需要注意的是，生成的数据可能不合理，比如生成的两个时间“1-3(全周),1-3(前八周)”相互重叠，这是可以接受的，我们只需要考虑是否有重叠；同时已选课中如果出现了时间重叠的情况，我们也接受。

你可能需要通过使用

```python3
python3 conflict.py input_file output_file
```
来运行你的程序。对于gen.py，其运行方式请自行阅读代码来发现。

本次主要考察大家的**文档阅读能力、搜索引擎使用以及代码阅读能力**，可以讨论和查阅资料，不可抄袭。在此，我们提醒几个可能没有教过的知识点，需要同学们通过搜索引擎或文档去了解：传参，文件读写，随机数生成等。

## 样例与评分

我们在 `data` 目录下提供了八组数据，分别对应不同的情况和数据量大小。和之前的题目一样，你可以通过 `python3 grade.py` 来进行一次的本地测评。

这次会考验你代码编写的效率，如果代码运行的不够快，可能不到黑盒的满分。本题设置了 1s 的时间限制，如果超过了这个时间，评测程序会提示你超时；对于未超时的数据，它会输出你的代码的实际用时。

最终评分以在助教机器上运行的时间为准。所用电脑的 CPU 为 Intel Core i7-8750H。

最终分数构成为：

* 黑盒 80 分：共 8 个测例，每个 10 分
* 白盒 20 分：代码风格（评测不参考pylint，推荐大家自用pylint），Git 使用 20 分（包括恰当注释（一句话一个注释者，倒扣）、合理命名、提交日志等）

助教以 deadline 前 GitHub 上最后一次提交为准进行评测。