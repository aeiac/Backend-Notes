# 一、Liunx知识点

​	Liunx系有上百种不同的发行版，主要包括基于社区开发和商业开发两种类型，具体如下：

- 基于社区开发的发行版。Debian、Arch Linux、Ubuntu、Fedora、CentOS、openSUSE、Mindriva、Gentoo、Slackware。
- 基于商业开发的发行版。Red Hat Enterprise Linux、SUSE、Oracle Linux。

## 1.1、基础命令20条

1. **cd：**切换当前目录。
2. **ls：**列出目录中所有文件和子目录。
3. **mkdir：**创建新目录`mkdir fileName`。
4. **rm：**删除目录和文件，删除fileName目录命令，具体如下：
   - `rm -rf fileName` 
   - -r代表递归删除目录下所有文件，-f强制删除。
5. **cp：**复制文件或目录，将mydlr目录复制到home目录下命令，具体如下：
   - `cp -rp ./mydlr /home`；
   - -r代表递归复制目录下文件，-p代码不改变原有属性，如已读、只读、权限等。
6. **mv**：移动文件、或重命名
   - `mv file ./home`；
   - 将file文件移动到home目录下；
   - `mv file file_back`；
   - 将file文件重命名file_back。
7. **cat：**把文件内容打印到终端，具体如下：
   - `cat error.log`
8. **tail：**输出文件内容的末尾到终端，通常搭配-f和-n使用，具体如下：
   - `tail -f error.log`；
   - <u>**实时输出**</u>内容，是排查日志BUG的最常用指令之一；
   - `tail -n 500 error.log`；
   - 输出error.log文件最后500行。
9. **head**：输出内容文件的开头几行，具体如下：
   - `head -n 40 error.log` ；
   - 输出文件的开头前40行。
10. **grep：**筛选符合某种文本的内容，通常搭配管道符“|”，具体如下：
    - `cat error.log |grep 2024-05-11`；
    - 查询文件中包含2024-05-11的信息。
11. **find：**查找文件和目录，具体如下：
    - `find / -name error.log`；
    - 查找 / 根目录下 拥有error.log 文件名。
12. **ps ：**查看进程信息，具体如下：
    - `ps -ef`
    - -e代表显示所有进程，-f代表使用详细的进程信息。
13. **pwd：**显示当前工作台目录的路径。
14. **chmod：**更改文件或目录的权限，具体如下：
    - `chmod 777 text.png`；
15. **top：**实时显示系统中各个进程的资源占用情况。
16. **vi：**对文件进行编辑。
17. **diff：**比较文件差异，具体如下：
    - `diff t1.log t2.log`；
    - 比较t1.log和t2.log文件内容的差异。
18. **sh：**执行shell脚本文件。
19. **clear：**清屏。
20. **tree：**查看内存

