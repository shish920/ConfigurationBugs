# ConfigurationBugs
record some configuration problems 
## python  
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
remember to replace your installation package in /home/username/  
#### Problem1  
> Ubuntu 16.04, using ` cv::Mat image = imread('1.jpg', IMREAD_COLOR); ` can not open picture.  
#### Solution1  
> correct ` '1.jpg' ` to ` '/home/username/yourworkspace/1.jpg' `  
