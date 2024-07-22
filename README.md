# CS50 笔记

- week 0
	- 主要介绍了课程内容：Scratch、C、Javascript、算法、人工智能...(没记住)
	- 重要的观点：
		- 对于写程序，一次只处理好一件事，并慢慢迭代版本进行完善。
		- 编程是解决问题的艺术。
		- 课程的内容非常多，可能无法完全吸收完。重要的是关注自己的成长（课程之后自己的位置和之前的比较）
	- 数字如何表示一切
		- 数字：10 -> 2 （二进制）
		- 单词： A -> 56 
		- 颜色： 1e1e1e -> 黑色 （十六进制）
		- 图片： 1e1e1e -> 颜色块 -> 图片
		- 表情：Unicode -> 表情 （十六进制）
		- 视频： 图片 -> 视频
		- 音乐
	- 有关 Scratch 
		- 伪代码：用人类语言描述程序解决问题的方法。
		- 语言的组成：
			- 条件
			- 循环
			- 函数
			- ...
		- 使代码更加简洁的方法
			- 抽象
			- 模块
	- 算法的考量：效率（时间/数据量）、准确率。
	- 其他
		- 字节 = 8 位 （2^3）
- week1
	- 这一周主要讲了 C 语言。
	- 重要的观点
		- 不要重复自己。这样有助于之后的维护和修改。
		- 计数从 0 开始，不浪费比特。
		- 语言并不需要了解所有函数，只要了解在哪里（库/手册）得到解决就好。语言在发展时会包含许多内容，使得语言越来越大。
	- C 语言特性和优化
		- `int main(void)` 是有隐藏返回值的，0 表示正常，其他的是一些错误代码。
		- 最好将 `main()` 方法放在程序的最前。方便其他人寻找和修改代码。
	- 一些程序错误
		- 内存溢出。
			- 计算机只能表现有限的数字，当数字超出表示范围时，就会出现 “内存溢出“ 错误。
		- 小数精确度
			- 同样是，计算机无法储存精确数据，导致在数字的四则运算时，可能出现小数并不精准的问题。
			- 比如，可以测试一下 1/3
	- 简单的介绍了一下 Linux 系统
		- cd
		- mv
		- rm
		- cp
		- ls
		- mkdir
		- mrdir
	- 程序的运行过程
		- 编写源码（code）
		- 编译机器码（make）
		- 运行
- 阅读 [Style Guide for C — CS50 Docs](https://cs50.readthedocs.io/style/c/)
	- 每行不要超过 100 字符（以前的屏幕建议是 80）。
	- 备注
		- 备注的作用
			- 给以后的自己维护时
			- 给别人查看时
		- 好的备注
			- 主要解决两个问题
				- 这个功能是什么
				- 为什么这样实现
			- 太长和太短的备注都不好。
			- 最好每个几行备注一下。
			- 每个文件的上面总结一下。
			- 每个方法上总结一下。
			- 除特殊名称，首字母大写。
	- 之后是对于不同方法的书写建议，大体建议如下
		- 花括号单独占一行
		- 空格
			- 方法体要缩进（4个空格）
			- 方法名后的括号`()`有空格
			- 其他`()`周围没有空格。 
			- 运算符周围有空格。
		- 其他
			- switch 的每个分支都要有 `break;`
			- for 循环建议使用 `i-k` 作为参数，超过 `k` 的重新考虑程序设计。
			- 多个单词的参数名以`_`连接。