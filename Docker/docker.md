# 一、安装docker

## 环境查看

> ```shell
> #系统内核是3.10及以上的
> [root@localhost /]# uname -r
> 3.10.0-1127.19.1.el7.x86_64
> 
> 
> #系统版本
> [root@localhost /]# cat /etc/os-release 
> NAME="CentOS Linux"
> VERSION="7 (Core)"
> ID="centos"
> ID_LIKE="rhel fedora"
> VERSION_ID="7"
> PRETTY_NAME="CentOS Linux 7 (Core)"
> ANSI_COLOR="0;31"
> CPE_NAME="cpe:/o:centos:centos:7"
> HOME_URL="https://www.centos.org/"
> BUG_REPORT_URL="https://bugs.centos.org/"
> 
> CENTOS_MANTISBT_PROJECT="CentOS-7"
> CENTOS_MANTISBT_PROJECT_VERSION="7"
> REDHAT_SUPPORT_PRODUCT="centos"
> REDHAT_SUPPORT_PRODUCT_VERSION="7"
> ```

## 帮助文档

https://docs.docker.com/engine/install/centos/

## 安装步骤

> ```shell
> #1.卸载旧版本docker
> yum remove docker \
>                   docker-client \
>                   docker-client-latest \
>                   docker-common \
>                   docker-latest \
>                   docker-latest-logrotate \
>                   docker-logrotate \
>                   docker-selinux \
>                   docker-engine-selinux \
>                   docker-engine
>                   
> #2.安装必要软件包
> yum install -y yum-utils
> 
> #3.设置镜像的仓库
> yum-config-manager \
>     --add-repo \
>     https://download.docker.com/linux/centos/docker-ce.repo #默认是国外的
>     
> yum-config-manager \
>     --add-repo \
>     http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo #阿里云镜像地址
>     
> #4.更新yum软件包索引
> yum makecache fast
> 
> #5.安装dockcer
> yum install docker-ce docker-ce-cli containerd.io
> 
> #6.启动docker
> systemctl start docker
> 
> #7.查看否安装成功
> dockr version
> 
> #8.设置开机自动启动
> systemctl enable docker
> ```

## 卸载步骤

>```shell
>#1.卸载docker
>yum remove docker-ce docker-ce-cli containerd.io
>
>#2.删除资源
>rm -rf /var/lib/docker  #是其工作路径
>
>#3.双重保险
>yum remove docker \
>                  docker-client \
>                  docker-client-latest \
>                  docker-common \
>                  docker-latest \
>                  docker-latest-logrotate \
>                  docker-logrotate \
>                  docker-selinux \
>                  docker-engine-selinux \
>                  docker-engine
>```

## 配置ustc镜像

编辑该文件：

```
vim /etc/docker/daemon.json
```

输入以下内容：

```
{
"registry-mirrors":["https://docker.mirrors.ustc.edu.cn"]
}
```

重启docker

```
systemctl restart docker
```

查看docker状态

```
systemctl status docker
```

![image-20200916171550580](docker.assets/image-20200916171550580.png)

设置开机自动启动

