# cpprestsdk4mingw
a cpprestsdk port to mingw32
## usages:
1. replace cpprestsdk/Release with this git.
2. modify your winnt.h of mingw platform, make C_ASSERT work correctly.
3. if any template typename U in boost headers confilt with macro U in cpprest, change the typename U in boost headers.
