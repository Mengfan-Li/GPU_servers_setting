# GPU_servers_setting
Server configuration operation and installation package

## XJTLU (2021.1)
###windows
server configuration：  
~  Quadro RTX 6000 *3  
~  CUDA 10.1  
~  conda 4.9.2  
~  Python 3.8.5  
~  Pytorch 1.7.1  

Since the server is located in the school’s intranet, a relay server is needed. Use the WSL function of win10 to install Ubuntu 20.4.
 
[Windows Subsystem for Linux Installation Guide for Windows 10](https://docs.microsoft.com/zh-cn/windows/wsl/install-win10)

Then the following command:  
Configure SSH: `ssh -J st_010@10.7.88.28 st_010@192.168.100.29 -R 18001`
Text: `p curl baidu.com `   
&ensp;&ensp;if return `<meta http-equiv="refresh" content="0;url=http://www.baidu.com/">` is correct

----

###Linux


