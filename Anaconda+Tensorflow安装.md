1.安装Anaconda  
前往 https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/ 下载对应版本的Anaconda  
下载完毕进行安装  
一路next，在Select Installation Type 中两个都勾选  
等待安装完成，打开cmd输入conda --version出现队形版本表示安装完成  
2.安装TensorFlow  
管理员身份运行Anacond Prompt  
conda create -n tensorflow python=3.6  
进入tensorflow环境：conda activate tensorflow  
下载tensorflow pip install tensorflow (tensorflow 已经可以支持python3.7）  
测试tensorflow安装是否成功：   
输入python进入python命令行   
输入import tensorflow as tf 结果不报错，说明安装成功   

activate tensorflow 激活tensorflow环境  
