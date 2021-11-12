# cpprestsdk4mingw
a cpprestsdk port to mingw32
## license:
1. the origin cpprestsdk.zip is licensed by Microsoft Corporation.
## usages:
1. replace cpprestsdk/Release with this git.
2. modify your winnt.h of mingw platform, make C_ASSERT work correctly. ```#if defined(_WIN32) || defined(__mingw32__)```
4. if any template typename U in boost headers confilt with macro U in cpprest, change the typename U in boost headers.```replace U with UU```
5. change the ```Release\src\CMakeFiles\cpprest.dir\linklibs.rsp```, add the path of msvcrt_locale.dll
## dll:
1. define Z_PORT_MINGW
2. define CPPREST_FORCE_HTTP_LISTENER_ASIO
3. define CPPREST_FORCE_HTTP_CLIENT_ASIO
4. define \_UNICODE
## libraries dependence:
1. boost, should be compiled by a g++ that has the same major version as yours has.
2. openssl
3. zlib
4. websocketpp, which you can extract the project to cpprestsdk/Release/libs/websocketpp.
5. msvcrNN.dll, you should write manifest files to tell winsxs solve dlls, and rename for your binaries.
## boost.rpm and g++ version map
1. boost.1.54 -- mingw4.9x
2. boost.1.66 -- mingw7x
3. boost.1.69 -- mingw8x or mingw9x
4. boost.1.60 -- mingw6x
## mingw version
| |ver|vendor|default|other choice|
|:--|:--|:--|:--|:--|
 |1. | 4 | tdm | dw2 | |
 |2. | 5 | w64 | sjlj | dw2|
 |3. | 6 | w64 | sjlj |  dw2|
 |4. | 7 | w64 | sjlj | dw2| 
 |5. | 8 | w64 | sjlj | dw2| 
 |6. | 9 | tdm | dw2 |  |
 |7. | 10| tdm | dw2 |  |
