---
title: "My macOS Setup"
date: 2021-02-02T22:48:52+08:00
draft: false
tags: ["macOS"]
categories: ["Mac/Linux杂七杂八"]
featured_image: ""
description: ""
---

[TOC]

> 创建于：2021-02-02
> 更新时间：2021-08-17

📝因为使用黑苹果，因此经常需要重新安装系统。本文记录我的`mac`的设置，以及我常用的软件、工作环境等信息，以便能够更快地完成macOS的环境配置。

## 🆕 调整新`mac`的系统设置

1. 登陆apple id

2. 设置 --> 显示器 --> 更多空间

3. 系统偏好设置 -> 辅助功能 -> 指针控制 -> 触控板选项 -> 启用拖移（三指拖移）

4. 键盘，设置触控栏显示f1,f2等键

5. 配置访达，网格间距拉到最小，文字大小10，排序方式名称，分组方式种类。用作默认。

6. 将个人的home目录和dev目录加入左侧边栏

7. `launchpad`图标大小调整（可选）

   ```bash
   defaults write com.apple.dock springboard-columns -int 16
   defaults write com.apple.dock springboard-rows -int 10
   defaults write com.apple.dock ResetLaunchPad -bool TRUE # 将系统应用和用户应用分页
   killall Dock
   ```

## 🪜 科学上网

macOS科学上网工具：[clashX](https://github.com/yichengchen/clashX)

## 🔧 安装基础工具包

```bash
xcode-select --install
```

## 💼 包管理软件

macOS上一般使用第三方包管理软件，最常见的是：[homebrew](https://brew.sh/index_zh-cn)，直接在命令行执行以下命令（需要🪜）：

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## 🌉 生成ssh key

主要是用于下载git项目。 执行以下命令，一路回车，密钥默认存放在`~/.ssh`目录下，以`.pub`结尾的便是公钥：

```bash
ssh-keygen -t ed25519 -C "mymbp@home"
```

## 📃 配置工作环境

我将平时经常使用的软件，命令行工具以及其配置维护在我个人的[dotfiles](git@github.com:oops-lgtm/dotfiles.git)仓库中。可以参考[Install](https://github.com/oops-lgtm/dotfiles#install)一节进行安装。

在终端配置了代理的情况下，安装脚本会提示是否使用`Brewfile`来安装软件，一般在拿到新系统的时候，我都会选择`y`(es)。
PS. 安装软件的过程时间较长，可以选择跳过，等到用的时候在进行安装。

### 常用软件

👇下面这个表格汇总了一些我的mac上安装的软件（星号代表已经集成到了Brewfile中）：

| 软件               | 说明                     | 官网                                                         | Brewfile |
| :----------------- | :----------------------- | :----------------------------------------------------------- | :------: |
| google-chrome      | 谷歌浏览器               | https://www.google.com/chrome/                               |          |
| typora             | 所见即所得markdown编辑器 | https://typora.io/                                           |    *     |
| appcleaner         | 软件卸载                 | https://freemacsoft.net/appcleaner/                          |    *     |
| iterm2             | terminal替代品           | https://iterm2.com/                                          |    *     |
| alacritty          | terminal替代，据说性能好 | https://github.com/alacritty/alacritty                       |    *     |
| tmux               | terminal分屏             | https://github.com/tmux/tmux/wiki                            |    *     |
| Alfred4            | finder替代品             | https://www.alfredapp.com/                                   |    *     |
| visual-studio-code | 编辑器，maybe IDE        | https://code.visualstudio.com/                               |    *     |
| wechat             | 微信                     | https://weixin.qq.com/                                       |          |
| 企业微信           | 工作使用                 | https://work.weixin.qq.com/                                  |          |
| WPS                | 办公套件                 | https://mac.wps.cn/                                          |          |
| Skim               | PDF阅读器                | https://skim-app.sourceforge.io/                             |          |
| Snipaste           | 截图工具                 | https://www.snipaste.com/                                    |    *     |
| MacTex             | Latex编译器              | http://www.tug.org/mactex/                                   |          |
| texstudio          | Latex编辑器              | https://www.texstudio.org/                                   |          |
| Zotero             | 论文管理                 | https://www.zotero.org/                                      |    *     |
| Itsycal            | 接管macOS日历            | https://www.mowglii.com/itsycal/                             |          |
| RunCat             | 一个奔跑的小猫           | https://kyome.io/runcat/                                     |    *     |
| 网易云音乐         | 听歌                     | https://music.163.com/#/download                             |    *     |
| OneNote            | 微软出品的笔记软件       | https://www.microsoft.com/zh-cn/microsoft-365/onenote/digital-note-taking-app |    *     |
| Notion             | 笔记软件                 | https://www.notion.so/                                       |    *     |
| logseq             | 双链笔记软件             | https://logseq.com/                                          |    *     |
| obsidian           | 知识库                   | https://obsidian.md/                                         |    *     |
| PicGo              | 图床管理                 | https://molunerfinn.com/PicGo/                               |    *     |
| XMind              | 思维导图工具             | https://www.xmind.cn/                                        |          |

### chrome插件

chrome插件通过google账号同步。

1. Google翻译：网页翻译工具
2. SwitchyOmega：一个代理设置工具
3. Bitwarden：密码管理插件，主要用来生成随机密码
4. OneNote Web Clipper：OneNote的网页剪藏插件
5. Zotero Connector：Zotero剪藏插件

## 🀄️ 字体

字体对于程序员来说太重要了，好看的字体能够使人心情舒畅。

| 名称           | 网址                                                         | 安装                                    | Brewfile |
| -------------- | ------------------------------------------------------------ | --------------------------------------- | :------: |
| fira code      | https://github.com/tonsky/FiraCode                           | brew install --cask font-fira-code      |    *     |
| JetBrains Mono | https://www.jetbrains.com/lp/mono/<br />https://github.com/JetBrains/JetBrainsMono | brew install --cask font-jetbrains-mono |          |

## 🎙️ 总结

以上就是我的`mac setup`的全过程，仅供参考。

另外也可参考：https://sourabhbajaj.com/mac-setup/

<br> 

<center>  ·End·  </center>
