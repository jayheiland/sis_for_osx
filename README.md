
This is a macOS port of SIS, a software package for interactive optimization of sequential digital circuits.

Rf. https://ptolemy.berkeley.edu/projects/embedded/Alumni/pchong/sis.html

See the original copyright here:
https://ptolemy.berkeley.edu/projects/embedded/Alumni/pchong/sis/COPYING

## Building on macOS

To use the default "gcc" on your Mac.
```
./configure 

without warnings:
./configure CFLAGS="-w"

$ make
...
Making all in nova
gcc -DHAVE_CONFIG_H -I. -I. -I..  -I../port -I../sis/include   -w -c exact_graph.c
exact_graph.c:98:37: error: non-void function 'base_graph' should return a value [-Wreturn-type]
    if ((*net) == (CONSTRAINT *) 0) return; 
                                    ^
exact_graph.c:209:13: error: non-void function 'inter_graph' should return a value [-Wreturn-type]
                          return;
                          ^
2 errors generated.
```

---
HOWEVER, by this time, the sis/sis executable should have been successfully created:
```
$ ll sis/sis
-rwxr-xr-x  1 username  staff  3085376 May 11 21:06 sis/sis*
```

To use another "gcc", e.g., one installed using "brew":
```
./configure CC="gcc-8" CXX="g++-8"
```
