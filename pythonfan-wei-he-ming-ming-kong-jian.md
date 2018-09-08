在介绍类之前，我首先要告诉你一些Python的范围规则。类定义对命名空间有一些巧妙的技巧，你需要知道范围和命名空间如何工作才能完全理解正在发生的事情。顺便说一下，关于这个主题的知识对任何高级Python程序员都很有用。



让我们从一些定义开始。



一个命名空间是从名字到对象的映射。大多数名称空间当前都是作为Python词典实现的，但通常不会以任何方式显示（性能除外），并且它可能在将来发生变化。命名空间的示例是：内置名称集（包含诸如abs\(\)和内置异常名称之类的函数）; 模块中的全局名称; 和函数调用中的本地名称。在某种意义上，对象的属性集也形成了命名空间。关于命名空间的重要一点是，不同命名空间中的名称之间绝对没有关系; 例如，两个不同的模块都可以定义函数maximize而不会产生混淆 - 模块的用户必须在其前面加上模块名称。



顺便说一句，我对word 后面的任何名称使用word 属性 - 例如，在表达式中z.real，real是对象的属性 z。严格地说，对模块中名称的引用是属性引用：在表达式中modname.funcname，modname是模块对象并且funcname是它的属性。在这种情况下，模块的属性和模块中定义的全局名称之间恰好有一个直接的映射：它们共享相同的命名空间！ \[1\]



属性可以是只读的或可写的。在后一种情况下，可以分配属性。模块属性是可写的：你可以写 。可写属性也可以使用语句删除 。例如，将从名为的对象中删除该属性。modname.the\_answer = 42deldel modname.the\_answerthe\_answermodname



命名空间在不同时刻创建，具有不同的生命周期。包含内置名称的命名空间是在Python解释器启动时创建的，并且永远不会被删除。读入模块定义时会创建模块的全局命名空间; 通常，模块命名空间也会一直持续到解释器退出。由解释程序的顶级调用执行的语句（从脚本文件读取或交互式读取）被视为调用模块的一部分\_\_main\_\_，因此它们具有自己的全局命名空间。（内置名称实际上也存在于模块中;这称为builtins。）



函数的本地命名空间在调用函数时创建，并在函数返回或引发函数内未处理的异常时删除。（实际上，遗忘是描述实际情况的更好方法。）当然，递归调用每个都有自己的本地命名空间。



甲范围是Python程序，其中一个命名空间是可直接访问的文本区域。这里的“可直接访问”意味着对名称的非限定引用会尝试在命名空间中查找名称。



尽管范围是静态确定的，但它们是动态使用的。在执行期间的任何时候，至少有三个嵌套的作用域，其名称空间可以直接访问：



最先搜索的最内部范围包含本地名称

从最近的封闭范围开始搜索的任何封闭函数的范围包含非本地名称，但也包括非全局名称

倒数第二个范围包含当前模块的全局名称

最外面的范围（最后搜索）是包含内置名称的命名空间

如果名称声明为全局，则所有引用和赋值将直接转到包含模块全局名称的中间作用域。要重新绑定在最内层范围之外找到的变量，nonlocal可以使用该语句; 如果没有声明为非本地变量，那些变量是只读的（尝试写入这样的变量只会在最里面的范围内创建一个新的局部变量，保持同名的外部变量不变）。



通常，本地范围引用（文本）当前函数的本地名称。在外部函数中，本地作用域引用与全局作用域相同的名称空间：模块的名称空间。类定义在本地范围中放置另一个命名空间。



重要的是要意识到范围是以文本方式确定的：模块中定义的函数的全局范围是模块的命名空间，无论从何处或通过调用函数的别名。另一方面，名称的实际搜索是在运行时动态完成的 - 但是，语言定义在“编译”时朝着静态名称解析发展，所以不要依赖于动态名称解析！（事实上​​，局部变量已经静态确定。）



Python的一个特殊之处在于 - 如果没有global语句生效 - 对名称的赋值总是进入最内层范围。分配不复制数据 - 它们只是将名称绑定到对象。删除也是如此：该语句删除了本地范围引用的命名空间的绑定。实际上，引入新名称的所有操作都使用本地范围：特别是，语句和函数定义绑定本地范围中的模块或函数名称。del xximport



该global陈述可用于表明特定变量存在于全球范围内，并应在那里反弹; 该 nonlocal陈述表明特定变量存在于封闭范围内，应该在那里反弹。
