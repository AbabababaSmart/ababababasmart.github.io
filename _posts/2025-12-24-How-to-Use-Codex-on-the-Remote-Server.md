---
title: 'How to Use Codex on the Remote Server?'
date: 2025-12-24
permalink: /posts/2025/12/2025-12-24-How-to-Use-Codex-on-the-Remote-Server/
---

有时候我们想在VSCode连接远程服务器的情况下，使用Codex插件来辅助编程。但由于某些转发原因，Codex 可能会不太配合：首先在第一步登录时就会报错，如下图所示。
![image](images/blog/codex/{1988EAE4-3BDD-422D-92CE-26B5E7475116}.png)
因此，这篇教程主要记录如何在VSCode连接远程服务器的情况下使用Codex插件。

### 前置条件: 
1. GPT plus/pro账户, 以确保能够使用codex功能
2. 在远程服务器上配置成功的代理, 具体配置方法可以参考 [How to Use Clash on a Remote Linux Server](https://ababababasmart.github.io//posts/2025/10/How-to-Use-Clash-on-a-Remote-Linux-Server/)


### 具体操作流程:

Step 1.
查看clash配置中指定的端口号, 此处示例的port设置为7896。 
![image](images/blog/codex/73a9a29c84b43c8704322f7ff7ad05ca.png)

Step 2.
在VSCode中按`Ctrl + Shift + P`，选择Preferences: Open User Settings (JSON)，打开`settings.json`，设置如下三行变量（注意这里变量的port要与Step 1中查看的port一致，比如这里都为7896）。

```
"http.proxy": "http://127.0.0.1:YOURPORT",
"https.proxy": "http://127.0.0.1:YOURPORT",
"http.proxyStrictSSL": false,
```
![image](images/blog/codex/84251f7ab9a14d76c28a6efdec5d8173.png)


Step 3.
在vscode中按`Ctrl+shfit+P`，选择Developer:Reload Window，重新加载一遍窗口。

![image](images/blog/codex/{3829180B-1A9A-4170-BC5B-A080F8F1353F}.png)

Step 4.
使用时首先在终端中**打开clash**，如果是第一次使用的话首先需要Sign in with ChatGPT，登录成功之后的界面如下图所示，然后就可以打开新聊天进行交流啦，注意整个登录和交流的过程中都需要**保持clash代理处于打开的状态**。

![image](images/blog/codex/0d493c31b647ef7eb261e28de3dcf035.png)