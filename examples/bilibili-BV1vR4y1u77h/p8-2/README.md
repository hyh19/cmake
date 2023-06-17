# p8

<https://www.bilibili.com/video/BV1vR4y1u77h?p=8>

```bash
cd build && rm -rf *

cmake ..

make

$ ll bin/libhello*
-rwxr-xr-x 1 gitpod gitpod 16168 Jun 17 13:05 bin/libhello.so*
-rw-r--r-- 1 gitpod gitpod  2902 Jun 17 13:05 bin/libhello_static.a
```

## Q&A

逐行解释以下 CMakeLists.txt

```
SET(LIBHELLO_SRC hello.cpp)

ADD_LIBRARY(hello_static STATIC ${LIBHELLO_SRC})
SET_TARGET_PROPERTIES(hello_static PROPERTIES OUTPUT_NAME "hello")
SET_TARGET_PROPERTIES(hello_static PROPERTIES CLEAN_DIRECT_OUTPUT 1)

ADD_LIBRARY(hello SHARED ${LIBHELLO_SRC})
SET_TARGET_PROPERTIES(hello PROPERTIES OUTPUT_NAME "hello")
SET_TARGET_PROPERTIES(hello PROPERTIES CLEAN_DIRECT_OUTPUT 1)
```

这是一个简单的CMakeLists.txt文件，用于构建两个版本的库：一个静态库（.a或.lib）和一个共享库（.so或.dll）。

下面是逐行解释：

```markdown
1. SET(LIBHELLO_SRC hello.cpp)
```

将变量`LIBHELLO_SRC`设置为`hello.cpp`。这个变量将在后面用于指定库的源文件。

```markdown
2. ADD_LIBRARY(hello_static STATIC ${LIBHELLO_SRC})
```

使用`hello.cpp`（`${LIBHELLO_SRC}`）创建一个名为`hello_static`的静态库。

```markdown
3. SET_TARGET_PROPERTIES(hello_static PROPERTIES OUTPUT_NAME "hello")
```

设置`hello_static`静态库的输出名称为`hello`。这意味着生成的库文件将被命名为`hello.a`（Linux/macOS）或`hello.lib`（Windows）。

```markdown
4. SET_TARGET_PROPERTIES(hello_static PROPERTIES CLEAN_DIRECT_OUTPUT 1)
```

设置`hello_static`静态库的`CLEAN_DIRECT_OUTPUT`属性为`1`。这意味着在执行`make clean`或类似的清理命令时，这个库的输出文件将被删除。

```markdown
5. ADD_LIBRARY(hello SHARED ${LIBHELLO_SRC})
```

使用`hello.cpp`（`${LIBHELLO_SRC}`）创建一个名为`hello`的共享库。

```markdown
6. SET_TARGET_PROPERTIES(hello PROPERTIES OUTPUT_NAME "hello")
```

设置`hello`共享库的输出名称为`hello`。这意味着生成的库文件将被命名为`libhello.so`（Linux）、`libhello.dylib`（macOS）或`hello.dll`（Windows）。

```markdown
7. SET_TARGET_PROPERTIES(hello PROPERTIES CLEAN_DIRECT_OUTPUT 1)
```

设置`hello`共享库的`CLEAN_DIRECT_OUTPUT`属性为`1`。这意味着在执行`make clean`或类似的清理命令时，这个库的输出文件将被删除。
