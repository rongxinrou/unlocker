适用于VMware Workstation的macOS Unlocker V3.0
==========================================

+ ------------------------------------------------- ---------------------------- +
|重要提示：|
| ========== |
| |
|在使用新的|之前，请务必卸载以前版本的Unlocker
|版。如果不这样做，可能会导致VMware无法使用。 |
| |
+ ------------------------------------------------- ---------------------------- +

1.简介
---------------

Unlocker 3专为VMware Workstation 11-15和Player 7-15而设计。

如果您使用的是早期产品，请继续使用Unlocker 1。

版本3已经过测试：

* Windows和Linux上的工作站11/12/14/15
* Windows和Linux上的工作站播放器7/12/14/15

补丁代码根据产品执行以下修改
修补：

*修复vmware-vmx和衍生产品以允许macOS启动
*修复vmwarebase .dll或.so以允许在创建VM期间选择Apple
*下载适用于macOS的最新VMware Tools副本

请注意，并非所有产品都通过安装工具菜单项识别darwin.iso。
您必须手动安装darwin.iso，例如在Workstation 11和Player 7上。

在所有情况下，请确保VMware未运行，并且任何后台客户都有
被关闭了。

代码是用Python编写的。

2.先决条件
----------------

该代码需要Python 2.7才能工作。大多数Linux发行版都附带兼容版
Python解释器，无需任何其他软件即可工作。

Windows Unlocker使用PyInstaller有一个Python脚本的打包版本，
所以不需要安装Python。

3.限制
--------------

如果您在Windows上使用VMware Player或Workstation，则可能会获得核心转储。

最新的Linux产品没问题，也没有显示这个问题。

+ ------------------------------------------------- ---------------------------- +
|重要提示：|
| ========== |
| |
|如果您创建新VM，VMware可能会停止并创建核心转储。 |
|有两种方法可以解决此问题：|
| |
| 1.将VM更改为HW 10  - 这不会影响性能。 |
| 2.编辑VMX文件并添加：|
| smc.version =“0”|
| |
+ ------------------------------------------------- ---------------------------- +

4. Windows
----------
在Windows上，您需要以管理员身份运行cmd.exe或使用
资源管理器右键单击命令文件并选择“以管理员身份运行”。

win-install.cmd  - 补丁VMware
win-uninstall.cmd  - 恢复VMware
win-update-tools.cmd  - 检索最新的macOS客户工具

5. Linux
---------
在Linux上，您需要是root用户或使用sudo来运行脚本。

您可能需要确保Linux脚本具有执行权限
通过对2个文件运行chmod + x。

lnx-install.sh  - 补丁VMware
lnx-uninstall.sh  - 恢复VMware
lnx-update-tools.sh  - 检索最新的macOS客户工具
   
谢谢
---------

感谢Zenith432最初构建C ++解锁器和Mac Son of Knife
（MSoK）进行所有测试和支持。

还要感谢Sam B找到ESXi 6的解决方案并帮助我
调试专长。 Sam还编写了修补ESXi ELF文件和代码的代码
修改了解锁程序代码以在ESXi 6.5环境中的Python 3上运行。


历史
-------
27/09/18 3.0.0  - 首次发布
02/10/18 3.0.1  - 修复了gettools.py与Python 3一起使用并正确下载darwinPre15.iso
10/10/18 3.0.2  - 修复了使用Windows可执行文件的防病毒软件的误报
                - 允许Python 2和3从Bash脚本运行Python代码


（c）2011-2018 Dave Parsons
