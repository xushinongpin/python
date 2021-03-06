本节中的其余示例将假定f已创建一个名为的文件对象 。

要读取文件的内容，请调用f.read\(size\)，读取一些数据并将其作为字符串（在文本模式下）或字节对象（在二进制模式下）返回。 size是可选的数字参数。当省略size或negative时，将读取并返回文件的全部内容; 如果文件的大小是机器内存的两倍，那么这就是你的问题。否则，最多读取并返回大小字节。如果已到达文件末尾，f.read\(\)则返回空字符串（''）。

```
>>> with open('fibo') as f:
...     read_data = f.read()
...
>>> read_data
''
>>>
```

本节中的其余示例将假定f已创建一个名为的文件对象 。

要读取文件的内容，请调用f.read\(size\)，读取一些数据并将其作为字符串（在文本模式下）或字节对象（在二进制模式下）返回。 size是可选的数字参数。当省略size或negative时，将读取并返回文件的全部内容; 如果文件的大小是机器内存的两倍，那么这就是你的问题。否则，最多读取并返回大小字节。如果已到达文件末尾，f.read\(\)则返回空字符串（''）。

&gt;&gt;&gt;

&gt;&gt;&gt; f.read\(\)

'This is the entire file.\n'

&gt;&gt;&gt; f.read\(\)

''

f.readline\(\)从文件中读取一行; 换行符（\n）留在字符串的末尾，如果文件没有以换行符结尾，则只在文件的最后一行省略。这使得返回值明确无误; 如果f.readline\(\)返回一个空字符串，则表示已到达文件末尾，而空行表示为'\n'一个只包含一个换行符的字符串。

&gt;&gt;&gt;

&gt;&gt;&gt; f.readline\(\)

'This is the first line of the file.\n'

&gt;&gt;&gt; f.readline\(\)

'Second line of the file\n'

&gt;&gt;&gt; f.readline\(\)

''

要从文件中读取行，可以循环遍历文件对象。这是内存高效，快速，并导致简单的代码：

&gt;&gt;&gt;

&gt;&gt;&gt; for line in f:

...     print\(line, end=''\)

...

This is the first line of the file.

Second line of the file

如果要读取列表中文件的所有行，也可以使用 list\(f\)或f.readlines\(\)。

f.write\(string\)将string的内容写入文件，返回写入的字符数。

&gt;&gt;&gt;

&gt;&gt;&gt; f.write\('This is a test\n'\)

15

在编写之前，需要将其他类型的对象转换为字符串（在文本模式下）或字节对象（在二进制模式下）：

&gt;&gt;&gt;

&gt;&gt;&gt; value = \('the answer', 42\)

&gt;&gt;&gt; s = str\(value\)  \# convert the tuple to string

&gt;&gt;&gt; f.write\(s\)

18

f.tell\(\) 返回一个整数，给出文件对象在文件中的当前位置，表示为二进制模式下文件开头的字节数和文本模式下的不透明数字。

要更改文件对象的位置，请使用。通过向参考点添加偏移来计算位置; 参数点由from\_what参数选择。甲from\_what从文件的开头0措施值，1使用当前文件位置，和2使用该文件作为参考点的端部。 from\_what可以省略，默认为0，使用文件的开头作为参考点。f.seek\(offset, from\_what\)

&gt;&gt;&gt;

&gt;&gt;&gt; f = open\('workfile', 'rb+'\)

&gt;&gt;&gt; f.write\(b'0123456789abcdef'\)

16

&gt;&gt;&gt; f.seek\(5\)      \# Go to the 6th byte in the file

5

&gt;&gt;&gt; f.read\(1\)

b'5'

&gt;&gt;&gt; f.seek\(-3, 2\)  \# Go to the 3rd byte before the end

13

&gt;&gt;&gt; f.read\(1\)

b'd'

在文本文件中（那些b在模式字符串中没有打开的文件），只允许相对于文件开头的搜索（寻找到文件结尾的例外），唯一有效的偏移值是从，或者返回的那些，或者零。任何其他偏移值都会产生未定义的行为。seek\(0, 2\)f.tell\(\)

文件对象有一些额外的方法，如isatty\(\)和 truncate\(\)其中较不频繁地使用的; 有关文件对象的完整指南，请参阅“库参考”。

### 使用保存结构化数据

可以轻松地将字符串写入文件并从文件中读取。数字需要更多的努力，因为该read\(\)方法只返回字符串，它必须传递给类似的函数int\(\)，它接受类似的字符串'123' 并返回其数值123.当您想要保存更复杂的数据类型，如嵌套列表和字典，手工解析和序列化变得复杂。

Python允许您使用称为JSON（JavaScript Object Notation）的流行数据交换格式，而不是让用户不断编写和调试代码以将复杂的数据类型保存到文件中。调用的标准模块json可以采用Python数据层次结构，并将它们转换为字符串表示形式; 这个过程称为序列化。从字符串表示中重建数据称为反序列化。在序列化和反序列化之间，表示对象的字符串可能已存储在文件或数据中，或通过网络连接发送到某个远程机器。

注意 JSON格式通常被现代应用程序用于允许数据交换。许多程序员已经熟悉它，这使其成为互操作性的良好选择。

如果您有一个对象x，则可以使用一行简单的代码查看其JSON字符串表示：

```
>>> import json
>>> json.dumps([1,'simple','list'])
'[1, "simple", "list"]'
>>>
```

dumps\(\)调用该函数的另一个变体dump\(\)，只是将对象序列化为文本文件。因此，如果f是一个 文本文件，对象为写入打开，我们可以这样做：



