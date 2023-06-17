# p8

<https://www.bilibili.com/video/BV1vR4y1u77h?p=8>

```bash
cd build && \
rm -rf * && \
cmake .. && \
make

$ ll bin/libhello*
-rw-r--r-- 1 gitpod gitpod  2894 Jun 17 14:43 bin/libhello.a
lrwxrwxrwx 1 gitpod gitpod    13 Jun 17 14:43 bin/libhello.so -> libhello.so.1*
lrwxrwxrwx 1 gitpod gitpod    15 Jun 17 14:43 bin/libhello.so.1 -> libhello.so.1.2*
-rwxr-xr-x 1 gitpod gitpod 16168 Jun 17 14:43 bin/libhello.so.1.2*

$ sudo make install
-- Installing: /usr/local/include/hello/hello.h
-- Installing: /usr/local/lib/libhello.so.1.2
-- Installing: /usr/local/lib/libhello.so.1
-- Installing: /usr/local/lib/libhello.so
-- Installing: /usr/local/lib/libhello.a
```
