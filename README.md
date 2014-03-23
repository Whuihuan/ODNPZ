Nginx+PHP 一键包 （V5.3.9） 
=============================
这是一个Openshift架设Nginx+PHP+Zend Guard Loader的一键包。
更多有关 OpenShift 的信息，请访问：https://openshift.redhat.com/。

============文件列表============

=.openshift //openshift默认的文件夹

==action_hooks //程序主位置

===build //编译主程序

===build_nginx //Nginx编译主程序

===build_php //PHP编译主程序

===common //用于重启时输出路径

===deploy //模版应用程序

===start //启动程序

===stop //停止程序

==tmpl //配置模版位置

=php //网站位置

============使用方法============

前言：若想让Openshift运行Nginx+PHP环境，您需要如下操作：

1.创建一个Openshift的应用:"Do-It-Yourself"。

2.通过SSH(SFTP和SCP)连接到您的应用。

3.通过SFTP将本程序传输至"app-root/repo/"目录。

4.通过SCP命令"cd"来定位到"action_hooks"目录。

5.输入命令"./build"开始编译，若提示"Permission denied"，请赋予文件执行权限。
建议权限为"0755"。

6.等待编译完成，预计一个小时。

7.编译完成后，输入命令"./deploy"。

8.输入命令"./start"

9.打开您的应用地址，若显示出雅黑探针界面，说明安装成功。

后记：那么祝您使用愉快！

============常见问题============

Q.Nginx无法启动，原因：端口被占用。
A.在程序里本结束了ruby的进程，也许出现意外并未结束，可输入命令"killall ruby"来结束进程，再尝试启动即可。

更多问题请发邮件至邮箱：wyuanji@qq.com