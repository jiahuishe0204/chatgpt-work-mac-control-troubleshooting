# Work 无法控制本机浏览器：先确认连接到哪里

我遇到的问题是：ChatGPT 桌面版已安装、系统操控权限已开启，但部分 Work 会话仍无法启动或访问本机浏览器。关键原因在于，**桌面版和权限开关不等于当前 Work 会话已连上本机控制执行端**。不同会话可能连接到不同执行环境。

排查时，终端不是用来盲目试命令，而是用只读证据确认故障在哪一层：会话执行端、本机控制通道、网络/代理、配置还是应用权限。我的记录里出现过本机 rendezvous WebSocket 超时，提示连接握手值得优先检查；但它是否就是当时故障的根因，尚未被对照验证。`respect_system_proxy = true` 也不能写成已证实修复。

我把这个思路整理成了可复制的提示词：让 AI 先识别操作系统和具体症状，再一次带用户做一个检查，并说明每一步在验证什么；Mac 和 Windows 使用各自的步骤，不盲目改配置。

排障记录：[GitHub 仓库](https://github.com/jiahuishe0204/chatgpt-work-mac-control-troubleshooting)

可直接复制：[通用排障提示词](https://github.com/jiahuishe0204/chatgpt-work-mac-control-troubleshooting/blob/main/PROMPT.md)

把真实问题拆成有证据的检查步骤，再沉淀成别人能复用的方法，这是我理解的 AI-native 实践。