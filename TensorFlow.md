## TensorFlow  
TensorFlow > 1.3.0  
#### install
![tf_install](https://github.com/shish920/ConfigurationBugs/blob/master/pictures/tf_install.png)  
refer to https://www.bilibili.com/video/av22530538/?p=2  
#### Problem1  
![tf_cpu_set](https://github.com/shish920/ConfigurationBugs/blob/master/pictures/tf_set.png)  
#### Solution1
type `vim ~/.bashrc`, then add `export TF_CPP_MIN_LOG_LEVEL=2`at the end.
