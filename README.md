Debian，Ubuntu

查看系统启动时间

systemd-analyze


一键纯净更新

apt update -y && apt full-upgrade -y && apt autoremove -y && apt autoclean -y


一键清理垃圾

sudo apt autoremove --purge

sudo apt clean

sudo apt autoclean

sudo apt remove --purge $(dpkg -l | awk '/^rc/ {print $2}')

sudo journalctl --rotate

sudo journalctl --vacuum-time=1s

sudo journalctl --vacuum-size=50M

sudo apt remove --purge $(dpkg -l | awk '/^ii linux-(image|headers)-[^ ]+/{print $2}' | grep -v $(uname -r | sed 's/-.*//') | xargs)


查看Debian版本

cat /etc/debian_version


查看Ubuntu版本

cat /etc/lsb-release



CentOS

应广大CentOS 用户要求 哈哈 下面是CentOS命令


查看系统启动时间

systemd-analyze


一键纯净更新

yum update -y && yum upgrade -y && yum autoremove -y && yum clean all


一键清理垃圾

sudo yum autoremove

sudo yum clean all

sudo journalctl --rotate

sudo journalctl --vacuum-time=1s

sudo journalctl --vacuum-size=50M

sudo yum remove $(rpm -qa kernel | grep -v $(uname -r))


查看CentOS版本

cat /etc/centos-release



