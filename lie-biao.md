格式

```
>>> squares = [1,2,4,5,6,7,89,0]
>>> squares
[1, 2, 4, 5, 6, 7, 89, 0]
>>>
```

索引与切片

```
>>> squares[0] #indexing returns the item
1
>>> squares[-1]
0
>>> squares[-3:] # slicing returns a new list
[7, 89, 0]
>>>
返回列表的新（浅）副本
>>> squares[:]
[1, 2, 4, 5, 6, 7, 89, 0]
>>>
串联
>>> squares + [123,345,567,789,534]
[1, 2, 4, 5, 6, 7, 89, 0, 123, 345, 567, 789, 534]
>>>
```

可变字符【字符串不能根据索引修改，列表可以】

```
>>> cubes = [1,2,3,4,56,7,8,9] # someting's wrong here
>>> 4 ** 3 # the cubes of 4 is 64,not 65!
64
>>> cubes[3] = 64 #replace the wrong value
>>> cubes
[1, 2, 3, 64, 56, 7, 8, 9]
>>>
```

append  末尾追加

```
>>> cubes.append(5)
>>> cubes.append(7**3)
>>> cubes
[1, 2, 3, 64, 56, 7, 8, 9, 5, 343]
>>>
```

增删改

```
>>> letters = ['q','w','e','h','s','i','y','z']
>>> letters
['q', 'w', 'e', 'h', 's', 'i', 'y', 'z']
>>> # replace some values
...
>>> letters[2:5] = ['h','c','u']
>>> letters
['q', 'w', 'h', 'c', 'u', 'i', 'y', 'z']
>>> # now remove them
...
>>> letters[2:5] = []
>>> letters
['q', 'w', 'i', 'y', 'z']
>>> #clear the list by replacing all the elements with an empty list
...
>>> letters[:] = []
>>> letters
[]
>>>
```

len\(\)

```
>>> letters = ['a','gh','a','g','n']
>>> len(letters)
5
>>>
```

嵌套

```
>>> a = ['a','b','x']
>>> n = [1,2,3,4]
>>> x = [a,n]
>>> x
[['a', 'b', 'x'], [1, 2, 3, 4]]
>>> x[0]
['a', 'b', 'x']
>>> x[0][1]
'b'
>>>

```



