# 中文版:
## 名称:
- [流氓软件终结者](https://liwei2.com/2015/11/27/378.html)的PowerShell重制版

## 说明:
#### 首先十分感谢 leave 支持 
#### 我为什么要用PowerShell把malware kill重新制作一遍?
    一方面CMD已经全面被Windows淘汰,作者也因为时间关系不能维护更新,并且PowerShell可以更好处理Windows上的脚本操作.
    另一方面,虽然我了解网络安全,但我的家人和我的朋友仍然是流氓软件的受害者,当我给他们处理类似问题时候,使用脚本可以一劳永逸.
#### Windows防流氓软件指南
    1.永远不要完全关闭UAC,这对malware,virus都能起到极大的防治作用.
    2.尽量使用功能单一的国外软件代替.
    3.如果你因为某些原因无法离开国产流氓软件(如某雷),请把他们扔在虚拟机内使用.
    4.安装/卸载/修复 软件时请注意右下角/左下角/各种死角 有没有
      这样的标志,做一个简单的逻辑题,就可以少一些麻烦和困扰.
    5.最后祝流氓软件 all go to hell , cheers! 渐行渐远,好自为之!
#### 目录介绍
    malware-kill目录     存放源版本(使用Bat编写)文件.
    CA目录               存放流氓软件的所有证书.
    latestBlockhosts.txt 存放需要屏蔽的域名→hosts格式
    ExistingCA.md        列出了CA中我收集的各大malware厂商证书列表.
    Kill-Malware.ps1     主脚本
    Restore-Status.ps1   恢复脚本
    两个ps1脚本为GBK编码(PowerShell输出中文真蛋疼),除此之外UTF-8. 

## 用法:
- Windows系统默认不能执行Powershell脚本,第一次运行Powershell脚本需要做如下操作:
```powershell
    Set-ExecutionPolicy   UnRestricted  #把脚本权限设置为最低
```
- 然后你就可以在PowerShell命令行中执行此脚本:
```
    .\Kill-malware.ps1
```
- 如果影响到了你的正常使用,执行恢复脚本:
```
    .\Restore-Status.ps1
```
- 如果不想拉黑某个证书,比如CNNIC,到CA目录下删除cnnic_CA.cer

## 开源协议:
- malware-kil作者[leave](https://liwei2.com/) 
- malware-kill文件夹以外的所有源文件的遵循MIT

