Python更换为默认源（pip）

```python
C:\Users\Susan\AppData\Roaming\pip\pip.ini
```

Python把新环境加入ipykernel

```python
conda install ipykernel #先在当前环境安装ipykernel
python -m ipykernel install --user --name=[environment name]
```

删除kernel

```python
jupyter kernelspec uninstall unwanted-kernel
```

**conda换源**

含有国内源的.condarc文件：C:\Users\Susan\\.condarc

```
show_channel_urls: true
default_channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
custom_channels:
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud

```

默认的：

```
channels:
  - defaults
ssl_verify: true
show_channel_urls: true
```

pip换源

```
查看源的列表：
pip config list

换回默认源：
pip config set global.index-url https://pypi.python.org/simple/

换成清华源：
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```



```
conda install -c menpo opencv
```

**CODE:**

前后三个引号配对，可以括住字符串换行的情况，输出的时候换行也照样输出

`sentence = """Who's going to win the Superbowl again? 
Mahomes maybe?"""`



```python
pi=3.14
str(int(float(pi)))
```

float(pi)是强制类型转换，把pi从str转为float类型
int(float(pi))也是强制类型转换，把float(pi)从float类型转为int类型。此时，int(float(pi))=3
str(int(float(pi)))最终把3转换为str类型

`sentence[0:9:2]`取第0位到第8位，step=2

`sentence[:-n] `去掉最后n位

`sentence[::-1] `整个sentence字符串倒序完整输出

`sentence.startswith('?')`返回值：boolean，看是否以问号打头

`sentence.endswith('?')`返回值：boolean，看是否以问号结尾

`my_array = sentence.split()`by default split on whitespaces, returns a list (see below)

`' '.join(my_array)`把my_array的各个元素从左到右用空格相连接起来

`list[],tuple(),set{}`

`zip(a,b)`把a和b相应的位置拼成一对，变成一个个的数组输出

`len(array)`返回array的长度



while语句的语法

```python
while 条件==true:
  code
```

if语句的语法

```python
if 条件==true:
  code
elif 条件==true：
	code
else
	code
```



关系运算

```python
and or not
(对应java和c的&& || !=)
```



取整：`a=3.75`

`3//a`3除以a 结果向下取整

`int(a)` 直接对a向下取整

`round(a)` 四舍五入，返回4.0

`math.ceil(a)` 向上取整，返回4.0

`math.modf(a)` 返回(0.75, 3.0)



表示空：

数组为空`arr == None`

表示无穷：

`a = float('inf')`



Binary Search二分查找

```python
def search(self, nums: List[int], target: int) -> int: 
        # if nums == None and len(nums) == 0
        # 1 <= nums.length <= 10^4, 所以第二个条件在这题可以删了
        # 如果nums这个array的地址为空
        if nums == None:
            return -1
        
        # python需要定义数据类型吗？好像不定义也行，但是这题mid必须得是int


        # 左指针指向index = 0，右指针指向index = array长度 - 1
        left = 0
        right = len(nums) - 1

        # 左指针和右指针不相邻的时候，执行while里面的代码
        while left + 1 < right :
            mid = (left + right) // 2 # 这题/和//有区别吗 等一下试试看。mid指针指向的index，是左右指针的index相加再除以2，并把这个数字向下取整
            if target == nums[mid]: # mid指向的index对应的数值正好是target
                return mid
            elif target < nums[mid]: # mid指针指向的index对应的数值有点大
                right = mid # 把范围限定在分界线的左边（让右指针往左
            else:
                left = mid # 把范围限定在分界线的右边（让左指针往右

        # 现在：左右指针做邻居
        # 如果左指针指向target，那么返回左指针指向的index。右边同理。找不到的话就return -1
        if target == nums[right] : 
            return right
        if target == nums[left] :
            return left
        return -1
```

