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
查看最全的显示，尤其是前十个字母的后九个，表示文件的权限
```bash
ls -l
```
排序显示
```bash
## 按文件名排序
ls -fl
## 按文件大小排序
ls -Sr
## 按时间排序
ls -tr
```
## 文件的权限，即修改
```bash
chmod a+x <filename>
chmod u=wr <filrname>
chmod o=wr <filename>
chomod g-x <filename>
```
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
查看所有环境变量
```bash
env
```
最常用的环境变量就是PATH  
PATH说简单点就是一个很长很长，集合所有地址的，字符串变量，  
当输入命令的时候LINUX会去查找PATH里面记录的路径  
所以，path 配置的路径下的文件可以在任何位置执行，并且可以通过which 可执行文件 命令来找到该文件的位置  
```bash
export PATH= ##直接赋值的结果就是PATH里只有一条路径
export PATH=$PATH:/public/home/bma/application/FastQC ##这样赋值的结果就是添加变量，因为PATH其实是个集合
export PATH=/usr/local/mongodb/bin:$PATH ## 冒号：其实是分隔符，这样是把我们的路径添加到原PATH集合的最前面
##但用的时候记得取变量，即
echo $PATH ## 查看路径
$ export TEST="Test..." #增加一个环境变量TEST

$ env|grep TEST #此命令有输入，证明环境变量TEST已经存在了

TEST=Test...

$ unset $TEST #删除环境变量TEST

$ env|grep TEST #此命令没有输出，证明环境变量TEST已经存在了

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
### 查找
```bash
grep
```
### 对比
diff
### 只读展示（更好看地）
```bash
less -N filename.txt ## 显示行号

less -l filename.txt
## 如果指定了-l选项，less将尝试在屏幕上以水平滚动的方式显示文本，而不是将文本自动折行显示。这样可以在水平方向上查看整行文本，而不需要折行。
## 打开文件之后，想高亮显示

/查找词
## 在 less 中查找文本的方法是使用 "/"（斜杠）键，然后输入您想要查找的文本，并按 Enter 键。
## 如果有多个匹配项，您可以继续按 "n" 键查找下一个匹配项，或按 "N" 键查找上一个匹配项。 
## 若要退出查找模式，按下 "q" 键。
```
