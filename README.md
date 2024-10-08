# CS51 笔记

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
	- 讲座
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
			- 运算截断错误
				- 不同类型换算时，可能出现小数被截断的问题。比如 int 类型的 1/3 = 0
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
	- 其他视频
		- 主要作用是详细描述了课程中没有详细讲到的语言部分。
		- 变量
			- int 
			- long
			- float
			- double
			- char 
			- string
			- bool
		- 操作符
			- + - * /
			- and &&
			- or ||
			- not !
		- 条件语句
			- if
			- if else
			- switch
			- ?: 三目运算符
		- 循环
			- while 
			- do while 总是执行一次
			- for 适合有明确次数的循环
		- 命令行
			- ls
			- cd
			- cp
			- mv
			- rm
				- -f 强制执行
				- -r 内部文件递归
			- mkdir
			- rmdir
			- sudo
			- touch
			- telnet
- week2
	- 这周主要谈论了一部分的编译原理、提了一嘴逆向工程、详细讲解了 Array、String 以及了解了一下密码学。
	- 编译原理：从源码到可执行文件一共经历了 4 部分
		- 预处理(pro-processing)：将使用到的包引用转变为原型。`#include <stdio.h>` -> `void printf(string value)`
		- 编译（compiling)：将预处理后的代码编译为汇编语言。`2 + 3` -> `add 2 3`
		- 汇编（assembling）：将编译代码转变为二进制文件，这是生成了文件。
		- 连接（linking)：将库的二进制文件和上述文件连接。
	- 逆向工程：就是从二进制文件倒推生成源文件。但是，在生成源文件时，会有大量的信息丢失（变量名...），所以本质上逆向工程是十分困难的。
	- Array
		- Array 的数据是有序的储存在内存中。
		- Array 储存的是单类型的数据。
		- Array 没有获取长度的方式，需要自己管理长度。
		- 声明的方式：`int Array[3]; or int Array[] = {72, 73, 33}`
		- Array 不能够直接通过 `=` 复制，需要通过循环来复制。
		- Array 作为参数时，是以`值传递`，意味着，如果传递途中改变，那么原值也会改变。
		- Array 有超出索引而引发错误的可能。
	- String
		- String 是一个字符数组，而字符是一堆数字，可以通过数字计算来转换大小写（Unicode），不过最好使用 `<string.h>` 提供的 `toupper`。
		- 每个字符串都有一个结尾的哨兵字符（`\0`) ，用来标记结束位置。所以每个字符串的长度会比原有数组大 1。
		- 迭代 String 的方式
			- 以哨兵字符为条件的循环。（不推荐）
			- 以 `strlen` 为条件的循环。`for (int i = 0, n = strlen(name), i < n, i++)`
	- 命令行参数
		- `int main(int argc, int argv[])`
		- main 方法默认返回 0 作为程序正常的标志。通过手动返回不同的数字代码可以用来标记错误。测试工具的原理就是如此。
	- 密码学
		- 加密
		- 解密
		- 密钥
	- Debugger 
		- printf 不推荐，每次修改都需要重新编译非常浪费时间。
		- debugger 推荐使用
		- 橡胶鸭调试。向非生命体描述程序的构成，可以发现自己的错误。
	- 其他
		- make 在执行 clang 所执行的内容，只是简化了步骤。
		- 全局变量：`const int N`，放在所有方法外，const 保证不可变，通常建议大写。
		- 命令行的艺术，`cowsay` 自己玩玩
