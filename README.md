# learn docker

## 1. 安装docker

```sh
# yum centos工具包 类似于 npm
yum install -y yum-utils device-mapper-persistent-data lvm2
# 添加一个阿里的源
yum-config-manager \
    --add-repo \
    https://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo

# 安装docker ce社区版免费  ee企业版收费
yum install -y docker-ce docker-ce-cli containerd.io
```

## 2. docker安装软件加速
```sh
# 创建文件夹
mkdir -p /etc/docker

# 将内容写入
tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https://xx.mirror.aliyuncs.com"]
}
EOF

# 重载所有修改过的配置文件
systemctl daemon-reload
systemctl restart docker
```



