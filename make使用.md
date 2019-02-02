# make使用

make  默认 搜索文件名为 makefile Makefile

## 指定文件名
make -f filename 
make --file filename

make -n 只打印命令输出 不执行

make -k 遇到错误继续向下执行 不加遇到第一个错误停止

make -B 无条件重建所有目标

make -I dir 指定被包含的makefile目录

make -c dir 读入指定目录下的makefile

make -i 忽略错误

make -s 不显示执行命令

make -t 更新目标文件 不存在创建文件 touch objectivename

make -j 例如make -j4 最多允许4个编译进程同时执行

## 基本

target ... : prerequisites ...
		recipe

test.exe: a.o b.o
	gcc a.o b.o -o test.exe
a.o: a.h
	gcc -c a.c
b.o: b.h
	gcc -c b.c

clean:
	rm a.o b.o test.exe

## 使用变量

object=a.o b.o
test.exe: $(object)
	gcc $(object) -o test.exe
...

## 自动推导

a.o: a.h 那么会自动推导出 cc -c a.c 

%.o:%.c
	gcc -c $< -o $@



$+ 所有依赖文件 可能重复
$< 依赖目标中的第一个目标名字 模式匹配中 表示符合目标文件集 例如上文中的%.o
$@ 表示规则中的目标文件集
$^ 所有的依赖目标的集合 去除重复
$? 所有比目标新的依赖目标的集合
$% 仅当目标是函数库文件中，表示规则中的目标成员名
$* 目标模式中"%"及其之前的部分 即不包括后缀 如%.c 只保留%部分



## 多个目标依赖一个文件或相同文件

a.o b.o c.o ... : head.h



## 伪目标

.PHONY clean

clean:
	-rm $(object)  -表示某些文件可能出问题 不管他继续向后执行

伪目标并不是一个"目标(target)", 不像真正的目标那样会生成一个目标文件



## 命令前缀

- 不用前缀 :: 输出执行的命令以及命令执行的结果, 出错的话停止执行
- 前缀 @   :: 只输出命令执行的结果, 出错的话停止执行
- 前缀 -   :: 命令执行有错的话, 忽略错误, 继续执行





