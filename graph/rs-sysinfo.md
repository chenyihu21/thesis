```txt
========== START entry-static.exe rlimit_open_files ==========
Pass!
========== END entry-static.exe rlimit_open_files ==========
```

```txt
System Uptime: 3 seconds
Total RAM: 130646016 KB 
Free RAM: 114114560 KB 
Number of Processors: 4 
Memory Unit Size: 1 bytes
Current STACK limits: soft=65536
Set new STACK limits: soft=8388608, hard=16777216 
New STACK limits: soft=8388608
```

s1-starry
```txt
Testing memory allocation performance... 
Memory allocation time: 17.35 ms
Testing memory free performance... 
Memory free time: 18.18 ms
Testing memory access performance... 
Memory write time: 10.92 ms
Memory read time: 0.76 ms 
```

s1
```txt
Testing memory allocation performance... 
Memory allocation time: 0.03 ms
Testing memory free performance... 
Memory free time: 0.05 ms
Testing memory access performance...
Memory write time: 0.38 ms
Memory read time: 0.10 ms 
```

s2-local
```txt
Starting test: test_mmap 
file len: 27
mmap content: Hello, mmap successfully! 
Ending test: test_mmap
time: 0.12 ms 
```

s2-starry
```txt
Starting test: test_mmap 
file len: 27
mmap content: Hello, mmap successfully! 
Ending test: test_mmap
time: 111.25 ms 
```

page-fault
```txt
[  1.740581 0:5 starry:task:96] Enter user space:entry=0x404d7f,ustack=0x1,kstack=VA:0xffff8000008ee010
[  1.744583 0:5 starry:mm:172] Page fault at VA:0x0,access_flags:READ USER
[  1.766803 0:5 starry:mm:186] Task(5,"Task(4,\"userboot\")"):segmentation fault at VA:0x0,exit!
[  1.782333 0:4 starry:task:333] wait pid _5_ with code _-1_
```

return0
```txt
[  1.719986 0:4 starry:syscall_imp:57] Syscall rt_sigprocmask
[  1.721138 0:4 starry:syscall_imp:signal:13] sys_rt_sigprocmask:not implemented
[  1.722763 0:4 starry:syscall_imp:177] Syscall rt_sigprocmask return 0
```

starry
```txt
Testing memory allocation performance...
Memory mmap time: 60.90 ms
Testing memory free performance...
Memory free time: 259.63 ms
Testing memory access performance...
Memory write time: 84.50 ms
Memory read time: 11.78 ms
Testing memory protect performance...
Memory protect time: 48.65 ms
```

Linux
```txt
Testing memory allocation performance...
Memory mmap time: 25.52 ms
Testing memory free performance...
Memory free time: 47.71 ms
Testing memory access performance...
Memory write time: 86.24 ms
Memory read time: 13.15 ms
Testing memory protect performance...
Memory protect time: 11.83 ms
```