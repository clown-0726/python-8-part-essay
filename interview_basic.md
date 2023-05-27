#### 📖 Python 的作者？

使用 Python 要知道是谁开发的，作为常识。

![](./asset/img/guido_van_rossum.png)

吉多·范罗苏姆（Guido van Rossum） ，是一名荷兰计算机程序员，他作为 Python 程序设计语言的作者而为人们熟知。在 Python 社区，吉多·范罗苏姆被人们认为是“仁慈的独裁者（BDFL）”，意思是他仍然关注 Python 的开发进程，并在必要的时刻做出决定。他在 Google 工作，在那里他把一半的时间用来维护 Python 的开发。

#### 📖 Python 类型鉴别？

Python 的语言类型定义是**强类型**的**动态语言**。

这道题核心点是在于知道区分语言类型的标准：

- 强类型和弱类型指的是是否会发生类型的隐式转换；
- 动态语言还是静态语言指的是编译期还是运行期确定类型；

Python 中变量一旦确定类型，如果在之后的代码中赋值给此变量其他类型，Python 是会报错的，因此 Python 中类型不会发生隐式转换，所以 Python 属于强类型。

```python
# 下面的转换是不允许的，但这在弱类型的 Javascript 中是允许的
foo = 'abc'
abc = 123
print(foo + abc)
```

Python 变量的类型是在运行期间才确定的，因此 Python 属于动态语言，这有别与 Java，Java 在变量声明时就必须指定变量的类型。

#### 📖 Python 的基本数据类型？

Python3 中有六个标准的数据类型：

- Number（数字）(包括整型、浮点型、复数、布尔型等)
- String（字符串）
- List（列表）
- Tuple（元组）
- Set（集合）
- Dictionary（字典）

Python3 的六个标准数据类型中：

不可变数据（3 个）：Number（数字）、String（字符串）、Tuple（元组）；
可变数据（3 个）：List（列表）、Dictionary（字典）、Set（集合）；

#### 📖 Python 中的 `*args` 和 `**kwargs` 表示什么？

是当函数进行参数传递时，用来处理可变参数的。

- `*args` 被打包成 tuple
- `**kwargs` 被打包成 dict

*args 参数传递实例：

```python
def multiple_args(*args):
    print(type(args), args)  # 是 tuple 类型：<class 'tuple'>
    for idx, val in enumerate(args):  # enumerate() 枚举函数
        print(idx, val)

# 可以直接依次输入
multiple_args('a', 'b', 'c')
# 可以通过将列表前加 * 打包成关键字参数
multiple_args(*['a', 'b', 'c'])
```

**kwargs 参数传递实例：

```python
def multiple_kwargs(**kwargs):
    print(type(kwargs), kwargs)  # <class 'dict'>
    for k, v in kwargs.items():
        print('{}: {}'.format(k, v))

# 可以直接依次输入
multiple_kwargs(a=1, b=2)
# 给字典前加 ** 打包成关键字参数
multiple_kwargs(**dict(a=1, b=2))
```

#### 📖 Python 语法中 “==” 和 “is” 的区别是什么？

在 Python 中，“==” 和 “is” 都是运算符。用 “==” 是比较两个对象的值，而 “is” 比较的是两个对象的标识，也就是 `id()` 函数所获取的对象的标识。

```python
a = 5
b = 5
print(a == b)  # True，两个变量的值一样
print(a is b)  # True，python 维护了一个整数列表，因此相同的整数其实是一样的地址

c = []
d = []
print(c == d)  # True，两个列表的元素一致
print(c is d)  # False，两个列表对象，其 id() 不一样
```

#### 📖 Python 中为什么没有函数重载？

C++、Java、C# 等诸多编程语言都支持函数重载，所谓函数重载指的是在同一个作用域中有多个同名函数，它们拥有不同的参数列表（参数个数不同或参数类型不同或二者皆不同），可以相互区分。重载也是面向对象多态性的体现，因为通常是在编译时通过参数的个数和类型来确定到底调用哪个重载函数，所以也被称为编译时多态性或者叫前绑定。

而 Python 不支持函数重载主要有下面几点原因：

- Python 是解释型语言，函数重载现象通常出现在编译型语言中。
- Python 是动态类型语言，函数的参数没有类型约束，也就无法根据参数类型来区分重载。
- Python 中函数的参数可以有默认值，可以使用可变参数和关键字参数，因此可以让函数根据调用者传入的参数产生不同的行为。

#### 📖 介绍用过 Python 标准库中的哪些模块？

Python 标准库中的模块非常多，主要根据自己过往的项目经历来介绍你用过的标准库和三方库。

| 模块名                       | 介绍                                                         |
| ---------------------------- | ------------------------------------------------------------ |
| sys                          | 跟 Python 解释器相关的变量和函数，例如：sys.version、sys.exit() |
| os                           | 和操作系统相关的功能，例如：os.listdir()、os.remove()        |
| re                           | 和正则表达式相关的功能，例如：re.compile()、re.search()      |
| math                         | 和数学运算相关的功能，例如：math.pi、math.e、math.cos        |
| logging                      | 和日志系统相关的类和函数，例如：logging.Logger、logging.Handler |
| json / pickle                | 实现对象序列化和反序列的模块，例如：json.loads、json.dumps   |
| hashlib                      | 封装了多种哈希摘要算法的模块，例如：hashlib.md5、hashlib.sha1 |
| urllib                       | 包含了和URL相关的子模块，例如：urllib.request、urllib.parse  |
| itertools                    | 提供各种迭代器的模块，例如：itertools.cycle、itertools.product |
| functools                    | 函数相关工具模块，例如：functools.partial、functools.lru_cache |
| collections / heapq          | 封装了常用数据结构和算法的模块，例如：collections.deque      |
| threading / multiprocessing  | 多线程/多进程相关类和函数的模块，例如：threading.Thread      |
| concurrent.futures / asyncio | 并发编程/异步编程相关的类和函数的模块，例如：ThreadPoolExecutor |
| base64                       | 提供 BASE-64 编码相关函数的模块，例如：bas64.encode          |
| csv                          | 和读写CSV文件相关的模块，例如：csv.reader、csv.writer        |
| profile / cProfile / pstats  | 和代码性能剖析相关的模块，例如：cProfile.run、pstats.Stats   |
| unittest                     | 和单元测试相关的模块，例如：unittest.TestCase                |

