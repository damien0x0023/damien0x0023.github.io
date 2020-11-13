---
layout: post
title: Manually set default terminal to Bash in the Visual Studio Code
category: it
tags: [it]
excerpt: powershell to bash
no-post-nav: true
---

# Manually set default terminal to Bash in the Visual Studio Code

by Damien

Visual Studio Code (VSCode) is the easy-to-use and free IDE after I suffered from many development environments for a long term. The default integrated terminal in Windows version of VSCode is powershell, which is not convenient for users who are used to UNIX-based OS terminal. Therefore, here is a simple manual way to convert the default temianl to Bash.  
&emsp;&emsp;VSCode是一个简单易用且免费的集成开发环境，在我长期经受许多开发环境的折磨后。其默认的的集成终端是powershell，对那些习惯于UNIX类系统终端的用户来说是不便利的。因此，这里简单介绍一种将默认的终端转化为Bash的手动方法。

## Bash with Git

There are many versions of Bash, and here I recommend the version with Git installation by default. It is because Git is a popular distributed version control system, which is a necessary tool for developers using Windows. Instead of installing Bash independently, we thus can replace the default shell in VSCode with it to save time for Bash configuring.  
&emsp;&emsp;有许多版本的Bash，在这里我推荐伴随着Git的默认安装的版本。这是因为Git是一个流行的分布式版本控制系统，对于使用win10的开发者来说是必备的工具。不用独立安装Bash，我们因此可以将其用来代替VSCode中默认的powershell，从而节省配置Bash的时间。

1. Install Git from Official Website

For Git installation, please download the Windows version directly from its [ official website](https://git-scm.com/download/win).  
&emsp;&emsp;对于Git的安装，请参照Git的官方网站。

2. Confirm the installation path of Bash

![](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/it/gitDirectory.png "Bash under git Directory in author's device")

First of all, we need to confirm the path of the Bash client. Open and locate Bash in the Git installation directory, if Git is alreadly installed on the device. The figure above shows the Git installation directory in my device, so I can confirm that the  path of Bash to be used is as follows:  
&emsp;&emsp;首先，我们需要确认Bash客户端的路径。打开并找到Git安装路径中的Bash，如果该设备已经安装了Git。上图为我的设备中的Git安装目录，我因此可以确认所需要用到的Bash的路径如下：

```
D:\Program Files\Git\bin\bash.exe
```

3. Open Visual Studio Code and open the command palette using Ctrl + Shift + P. 

4. Type "open settings json", then choose "Open Settings (JSON)" and press Enter.

![](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/it/commandPalette.png "Open command palette and type commands")

5. Add the following lines at the end of the JSON file which is displayed in the pane.

```
    "terminal.integrated.shell.windows": "D:\\Program Files\\Git\\git-bash.exe",
```

![](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/it/shellSetting.png "Type key-value pair to reset user setting")


6. Close and reopen the Visual Studio Code instance.

![](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/it/defaultShellChanged.png "New default Shell")

&emsp;The default terminal has been changed to Bash.

Note1: Type "powershell", "cmd" or "bash" in the integrated terminal and press Enter, we can switch from one to another. 

![](https://raw.githubusercontent.com/damien0x0023/damien0x0023.github.io/master/assets/images/2020/it/shellSwitch.png "Shell switch")

Note2: Latest version of VSCode may find the bash automatically if the git is installed under system drive with folder such as "C:\Program Files\Git\..." by default. We can choose the option "Select Default Shell" under the dropbox or type the listing command in command palette to check it later.

```
    terminal: select default shell
```


## Reference 

- Microsoft - Visual Studio Code - [Integrated Terminal](https://code.visualstudio.com/docs/editor/integrated-terminal)

- StackOverflow - [How to add multiple terminals in VS Code?](https://stackoverflow.com/questions/43427631/how-to-add-multiple-terminals-in-vs-code/50890703#50890703)

- StackOverflow - [How do I use Bash on Windows from the Visual Studio Code integrated terminal?](https://stackoverflow.com/questions/42606837/how-do-i-use-bash-on-windows-from-the-visual-studio-code-integrated-terminal)



