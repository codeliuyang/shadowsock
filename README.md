# shadowsock 使用教程
如何用shaowsock翻墙使用呢？
不同的系统使用的方法不一样

## centos
````
yum install m2crypto python-setuptools
easy_install pip
pip install shadowsocks
vi /etc/shadowsocks.json
cat /etc/shadowsocks.json 
yum install firewalld
systemctl start firewalld
firewall-cmd --permanent --zone=public --add-port=443/tcp
firewall-cmd --reload
nohup ssserver -c /etc/shadowsocks.json &
````
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
