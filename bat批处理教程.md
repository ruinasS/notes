---
title: bat批处理教程
date: 2022-5-18 22:35:07
tab: 
---

bat批处理教程
==

# 0.批处理

**批处理(Batch)**，也称为批处理[脚本](https://baike.baidu.com/item/脚本)。顾名思义，批处理就是对某对象进行批量的处理，通常被认为是一种简化的[脚本语言](https://baike.baidu.com/item/脚本语言/1379708)，它应用于[DOS](https://baike.baidu.com/item/DOS)和Windows系统中。[批处理文件](https://baike.baidu.com/item/批处理文件/5363369)的扩展名为[bat](https://baike.baidu.com/item/bat/365230) 。比较常见的批处理包含两类：[DOS](https://baike.baidu.com/item/DOS)批处理和PS批处理。PS批处理是基于微软的强大的PowerShell的，用来[批量处理](https://baike.baidu.com/item/批量处理/4973973)一些任务的[脚本](https://baike.baidu.com/item/脚本/399)；而DOS批处理则是基于DOS命令的，用来自动地[批量](https://baike.baidu.com/item/批量)地执行DOS命令以实现特定操作的脚本。

注：这里是DOS批处理的粗浅学习，把常用的命令进行学习，以后有机会进行Power shell的学习

# 1.运行、自学、简易语句

## 1.1运行

<kbd>win</kbd>+<kbd>R</kbd>打开命令输入cmd启动命令提示符

![image-20220531144652513](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531144652513.png)

或者新建文件并将文件名后缀修改为：文件名.bat 或者 文件名.cmd 后编辑运行

![image-20220531144909203](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531144909203.png)

![image-20220531144945918](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531144945918.png)

![image-20220531144955826](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531144955826.png)



## 1.2学习方式

在命令行界面输入help即可查看其语句，使用help+空格+语句即可查看使用方式

![image-20220531145249269](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531145249269.png)

如清楚屏幕命令help+空格+<kbd>cls</kbd>

![image-20220531145322641](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531145322641.png)

也可以使用 语句+空格+/? 来进行 

除此以外参考网上文章学习，具体地址详见文末的参考资料

## 1.3简易语句

### 1.3.1 注释 REM

![image-20220531145723647](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531145723647.png)

REM为注释命令，一般用来给程序加上注解，该命令后的内容不被执行，但能回显。
其次, :: 也可以起到rem 的注释作用, 而且更简洁有效; 但有两点需要注意：
第一, 任何以冒号:开头的字符行, 在批处理中都被视作标号, 而直接忽略其后的所有内容。
有效标号：冒号后紧跟一个以字母数字开头的字符串，goto语句可以识别。
无效标号：冒号后紧跟一个非字母数字的一个特殊符号，goto无法识别的标号，可以起到注释作用，所以 :: 常被用作注释符号，其实 :+ 也可起注释作用。
第 二, 与rem 不同的是, ::后的字符行在执行时不会回显, 无论是否用echo on打开命令行回显状态, 因为命令解释器不认为他是一个有效的命令行, 就此点来看, rem 在某些场合下将比 :: 更为适用; 另外, rem 可以用于 config.sys 文件中。

### 1.3.2 清除屏幕 CLS

清除屏幕

### 1.3.3 CMD

打开另一个 Windows 命令解释程序窗口。

### 1.3.4 ECHO

```
@字符放在命令前将关闭该命令回显，无论此时echo是否为打开状态。
echo命令的作用列举如下：
（1）打开回显或关闭回显功能
    格式:echo [{ on|off }]
    如果想关闭“ECHO OFF”命令行自身的显示，则需要在该命令行前加上“@”。
（2）显示当前ECHO设置状态
    格式:echo
（3）输出提示信息 
    格式：ECHO 信息内容


上述是ECHO命令常见的三种用法，也是大家熟悉和会用的，但作为DOS命令淘金者你还应该知道下面的技巧：
（4）关闭DOS命令提示符 
    在DOS提示符状态下键入ECHO OFF，能够关闭DOS提示符的显示使屏幕只留下光标，直至键入ECHO ON，提示符才会重新出现。
（5）输出空行，即相当于输入一个回车 
    格式：ECHO．
    值得注意的是命令行中的“．”要紧跟在ECHO后面中间不能有空格，否则“．”将被当作提示信息输出到屏幕。另外“．”可以用，：；”／[\]＋等任一符号替代。
    命令ECHO．输出的回车，经DOS管道转向可以作为其它命令的输入，比如echo.|time即相当于在TIME命令执行后给出一个回车。所以执行时系统会在显示当前时间后，自动返回到DOS提示符状态
（6）答复命令中的提问 
    格式：ECHO 答复语|命令文件名
上述格式可以用于简化一些需要人机对话的命令（如：CHKDSK／F；FORMAT Drive:；del *.*）的操作，它是通过DOS管道命令把ECHO命令输出的预置答复语作为人机对话命令的输入。下面的例子就相当于在调用的命令出现人机对话时输入“Y”回车：
C:>ECHO Y|CHKDSK/F
C:>ECHO Y|DEL A :*.*
（7）建立新文件或增加文件内容 
格式：ECHO 文件内容>文件名
      ECHO 文件内容>>文件名
例如：
C:>ECHO @ECHO OFF>AUTOEXEC.BAT建立自动批处理文件
C:>ECHO C:\CPAV\BOOTSAFE>>AUTOEXEC.BAT向自动批处理文件中追加内容
C:>TYPE AUTOEXEC.BAT显示该自动批处理文件
@ECHO OFF
C:\CPAV\BOOTSAFE
（8）向打印机输出打印内容或打印控制码 
格式：ECHO 打印机控制码>;PRN
      ECHO 打印内容>;PRN
下面的例子是向M－1724打印机输入打印控制码。＜Alt＞156是按住Alt键在小键盘键入156，类似情况依此类推：
C:>ECHO +156+42+116>;PRN（输入下划线命令FS＊t）
C:>ECHO [email=+155@]+155@>;PRN[/email]（输入初始化命令ESC@）
C:>ECHO.>;PRN（换行）
（9）使喇叭鸣响 
C:>ECHO ^G
“^G”是在dos窗口中用Ctrl＋G或Alt＋007输入，输入多个^G可以产生多声鸣响。使用方法是直接将其加入批处理文件中或做成批处理文件调用。
```

### 1.3.5 PAUSE

```
暂停批处理程序，并显示以下消息:
    请按任意键继续. . .

要显示其他提示语，可以这样用：
Echo 其他提示语 & pause > nul
```

例：

![image-20220531182438077](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531182438077.png)

# 2.文件目录磁盘操作

## 2.1 ASSOC

```
显示或修改文件扩展名关联

ASSOC [.ext[=[fileType]]]

  .ext      指定跟文件类型关联的文件扩展名
  fileType  指定跟文件扩展名关联的文件类型

键入 ASSOC 而不带参数，显示当前文件关联。如果只用文件扩展
名调用 ASSOC，则显示那个文件扩展名的当前文件关联。如果不为
文件类型指定任何参数，命令会删除文件扩展名的关联。
```

例：

![image-20220531150459092](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531150459092.png)

![image-20220531150519779](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531150519779.png)

## 2.2 ATTRIB

显示或更改文件属性。

    ATTRIB [+R | -R] [+A | -A] [+S | -S] [+H | -H] [+O | -O] [+I | -I] [+X | -X] [+P | -P] [+U | -U]
       [drive:][path][filename] [/S [/D]] [/L]
    
    +	设置属性。
    -	清除属性。
    R   只读文件属性。
    A   存档文件属性。
    S   系统文件属性。
    H   隐藏文件属性。
    O   脱机属性。
    I   无内容索引文件属性。
      X   无清理文件属性。
    V   完整性属性。
    P   固定属性。
    U   非固定属性。
    [drive:][path][filename]
      指定属性要处理的文件。
    /S  处理当前文件夹及其所有子文件夹中
      的匹配文件。
    /D  也处理文件夹。
    /L  处理符号链接和
      符号链接目标的属性

例：

![image-20220531150737005](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531150737005.png)

![image-20220531151021182](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531151021182.png)

![image-20220531151036127](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531151036127.png)

## 2.3 CD/CHDIR
```
显示当前目录名或改变当前目录。


CHDIR [/D] [drive:][path]
CHDIR [..]
CD [/D] [drive:][path]
CD [..]

  ..   指定要改成父目录。

键入 CD drive: 显示指定驱动器中的当前目录。
不带参数只键入 CD，则显示当前驱动器和目录。

使用 /D 开关，除了改变驱动器的当前目录之外，
还可改变当前驱动器。

如果命令扩展被启用，CHDIR 会如下改变:

当前的目录字符串会被转换成使用磁盘名上的大小写。所以，
如果磁盘上的大小写如此，CD C:\TEMP 会将当前目录设为
C:\Temp。

CHDIR 命令不把空格当作分隔符，因此有可能将目录名改为一个
带有空格但不带有引号的子目录名。例如:

     cd \winnt\profiles\username\programs\start menu

与下列相同:

     cd "\winnt\profiles\username\programs\start menu"

在扩展停用的情况下，你必须键入以上命令。
```

例：

![image-20220531152243687](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531152243687.png)

## 2.4 CHKDSK

```
检查磁盘并显示状态报告。

CHKDSK [volume[[path]filename]]] [/F] [/V] [/R] [/X] [/I] [/C] [/L[:size]] [/B] [/scan] [/spotfix]

  volume              指定驱动器号(后面跟一个冒号)、
                      装入点或卷名。
  filename            仅 FAT/FAT32: 指定要检查
                      碎片的文件。
  /F                  修复磁盘上的错误。
  /V                  在 FAT/FAT32 上: 显示磁盘上每个文件的
                      完整路径和名称。
                  在 NTFS 上: 显示清理消息(如果有)。
  /R                  查找坏扇区并恢复可读信息
                      (未指定 /scan 时，隐含 /F)。
  /L:size             仅 NTFS: 将日志文件大小更改为指定
                      的 KB 数。如果未指定大小，则显示
                      当前大小。
  /X                  如果必要，则先强制卸除卷。
                       该卷的所有打开的句柄都将无效
                      (隐含 /F)。
  /I                  仅 NTFS: 对索引项进行强度较小的
                      检查。
  /C                  仅 NTFS: 跳过文件夹结构内的
                      循环检查。
  /B                  仅 NTFS: 重新评估该卷上的坏簇
                      (隐含 /R)
  /scan               仅 NTFS: 在卷上运行联机扫描
  /forceofflinefix    仅 NTFS: (必须与 "/scan" 一起使用)
                      跳过所有联机修复；找到的所有故障都
                      排队等待脱机修复(即 "chkdsk /spotfix")。
  /perf               仅 NTFS: (必须与 "/scan" 一起使用)
                      使用更多系统资源尽快完成
                      扫描。这可能会对系统中运行的其他任务的性能
                      造成负面影响。
  /spotfix            仅 NTFS: 在卷上运行点修复
  /sdcleanup          仅 NTFS: 回收不需要的安全描述符
                      数据(隐含 /F)。
  /offlinescanandfix  在卷上运行脱机扫描并进行修复。
  /freeorphanedchains 仅 FAT/FAT32/exFAT: 释放所有孤立的簇链
                      而不恢复其内容。
  /markclean          仅 FAT/FAT32/exFAT: 如果未检测到损坏，则将卷
                      标记为干净，即使未指定 /F 也是如此。

/I 或 /C 开关通过跳过对卷的某些检查，
来减少运行 Chkdsk 所需的时间。
```

## 2.5 CHKNTFS

```
启动时显示或修改磁盘检查。

CHKNTFS volume [...]
CHKNTFS /D
CHKNTFS /T[:time]
CHKNTFS /X volume [...]
CHKNTFS /C volume [...]

  volume         指定驱动器号(后面跟一个冒号)、装入点或卷名。
  /D             将计算机还原为默认行为；
                 启动时检查所有驱动器，并对有问题的驱动器运行 chkdsk。
  /T:time        将 AUTOCHK 初始递减计数时间
                 更改为指定的时间，单位为秒。
                 如果没有指定时间，则显示当前设置。
  /X             将驱动器排除在启动时检查范围之外。被排除的驱动器在命令调用之间不会
                 累计。
  /C             安排驱动器在启动时检查；
                 如果驱动器有问题，则运行 chkdsk。

如果未指定开关，CHKNTFS 将显示指定的驱动器是否有问题
或者是否计划在下一次重新启动时执行检查。
```

## 2.6 COLOR

```
启动时显示或修改磁盘检查。

CHKNTFS volume [...]
CHKNTFS /D
CHKNTFS /T[:time]
CHKNTFS /X volume [...]
CHKNTFS /C volume [...]

  volume         指定驱动器号(后面跟一个冒号)、装入点或卷名。
  /D             将计算机还原为默认行为；
                 启动时检查所有驱动器，并对有问题的驱动器运行 chkdsk。
  /T:time        将 AUTOCHK 初始递减计数时间
                 更改为指定的时间，单位为秒。
                 如果没有指定时间，则显示当前设置。
  /X             将驱动器排除在启动时检查范围之外。被排除的驱动器在命令调用之间不会
                 累计。
  /C             安排驱动器在启动时检查；
                 如果驱动器有问题，则运行 chkdsk。

如果未指定开关，CHKNTFS 将显示指定的驱动器是否有问题
或者是否计划在下一次重新启动时执行检查。

C:\Users\RUINA>help color
设置默认的控制台前景和背景颜色。

COLOR [attr]

  attr        指定控制台输出的颜色属性。

颜色属性由两个十六进制数字指定 -- 第一个
对应于背景，第二个对应于前景。每个数字
可以为以下任何值:

    0 = 黑色       8 = 灰色
    1 = 蓝色       9 = 淡蓝色
    2 = 绿色       A = 淡绿色
    3 = 浅绿色     B = 淡浅绿色
    4 = 红色       C = 淡红色
    5 = 紫色       D = 淡紫色
    6 = 黄色       E = 淡黄色
    7 = 白色       F = 亮白色

如果没有给定任何参数，此命令会将颜色还原到 CMD.EXE 启动时
的颜色。这个值来自当前控制台
窗口、/T 命令行开关或 DefaultColor 注册表
值。

如果尝试使用相同的
前景和背景颜色来执行
 COLOR 命令，COLOR 命令会将 ERRORLEVEL 设置为 1。

示例: "COLOR fc" 在亮白色上产生淡红色
```

例：

![image-20220531153131635](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531153131635.png)

## 2.7 COMP

```
比较两个文件或两个文件集的内容。

COMP [data1] [data2] [/D] [/A] [/L] [/N=number] [/C] [/OFF[LINE]] [/M]

  data1      指定要比较的第一批文件的位置和名称。
  data2      指定要比较的第二批文件的位置和名称。
  /D         以十进制格式显示差异。
  /A         以 ASCII 字符显示差异。
  /L         显示不同的行数。
  /N=number  只比较每个文件中第一个指定的行数。
  /C         比较文件时 ASCII 字母不区分大小写。
  /OFF[LINE] 不要跳过带有脱机属性集的文件。
  /M         不提示比较更多文件。

要比较文件集，请在 data1 和 data2 参数中使用通配符。
```

## 2.8 COPY

```
将一份或多份文件复制到另一个位置。

COPY [/D] [/V] [/N] [/Y | /-Y] [/Z] [/L] [/A | /B ] source [/A | /B]
     [+ source [/A | /B] [+ ...]] [destination [/A | /B]]

  source       指定要复制的文件。
  /A           表示一个 ASCII 文本文件。
  /B           表示一个二进位文件。
  /D           允许解密要创建的目标文件
  destination  为新文件指定目录和/或文件名。
  /V           验证新文件写入是否正确。
  /N           复制带有非 8dot3 名称的文件时，
               尽可能使用短文件名。
  /Y           不使用确认是否要覆盖现有目标文件
               的提示。
  /-Y          使用确认是否要覆盖现有目标文件
               的提示。
  /Z           用可重新启动模式复制已联网的文件。
/L           如果源是符号链接，请将链接复制
               到目标而不是源链接指向的实际文件。

命令行开关 /Y 可以在 COPYCMD 环境变量中预先设定。
这可能会被命令行上的 /-Y 替代。除非 COPY
命令是在一个批处理脚本中执行的，默认值应为
在覆盖时进行提示。

要附加文件，请为目标指定一个文件，为源指定
数个文件(用通配符或 file1+file2+file3 格式)。
```

例：

![image-20220531154133051](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531154133051.png)

## 2.9 DEL/ERASE

```
DEL [/P] [/F] [/S] [/Q] [/A[[:]attributes]] names
ERASE [/P] [/F] [/S] [/Q] [/A[[:]attributes]] names

  names         指定一个或多个文件或者目录列表。
                通配符可用来删除多个文件。
                如果指定了一个目录，该目录中的所
                有文件都会被删除。

  /P            删除每一个文件之前提示确认。
  /F            强制删除只读文件。
  /S            删除所有子目录中的指定的文件。
  /Q            安静模式。删除全局通配符时，不要求确认
  /A            根据属性选择要删除的文件
  属性          R  只读文件            S  系统文件
                H  隐藏文件            A  准备存档的文件
                I  无内容索引文件      L  重新分析点
                O  脱机文件            -  表示“否”的前缀

如果命令扩展被启用，DEL 和 ERASE 更改如下:

/S 开关的显示句法会颠倒，即只显示已经
删除的文件，而不显示找不到的文件。
```

例：

![image-20220531154717281](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531154717281.png)

## 2.10 DIR

```
显示目录中的文件和子目录列表。

DIR [drive:][path][filename] [/A[[:]attributes]] [/B] [/C] [/D] [/L] [/N]
  [/O[[:]sortorder]] [/P] [/Q] [/R] [/S] [/T[[:]timefield]] [/W] [/X] [/4]

  [drive:][path][filename]
              指定要列出的驱动器、目录和/或文件。

  /A          显示具有指定属性的文件。
  属性         D  目录                R  只读文件
               H  隐藏文件            A  准备存档的文件
               S  系统文件            I  无内容索引文件
               L  重新分析点          O  脱机文件
               -  表示“否”的前缀
  /B          使用空格式(没有标题信息或摘要)。
  /C          在文件大小中显示千位数分隔符。这是默认值。用 /-C 来
              禁用分隔符显示。
  /D          跟宽式相同，但文件是按栏分类列出的。
  /L          用小写。
  /N          新的长列表格式，其中文件名在最右边。
  /O          用分类顺序列出文件。
  排列顺序     N  按名称(字母顺序)     S  按大小(从小到大)
               E  按扩展名(字母顺序)   D  按日期/时间(从先到后)
               G  组目录优先           -  反转顺序的前缀
  /P          在每个信息屏幕后暂停。
  /Q          显示文件所有者。
  /R          显示文件的备用数据流。
  /S          显示指定目录和所有子目录中的文件。
  /T          控制显示或用来分类的时间字符域
  时间段      C  创建时间
              A  上次访问时间
              W  上次写入的时间
  /W          用宽列表格式。
  /X          显示为非 8dot3 文件名产生的短名称。格式是 /N 的格式，
              短名称插在长名称前面。如果没有短名称，在其位置则
              显示空白。
  /4          以四位数字显示年份

可以在 DIRCMD 环境变量中预先设定开关。通过添加前缀 - (破折号)
来替代预先设定的开关。例如，/-W。
```

## 2.11 EXIT

```
退出 CMD.EXE 程序(命令解释器)或当前批处理脚本。

EXIT [/B] [exitCode]

  /B          指定要退出当前批处理脚本而不是 CMD.EXE。如果从一个
              批处理脚本外执行，则会退出 CMD.EXE

  exitCode    指定一个数字号码。如果指定了 /B，将 ERRORLEVEL
              设成那个数字。如果退出 CMD.EXE，则用那个数字设置
              过程退出代码。
```

## 2.12 FC

```
比较两个文件或两个文件集并显示它们之间
的不同


FC [/A] [/C] [/L] [/LBn] [/N] [/OFF[LINE]] [/T] [/U] [/W] [/nnnn]
   [drive1:][path1]filename1 [drive2:][path2]filename2
FC /B [drive1:][path1]filename1 [drive2:][path2]filename2

  /A         只显示每个不同处的第一行和最后一行。
  /B         执行二进制比较。
  /C         不分大小写。
  /L         将文件作为 ASCII 文字比较。
  /LBn       将连续不匹配的最大值设置为指定
             的行数。
  /N         在 ASCII 比较上显示行数。
  /OFF[LINE] 不要跳过带有脱机属性集的文件。
  /T         不要将制表符扩充到空格。
  /U         将文件作为 UNICODE 文本文件比较。
  /W         为了比较而压缩空白(制表符和空格)。
  /nnnn      指定不匹配处后必须连续
             匹配的行数。
  [drive1:][path1]filename1
             指定要比较的第一个文件或第一个文件集。
  [drive2:][path2]filename2
             指定要比较的第二个文件或第二个文件集。
```

## 2.13 FIND

```
在文件中搜索字符串。

FIND [/V] [/C] [/N] [/I] [/OFF[LINE]] "string" [[drive:][path]filename[ ...]]

  /V         显示所有未包含指定字符串的行。
  /C         仅显示包含字符串的行数。
  /N         显示行号。
  /I         搜索字符串时忽略大小写。
  /OFF[LINE] 不要跳过具有脱机属性集的文件。
  "string" 指定要搜索的文本字符串。
  [drive:][path]filename
             指定要搜索的文件。

如果没有指定路径，FIND 将搜索在提示符处键入
的文本或者由另一命令产生的文本。
```

例：

test2.txt内容

![image-20220531160540745](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531160540745.png)

![image-20220531160618596](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531160618596.png)

## 2.14 FINDSTR

```
在文件中寻找字符串。

FINDSTR [/B] [/E] [/L] [/R] [/S] [/I] [/X] [/V] [/N] [/M] [/O] [/P] [/F:file]
        [/C:string] [/G:file] [/D:dir list] [/A:color attributes] [/OFF[LINE]]
        strings [[drive:][path]filename[ ...]]

  /B         在一行的开始配对模式。
  /E         在一行的结尾配对模式。
  /L         按字使用搜索字符串。
  /R         将搜索字符串作为一般表达式使用。
  /S         在当前目录和所有子目录中搜索匹配文件。
  /I         指定搜索不分大小写。
  /X         打印完全匹配的行。
  /V         只打印不包含匹配的行。
  /N         在匹配的每行前打印行数。
  /M         如果文件含有匹配项，只打印其文件名。
  /O         在每个匹配行前打印字符偏移量。
  /P         忽略有不可打印字符的文件。
  /OFF[LINE] 不跳过带有脱机属性集的文件。
  /A:attr    指定有十六进位数字的颜色属性。请见 "color /?"
  /F:file    从指定文件读文件列表 (/ 代表控制台)。
  /C:string  使用指定字符串作为文字搜索字符串。
  /G:file    从指定的文件获得搜索字符串。 (/ 代表控制台)。
  /D:dir     查找以分号为分隔符的目录列表
  strings    要查找的文字。
  [drive:][path]filename
             指定要查找的文件。

除非参数有 /C 前缀，请使用空格隔开搜索字符串。
例如: 'FINDSTR "hello there" x.y' 在文件 x.y 中寻找 "hello" 或
"there"。'FINDSTR /C:"hello there" x.y' 文件 x.y  寻找
"hello there"。

一般表达式的快速参考:
  .        通配符: 任何字符
  *        重复: 以前字符或类出现零或零以上次数
  ^        行位置: 行的开始
  $        行位置: 行的终点
  [class]  字符类: 任何在字符集中的字符
  [^class] 补字符类: 任何不在字符集中的字符
  [x-y]    范围: 在指定范围内的任何字符
  \x       Escape: 元字符 x 的文字用法
  \<xyz    字位置: 字的开始
  xyz\>    字位置: 字的结束
```

## 2.15 FORMAT

```
格式化磁盘以供 Windows 使用。

FORMAT volume [/FS:file-system] [/V:label] [/Q] [/L[:state]] [/A:size] [/C] [/I:state] [/X] [/P:passes] [/S:state]
FORMAT volume [/V:label] [/Q] [/F:size] [/P:passes]
FORMAT volume [/V:label] [/Q] [/T:tracks /N:sectors] [/P:passes]
FORMAT volume [/V:label] [/Q] [/P:passes]
FORMAT volume [/Q]

  volume          指定驱动器号(后面跟一个冒号)、
                  装入点或卷名。
  /FS:filesystem  指定文件系统类型(FAT、FAT32、exFAT、
                  NTFS、UDF、ReFS)。
  /V:label        指定卷标。
  /Q              执行快速格式化。请注意，此开关可替代 /P。
  /C              仅适于 NTFS: 默认情况下，将压缩在该新建卷上创建的
                  文件。
  /X              如果必要，请先强制卸除卷。该卷的所有打开句柄
                  不再有效。
  /R:revision     仅 UDF: 强制格式化为特定的 UDF 版本
                  (1.02、1.50、2.00、2.01、2.50)。
                  默认 修订版为 2.01。
  /D              仅适用于 UDF 2.50: 将复制元数据。
  /L[:state]      仅适用于 NTFS: 覆盖文件记录的默认大小。
                  默认情况下，非分层卷将使用较小的
                  文件记录格式化，分层卷将使用较大的
                  文件记录格式化。/L 和 /L:enable 会强制使用较大的文件记录
                  格式化，而 /L:disable 会强制使用较小的
                  文件记录格式化。
  /A:size         替代默认分配单元大小。强烈建议你在通常情况下使用
                  默认配置。
                  ReFS 支持 4096、64K。
                  NTFS 支持 512、1024、2048、4096、8192、16K、32K、64K、
                  128K、256K、512K、1M、2M。
                  FAT 支持 512、1024、2048、4096、8192、16K、32K、64K，
                  (128K、256K 用于大于 512 个字节的扇区)。
                  FAT32 支持 512、1024、2048、4096、8192、16K、32K、64K，
                  (128K、256K 用于大于 512 个字节的扇区)。
                  exFAT 支持 512、1024、2048、4096、8192、16K、32K、64K、
                  128K、256K、512K、1M、2M、4M、8M、16M、32M。

                  请注意，FAT 和 FAT32 文件系统
                  对卷上的群集数量施加以下限制:

                  FAT: 群集数量 <= 65526
                  FAT32: 65526 < 群集数量 < 4177918

                  如果判定使用的指定群集大小无法
                  满足以上需求，将立即
                  停止格式化。

                  大于 4096 的分配单元大小
                  不支持 NTFS 压缩。

  /F:size         指定要格式化的软盘大小(1.44)
  /T:tracks       为磁盘指定每面磁道数。
  /N:sectors      指定每条磁道的扇区数。
  /P:count        将卷上每个扇区清零。此后，该卷将被改写 "count" 次，
                  且每次使用不同的随机数。如果 "count" 为零，
                  则每个扇区清零后，不再进行改写。
                  如果已指定 /Q，则忽略此开关。
  /S:state        指定对短文件名的支持(enable、disable)
                  默认情况下禁用了短名称
  /TXF:state      指定 txf 已启用/已禁用(值分别为 enabled 和 disabled)
                   默认情况下，将启用 TxF
  /I:state        仅 ReFS: 指定是否应在新卷上
                  启用完整性。"state" 为 "enable" 或 "disable"
                  默认情况下，在支持数据冗余的存储上
                  启用完整性。
  /DAX[:state]    仅适用于 NTFS: 对此卷启用直接访问存储(DAX)
                  模式。在 DAX 模式下，可以通过内存总线
                  访问卷，从而大幅提升 IO 性能。仅当硬件
                  支持 DAX 时，才能使用 DAX 模式格式化卷。
                  State 可指定为 "enable" 或 "disable"。/可将 DAX 视
                  为 /DAX:enable。
  /LogSize[:size] 仅适用于 NTFS: 以千字节为单位指定 NTFS 日志文件的大小。
                  最小支持大小为 2MB，因此即使指定的大小
                  小于 2MB，也将产生 2MB 的日志文件。零表示
                  通常取决于卷大小的默认值。
  /NoRepairLogs   仅适用于 NTFS: 禁用 NTFS 修复日志。如果设置此标志
                  spotfix (即 chkdsk /spotfix)将不起作用。
```

## 2.16  FTYPE

```
显示或修改用在文件扩展名关联中的文件类型

FTYPE [fileType[=[openCommandString]]]

  fileType  指定要检查或改变的文件类型
  openCommandString 指定调用这类文件时要使用的开放式命令。

键入 FTYPE 而不带参数来显示当前有定义的开放式命令字符串的
文件类型。FTYPE 仅用一个文件类型启用时，它显示那个文件类
型目前的开放式命令字符串。如果不为开放式命令字符串指定，
FTYPE 命令将删除那个文件类型的开放式命令字符串。在一个
开放式命令字符串之内，命令字符串 %0 或 %1 被通过关联调用
的文件名所代替。%* 得到所有的参数，%2 得到第一个参数，
%3 得到第二个，等等。%~n 得到其余所有以 nth 参数打头的
参数；n 可以是从 2 到 9 的数字。例如:

    ASSOC .pl=PerlScript
    FTYPE PerlScript=perl.exe %1 %*

允许你启用以下 Perl 脚本:

    script.pl 1 2 3

如果不想键入扩展名，则键入以下字符串:

    set PATHEXT=.pl;%PATHEXT%

被启动的脚本如下:

    script 1 2 3
```

## 2.17 LABEL

```
创建、更改或删除磁盘的卷标。

LABEL [drive:][label]
LABEL [/MP] [volume] [label]

  drive:          指定驱动器号。
  label           指定卷标。
  /MP             指定卷应被视为装入点或卷名。
  volume          指定驱动器号(后面跟一个冒号)、装入点或卷名。
                  如果指定了卷名，/MP 标志则不必要。
```

## 2.18 MD/MKDIR

```
创建目录。

MKDIR [drive:]path
MD [drive:]path

如果命令扩展被启用，MKDIR 会如下改变:

如果需要，MKDIR 会在路径中创建中级目录。例如: 假设 \a 不
存在，那么:

    mkdir \a\b\c\d

与:

    mkdir \a
    chdir \a
    mkdir b
    chdir b
    mkdir c
    chdir c
    mkdir d

相同。如果扩展被停用，则需要键入 mkdir \a\b\c\d。
```

例：

![image-20220531161741999](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531161741999.png)

![image-20220531161804044](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531161804044.png)

## 2.19 PUSHD

```
保存当前目录以供 POPD 命令使用，然后改到指定的目录。

PUSHD [path | ..]

  path        指定要成为当前目录的目录。

如果命令扩展被启用，除了一般驱动器号和路径，PUSHD
命令还接受网络路径。如果指定了网络路径，PUSHD 将创建一个
指向指定网络资源的临时驱动器号，然后再用刚定义的驱动器
号更改当前的驱动器和目录。可以从 Z: 往下分配临时驱动器
号，使用找到的第一个没有用过的驱动器号。
```

## 2.20 RD/RMDIR

```
删除一个目录。

RMDIR [/S] [/Q] [drive:]path
RD [/S] [/Q] [drive:]path

    /S      除目录本身外，还将删除指定目录下的所有子目录和
            文件。用于删除目录树。

    /Q      安静模式，带 /S 删除目录树时不要求确认
```

例：

![image-20220531162555762](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531162555762.png)

## 2.21 RECOVER

```
从损坏的磁盘中恢复可读取的信息。

RECOVER [drive:][path]filename
在使用 RECOVER 命令之前，
请先参阅 Windows 帮助中的联机命令参考。
```

## 2.22 REN/RENAME

```
重命名文件。

RENAME [drive:][path]filename1 filename2.
REN [drive:][path]filename1 filename2.

请注意，你不能为目标文件指定新的驱动器或路径。
```

例：

![image-20220531162946177](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531162946177.png)

## 2.23 REPLACE

```
替换文件。

REPLACE [drive1:][path1]filename [drive2:][path2] [/A] [/P] [/R] [/W]
REPLACE [drive1:][path1]filename [drive2:][path2] [/P] [/R] [/S] [/W] [/U]

  [drive1:][path1]filename 指定源文件。
  [drive2:][path2]         指定要替换文件的目录。
  /A                       把新文件加入目标目录。不能和/S 或 /U 命令行开关搭配使用。
  /P                       替换文件或加入源文件之前会先提示你进行确认。
  /R                       替换只读文件以及未受保护的文件。
  /S                       替换目标目录中所有子目录的文件。不能与 /A 命令开关搭配使用。
  /W                       等你插入磁盘以后再运行。
  /U                       只会替换或更新比源文件日期早的文件。不能与 /A 命令行开关搭配使用。
```

## 2.24 TIME

```
显示或设置系统时间。

TIME [/T | time]

显示当前时间设置和输入新时间的提示，请键入
不带参数的 TIME。要保留现有时间，请按 Enter。

如果命令扩展被启用，TIME 命令会支持 /T 命令行开关；该命令行开关告诉
命令只输出当前时间，但不提示输入新时间。
```

例：

![image-20220531163507555](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531163507555.png)

## 2.25 TITLE/DATE

```
设置命令提示窗口的窗口标题。

TITLE [string]

  string       指定命令提示窗口的标题。
```

例：

![image-20220531164015649](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531164015649.png)

```
显示或设置日期。

DATE [/T | date]

显示当前日期设置和输入新日期的提示，请键入
不带参数的 DATE。要保留现有日期，请按 Enter。

如果命令扩展被启用，DATE 命令会支持 /T 开关；
该开关指示命令只输出当前日期，但不提示输入新日期。
```

## 2.26 TREE

```
以图形显示驱动器或路径的文件夹结构。

TREE [drive:][path] [/F] [/A]

   /F   显示每个文件夹中文件的名称。
   /A   使用 ASCII 字符，而不使用扩展字符。
```

## 2.27 TYPE

```
显示文本文件的内容。

TYPE [drive:][path]filename
```



## 2.28 VER

```
显示 Windows 版本。

VER
```

例：

![image-20220531164535668](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531164535668.png)

## 2.29 VERIFY

```
指示 cmd.exe 是否要验证文件是否已正确地写入磁盘。

VERIFY [ON | OFF]

要显示当前 VERIFY 设置，键入不带参数的 VERIFY。
```

例：

![image-20220531164654044](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531164654044.png)

## 2.30 VOL

```
显示磁盘卷标和序列号(如果存在)。

VOL [drive:]
```

例：

![image-20220531164840101](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220531164840101.png)

## 2.31 XCOPY

```
复制文件和目录树。

XCOPY source [destination] [/A | /M] [/D[:date]] [/P] [/S [/E]] [/V] [/W]
                           [/C] [/I] [/Q] [/F] [/L] [/G] [/H] [/R] [/T] [/U]
                           [/K] [/N] [/O] [/X] [/Y] [/-Y] [/Z] [/B] [/J]
                           [/EXCLUDE:file1[+file2][+file3]...] [/COMPRESS]

  source       指定要复制的文件。
  destination  指定新文件的位置和/或名称。
  /A           仅复制有存档属性集的文件，
               但不更改属性。
  /M           仅复制有存档属性集的文件，
               并关闭存档属性。
  /D:m-d-y     复制在指定日期或指定日期以后更改的文件。
               如果没有提供日期，则只复制
               源时间比目标时间新的文件。
  /EXCLUDE:file1[+file2][+file3]...
               指定含有字符串的文件列表。每个字符串
               在文件中应位于单独的一行。如果任何
               字符串与复制文件的绝对路径的任何部分相符，
               则排除复制该文件。例如，
               指定如 \obj\ 或 .obj 的字符串会分别
               排除目录 obj 下面的所有文件或带有
               .obj 扩展名的所有文件。
  /P           创建每个目标文件之前均进行提示。
  /S           复制目录和子目录，不包括空目录。
  /E           复制目录和子目录，包括空目录。
               与 /S /E 相同。可以用来修改 /T。
  /V           验证每个新文件的大小。
  /W           提示在复制前按键。
  /C           即使有错误，也继续复制。
  /I           如果目标不存在，且要复制多个文件，
               则假定目标必须是目录。
  /Q           复制时不显示文件名。
  /F           复制时显示完整的源文件名和目标文件名。
  /L           显示要复制的文件。
  /G           允许将加密文件复制到
               不支持加密的目标。
  /H           隐藏文件和系统文件也会复制。
  /R           覆盖只读文件。
  /T           创建目录结构，但不复制文件。不
               包括空目录或子目录。/T /E 包括
               空目录和子目录。
  /U           只复制已经存在于目标中的文件。
  /K           复制属性。一般的 Xcopy 会重置只读属性。
  /N           用生成的短名称复制。
  /O           复制文件所有权和 ACL 信息。
  /X           复制文件审核设置(隐含 /O)。
  /Y           取消提示以确认要覆盖
               现有目标文件。
  /-Y          触发提示，以确认要覆盖
               现有目标文件。
  /Z           在可重新启动模式下复制网络文件。
  /B           复制符号链接本身与链接目标。
  /J           复制时不使用缓冲的 I/O。推荐复制大文件时使用。
  /COMPRESS    如果适用，在传输期间请求网络
               压缩。

开关 /Y 可以预先在 COPYCMD 环境变量中设置。
这可能被命令行上的 /-Y 覆盖。
```

# 3.程序语句

## 3.1 **errorlevel**

程序返回码
echo %errorlevel%
每个命令运行结束，可以用这个命令行格式查看返回码
用于判断刚才的命令是否执行成功
默认值为0，一般命令执行出错会设 errorlevel 为1

## 3.2 GOTO

```
将 cmd.exe 定向到批处理程序中带标签的行。

GOTO label

  label   指定批处理程序中用作标签的文字字符串。

标签必须单独一行，并且以冒号打头。

如果命令扩展被启用，GOTO 会如下改变:

GOTO 命令现在接受目标标签 :EOF，这个标签将控制转移到当前
批脚本文件的结尾。不定义就退出批脚本文件，这是一个容易的
办法。有关能使该功能有用的 CALL 命令的扩展描述，请键入
CALL /?。
```

## 3.3 CALL

```
CALL命令可以在批处理执行过程中调用另一个批处理，当另一个批处理执行完后，再继续执行原来的批处理
CALL command
在批处理编程中，可以根据一定条件生成命令字符串，用call可以执行该字符串，见例子。
CALL [drive:][path]filename [batch-parameters]
调用的其它批处理程序。filename 参数必须具有 .bat 或 .cmd 扩展名。
CALL :label arguments
调用本文件内命令段，相当于子程序。被调用的命令段以标签:label开头
以命令goto :eof结尾。
另外，批脚本文本参数参照(%0、%1、等等)已如下改变:
     批脚本里的 %* 指出所有的参数(如 %1 %2 %3 %4 %5 ...)
     批参数(%n)的替代已被增强。您可以使用以下语法:（看不明白的直接运行后面的例子）
         %~1         - 删除引号(")，扩充 %1
         %~f1        - 将 %1 扩充到一个完全合格的路径名
         %~d1        - 仅将 %1 扩充到一个驱动器号
         %~p1        - 仅将 %1 扩充到一个路径
         %~n1        - 仅将 %1 扩充到一个文件名
         %~x1        - 仅将 %1 扩充到一个文件扩展名
         %~s1        - 扩充的路径指含有短名
         %~a1        - 将 %1 扩充到文件属性
         %~t1        - 将 %1 扩充到文件的日期/时间
         %~z1        - 将 %1 扩充到文件的大小
         %~$PATH : 1 - 查找列在 PATH 环境变量的目录，并将 %1
                       扩充到找到的第一个完全合格的名称。如果环境
                       变量名未被定义，或者没有找到文件，此组合键会
                       扩充到空字符串
    可以组合修定符来取得多重结果:
        %~dp1       - 只将 %1 扩展到驱动器号和路径
        %~nx1       - 只将 %1 扩展到文件名和扩展名
        %~dp$PATH:1 - 在列在 PATH 环境变量中的目录里查找 %1，
                       并扩展到找到的第一个文件的驱动器号和路径。
        %~ftza1     - 将 %1 扩展到类似 DIR 的输出行。
    在上面的例子中，%1 和 PATH 可以被其他有效数值替换。
%~ 语法被一个有效参数号码终止。%~ 修定符不能跟 %*使用
注意：参数扩充时不理会参数所代表的文件是否真实存在，均以当前目录进行扩展
要理解上面的知识，下面的例子很关键。
例：
@echo off
Echo 产生一个临时文件 > tmp.txt
Rem 下行先保存当前目录，再将c:\windows设为当前目录
pushd c:\windows
Call :sub tmp.txt
Rem 下行恢复前次的当前目录
Popd
Call :sub tmp.txt
pause
Del tmp.txt
exit
:sub
Echo 删除引号： %~1
Echo 扩充到路径： %~f1
Echo 扩充到一个驱动器号： %~d1
Echo 扩充到一个路径： %~p1 
Echo 扩充到一个文件名： %~n1
Echo 扩充到一个文件扩展名： %~x1
Echo 扩充的路径指含有短名： %~s1 
Echo 扩充到文件属性： %~a1 
Echo 扩充到文件的日期/时间： %~t1 
Echo 扩充到文件的大小： %~z1 
Echo 扩展到驱动器号和路径：%~dp1
Echo 扩展到文件名和扩展名：%~nx1
Echo 扩展到类似 DIR 的输出行：%~ftza1
Echo.
Goto :eof
例：
set aa=123456
set cmdstr=echo %aa%
call %cmdstr%
pause
本例中如果不用call，而直接运行%cmdstr%，将显示结果%aa%，而不是123456
```

## 3.4**pushd 和 popd**

```
切换当前目录
@echo off
c: & cd\ & md mp3       #在 C:\ 建立 mp3 文件夹
md d:\mp4               #在 D:\ 建立 mp4 文件夹
cd /d d:\mp4            #更改当前目录为 d:\mp4
pushd c:\mp3            #保存当前目录，并切换当前目录为 c:\mp3
popd                    #恢复当前目录为刚才保存的 d:\mp4
```

## 3.5 SET基础语法

```
显示、设置或删除 cmd.exe 环境变量。

SET [variable=[string]]

  variable  指定环境变量名。
  string    指定要指派给变量的一系列字符串。

要显示当前环境变量，键入不带参数的 SET。

set /p var = 提示语
```

**setlocal 与 变量延迟**

```
本条内容引用[英雄出品]的批处理教程：
要想进阶，变量延迟是必过的一关！所以这一部分希望你能认真看。
为了更好的说明问题，我们先引入一个例子。
例1:
@echo off
set a=4
set a=5 & echo %a%
pause
结果：4
解说：为什么是4而不是5呢？在echo之前明明已经把变量a的值改成5了？
让我们先了解一下批处理运行命令的机制：
批 处理读取命令时是按行读取的（另外例如for命令等，其后用一对圆括号闭合的所有语句也当作一行），在处理之前要完成必要的预处理工作，这其中就包括对该 行命令中的变量赋值。我们现在分析一下例1，批处理在运行到这句“set a=5 & echo %a%”之前，先把这一句整句读取并做了预处理——对变量a赋了值，那么%a%当然就是4了！（没有为什么，批处理就是这样做的。）
而为了能够感知环境变量的动态变化，批处理设计了变量延迟。简单来说，在读取了一条完整的语句之后，不立即对该行的变量赋值，而会在某个单条语句执行之前再进行赋值，也就是说“延迟”了对变量的赋值。
那么如何开启变量延迟呢？变量延迟又需要注意什么呢？举个例子说明一下：
例2:
@echo off
setlocal enabledelayedexpansion
set a=4
set a=5 & echo !a!
pause 
结果：5
解说：启动了变量延迟，得到了正确答案。变量延迟的启动语句是“setlocal enabledelayedexpansion”，并且变量要用一对叹号“!!”括起来（注意要用英文的叹号），否则就没有变量延迟的效果。
分析一下例2，首先“setlocal enabledelayedexpansion”开启变量延迟，然后“set a=4”先给变量a赋值为
4，“set a=5 & echo !a!”这句是给变量a赋值为5并输出（由于启动了变量延迟，所以批处理能够感知到动态变化，即不是先给该行变量赋值，而是在运行过程中给变量赋值，因此此时a的值就是5了）。
再举一个例子巩固一下。
例3:
@echo off
setlocal enabledelayedexpansion
for /l %%i in (1,1,5) do (
set a=%%i
echo !a!
)
pause
结果：
1
2
3
4
5
解说：本例开启了变量延迟并用“!!”将变量扩起来，因此得到我们预期的结果。如果不用变量延迟会出现什
么结果呢？结果是这样的：
ECHO 处于关闭状态。
ECHO 处于关闭状态。
ECHO 处于关闭状态。
ECHO 处于关闭状态。
ECHO 处于关闭状态。
即没有感知到for语句中的动态变化。
提示：在没有开启变量延迟的情况下，某条命令行中的变量改变，必须到下一条命令才能体现。这一点也可以加以利用，看例子。
例：交换两个变量的值，且不用中间变量
@echo off
::目的：交换两个变量的值，但是不使用临时变量
::Code by JM 2007-1-24 [email=CMD@XP]CMD@XP[/email]
::出处：http://www.cn-dos.net/forum/viewthread.php?tid=27078
set var1=abc
set var2=123
echo 交换前： var1=%var1% var2=%var2%
set var1=%var2%& set var2=%var1%
echo 交换后： var1=%var1% var2=%var2%
pause
```

**系统变量**
他们的值由系统将其根据事先定义的条件自动赋值,也就是这些变量系统已经给他们定义了值,
不需要我们来给他赋值,我们只需要调用

## 3.6 IF条件判断

```
执行批处理程序中的条件处理。

IF [NOT] ERRORLEVEL number command
IF [NOT] string1==string2 command
IF [NOT] EXIST filename command

  NOT               指定只有条件为 false 的情况下，Windows 才
                    应该执行该命令。

  ERRORLEVEL number 如果最后运行的程序返回一个等于或大于
                    指定数字的退出代码，指定条件为 true。

  string1==string2  如果指定的文字字符串匹配，指定条件为 true。

  EXIST filename    如果指定的文件名存在，指定条件为 true。

  command           如果符合条件，指定要执行的命令。如果指定的
                    条件为 FALSE，命令后可跟 ELSE 命令，该命令将
                    在 ELSE 关键字之后执行该命令。

ELSE 子句必须出现在同一行上的 IF 之后。例如:

    IF EXIST filename. (
        del filename.
    ) ELSE (
        echo filename. missing.
    )

由于 del 命令需要用新的一行终止，因此以下子句不会有效:

IF EXIST filename. del filename. ELSE echo filename. missing

由于 ELSE 命令必须与 IF 命令的尾端在同一行上，以下子句也
不会有效:

    IF EXIST filename. del filename.
    ELSE echo filename. missing

如果都放在同一行上，以下子句有效:

    IF EXIST filename. (del filename.) ELSE echo filename. missing

如果命令扩展被启用，IF 会如下改变:

    IF [/I] string1 compare-op string2 command
    IF CMDEXTVERSION number command
    IF DEFINED variable command

其中， compare-op 可以是:

    EQU - 等于
    NEQ - 不等于
    LSS - 小于
    LEQ - 小于或等于
    GTR - 大于
    GEQ - 大于或等于

而 /I 开关(如果指定)说明要进行的字符串比较不分大小写。
/I 开关可以用于 IF 的 string1==string2 的形式上。这些
比较都是通用的；原因是，如果 string1 和 string2 都是
由数字组成的，字符串会被转换成数字，进行数字比较。

CMDEXTVERSION 条件的作用跟 ERRORLEVEL 的一样，除了它
是在跟与命令扩展有关联的内部版本号比较。第一个版本
是 1。每次对命令扩展有相当大的增强时，版本号会增加一个。
命令扩展被停用时，CMDEXTVERSION 条件不是真的。

如果已定义环境变量，DEFINED 条件的作用跟 EXIST 的一样，
除了它取得一个环境变量，返回的结果是 true。

如果没有名为 ERRORLEVEL 的环境变量，%ERRORLEVEL%
会扩充为 ERROLEVEL 当前数值的字符串表达式；否则，你会得到
其数值。运行程序后，以下语句说明 ERRORLEVEL 的用法:

    goto answer%ERRORLEVEL%
    :answer0
    echo Program had return code 0
    :answer1
    echo Program had return code 1

你也可以使用以上的数字比较:

    IF %ERRORLEVEL% LEQ 1 goto okay

如果没有名为 CMDCMDLINE 的环境变量，%CMDCMDLINE%
将在 CMD.EXE 进行任何处理前扩充为传递给 CMD.EXE 的原始
命令行；否则，你会得到其数值。

如果没有名为 CMDEXTVERSION 的环境变量，
%CMDEXTVERSION% 会扩充为 CMDEXTVERSION 当前数值的
字串符表达式；否则，你会得到其数值。
```

## 3.7 特殊符号

**@ 命令行回显屏蔽符**

**% 批处理变量引导符**
这个百分号严格来说是算不上命令的，它只是批处理中的参数而已（多个%一起使用的情况除外，以后还将详细介绍）。
引用变量用%var%，调用程序外部参数用%1至%9等等
%0 %1 %2 %3 %4 %5 %6 %7 %8 %9 %*为命令行传递给批处理的参数
%0 批处理文件本身，包括完整的路径和扩展名
%1 第一个参数
%9 第九个参数
%* 从第一个参数开始的所有参数
参数%0具有特殊的功能，可以调用批处理自身，以达到批处理本身循环的目的，也可以复制文件自身等等。
例：最简单的复制文件自身的方法
copy %0 d:\wind.bat
小技巧：添加行内注释
%注释内容%（可以用作行内注释，不能出现重定向符号和管道符号）
为什么这样呢？此时“注释内容”其实被当作变量，其值是空的，故只起注释作用，不过这种用法容易出现语法错误，一般不用。

**>  重定向符**
输出重定向命令
DOS的标准输入输出通常是在标准设备键盘和显示器上进行的，利用重定向,可以方便地将输入输出改向磁盘文件或其它设备。其中: 
1.大于号“>”将命令发送到文件或设备，例如打印机>prn。使用大于号“>”时，有些命令输出(例如错误消息)不能重定向。
2.双大于号“>>”将命令输出添加到文件结尾而不删除文件中已有的信息。
3.小于号“<”从文件而不是键盘上获取命令所需的输入。
4.>&符号将输出从一个默认I/O流(stdout,stdin,stderr)重新定向到另一个默认I/O流。
例如，command >output_file 2>&1将处理command过程中的所有错误信息从屏幕重定向到标准文件输出中。

使用命令：echo hello >1.txt将建立文件1.txt，内容为”hello “（注意行尾有一空格）
使用命令：echo hello>1.txt将建立文件1.txt，内容为”hello“（注意行尾没有空格）

**>> 重定向符**
输出重定向命令
这个符号的作用和>有点类似，但他们的区别是>>是传递并在文件的末尾追加，而>是覆盖
用法同上
同样拿1.txt做例子
使用命令：
echo hello > 1.txt
echo world >>1.txt
这时候1.txt 内容如下:
hello
world

**<、>&、<& 重定向符**
<，输入重定向命令，从文件中读入命令输入，而不是从键盘中读入。
@echo off
echo 2005-05-01>temp.txt
date <temp.txt
del temp.txt
这样就可以不等待输入直接修改当前日期

\>&，将一个句柄的输出写入到另一个句柄的输入中。
<&，刚好和>&相反，从一个句柄读取输入并将其写入到另一个句柄输出中。
常用句柄：0、1、2，未定义句柄：3—9
1>nul 表示禁止输出正确的信息
2>nul 表示禁止输出错误信息。
其中的1与2都是代表某个数据流输入输出的地址（NT CMD 称之为句柄，MSDOS称之为设备）。
句柄0：标准输入stdin，键盘输入
句柄1：标准输出stdout，输出到命令提示符窗口（console，代码为CON）
句柄2：标准错误stderr，输出到命令提示符窗口（console，代码为CON）
其中的stdin可被<重定向，stdout可被>、>>重定向。
我们已经知道读取文本中的内容可以用for命令，但如果只需要读取第一行用for命令就有点麻烦。简单的办法如下:
@echo off
set /p str=<%0
echo %str%
pause
运行显示批处理文件自身的第一行：@echo off

**| 命令管道符**
格式：第一条命令 | 第二条命令 [| 第三条命令...]
将第一条命令的结果作为第二条命令的参数来使用，记得在unix中这种方式很常见。
例如：
dir c:\|find "txt"
以上命令是：查找C：\所有，并发现TXT字符串。
FIND的功能请用 FIND /? 自行查看
在不使format的自动格式化参数时，我是这样来自动格式化A盘的
echo y|format a: /s /q /v:system
用过format的都知道，再格盘时要输入y来确认是否格盘，这个命令前加上echo y并用|字符来将echo y的结果传给format命令
从而达到自动输入y的目的

**^ 转义字符**
^是对特殊符号<,>,&的前导字符，在命令中他将以上3个符号的特殊功能去掉，仅仅只把他们当成符号而不使用他们的特殊意义。
比如
echo test ^>1.txt
结果则是：test > 1.txt
他没有追加在1.txt里，呵呵。只是显示了出来
另外，此转义字符还可以用作续行符号。

**& 组合命令**
语法：第一条命令 & 第二条命令 [& 第三条命令...]
&、&&、||为组合命令，顾名思义，就是可以把多个命令组合起来当一个命令来执行。这在批处理脚本里是允许的，而且用的非常广泛。因为批处理认行不认命令数目。
这个符号允许在一行中使用2个以上不同的命令，当第一个命令执行失败了，也不影响后边的命令执行。
这里&两边的命令是顺序执行的，从前往后执行。
比如：
dir z:\ & dir y:\ & dir c:\
以上命令会连续显示z,y,c盘的内容，不理会该盘是否存在

**&& 组合命令**
语法：第一条命令 && 第二条命令 [&& 第三条命令...]
用这种方法可以同时执行多条命令，当碰到执行出错的命令后将不执行后面的命令，如果一直没有出错则一直执行完所有命令
这个命令和上边的类似，但区别是，第一个命令失败时，后边的命令也不会执行
dir z:\ && dir y:\ && dir c:\

**|| 组合命令**
语法：第一条命令 || 第二条命令 [|| 第三条命令...]
用这种方法可以同时执行多条命令，当一条命令失败后才执行第二条命令，当碰到执行正确的命令后将不执行后面的命令，如果没有出现正确的命令则一直执行完所有命令；

提示：组合命令和重定向命令一起使用必须注意优先级
管道命令的优先级高于重定向命令，重定向命令的优先级高于组合命令
问题：把C盘和D盘的文件和文件夹列出到a.txt文件中。看例：
dir c:\ && dir d:\ > a.txt
这 样执行后a.txt里只有D盘的信息！为什么？因为组合命令的优先级没有重定向命令的优先级高！所以这句在执行时将本行分成这两部分：dir c:\和dir d:\ > a.txt，而并不是如你想的这两部分：dir c:\ && dir d:\和> a.txt。要使用组合命令&&达到题目的要求，必须得这么写：
dir c:\ > a.txt && dir d:\ >> a.txt
这样，依据优先级高低，DOS将把这句话分成以下两部分：dir c:\ > a.txt和dir d:\ >> a.txt。例十八中的几句的差别比较特殊，值得好好研究体会一下。
当然这里还可以利用&命令（自己想一下道理哦）：
dir c:\ > a.txt & dir d:\ >> a.txt
[这个也可以用 dir c:\;d:\ >>a.txt 来实现]

**"" 字符串界定符**
双引号允许在字符串中包含空格，进入一个特殊目录可以用如下方法
cd "program files"
cd progra~1
cd pro*
以上三种方法都可以进入program files这个目录

**, 逗号**
逗号相当于空格，在某些情况下“,”可以用来当做空格使

**; 分号**
分号，当命令相同时，可以将不同目标用；来隔离，但执行效果不变，如执行过程中发生错误，则只返回错误报告，但程序仍会执行。

规则：

1.如果目标路径不存在，则整个语句都不执行，例如dir c:\;c:\dfdfdf\a.txt，则根本不会执行，因为我没有c:\dfdfdf\这个目录；
2.如果路径存在，仅文件不存在，则会继续执行，并且提示文件不存在的错误，例如：dir c:\;c:\temp\a.txt，我的目录中有c:\temp\文件夹，但这个目录下面没有1.txt这个文件。

**() 括号**
小括号在批处理编程中有特殊的作用，左右括号必须成对使用，括号中可以包括多行命令，这些命令将被看成一个整体，视为一条命令行。
  括号在for语句和if语句中常见，用来嵌套使用循环或条件语句，其实括号()也可以单独使用，请看例子。
例：
命令：echo 1 & echo 2 & echo 3
可以写成：
(
echo 1
echo 2
echo 3
)
上面两种写法效果一样，这两种写法都被视为是一条命令行。
注意：这种多条命令被视为一条命令行时，如果其中有变量，就涉及到变量延迟的问题。

**! 感叹号**
在变量延迟问题中，用来表示变量，即%var%应该表示为!var!

## 3.8 FOR循环

```
对一组文件中的每一个文件执行某个特定命令。

FOR %variable IN (set) DO command [command-parameters]

  %variable  指定一个单一字母可替换的参数。
  (set)      指定一个或一组文件。可以使用通配符。
  command    指定对每个文件执行的命令。
  command-parameters
             为特定命令指定参数或命令行开关。

在批处理程序中使用 FOR 命令时，指定变量请使用 %%variable
而不要用 %variable。变量名称是区分大小写的，所以 %i 不同于 %I.

如果启用命令扩展，则会支持下列 FOR 命令的其他格式:

FOR /D %variable IN (set) DO command [command-parameters]

    如果集中包含通配符，则指定与目录名匹配，而不与文件名匹配。

FOR /R [[drive:]path] %variable IN (set) DO command [command-parameters]

    检查以 [drive:]path 为根的目录树，指向每个目录中的 FOR 语句。
    如果在 /R 后没有指定目录规范，则使用当前目录。如果集仅为一个单点(.)字符，
    则枚举该目录树。

FOR /L %variable IN (start,step,end) DO command [command-parameters]

    该集表示以增量形式从开始到结束的一个数字序列。因此，(1,1,5)将产生序列
    1 2 3 4 5，(5,-1,1)将产生序列(5 4 3 2 1)

FOR /F ["options"] %variable IN (file-set) DO command [command-parameters]
FOR /F ["options"] %variable IN ("string") DO command [command-parameters]
FOR /F ["options"] %variable IN ('command') DO command [command-parameters]

    或者，如果有 usebackq 选项:

FOR /F ["options"] %variable IN (file-set) DO command [command-parameters]
FOR /F ["options"] %variable IN ("string") DO command [command-parameters]
FOR /F ["options"] %variable IN ('command') DO command [command-parameters]

    fileset 为一个或多个文件名。继续到 fileset 中的下一个文件之前，
    每份文件都被打开、读取并经过处理。处理包括读取文件，将其分成一行行的文字，
    然后将每行解析成零或更多的符号。然后用已找到的符号字符串变量值调用 For 循环。
    以默认方式，/F 通过每个文件的每一行中分开的第一个空白符号。跳过空白行。
    你可通过指定可选 "options" 参数替代默认解析操作。这个带引号的字符串包括一个
    或多个指定不同解析选项的关键字。这些关键字为:

        eol=c           - 指一个行注释字符的结尾(就一个)
        skip=n          - 指在文件开始时忽略的行数。
        delims=xxx      - 指分隔符集。这个替换了空格和制表符的
                          默认分隔符集。
        tokens=x,y,m-n  - 指每行的哪一个符号被传递到每个迭代
                          的 for 本身。这会导致额外变量名称的分配。m-n
                          格式为一个范围。通过 nth 符号指定 mth。如果
                          符号字符串中的最后一个字符星号，
                          那么额外的变量将在最后一个符号解析之后
                          分配并接受行的保留文本。
        usebackq        - 指定新语法已在下类情况中使用:
                          在作为命令执行一个后引号的字符串并且一个单
                          引号字符为文字字符串命令并允许在 file-set
                          中使用双引号扩起文件名称。

    某些范例可能有助:

FOR /F "eol=; tokens=2,3* delims=, " %i in (myfile.txt) do @echo %i %j %k

    会分析 myfile.txt 中的每一行，忽略以分号打头的那些行，将
    每行中的第二个和第三个符号传递给 for 函数体，用逗号和/或
    空格分隔符号。请注意，此 for 函数体的语句引用 %i 来
    获得第二个符号，引用 %j 来获得第三个符号，引用 %k
    来获得第三个符号后的所有剩余符号。对于带有空格的文件
    名，你需要用双引号将文件名括起来。为了用这种方式来使
    用双引号，还需要使用 usebackq 选项，否则，双引号会
    被理解成是用作定义某个要分析的字符串的。

    %i 在 for 语句中显式声明，%j 和 %k 是通过
    tokens= 选项隐式声明的。可以通过 tokens= 一行
    指定最多 26 个符号，只要不试图声明一个高于字母 "z" 或
    "Z" 的变量。请记住，FOR 变量是单一字母、分大小写和全局的变量；
    而且，不能同时使用超过 52 个。

    还可以在相邻字符串上使用 FOR /F 分析逻辑，方法是，
    用单引号将括号之间的 file-set 括起来。这样，该字符
    串会被当作一个文件中的一个单一输入行进行解析。

    最后，可以用 FOR /F 命令来分析命令的输出。方法是，将
    括号之间的 file-set 变成一个反括字符串。该字符串会
    被当作命令行，传递到一个子 CMD.EXE，其输出会被捕获到
    内存中，并被当作文件分析。如以下例子所示:

      FOR /F "usebackq delims==" %i IN (`set`) DO @echo %i

    会枚举当前环境中的环境变量名称。

另外，FOR 变量参照的替换已被增强。你现在可以使用下列
选项语法:

     %~I          - 删除任何引号(")，扩展 %I
     %~fI        - 将 %I 扩展到一个完全合格的路径名
     %~dI        - 仅将 %I 扩展到一个驱动器号
     %~pI        - 仅将 %I 扩展到一个路径
     %~nI        - 仅将 %I 扩展到一个文件名
     %~xI        - 仅将 %I 扩展到一个文件扩展名
     %~sI        - 扩展的路径只含有短名
     %~aI        - 将 %I 扩展到文件的文件属性
     %~tI        - 将 %I 扩展到文件的日期/时间
     %~zI        - 将 %I 扩展到文件的大小
     %~$PATH:I   - 查找列在路径环境变量的目录，并将 %I 扩展
                   到找到的第一个完全合格的名称。如果环境变量名
                   未被定义，或者没有找到文件，此组合键会扩展到
                   空字符串

可以组合修饰符来得到多重结果:

     %~dpI       - 仅将 %I 扩展到一个驱动器号和路径
     %~nxI       - 仅将 %I 扩展到一个文件名和扩展名
     %~fsI       - 仅将 %I 扩展到一个带有短名的完整路径名
     %~dp$PATH:I - 搜索列在路径环境变量的目录，并将 %I 扩展
                   到找到的第一个驱动器号和路径。
     %~ftzaI     - 将 %I 扩展到类似输出线路的 DIR

在以上例子中，%I 和 PATH 可用其他有效数值代替。%~ 语法
用一个有效的 FOR 变量名终止。选取类似 %I 的大写变量名
比较易读，而且避免与不分大小写的组合键混淆。
```

例：

![image-20220601150514574](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220601150514574.png)

![image-20220601150531224](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220601150531224.png)

## 3.9 条件循环

例：

```
@echo off
set var=0
rem ************循环开始了
:continue
set /a var+=1
echo 第%var%次循环
if %var% lss 100 goto continue
rem ************循环结束了
echo 循环执行完毕
pause

例：
@echo off
set var=100
rem ************循环开始了
:continue
echo 第%var%次循环
set /a var-=1
if %var% gtr 0 goto continue
rem ************循环结束了
echo 循环执行完毕
pause
```

## 3.10 进度条

```
@echo off
mode con cols=113 lines=15 & color 9f
cls
echo.
echo  程序正在初始化. . . 
echo.
echo ┌──────────────────────────────────────┐ 
ping 127.0.0.1 >nul /n 1 & set /p= <nul
for /L %%i in (1 1 39) do set /p a=▉<nul& ping /n 1 127.0.0.1>nul
echo  100%%
echo └──────────────────────────────────────┘
pause
```

![image-20220601163159122](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20220601163159122.png)

# 4.其它命令

| 命令 | 说明 |
| :---- | :----: |
| BREAK | 设置或清除扩展式 CTRL+C 检查。 |
| BCDEDIT | 设置启动数据库中的属性以控制启动加载。 |
| CACLS | 显示或修改文件的访问控制列表(ACL)。 |
| CALL | 从另一个批处理程序调用这一个。 |
| CHCP | 显示或设置活动代码页数。 |
| COMPACT | 显示或更改 NTFS 分区上文件的压缩。 |
| CONVERT | 将 FAT 卷转换成 NTFS。你不能转换当前驱动器。|
| DISKPART | 显示或配置磁盘分区属性。|
| DOSKEY | 编辑命令行、撤回 Windows 命令并创建宏。|
| DRIVERQUERY | 显示当前设备驱动程序状态和属性。|
| ENDLOCAL | 结束批文件中环境更改的本地化。 |
| FSUTIL | 显示或配置文件系统属性。 |
| GPRESULT | 显示计算机或用户的组策略信息。|
| GRAFTABL | 使 Windows 在图形模式下显示扩展字符集。 |
| HELP | 提供 Windows 命令的帮助信息。|
| ICACLS | 显示、修改、备份或还原文件和目录的 ACL。|
| MKLINK | 创建符号链接和硬链接 |
| MODE | 配置系统设备。|
| MORE | 逐屏显示输出。|
| MOVE | 将一个或多个文件从一个目录移动到另一个目录。|
| OPENFILES | 显示远程用户为了文件共享而打开的文件。|
| PATH | 为可执行文件显示或设置搜索路径。|
| PRINT | 打印一个文本文件。|
| PROMPT | 更改 Windows 命令提示。|
| ROBOCOPY | 复制文件和目录树的高级实用工具 |
| SETLOCAL | 开始本地化批处理文件中的环境更改。 |
| SC | 显示或配置服务(后台进程)。 |
| SCHTASKS | 安排在一台计算机上运行命令和程序。 |
| SHIFT | 调整批处理文件中可替换参数的位置。 |
| SHUTDOWN | 允许通过本地或远程方式正确关闭计算机。 |
| SORT | 对输入排序。 |
| START | 启动单独的窗口以运行指定的程序或命令。 |
| SUBST | 将路径与驱动器号关联。 |
| SYSTEMINFO | 显示计算机的特定属性和配置。 |
| TASKLIST | 显示包括服务在内的所有当前运行的任务。 |
| TASKKILL | 中止或停止正在运行的进程或应用程序。 |
| WMIC | 在交互式命令 shell 中显示 WMI 信息。 |
|  |  |
|  |  |

# 5.参考资料

1.windows cmd指令

2.[【最全的】BAT 批处理脚本教程_鹅厂程序小哥的博客-CSDN博客_bat教程](https://blog.csdn.net/qq826364410/article/details/79323351?spm=1001.2101.3001.6650.5&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-5.pc_relevant_paycolumn_v3&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-5.pc_relevant_paycolumn_v3&utm_relevant_index=9)

