# cubic-backup
简单可靠的备份管理工具

# 使用方式
首先，将config.example.py复制为config.py，仿照里面的格式，写上自己实际的目录路径，格式为 缓存路径:库路径 。

缓存就是你的工作目录，库就是备份的文件所在的地方。

（请注意，在第一次启动程序前，库应该是空目录，并且用户永远不应该手工改变其中的内容）

其次，运行commit.py，进行第一次提交。

接下来，你可以随心所欲的删除缓存中的东西了。如果再次需要，可以去库中直接复制出来使用。

如果在缓存中新建或修改了什么文件的话，重新运行commit.py来提交这些变更。

# 优势
这个备份工具相比于Windows的文件历史记录功能，最大的优势是它采用硬链接方式，使得相同文件只存储一次。用Windows文件历史记录时，如果你删掉了一个大文件，又从记录里重新提取出来，它会在历史记录中占用双倍的存储空间。如果重命名也会发生这样的情况。而cubic backup永远不会产生无用的磁盘空间消耗。

（注：Windows资源管理器可能会错误地显示库目录所占的磁盘空间，不要被误导。查看库目录中的.cubicpool这个文件夹的大小即可知道当前整个库的大小。）
