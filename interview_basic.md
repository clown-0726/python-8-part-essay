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

#### 📖 什么是鸭子类型（duck typing）？

鸭子类型是动态类型语言判断一个对象是不是某种类型时使用的方法，也叫做鸭子判定法。简单的说，鸭子类型是指判断一只鸟是不是鸭子，我们只关心它游泳像不像鸭子、叫起来像不像鸭子、走路像不像鸭子就足够了。换言之，如果对象的行为跟我们的预期是一致的（能够接受某些消息），我们就认定它是某种类型的对象。

在 Python 语言中，有很多 bytes-like 对象（如：bytes、bytearray、array.array、memoryview）、file-like 对象（如：StringIO、BytesIO、GzipFile、socket）、path-like对象（如：str、bytes）。

- 其中 file-like 对象都能支持 read 和 write 操作，可以像文件一样读写，这就是所谓的对象有鸭子的行为就可以判定为鸭子的判定方法。
- 再比如 Python 中列表的 extend 方法，它需要的参数并不一定要是列表，只要是可迭代对象就没有问题。

```
说明：动态语言的鸭子类型使得设计模式的应用被大大简化。
```

#### 📖 说一下 Python2 和 Python3 的区别？

Python2 中的 `print` 和 `exec` 都是关键字，在 Python3 中变成了函数。

Python3 中没有 `long` 类型，整数都是 `int` 类型。

Python2 中的不等号 `<>` 在 Python3 中被废弃，统一使用 `!=`。

Python2 中的 `xrange` 函数在 Python3 中被 `range` 函数取代。

Python3 对 Python2 中不安全的 `input` 函数做出了改进，废弃了 `raw_input` 函数。

Python2 中的 `file` 函数被 Python3 中的 `open` 函数取代。

Python2 中的 `/` 运算对于 int 类型是整除，在 Python3 中要用 `//` 来做整除除法。

Python3 中改进了 Python2 捕获异常的代码，很明显 Python3 的写法更合理。

Python3 生成式中循环变量的作用域得到了更好的控制，不会影响到生成式之外的同名变量。

Python3 中的 `round` 函数可以返回 `int` 或 float 类型，Python2 中的 `round` 函数返回 `float` 类型。

Python3 的 str 类型是 Unicode 字符串，Python2 的 `str` 类型是字节串，相当于 Python3 中的 `bytes`。

Python3 中的比较运算符必须比较同类对象。

Python3 中定义类的都是新式类，Python2 中定义的类有新式类（显式继承自 object 的类）和旧式类（经典类）之分，新式类和旧式类在 MRO 问题上有非常显著的区别。

Python3 对代码缩进的要求更加严格，如果混用空格和制表键会引发 TabError。

Python3 中字典的 keys、values、items 方法都不再返回 `list` 对象，而是返回 view object，内置的 `map`、`filter` 等函数也不再返回 `list` 对象，而是返回迭代器对象。

Python3 标准库中某些模块的名字跟 Python2 是有区别的；而在三方库方面，有些三方库只支持 Python2，有些只能支持 Python3。

#### 📖 什么是 Lambda 函数？

Lambda 函数也叫匿名函数，它是功能简单用一行代码就能实现的小型函数。Python 中的 Lambda 函数只能写一个表达式，这个表达式的执行结果就是函数的返回值，不用写 return 关键字。

Lambda 函数其实最为主要的用途是把一个函数传入另一个高阶函数（如内置的 filter、map 等）中来为函数做解耦合，增强函数的灵活性和通用性。

```python
items = [12, 5, 7, 10, 8, 19]
items = list(map(lambda x: x ** 2, filter(lambda x: x % 2, items)))
print(items)    # [25, 49, 361]

'''
1. The filter(lambda x: x % 2, items) part filters the elements in the items list using the lambda function lambda x: x % 2. This lambda function checks if an element is odd by checking if the element modulo 2 is not equal to 0. So, it filters out all the even numbers from the list.
2. The map(lambda x: x ** 2, ...) part applies the lambda function lambda x: x ** 2 to each element in the filtered list. This lambda function squares each element.
3. Finally, the list(...) function is used to convert the resulting map object into a list.
'''
```

#### 📖 正则表达式的 match 方法和 search 方法有什么区别？

在 Python 中，使用正则表达式有两种方式，一种是直接调用 re 模块中的函数，传入正则表达式和需要处理的字符串；一种是先通过 re 模块的 compile 函数创建正则表达式对象，然后再通过对象调用方法并传入需要处理的字符串。如果一个正则表达式被频繁的使用，我们推荐用 re.compile 函数创建正则表达式对象，这样会减少频繁编译同一个正则表达式所造成的开销。

match 方法是从字符串的起始位置进行正则表达式匹配，返回 Match 对象或 None。search 方法会扫描整个字符串来找寻匹配的模式，同样也是返回 Match 对象或 None。

#### 📖 什么是 Python 中的魔术方法？

