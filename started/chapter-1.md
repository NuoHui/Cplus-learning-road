# 入门学习

记录踩坑笔记。

## 初识 输入输出

```c++
#include <iostream>

int main() {
    std::cout << "Enter two numbers: " << std::endl;
    int v1 = 0, v2 = 0;
    std::cin >> v1 >> v2;
    std::cout << "the sum of  " << v1 << "and" << v2
        << "is" << v1 + v2 << std::endl;
    return 0;
}
```

开始在mac上直接执行，

```shell
gcc prog1.cc
```
会发现错误提示：

```shell
Undefined symbols for architecture arm64:
  "std::__1::locale::use_facet(std::__1::locale::id&) const", referenced from:
      std::__1::ctype<char> const& std::__1::use_facet<std::__1::ctype<char> >
```

发现需要使用标准C++库编译：

```shell
gcc -lstdc++ -o prog1 prog1.cc
```
这里主要说下`-o`命令，`-o`命令表示输出的意思，`gcc/g++`命令是非常灵活的，你不指定输出的文件名的时候默认生成的是`.exe`文件。

这个时候你就发现编辑成功，可以执行这个可执行文件了。

## while

```c++
#include <iostream>

int main() {
    int sum = 0, val = 1;
    while (val < 10) {
        sum += val;
        ++val;
    };
    std::cout << "sum of 1 to 10 inclusive is "
        << sum << std::endl;
    return 0;
}
```

## for

```c++
# include <iostream>

int main() {
    int sum = 0;
    for (int val = 1; val < 10; ++val) 
        sum += val;
    std::cout << "Sum of 1 to 10 is " << sum << std::endl;
    return 0;
}
```

```c++

#include <iostream>

int main() {
    int sum = 0, val = 0;
    while (std::cin >> val)
        sum += val;
    std::cout << "Sum is " << sum << std::endl;
    return 0;
}
// mac ctrl+d 退出
```




