#### 三种模式  命令行 末行 编辑

#### vim 编辑命令行模式

yy 快速复制一行 p 在下一行黏贴

u 撤销

ctr+r 反撤销

dd 直接删除

shift +zz 保存退出

(shift) + gg  跳转至第一行

#### 末行模式

wq 保存退出

q! 不保存退出

#### 系统操作

ctr + alt linux 和 windows 之间切换的命令

mv 对于文件是重新命名

(  >> 追加 >覆盖)

echo ' word ' >> a.text

history 查看所有命令

ln -s  创建软链接

tar -xvf file.tar 解压.tar结尾的

tar -zxvf file.tar.gz 解压.tar.gz文件

##### 权限

--rwx-r-r 第一列 当前用户  第二列 当前用户组 其他用户  第三列 其他用户

chmod 777  （-R为子集目录修改权限） a.text     777 为最高权限 

##### 文件查找

find / -name a.txt

grep 作为过滤查找条件

grep 内容 正则  grep 'error' test.log 查找以test.log文件中包含error的行

cat a.txt | grep a

查看pid

kill -9 name 杀死进程

netstat -nlp | grep 22

#### sed

nl /etc/passwd | sed '2,5c No 2-5 number' 

sed -e sed -i

sed -s 替换

sed 's/is/are/g' testfile

sed -d 删除

sed '\%pig%d' testfile



#### shell脚本命令

vim /etc/passwd

![image-20200808214001966](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200808214001966.png)

![image-20200808214029400](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200808214029400.png)

![image-20200808214135723](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200808214135723.png)



##### shell 数组

```shell
#!/bin/bash
my_array=(A B "C" D)
array_name[0]=value0
array_name[1]=value1
array_name[2]=value2
```

条件判断

```shell
#!/bin/bash
a=10
b=20
if [ $a == $b ]
then
   echo "a 等于 b"
elif [ $a -gt $b ]
then
   echo "a 大于 b"
elif [ $a -lt $b ]
then
   echo "a 小于 b"
else
   echo "没有符合的条件"
fi
```

for循环

```shell
#!/bin/bash
for loop in 1 2 3 4 5
do
    echo "The value is: $loop"
done
```

while循环

```shell
#!/bin/bash
int=1
while(( $int<=5 ))
do
    echo $int
    let "int++"
done
```

case

```shell
#!/bin/bash
echo '输入 1 到 4 之间的数字:'
echo '你输入的数字为:'
read aNum
case $aNum in
    1)  echo '你选择了 1'
    ;;
    2)  echo '你选择了 2'
    ;;
    3)  echo '你选择了 3'
    ;;
    4)  echo '你选择了 4'
    ;;
    *)  echo '你没有输入 1 到 4 之间的数字'
    ;;
esac
```

函数

```shell
#!/bin/bash
demoFun(){
    echo "这是我的第一个 shell 函数!"
}
echo "-----函数开始执行-----"
demoFun
echo "-----函数执行完毕-----"
```