- week3
	- 这周主要讲解了算法。
	- 主要的思想
		- 糟糕的代码有股代码气味。
		- 递归是一种以资源换资源的平衡。
		- 当参数足够大时，可以忽略其他系数所带来的影响。
	- 算法![[Pasted image 20240727105408.png]]
		- 搜索
			- 线性算法
			- 二分法
		- 排序
			- 选择
			- 冒泡
			- 合并（递归）
	- 算法的效率
		- 效率的几种类型（n表示数据的个数）
			- $n^2$：选择排序
			- $n\log n$：合并排序
			- $n$：二分法
			- $\log n$：
			- $1$
		- 算法的符号
			- $O$：表示算法大运算量时的情况。
			- $\Omega$：表示算法最小运算量的情况。
			- $\Theta$：表示算法最大和最小的情况相同时。
		- 效率的考量：数据在内存中移动的次数。
	- 数据构建 `typedef struct`
		- ![[Pasted image 20240727105529.png]]
	- 其他
		- 伪代码有利于思考问题，建议多用。
		- `time` 可以获取代码的运行时间。
- week4
	- ![[Pasted image 20240731165223.png]]
	- 这一节主要讲解了：十六进制数、指针，以及最后实现图片处理。
	- 十六进制数
		- `0xff`
			- 以 `0x` 作为十六进制数的标识。
			- 十六进制从 `0-15` 依次表示为：
				  `0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F`
			- 一个十六进制数，可以用 4 位表示：`f = 1111`，但是，计算机通常以1字节为最小单位（也就是 8 位），所以十六进制数通常两位为一对（比如 `ff`）。
		- 优先讲解十六进制数的原因是内存中储存指针的类型就是十六进制数。
	- 指针
		- `&`：地址运算符，获取指针中的地址。
		- `*`：分为2种情况。
			- `* buffer`: 一般为解引用，获取地址中的值。
			- `int* buffer`：当前面有类型时，表示声明一个指针变量，用于存储地址。
		- `string` 的本质是 `char *`，变量本身其实是一个**指针**
		- 指针可以通过 `%p` 打印出来。
		- 理解指针使我们拥有了操作文件/图片的强大能力。
		- 变量传递的方式
			- 值传递
			- 副本传递
	- 内存分为 4 个部分![[Pasted image 20240731165101.png]]
		- 部分
			- 机器码：用于储存代码运行时的源码。
			- 全局变量
			- 堆
			- 栈：先进先出。![[Pasted image 20240731165133.png]]
		- 其中**堆**和**栈**是相向而行，也就是说如果数据足够大，会产生错误。
		- 几种内存错误
			- 堆溢出（heap overflow）
			- 栈溢出（stack overflow）
			- 缓冲区溢出（buffer overflow)：使用内存过多时抛出
		- 内存管理 
			- `<stdlib.h>`
				- `malloc` 分配内存
				- `free` 释放内存
	- 文件IO
		- 常用操作：`fopen` `fread` `fwrite` `fseek` `fclose`
		- 常用的参数
			- `w` 写入
			- `r` 阅读
			- `a` 追加
	- 其他
		- `scanf` ：获取输入。
		- 暂时没有实现 `string` 的任意长度接收。
		- `clang -o filename -Wno-initialzation filename.c`
		- `valgrind` 寻找内存 debug 工具
		- `""` 
			- 是一个包含 `\0` 的字符串，所以它的长度是 1。
			- 它的返回值是开头字符所在的指针。
		- `NULL` 是 `0x00`。
		- `strcpy` 用于复制字符串。
		- `garbage value` 表示声明但没有初始化的数据。
		- 32位的内存 = $2^{23}$ 内存空间 = 4GB，计算正负值的话为 2G 内存。
		- 图片有其标准格式，可以通过这些格式在磁盘中实现数据恢复。
		- `typedef` 可以定义新类型。![[Pasted image 20240731165010.png]]
