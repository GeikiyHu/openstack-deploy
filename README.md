# openstack-deploy
Openstack基于CentOS7环境，利用RDO源repo安装部署

##openstack rdo源，版本自选
```
https://repos.fedorapeople.org/repos/openstack/
```
##基础环境mysql,monogodb安装
```
yum install -y mongodb mysql-devel mysql mysql-server
```
##安装liberty版本
```
yum install -y https://repos.fedorapeople.org/repos/openstack/openstack-liberty/rdo-release-liberty-3.noarch.rpm
```
##安装基础包
```
yum install -y openstack-packstack
packstack  --install-hosts=120.122.83.251  #指定可以访问IP,最后Testing过程需要等待一段时间，耐心等待
```
##查看安装完成服务所需基础数据
```
cat /root/keystonerc_admin
unset OS_SERVICE_TOKEN
export OS_USERNAME=admin
export OS_PASSWORD=8cc18195sdfafte1
export OS_AUTH_URL=http://120.122.83.251:5000/v2.0
export PS1='[\u@\h \W(keystone_admin)]\$ '
#dashborad访问
http://120.122.83.251/dashboard
