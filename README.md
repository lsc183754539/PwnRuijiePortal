# PwnRuijiePortal  
![python 3.7](https://img.shields.io/badge/Python-3.7-brightgreen.svg)
![Issuescolsed](https://img.shields.io/badge/Issues%20closed%20in-about%2012hours-brightgreen)
***  
2018年10月13日上传`getInfo.py`  

## ***为什么写这个？***  
早在去年就发现校园网认证获得的URL加密有规律(直接扔进notepad++进行HEX->ascii)，是一串不知道什么+IP+账号，但是一直不知道第一串是什么。  
前几天师哥突然说那个是固定的，然后突然就秒懂了。  
***  
## ***漏洞利用思路***  
~参考了两个大佬的代码，改进后的，暂时没做内容内容过滤~  
根据已知的信息(网络规划等，前几天看另一个大佬的代码，他做到了利用，但是对漏洞的分析并不正确，此处不做说明，涉及问题利益)，直接构造userIndex，对遍历的IP进行爆破  
借鉴大佬的代码，对程序采用了线程，加快速度，实测速度差不多4分钟可爆破一个用户。  
关于密码怎么来的，是锐捷工程师的疏忽，传输时对密码进行了加密，但是在前端显示的时候，会自动解码成明文，可直接通过Python读取  
暂时没写get的信息的过滤  
****  

2018年10月15日19点28分更新：`FuckRuijie.py`
1. 加入ping验证，对IP进行测试，不存活的IP跳过，提高效率
