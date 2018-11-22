## qt
> qt5.5.1

if you establish an empty project, and you also want to use OpenCV, type these codes in your .pro file
```
#Configs 
TEMPLATE = app 
CONFIG += console
CONFIG -= app_bundle
CONFIG -= qt
CONFIG += c++14

#Libraries
unix: CONFIG += link_pkgconfig

#OpenCV
unix: PKGCONFIG += opencv
```
#### Problem1  
`cannot find -lGL`   
#### Solution1
> https://www.cnblogs.com/coding-my-life/p/5677256.html  
#### Problem2
` TypeError: Property 'asciify' of object Core::Internal::UtilsJsExtension(0xa2d060) is not a function`  
#### Solution2  
> https://www.cnblogs.com/zhangjunwu/p/7417566.html  
#### Problem3  
` error while loading shared libraries: libgstreamer-0.10.so.0: cannot open shared object file: No such file or directory`  
#### Solution3  
> `sudo apt-get install apt-file ` 
> `sudo apt-file update`  
> `apt-file search libgstreamer-0.10.so.0`  
>  it may show `libgstreamer0.10-0: /usr/lib/x86_64-linux-gnu/libgstreamer-0.10.so.0  
>   libgstreamer0.10-0: /usr/lib/x86_64-linux-gnu/libgstreamer-0.10.so.0.30.0`  
> then install this package `sudo apt-get install libgstreamer0.10-0`  
> So using apt-file search you can find lacking files associated with their package, then install it and your problems will be solved.
