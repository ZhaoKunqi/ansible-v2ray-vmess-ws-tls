1. 安装需要用到的软件包

如果是RHEL8版本兼容的系统，例如CentOS Stream 8或者Rocky Linux 8等等，需要安装的Ansible包名称为 'ansible'

```
dnf install git ansible -y
```

如果是RHEL9版本兼容的系统，例如CentOS Stream 9或者Alma Linux 9等等，需要安装的Ansible包名称为 'ansible-core'

```
dnf install git ansible-core -y
```

获取Ansible Playbook

```
git clone https://github.com/ZhaoKunqi/ansible-v2ray-vmess-ws-tls.git
```

进入项目的目录

```
cd ansible-v2ray-vmess-ws-tls
```

修改配置文件
```
vi config.yml
```

编辑以下内容

```

# 已经解析到本机IP(VPS的IP地址)的域名, 如果是CloudFlare之类的话需要先关闭CDN.

custom_domain_name: 这里写你的域名,例如 server01.example.com

# ACME验证用的邮箱，写自己的电子邮箱

acme_email: 'raman@rebecca.net'

# 自定义Nginx路径，随便写一个即可

custom_path: 'b5c403e4'

# VMess的UUID(或密码)，可以使用uuidgen命令生成，也可以使用https://www.uuidgenerator.net/生成

uuid: 'f7fd888b-03ac-43d4-a650-3b2c098da1f3'

```

保存退出以后，运行Ansible Playbook

```
ansible-playbook site.yml
```
