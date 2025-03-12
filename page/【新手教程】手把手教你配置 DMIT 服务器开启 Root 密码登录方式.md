
在黑五期间，许多朋友纷纷入手了 DMIT 的云服务器。尽管使用密钥方式登录服务器是默认设置，更加安全，但部分用户可能习惯使用密码登录，便于操作。本教程将以 Debian 11 系统为例，分享如何配置 DMIT 服务器以允许通过 root 密码方式登录，希望对您有所帮助。


禁止通过 root 密码方式登录是出于服务器安全的考量。如果您仍希望使用密码登录，请务必设置一个足够复杂且安全的密码！

---

👉 [【推荐收藏】2025年 DMIT 最新优惠活动整理汇总 - 每日更新可用优惠套餐](https://bit.ly/dmit_coupon)

---


以下步骤讲解如何在 DMIT 服务器上开启 Root 密码登录，以 Debian 11 为例，其他 Linux 系统设置方法大致类似：


- 登录 DMIT 的服务器控制面板。
- 进入“访问”选项，下载包含密钥文件的压缩包。
- **注意：** 该压缩包仅可下载一次，请妥善保存解压后的文件至安全位置。


- 下载并安装 PuTTY（建议直接从官网获取：[https://www.putty.org/](https://www.putty.org/)）。
- 在 PuTTY 的配置界面，找到加载密钥的位置，选择解压后的 `id_rsa.ppk` 文件。


- 在 PuTTY 的“Session”菜单中，输入服务器的 IP 地址，完成后点击“Open”。
- 在弹出的终端窗口中，输入默认 root 用户名并按回车键，即可通过密钥登录服务器。


- 输入以下命令打开 SSH 配置文件：

  bash
  nano /etc/ssh/sshd_config
  

- 在文件中找到以下两项设置，并修改为 `yes`：

  plaintext
  PermitRootLogin yes
  PasswordAuthentication yes
  


- 修改完成后，按下 `Ctrl+O` （保存），回车确认。
- 然后按下 `Ctrl+X` 退出编辑器。


- 为使修改生效，运行以下命令重启 SSH 服务：

  bash
  service ssh restart
  


- 输入以下命令设置 root 密码：

  bash
  passwd
  

- 您将被要求输入密码两次（出于安全考虑，输入时不会显示任何字符，这是正常现象）。
- 当屏幕提示 `password updated successfully` 时，表示密码设置成功。


完成上述步骤后，您即可使用 root 用户名和新设置的密码登录服务器。为确保安全性，请妥善保管好密码，并避免将密码随意透露。

---

希望本教程对您有所帮助！祝您在使用 DMIT 云服务器时体验愉快！
