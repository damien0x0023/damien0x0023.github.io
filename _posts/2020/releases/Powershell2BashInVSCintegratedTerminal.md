---
layout: post
title: Manually Replace powershell with Bash from the Visual Studio Code integrated terminal
category: it
tags: [it]
excerpt: powershell to bash
no-post-nav: true
---

# Manually Replace powershell with Bash from the Visual Studio Code

by Damien

VSCode is the easy-to-use and free IDE after I suffered from many development environments for a long term. The default integrated terminal of VSCode in Win10 is powershell, which is not convenient for users who are used to UNIX-based OS terminal. Therefore, here is a simple manual way to convert the default temianl to Bash.  
&emsp;&emsp;VSCode是一个简单易用且免费的集成开发环境，在我长期经受许多开发环境的折磨后。其默认的的集成终端是powershell，对那些习惯于UNIX类系统终端的用户来说是不便利的。因此，这里简单介绍一种将默认的终端转化为Bash的手动方法。

## Bash with Git

There are many versions of Bash, and here I recommend the version with Git installation by default. It is because Git is a popular distributed version control system, which is a necessary tool for developers using Windows. Instead of installing Bash independently, we thus can replace the default shell in VSCode with it to save time for Bash configuring.  
&emsp;&emsp;有许多版本的Bash，在这里我推荐伴随着Git的默认安装的版本。这是因为Git是一个流行的分布式版本控制系统，对于使用win10的开发者来说是必备的工具。不用独立安装Bash，我们因此可以将其用来代替VSCode中默认的powershell，从而节省配置Bash的时间。

1. Install Git from Official Website

For Git installation, please download the Windows version directly from its [ official website](https://git-scm.com/download/win).  
&emsp;&emsp;对于Git的安装，请参照Git的官方网站。

2. Confirm the installation path of Git

![](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/it/gitDirectory.png "Git Directory in author's device")

First of all, we need to confirm the path of the Bash client. Open and locate Bash in the Git installation directory, if Git is alreadly installed on the device. The figure above shows the Git installation directory in my device, so I can confirm that the  path of Bash to be used is as follows:  
&emsp;&emsp;首先，我们需要确认Bash客户端的路径。打开并找到Git安装路径中的Bash，如果该设备已经安装了Git。上图为我的设备中的Git安装目录，我因此可以确认所需要用到的Bash的路径如下：

```
D:\Program Files\Git\git-bash.exe
```

3. Open Visual Studio Code and open the command palette using Ctrl + Shift + P. 

![](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/it/commandPalette.png "Open command palette and type commands")

4. Type "open user settings" and press Enter.

5. Select "Feature"->"Terminals" in the navigation bar on the left, and 



