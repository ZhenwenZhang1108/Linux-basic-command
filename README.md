# 张振文同学的Linux小技巧
## 一些快捷键
tab点一次， 代码自动补全  
tab点两次， 显示当前目录里的所有文件名，但不中断当前操作  
一个点 . 代表当前文件夹的地址  
两个点 .. 代表上级文件夹的路径，可以联用 ../../   
\*省略一些文件名，可以同时操作很多具有相同前缀/后缀/中缀的文件，e.g. \*abc\*也行  
## 和windows互传
新打开一个terminal界面
```bash
scp gsa_2023@emily.popgen.dk:/home/course/文件地址/文件名 /C/Desktop/文件夹地址
```
## 查看文件夹 ls
## 查看文件size（行数，文本数等）wc 
## 建立可执行脚本
```bash
touch A1.sh
vim A1.sh  #打开文本编辑器
#!/bin/bash  ##一般sh文件的第一行要指定解释器，可以是bash，R
chmod +x A1.sh
./A1.sh
```
## for循环（建议在上述可执行脚本中编译）
```bash
for i in Alpha Belta
do
    echo $i > keep.txt
done
```
## 环境变量（全大写）与取变量（$）
最常用的环境变量就是PATH  
PATH说简单点就是一个字符串变量，当输入命令的时候LINUX会去查找PATH里面记录的路径  
所以，path 配置的路径下的文件可以在任何位置执行，并且可以通过which 可执行文件 命令来找到该文件的位置  
```bash
$PATH=""
##但用的时候记得取变量，即
$PATH
```
```bash
for i in Alpha Belta
do
    echo $i ## 这是打印Alpha 和Belta
done

for i in Alpha Belta
do
    echo i # 这就是打印i本身
done
```
## 压缩与解压缩
注意区分 .zip .tar 和 .gz 文件
还可以多重压缩和多重解压缩
### 解压
对于Winzip文件  
```bash
unzip <filename>
```
对于 .tar 和 .tar.gz文件
```bash
tar -xf <filename>
```
对于 .gz 文件
```bash
gunzip <filename>
```
### 压缩
```bash
tar -cf backup.tar <directory>
gzip backup.tar
```
## 文件的简单操作（非编辑）
