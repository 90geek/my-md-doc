1、提交Topologies

命令格式：storm jar 【jar路径】 【拓扑包名.拓扑类名】【stormIP地址】【storm端口】【拓扑名称】【参数】
eg：
storm jar /home/storm/storm-starter.jar storm.starter.WordCountTopology wordcountTop;
storm jar /home/storm/storm-starter.jar storm.starter.WordCountTopology wordcountTop 192.168.2.191 40000 analyse;
#提交storm-starter.jar到远程集群，并启动wordcountTop拓扑。

[root@master storm-0.8.1]# bin/storm jar ulib/taosy_analyse_fat.jar  com.tongrong.taoshiye.shop.Si
ngle.SingleTopology analyse-taobao-shop-single
**说明：**
[root@master storm-0.8.1]#  storm的home目录
bin/storm jar ->执行jar命令
ulib/taosy_analyse_fat.jar ->storm jar包的存放位置
com.tongrong.taoshiye.shop.Single.SingleTopology ->拓扑入口类，main函数
analyse-taobao-shop-single ->main函数参数


2、显示当前的Topologies列表

命令格式:storm list

显示如下：
Topology_name | Status | Num_tasks | Num_workers | Uptime_secs
| -------------- | ------------- | ----------- | -------------- | -----------|
wordcount     |    ACTIVE  |      26      |                 3     |            1204740 
data                 |  ACTIVE    |    26        |               1       |          1205136 
exclamation   |   KILLED    |     0         |              0        |         1226857


3、启动nimbus后台程序
命令格式：storm nimbus
启动supervisor后台程序
 命令格式：storm supervisor

4、启动drpc服务
命令格式：storm drpc

5、启动ui服务
命令格式：storm ui

6、启动REPL
REPL — read-evaluate-print-loop。
虽然clojure可以作为一种脚本语言内嵌在java里面，但是它的首选编程方式是使用REPL，这是一个简单的命令行接口，使用它你可以输入你的命令，执行，然后查看结果， 你可以以下面这个命令来启动REPL：
命令格式：storm repl

REPL：“读取-求值-输出”循环（英语：Read-Eval-Print Loop，简称REPL）是一个简单的，交互式的编程环境。这个词常常用于指代一个Lisp的交互式开发环境，但也能指代命令行的模式和例如 APL, BASIC, Clojure, F#, Haskell, J, Julia, Perl, PHP, Prolog, Python, R, Ruby, Scala, Smalltalk, Standard ML, Tcl,Javascript 这样的编程语言所拥有的类似的编程环境。这也被称做交互式顶层构件（interactive toplevel）。
“读入-求值-输出”循环 的名字来自于以下几个Lisp用来实现这种机制的内置函数：

读入函数接收一个来自于用户的表达式，将其解析成数据结构并存入内存。例如，用户可能会输入一个s-表达式　(+ 1 2 3)，这句活会被解析成一个包含四个元素的链表。
求值函数　负责处理内部的数据结构并对其求值。在Lisp中，求一个以函数名开头的ｓ－表达式意味着对接下来的参数调用那个函数。所以函数"+"被在参数1 2 3上调用，产生结果6。
输出函数接受求值结果，并呈现将其给用户。尽管当前的结果“6”并不具有复杂的格式，但如果是一个较为复杂的表达式，那么它将会被精心处理，以便于更方便地被理解。
REPL使得探索性的编程和调试更加便捷，因为“读取-求值-输出”循环通常会比经典的“编辑-编译-运行-调试”模式要更快。


7、打印本地配置
命令格式：storm localconfvalue 【配置参数关键字】
例如：storm localconfvalue storm.zookeeper.servers
根据指定参数打印本地配置的值。
8、打印远程配置
命令格式：storm remoteconfvalue 【配置参数关键字】
例如：storm remoteconfvalue storm.zookeeper.servers
根据指定参数打印远程配置的值。

9、执行Shell脚本
命令格式：storm shell resourcesdir command args

10、打印CLASSPATH
命令格式：storm classpath

11、显示版本号
命令格式: storm version

12、停止Topologies
命令格式：storm kill 【拓扑名称】
例如：storm kill wordcountTop  杀掉wordcountTop拓扑

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1MTM0NTQ0NTVdfQ==
-->