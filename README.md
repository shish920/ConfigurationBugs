# ConfigurationBugs
record some configuration problems 
## *Workspace*  
Ubuntu 16.04  

## python  
Python 3.5.2 && Python 2.7.12  
#### Problem1
```
Traceback (most recent call last):
  File "/usr/bin/pip3", line 7, in <module>
    from pip._internal import main
ModuleNotFoundError: No module named 'pip._internal'
```
#### Solution1
you just need to modify your pip file instand of reinstalling pip
> type ` sudo gedit /usr/bin/pip3 `   
> then correct ` from pip._internal import main ` to `from pip import main `  
#### Problem2
```
Traceback (most recent call last):
  File "/usr/bin/pip", line 9, in <module>
    from pip import main
ImportError:cannot import name main
```
#### Solution2
> ` sudo gedit /usr/bin/pip`  
> then correct ` sys.exit(main()) ` to `sys.exit(__main__._main()) `  

## OpenCV   
> OpenCV 3.4.0   

**Attention: remember to extract your installation package in /home/username/**  
#### Problem1  
> using ` cv::Mat image = imread('1.jpg', IMREAD_COLOR); ` can not open picture.  
#### Solution1  
> correct ` '1.jpg' ` to ` '/home/username/yourworkspace/1.jpg' `  

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
> cannot find -lGL   
#### Solution1
> https://www.cnblogs.com/coding-my-life/p/5677256.html  
#### Problem2
> TypeError: Property 'asciify' of object Core::Internal::UtilsJsExtension(0xa2d060) is not a function  
#### Solution2  
> https://www.cnblogs.com/zhangjunwu/p/7417566.html  
#### Problem3  
> error while loading shared libraries: libgstreamer-0.10.so.0: cannot open shared object file: No such file or directory  
#### Solution3  
> `sudo apt-get install apt-file ` 
> `sudo apt-file update`  
> `apt-file search libgstreamer-0.10.so.0`  
>  it may show `libgstreamer0.10-0: /usr/lib/x86_64-linux-gnu/libgstreamer-0.10.so.0  
>   libgstreamer0.10-0: /usr/lib/x86_64-linux-gnu/libgstreamer-0.10.so.0.30.0`  
> then install this package `sudo apt-get install libgstreamer0.10-0`  
> So using apt-file search you can find lacking files associated with their package, then install it and your problems will be solved.

