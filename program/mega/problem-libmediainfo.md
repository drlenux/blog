### Mega: error while loading shared libraries: libmediainfo.so.0: cannot open shared object file: No such file or directory
[home][go-home] / [Програмное обеспичение][go-program] / [Mega][go-mega] / **libmediainfo.so.0**

---

**Проблемма с установкой на Ubuntu 18.04.1 **
```log
error while loading shared libraries: `libmediainfo.so.0`: cannot open shared object file: No such file or directory
```
 
 Решение:
 - 1 
 
 ```bash
 sudo apt install libmediainfo0v5
 ```
 
 - 2
 
 ```bash
 sudo apt --fix-broken install
 ```
 
 
[go-home]: ../../index.md
[go-program]: ../index.md
[go-mega]: ./index.md
