# 张振文同学的Liunx小技巧
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