魔术方法也称为魔法方法，是 Python 中的特色语法，也是 Python 面向协议变成的基础。

| 魔术函数                                                     | 作用               |
| ------------------------------------------------------------ | ------------------ |
| `__new__`、`__init__`、`__del__`                             | 创建和销毁对象相关 |
| `__eq__`、`__ne__`、`__lt__`、`__gt__`、`__le__`、`__ge__`   | 关系运算符相关     |
| `__pos__`、`__neg__`、`__invert__`                           | 一元运算符相关     |
| `__lshift__`、`__rshift__`、`__and__`、`__or__`、`__xor__`   | 位运算相关         |
| `__enter__`、`__exit__`                                      | 上下文管理器协议   |
| `__iter__`、`__next__`、`__reversed__`                       | 迭代器协议         |
| `__int__`、`__long__`、`__float__`、`__oct__`、`__hex__`     | 类型/进制转换相关  |
| `__str__`、`__repr__`、`__hash__`、`__dir__`                 | 对象表述相关       |
| `__len__`、`__getitem__`、`__setitem__`、`__contains__`、`__missing__` | 序列相关           |
| `__add__`、`__sub__`、`__mul__`、`__div__`、`__floordiv__`、`__mod__` | 算术运算符相关     |

#### 📖 说一下你对 Python 中模块和包的理解？

每个 Python 文件就是一个模块，而保存这些文件的文件夹就是一个包，但是这个作为 Python 包的文件夹必须要有一个名为 `__init__.py` 的文件，否则无法导入这个包。通常一个文件夹下还可以有子文件夹，这也就意味着一个包下还可以有子包，子包中的 `__init__.py` 并不是必须的。

模块和包解决了 Python 中命名冲突的问题，不同的包下可以有同名的模块，不同的模块下可以有同名的变量、函数或类。在 Python 中可以使用 `import` 或 `from ... import ...` 来导入包和模块，在导入的时候还可以使用 `as` 关键字对包、模块、类、函数、变量等进行别名。

#### 📖 什么情况下会出现 `KeyError`、`TypeError`、`ValueError`？

通过一个字典 a，执行 `int(a['x'])` 这个操作就有可能引发上述三种类型的异常。

- 如果字典中没有键 x，会引发 KeyError；
- 如果键 x 对应的值不是 str、float、int、bool 以及 bytes-like 类型，在调用 int 函数构造 int 类型的对象时，会引发 TypeError；
- 如果 a[x] 是一个字符串或者字节串，而对应的内容又无法处理成 int 时，将引发 ValueError。

#### 📖 说说对 Python 中的浅拷贝和深拷贝的理解？

浅拷贝通常只复制对象本身，而深拷贝不仅会复制对象，还会递归的复制对象所关联的对象。

一个对象如果直接或间接的引用了自身，会导致无休止的递归拷贝。Python 通过 copy 模块中的 copy 和 deepcopy 函数来实现浅拷贝和深拷贝操作，其中 deepcopy 可以通过 memo 字典来保存已经拷贝过的对象，从而避免自引用递归问题。

deepcopy 函数的本质其实就是对象的一次序列化和一次返回序列化，显然我们可以使用 pickle 模块的 dumps 和 loads 来做到。

另外，需要了解的是：

- 列表的切片操作 `[:]` 相当于实现了列表对象的浅拷贝；
- 字典的 copy 方法可以实现字典对象的浅拷贝；

#### 📖 说一下 Python 中变量的作用域？

Python 中有四种作用域，分别是局部作用域（Local）、嵌套作用域（Embedded）、全局作用域（Global）、内置作用域（Built-in），搜索一个变量时，会按照 LEGB 的顺序进行搜索，如果所有的作用域中都没有找到这个变量，就会引发 `NameError` 异常。

局部作用域（Local scope）：

局部作用域是在函数内部定义的范围。在函数内部定义的变量和函数只能在函数内部访问。

```python
def local_function():
    local_var = 20
    print(local_var)

local_function()  # 输出：20
print(local_var)  # 报错：NameError: name 'local_var' is not defined
```

嵌套作用域（Enclosing scope）：

嵌套作用域是指在函数内部定义的函数中的范围。内部函数可以访问外部函数中定义的变量。

```python
def outer_function():
    outer_var = 30

    def inner_function():
        print(outer_var)

    inner_function()  # 输出：30

outer_function()
```

全局作用域（Global scope）：

全局作用域是在整个程序中都可访问的范围。在函数外部定义的变量和函数属于全局作用域。

```python
global_var = 10

def global_function():
    print("This is a global function")

print(global_var)  # 输出：10
global_function()  # 输出：This is a global function
```

内置作用域（Built-in scope）：

内置作用域是 Python 解释器中默认提供的范围，包含了一些内置的函数和变量，如 `print()`、`len()` 等。

```python
print(len([1, 2, 3]))  # 输出：3
```



