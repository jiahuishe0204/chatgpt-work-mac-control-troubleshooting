# Work 无法控制 Mac 浏览器：一次实测排查

Mac 上装了 ChatGPT 桌面版，也开了电脑操控权限，部分 Work 会话仍可能无法访问本机浏览器。关键是检查**发生问题的那个会话**实际连到哪里：本次工具目标和命令执行端均显示为 Mac；另一次会话曾显示 Linux/Chromium，说明不同会话不能互相代替作证。

我在 Mac 接入的会话里实际操作了 Safari 页面导航，并检查了 Firefox 中的 GitHub 登录状态，确认本次会话能控制这两个本机浏览器。单次读取本机文件并不能证明桌面控制已连通。


用户已确认此前的 Work 问题已解决；本次实测确认当前会话连接 Mac，Safari 和 Firefox 操作成功，但没有隔离此前故障的具体根因。待确认：Work 发送按钮变灰的直接原因；`respect_system_proxy = true` 的因果作用未证实。

把一次真实故障排查整理成别人能复用的步骤，是我实践 AI-native 工作方式的一部分。

排障记录与检查清单：<https://github.com/jiahuishe0204/chatgpt-work-mac-control-troubleshooting>
