# R
清空控制台 Ctrl+L
去重 unique()
identify if an element belongs to a vector %in%
把字符串x_name变成变量再给变量赋值，用于批量读取文件并按规律命名  assign(x_name, read.table(file_name)
返回与字符串同名的变量 get(x_name)
下载bioconductor包管理器  
if (!requireNamespace("BiocManager", quietly = TRUE)) install.packages("BiocManager")
install bioconductor packages with `BiocManager` 
创建文件夹 dir.create("E:/project/CountsMatrices")
数据框两列相减 atac_acc_norm_ct$end-atac_acc_norm_ct$start
查看数据框数据类型 str(atac_acc_norm_ct)
[数据框操作](https://www.cnblogs.com/studyzy/p/R_DataFrame_Operation.html)
get the type of an object  typeof() 
## R packages
plyr: the split-apply-combine paradigm for R.
stringr: Simple, Consistent Wrappers for Common String Operations
karyoploteR: plot customizable linear genomes displaying arbitrary data
# unix
Shebang #!/bin/sh
解压到指定目录 unzip .zip -d directory
统计当前目录下文件的个数（不包括目录）ls -l | grep "^-" | wc -l
解压.tar.gz tar xvfz HINT_ATACTest.tar.gz
"--strip-components 8" extracts the files without copying their original directory structure: tar -zxvf file_name.tgz --strip-components 8
解压.gz文件 gzip -d CTCF_SE_CTRL_chr22_50k.bed.gz
显示文件某一列出现的不重复字符 awk '{print $4}' run_pileup_CTRL.bed.bdg | sort | uniq
创建新的目录和它的子目录 mkdir -p LectureExercises/Lecture03
显示目标文件夹包含文件以及路径 ls PeakFasta/*
more 
-   按回车：默认下一行数据；
-   按空格键盘，默认下一页，以当前屏幕为单位；
-   按Ctrl+ B 上一页，以当前屏幕大小为单位；
-   按B 回到文档第一页面
```bash
 sort -nrk 4 peaks_pvalue.bdg | head
```
df -h ./ 
du -h ./
# sed
```bash
# 将连续多个空格转换为单个tab
sed -i 's/\s\+/\t/g' file
```
# vim
-   $
-   ^
-   GG
-   g
-   w
-   b
-   Visual - d
-   Visual - y
-   Visual - p
使用系统粘贴板 在输入模式按Shift+Inset（粘贴）
# awk
关于 awk 脚本，我们需要注意两个关键词 BEGIN 和 END。
-   BEGIN{ 这里面放的是执行前的语句 }
-   END {这里面放的是处理完所有的行后要执行的语句 }
-   {这里面放的是处理每一行时要执行的语句}
```bash
# 先判断当前行是不是 > 开头，如果是，表示是序列名字行，替换掉大于号，取出名字。
# sub 替换, sub(被替换的部分，要替换成的，待替换字符串)
# 如果不以大于号开头，则为序列行，存储起来。
# seq[name]: 相当于建一个字典，name为key，序列为值。然后就可以使用name调取序列。
# ~ 表示模式开始。// 匹配代码块，可以是字符串或正则表达式
$ awk 'BEGIN{OFS=FS="\t"}{if($0~/>/) {name=$0; sub(">", "", name);} else seq[name]=$0;}END{print ">SOX2"; print seq["SOX2"]}' test.fasta
```
不等于: awk '$1 != "asima"' temp
[https://my.oschina.net/u/2391658/blog/703922](https://my.oschina.net/u/2391658/blog/703922)
# Python
iloc 则是通过行号对行进行索引
# Tips
revise a little bit and test each time
use the same platform to develop

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTIxMjcxNzM5NSwtODE5NjkzMDgsMTM0OT
MxNDc4OSw1ODM1OTE0MDQsMTMzNjg4MTkzNywtMzgzOTk5MDY2
LDE1NjM5NjU2MCwtMTYzMTAwODQwNCwxMjMyMzYxMTgzLDk0Mj
YzODA3NiwtOTQxNjg5MzU2LC0zNTM3Njk3MTgsLTE0MDQwNjc4
NzQsMjA2MjM0OTg0LDIwMzUyNDYwMDcsLTM1MDc5OTc3OSwtMT
U4MDU1MTQ2OSwtMTgzNDM0NjQ3NiwxNTQ2ODAxOTg4LDI0NDk2
OTYzOV19
-->