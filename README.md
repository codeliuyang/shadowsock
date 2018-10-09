# shadowsock 使用教程
如何用shaowsock翻墙使用呢？
首先需要去vultr买一个可以ping通的国外的服务器，然后安装shadowsock服务

## centos 服务器

首先创建文件
/etc/shadowsocks.json
````
{
  "server":"0.0.0.0",
  "server_port":443,
  "local_adderss":"127.0.0.1",
  "local_port":1080,
  "password":"your_password",
  "timeout":300,
  "method":"aes-256-cfb",
  "fast_open":false
}
````

然后依次执行以下命令，即可成功
````
# yum install m2crypto python-setuptools
# easy_install pip
# pip install shadowsocks
# vi /etc/shadowsocks.json
# cat /etc/shadowsocks.json 
# yum install firewalld
# systemctl start firewalld
# firewall-cmd --permanent --zone=public --add-port=443/tcp
# firewall-cmd --reload
# nohup ssserver -c /etc/shadowsocks.json &
````

不同的系统安装不同的shadowsock工具即可

## 不同系统使用工具
Android：https://github.com/shadowsocks/shadowsocks-android
https://github.com/shadowsocks/shadowsocks-android/releases

MacOSX：https://github.com/shadowsocks/ShadowsocksX-NG

Windows：https://github.com/shadowsocks/shadowsocks-windows

官方网站所有版本：http://shadowsocks.org/en/download/clients.html