- week5
	- 这周主要讲了 8 种数据结构。
	- 数据结构是内存中的数据组织形式。
	- 8 种抽象数据
		- 列表 `Array`：连续且有序的数据。
		- 队列 `Queen`：遵循 `FIFO` 的数据。
			- `enqueen` 入列
			- `dequeen` 出列
		- 栈 `stack`：遵循 `LIFO` 的数据。
			- `push` 从顶部推入
			- `pop` 从顶部弹出
		- 链表 `Linked`：可以动态储存的结构，以数据和指针构成。![[Pasted image 20240802140844.png]]
		  ```c
		  typedef struct node
		  {
			  int number;
			  struct node *next;
		  }
		  node;
		   ```
		- 树 `tree`：由数据和两个指针构成![[Pasted image 20240802140908.png]]
		  ```c
		  typedef struct node
		  {
			  int number;
			  struct node *left;
			  struct node *right;
		  }
		  node;
		   ```
		- 字典 `dictionary`：由键值对构成的数据。
		- 哈希表 `Hash table`：由数组和链表构成的数据。![[Pasted image 20240802140933.png]]
			- 哈希函数：将较大值转换为较小且可预测的数据。
		- `Tries`![[Pasted image 20240802140955.png]]
	- 其他
		- 内存泄露：未能正确的释放不再使用的内存，使内存不断被消耗。课程中在创建链表时出现。
		- 元数据
		- `(n*).number` 简写为 `n->number`
- week6
	- 这周主要介绍了 Python 语言，从中可以看到对于语言的学习方式。
	- 语言的组成部分
		- 变量
		- 数据类型
		- 数据结构
		- 循环：减少重复
		- 条件：判断特定条件
		- 函数：对于事物处理步骤的抽象
		- 异常处理：异常捕获和抛出
		- 程序返回状态：程序结束时的状态
		- 命令行参数：程序运行时接收数据
		- IO流：程序外数据读取
		- 备注：用于维护和理解
		- 面向对象编程：每个对象都有自己的属性和方法。
		- 函数式编程
		- 包管理器
		- 库/手册
		- 其他特性
	- Python 和 C 语言的不同
		- 语法上的区别
		  ```python
		  # This is test
		  def main():
			  print("Hello!")
			```
			
			- 方法体没有 `{`
			- 语句结尾没有 `;`
			- 3 种备注方式 `#` `"""` `'''`
		- 异常处理上的不同
			- 使用 `try` 捕获，`except` 抛出异常
		- 消除两种异常
			- 没有整数计算截断异常
		- 数据类型不同
- week7 
	- 这周主要介绍了 SQL 语言，sqlite 以及 SQL 与 Python 的简单结合。
	- SQL 主要的部分 CRUD
		- CREATE, INSERT
		- READ
		- UPDATE
		- DELETE, DROP
	- 关系表之间
		- 一对多
		- 多对多
	- 常见错误
		- 竞争条件，例如在多服务器插入时，可能会导致某些插入数据丢失得问题。可以通过事务处理一部分情况。
		- SQL 注入，某些人会在输入框中直接写入 SQL 关键词，导致程序非理想情况下执行。
	- 其他
		- 可以利用 `indexes` 建立索引，加快查询。但是，也会占据较大的内存。（B 树
		- 由于计算机更擅长处理数字，所以重复数字要比重复字符串更好。
		- 默认情况下，主键会自动加入索引。
