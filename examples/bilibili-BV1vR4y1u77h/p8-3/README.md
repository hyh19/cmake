# p8

<https://www.bilibili.com/video/BV1vR4y1u77h?p=8>

```bash
cd build && \
rm -rf * && \
cmake .. && \
make

$ ll bin/libhello.so*
lrwxrwxrwx 1 gitpod gitpod    13 Jun 17 14:42 bin/libhello.so -> libhello.so.1*
lrwxrwxrwx 1 gitpod gitpod    15 Jun 17 14:42 bin/libhello.so.1 -> libhello.so.1.2*
-rwxr-xr-x 1 gitpod gitpod 16168 Jun 17 14:42 bin/libhello.so.1.2*
```
