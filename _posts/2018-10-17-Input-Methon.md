---
layout: post
title:  "Debian中文输入法设置"
date:   2018-10-17 11:35:04 +0800
categories: debian
tags: debian 中文 输入法 
author: duziee
---

* content
{:toc}


# Debian中文输入法设置

1. 配置软件源

   通过图形界面设置，打开 **Software & Updates**，修改下载网址，使用官方中国源 

   > 实测中国官方源有两个，通常中科大源是速度最快的。
   >
   > 1. ftp.cn.debian.org --> mirrors.ustc.edu.cn 中科大源
   > 2. ftp2.cn.debian.org -->  mirrors.tuna.tsinghua.edu.cn 清华大学源

2. 安装输入法

   #更新源列表

   sudo apt update 

```
#安装ibus拼音输入法，apt会自动安装ibus框架，和各种支持包。
```

   #由于**ibus-pinyin**已废弃，推荐安装**ibus-libpinyin**

   sudo apt install ibus-libpinyin 

1. 添加输入源

   **Account Setting** --> **All Setting** --> **Region & Language** --> **Input Sources**

   添加**Chinese （Intelligent Pinyin）**。

   #通过**ibus-setup**添加的输入法，实测无法调出使用。

2. 后备方法（配置用户文件）

​       对***$HOME/.bashrc***追加一下语句，并重新登录图面界面。

> export GTK_IM_MODULE=ibus
>
> export XMODIFFIERS=@IM=ibus
>
> export QT_IM_MODULE=ibus

------

## 失败小记

*主要是在Ubuntu 18.04经历*

- **sudo dpkg-reconfigure locals**

  如果选择了en_US.UTF-8会出现一大堆不同英文区域设置，如果选择了zh_CN.UTF-8会出新加坡等其他中文区域设置，即使先前并没有选择多于的那些语言区域选项。

- 通过**ibus-setup**添加的输入法，实测无法调出使用。



