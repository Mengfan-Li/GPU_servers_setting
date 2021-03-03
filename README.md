# GPU_servers_setting
Server configuration operation and installation package

## XJTLU (2021.1)
windows：  
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

Linux：  
Because the school's server in the intranet has a relay server (springboard) in the middle, it needs to be reset.  
Reference：https://www.jianshu.com/p/8f262bc444f0  
~ Ubuntu 18.04  
~ Oracle Virtual Box  

Step1：Configure springboard machine password-free login  
Local configuration:`vim ~/.ssh/config `  
Enter the following in the config file: 
`Host *
    ControlPersist yes
    ControlMaster auto
    ControlPath ~/.ssh/%n:%p`  
After completing the configuration, log in to the springboard machine locally.  

Stp2:Set up ssh tunnel  
Enter the following command on the local command line:`ssh -N -f -L 6000:<intranet server ip>:22 -p <springboard port> username@<springboard ip> -o TCPKeepAlive=yes`  
The meaning of each parameter of the above command is as follows:  
-N tells the SSH client that this connection does not need to execute any commands. Just do port forwarding  
-f tells the SSH client to run in the background  
-L do local mapping port  
At this point, logging in to the local 6000 port is equivalent to logging in to the intranet server.  
`ssh -p 6000 server username@localhost`  

Step3:Configure pycharm  
Here you only need to configure the ip to `127.0.0.1`, the port to `6000`, and enter the account password of the intranet server to see the python installed on the server.



