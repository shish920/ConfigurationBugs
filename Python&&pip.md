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
> then correct ` from pip import main` to `from pip import __main__` and`sys.exit(main()) ` to `sys.exit(__main__._main()) `  

#### Problem3
pip install xxx so slowly

#### Solution3
add parameter -i 
>pip install xxx -i https://pypi.tuna.tsinghua.edu.cn/simple
reference:https://zhuanlan.zhihu.com/p/46975553

#### Problem4
vscode jupyter can not show plt.show() 

#### Solution4
%matplotlib inline
