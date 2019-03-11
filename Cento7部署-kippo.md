#### 安装环境

```bash
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
yum -y install epel-release 
yum -y install python-pip
yum install gcc python-devel  -y
yum install  python-zope-interface python-pyasn1
pip install twisted==13.1.0 
pip install pycrypto
firewall-cmd --permanent --add-port=2222/tcp
#
iptables -t nat -A PREROUTING -p tcp --dport 22 -j REDIRECT --to-ports 2222

firewall-cmd --reload
useradd -d /kippo/ kippo
chown -R kippo:kippo /kippo
git clone git clone https://github.com/desaster/kippo.git
cp kippo.cfg.dist  kippo.cfg
./start.sh

```