- week 8
	- ![[Pasted image 20240813150543.png]]
	- routers：
		- 链接不同地方的主机，
		- 两点之间的点可以视为路由器
		- 需要考虑 `路径决策(routing decisions)` 问题
	- IP（`internet protocol`）：
		- 在互联网上，计算机相互识别的方式。
		- 世界上每台计算机都有唯一的地址。
		- `#.#.#.#`
		- `#` 由 `32-bits` 表示（ `0 - 255` 的数字），可以表示 四十亿 个地址。（新版由 `128-bits` 表示） 
	- TCP （`transmission control protocol`）：用于区分网络服务
		- `80`：`HTTP`
		- `443`：`HTTPS`
	- DNS（`domain name systems`）：互联网上的服务器集合，域名和 IP 对应表。DNS只是保存一个表或数据库，将特定的完全合格域名链接到特定的IP地址。
	- DHCP：IP 分配
	- HTTP（`hypertext transfer protocol`）/HTTPS：`https://www.example.com`
		- 应用级别的协议
		- `.com`：顶级域名（`top-level domain`），用于表示与此地址关联的组织的位置或类型。
		- `curl -I https://harvard.edu`
		- 请求方式：`POST` 和 `GET`
		- 响应码：
		  ```javascript
		  200 OK 
		  301 Moved Permanently 
		  302 Found 
		  304 Not Modified 
		  304 Temporary Redirect 
		  401 Unauthorized 
		  403 Forbidden 
		  404 Not Found 
		  418 I'm a Teapot 
		  500 Internal Server Error 
		  503 Service Unavailable
			```
	- HTML（`hypertext markup language`）：只关乎页面展现的标记语言![[Pasted image 20240813151642.png]]
		- 浏览器开发者工具
		- `curl -I https://www.harvel.com/`
		- 标签
			- `<p>`
			- `<h1>`
			- `<lu>` 
				- `<li>`
			- `<lo>`
				- `<li>`
			- `<table>`
				- `<tr>`
					- `<td>`
			- `<img alt="" src="">`
			- `<video controls muted>`
				- `<source src="" type="video/mp4">`
			- `<a href="">`
			- `<meta property="" content="">`
			- `<input name="" type="" value="" autocomplete="" autofocus placeholder="" pattern=".+@.+\.edu">`
			- `<button>`
	- css（`cascading style sheet`）用于微调 html 的美观性
	- javascript：一种实现页面交互的编程语言。
		- 函数
			- `alert()`
			- `<form onsubmit="greet(); return false;>`
			- `document.addEventLister('DOMContentLoaded', function(){})`
			- `document.querySelector().addEventListener('submit, function(){})`
			- `window.setInterval(function, 500)`
			- `startsWith()`
			- 获取地理位置
			  ```javascript
				  navigator.geolocation.getCurrentPosition(function(position){
					  document.write(position.coords.latitude + ", " + position.coords.longitude);
				  }); 
			    ```
- week9 
	- 这周综合了 python、flask、javascript、sql、html、css、http 来制作一个网站。
	- 主要是对框架的使用上，可以看文档，这里没有太多记录。
	- Flask 的几个重要的库![[Pasted image 20240823134737.png]]
		- `Flask`：主要框架。
		- `render_template`：用于渲染网页
		- `request`： 用于处理网络请求 `POST` 和 `GET`
		- `redirect`：用于重定向请求
	- From 的重要作用是提交请求。![[Pasted image 20240823135024.png]]
	- Session 用户再一次会话中识别当前用户是谁![[Pasted image 20240823135552.png]]
	  ```python
		from flask import Flask
		from flask_session import Session

		# Configure app
		app = Flask(__name__)
		
		# Configure session
		app.config["SESSION_PERMANENT"] = False
		app.config["SESSION_TYPE"] = "filesystem"
		Session(app)
		```
	- JSON 的使用
	  ```python
		  from flask import jsonify
		  
		  return jsonify(shows)
		```
	- 
- week10
	- 这是最后一周，主要介绍了**加密**
		- 加密的几种方式
			- 密码管理（Password Managers）
			- 双因认证（Two-factor Authentication）
			- 哈希（Hashing）
			- Cryptography：利用公钥和私钥
			- 密钥（Passkeys）：通过设备创建唯一签名，用户名和密码可能很快就过时了。
			- Encryption：加密数据的方法。
				- 端对端加密（End-to-end encryption）可以防止中间人窥探
		- 解密的几种方式
			- 暴力破解![[Pasted image 20240823140046.png]]
			- 彩虹字典
		- 数据删除（Deletion）：通常的删除会保留数据残留。
		- 安全删除（Secure deletion）：将残余数据变成 0 或是 1
		- 也可以通过全盘加密的方式来保护数据。