# Thanks-Mirror

本项目灵感来自：[package-manager-proxy-settings](https://github.com/comwrg/package-manager-proxy-settings)，该项目分享的是包管理器配置代理的方法，这里分享的是包管理器直接可用，质量好，速度快的镜像，以及一些其他常用软件，系统镜像的国内镜像。

在此，对那些提供公共仓库镜像的企业或组织，致以感谢🫡！

Gitee：[https://gitee.com/eryajf/Thanks-Mirror](https://gitee.com/eryajf/Thanks-Mirror)

GitHub：[https://github.com/eryajf/Thanks-Mirror](https://github.com/eryajf/Thanks-Mirror)

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**目录**

- [Package-Mirror](#package-mirror)
  - [Go](#go)
  - [Npm](#npm)
  - [Pip](#pip)
  - [Composer](#composer)
  - [Rubygems](#rubygems)
  - [Maven](#maven)
  - [Yum](#yum)
  - [Remi](#remi)
  - [Epel](#epel)
  - [Homebrew](#homebrew)
  - [cargo](#cargo)
- [Software-Mirror](#software-mirror)
  - [Docker](#docker)
  - [Kubernetes](#kubernetes)
  - [K3s](#k3s)
  - [Minikube](#minikube)
  - [Helm](#helm)
  - [Harbor](#harbor)
  - [Jenkins](#jenkins)
  - [GitLab-ce](#gitlab-ce)
  - [GitLab-runner](#gitlab-runner)
  - [ElasticSearch](#elasticsearch)
  - [Logstash](#logstash)
  - [Kibana](#kibana)
  - [Filebeat](#filebeat)
  - [MySQL](#mysql)
  - [MariaDB](#mariadb)
  - [Percona](#percona)
  - [MongoDB](#mongodb)
  - [Redis](#redis)
  - [PostgreSQL](#postgresql)
  - [Golang](#golang)
  - [Node](#node)
  - [Yarn](#yarn)
  - [Python](#python)
  - [Rust](#rust)
  - [Zabbix](#zabbix)
  - [Prometheus](#prometheus)
  - [Grafana](#grafana)
  - [Pinpoint](#pinpoint)
  - [Apache](#apache)
  - [Nginx](#nginx)
  - [OpenResty](#openresty)
  - [Keepalived](#keepalived)
  - [Ceph](#ceph)
  - [Influxdata](#influxdata)
  - [ClickHouse](#clickhouse)
  - [Rabbitmq](#rabbitmq)
  - [ETCD](#etcd)
  - [WireShark](#wireshark)
  - [Virtualbox](#virtualbox)
  - [iina](#iina)
  - [Chromium](#chromium)
- [System-Mirror](#system-mirror)
  - [CentOS](#centos)
  - [CentOS-altarch](#centos-altarch)
  - [Ubuntu](#ubuntu)
  - [Debian](#debian)
  - [Deepin](#deepin)
  - [Fedora](#fedora)
  - [Gentoo](#gentoo)
  - [kali](#kali)
  - [Opensuse](#opensuse)
  - [Freebsd](#freebsd)
  - [GNU](#gnu)
- [Other-Mirror](#other-mirror)
  - [Docker-hub](#docker-hub)
- [如何贡献](#%E5%A6%82%E4%BD%95%E8%B4%A1%E7%8C%AE)
- [贡献者](#%E8%B4%A1%E7%8C%AE%E8%80%85)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Package-Mirror

以往工作中经历过建设企业内部私服的经历，私服的建设离不开国内一些优秀的镜像代理，这里记录下来，以供大家参考。

`注意：`假如所有的镜像都已经被本地nexus私服代理，那么对应的地址为`nexus.eryajf.net/repository/***/`。(这只是个域名示例，不代表实际可用！)

### Go

#### Configuration

如果go版本用的`go1.11`或者`go1.12`，需进行如下配置：

```sh
export GO111MODULE=on
export GOPROXY="http://nexus.eryajf.net/repository/go/"
```

如果使用 `go1.13`以上的版本则可以用如下配置：

```sh
export GOPROXY="http://nexus.eryajf.net/repository/go/"
GONOPROXY="gitlab.eryajf.net"
GONOSUMDB="gitlab.eryajf.net"
GOPRIVATE="gitlab.eryajf.net"
GOSUMDB="sum.golang.google.cn"
```

关于如上两个版本配置差异，以及配置参数详解可参考：[https://wiki.eryajf.net/pages/4941.html](https://wiki.eryajf.net/pages/4941.html)

#### Mirrors

- Aliyun
  - [https://mirrors.aliyun.com/goproxy/](https://mirrors.aliyun.com/goproxy/)
- Proxy-cn
  - [https://goproxy.cn](https://goproxy.cn)
- Proxy-io
  - [https://proxy.golang.com.cn](https://proxy.golang.com.cn)
- Baidu
  - [https://goproxy.bj.bcebos.com/](https://goproxy.bj.bcebos.com/)
- [Tencent](https://mirrors.cloud.tencent.com/help/go.html)
  - [https://mirrors.cloud.tencent.com/go/](https://mirrors.cloud.tencent.com/go/)
- HUAWEI
  - [https://repo.huaweicloud.com/repository/goproxy/](https://repo.huaweicloud.com/repository/goproxy/)


其中`GOSUMDB`在国内可用的两个镜像分别如下：

- Google
  - [https://sum.golang.google.cn/](https://sum.golang.google.cn/)
- sumdb-io
  - [https://gosum.io/](https://gosum.io/)

### Npm

#### Configuration

配置`npm`代理，需进行如下配置：

```
# npm配置
$ echo 'registry=http://nexus.eryajf.net/repository/npm' > ~/.npmrc
# 查看
$ npm config get registry
http://nexus.eryajf.net/repository/npm

# yarn配置
$ echo 'registry "http://nexus.eryajf.net/repository/npm"' > ~/.yarnrc
# 查看
$ yarn config get registry
http://nexus.eryajf.net/repository/npm
```

#### Mirrors

- Taobao
  - [https://registry.npm.taobao.org](https://registry.npm.taobao.org)
    但是请注意如下一个消息：
    - [淘宝 npm 域名即将切换 && npmmirror 重构升级](https://zhuanlan.zhihu.com/p/465424728?spm=a2c6h.24755359.0.0.6d444dccyRLxN8)：即原来的淘宝npm域名将停止解析，因此所有依赖此域名的都需要进行更改。
      - 域名切换规则：
        - [http://npm.taobao.org](http://npm.taobao.org/)=> [http://npmmirror.com](http://npmmirror.com/)
        - [http://registry.npm.taobao.org](http://registry.npm.taobao.org/)=> [http://registry.npmmirror.com](http://registry.npmmirror.com/)
- HUAWEI
  - [https://repo.huaweicloud.com/repository/npm/](https://repo.huaweicloud.com/repository/npm/)
- [Tencent](https://mirrors.cloud.tencent.com/help/npm.html)
  - [http://mirrors.cloud.tencent.com/npm/](http://mirrors.cloud.tencent.com/npm/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/npm/](http://mirrors.zju.edu.cn/npm/)
- 南京邮电
  - [https://mirrors.njupt.edu.cn/nexus/repository/npm/](https://mirrors.njupt.edu.cn/nexus/repository/npm/)
- npmjs
  - [https://registry.npmjs.org](https://registry.npmjs.org)

### Pip

#### Configuration

配置`Python`代理，需进行如下配置：

```shell
$ mkdir ~/.pip

$ cat > ~/.pip/pip.conf << EOF
[global]
timeout = 60
trusted-host =  nexus.eryajf.net
index-url = http://nexus.eryajf.net/repository/pypi/simple
EOF

```

`注意：`通常在配置文件后边，我们会添加一个`simple`。
```shell
# 简洁配置方式 1
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
# 简洁配置方式 2 
pip3 install --upgrade -i https://pypi.tuna.tsinghua.edu.cn/simple yt-dlp
```

#### Mirrors

目前代理外部私仓有：

- Aliyun
  - [http://mirrors.aliyun.com/pypi/](http://mirrors.aliyun.com/pypi/)
- douban
  - [http://pypi.douban.com/](http://pypi.douban.com/)
- 清华
  - [https://pypi.tuna.tsinghua.edu.cn/](https://pypi.tuna.tsinghua.edu.cn/)
- 163
  - [https://mirrors.163.com/pypi](https://mirrors.163.com/pypi)
- HUAWEI
  - [https://repo.huaweicloud.com/repository/pypi](https://repo.huaweicloud.com/repository/pypi)
- Tencent
  - [https://mirrors.cloud.tencent.com/pypi/](https://mirrors.cloud.tencent.com/pypi/)
- 北大
  - [https://mirrors.pku.edu.cn/pypi/](https://mirrors.pku.edu.cn/pypi/)
- 南阳理工
  - [https://mirror.nyist.edu.cn/pypi/](https://mirror.nyist.edu.cn/pypi/)
- 大连东软
  - [http://mirrors.neusoft.edu.cn/pypi/web/](http://mirrors.neusoft.edu.cn/pypi/web/)
- 哈尔滨工业大学
  - [https://mirrors.hit.edu.cn/pypi/web/](https://mirrors.hit.edu.cn/pypi/web/)
- 上海交通大学
  - [https://mirror.sjtu.edu.cn/pypi/web/simple/](https://mirror.sjtu.edu.cn/pypi/web/simple/)

### Composer

*Composer* 是PHP 的一个依赖管理工具，需要PHP 5.3.2 以上才能运行。

#### Configuration

配置`PHP`代理，需进行如下配置：

- 全局配置（推荐）
  - 所有项目都会使用该镜像地址：
    ```
    composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/
    ```
  - 取消配置：
    ```
    composer config -g --unset repos.packagist
    ```
- 项目配置
  - 仅修改当前工程配置，仅当前工程可使用该镜像地址：
    ```
    composer config repo.packagist composer https://mirrors.aliyun.com/composer/
    ```
  - 取消配置：
    ```
    composer config --unset repos.packagist
    ```

参考：[https://developer.aliyun.com/composer](https://developer.aliyun.com/composer)

#### Mirrors

目前代理外部私仓有：

- [Aliyun](https://developer.aliyun.com/composer)
  - [https://mirrors.aliyun.com/composer/](https://mirrors.aliyun.com/composer/)
- [Tencent](https://mirrors.cloud.tencent.com/help/composer.html)
  - [https://mirrors.cloud.tencent.com/composer/](https://mirrors.cloud.tencent.com/composer/)
- HUAWEI
  - [https://mirrors.huaweicloud.com/repository/php/](https://mirrors.huaweicloud.com/repository/php/)
- [Packagist](https://pkg.xyz/)
  - [https://packagist.phpcomposer.com](https://packagist.phpcomposer.com)
- 上海交通
  - [https://packagist.mirrors.sjtug.sjtu.edu.cn](https://packagist.mirrors.sjtug.sjtu.edu.cn)

### Rubygems

*RubyGems* 是Ruby 的一个包管理器，它提供一个分发Ruby 程序和库的标准格式，还提供一个管理程序包安装的工具。

#### Configuration

配置`Ruby`代理，需进行如下配置：

```sh
# 首先，查看当前源：
$ gem sources -l
*** CURRENT SOURCES ***
https://rubygems.org/


# 接着，移除 https://rubygems.org/，并添加国内下载源 https://gems.ruby-china.com/。
$ gem sources --remove https://rubygems.org/
$ gem sources -a https://gems.ruby-china.com/
$ gem sources -l
*** CURRENT SOURCES ***

https://gems.ruby-china.com/

# 请确保只有 gems.ruby-china.com
$ gem install rails
```

参考：[https://www.runoob.com/ruby/ruby-rubygems.html](https://www.runoob.com/ruby/ruby-rubygems.html)

#### Mirrors

目前代理外部私仓有：

- [Aliyun](https://developer.aliyun.com/mirror/rubygems)
  - [https://mirrors.aliyun.com/rubygems/](https://mirrors.aliyun.com/rubygems/)
- Tencent
  - [https://mirrors.cloud.tencent.com/rubygems/](https://mirrors.cloud.tencent.com/rubygems/)
- HUAWEI
  - [https://repo.huaweicloud.com/repository/rubygems/](https://repo.huaweicloud.com/repository/rubygems/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/rubygems/](https://mirrors.tuna.tsinghua.edu.cn/rubygems/)
- 中科大
  - [https://mirrors.ustc.edu.cn/rubygems/](https://mirrors.ustc.edu.cn/rubygems/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/rubygems/](https://mirrors.bfsu.edu.cn/rubygems/)
- 哈尔滨工业大学
  - [https://mirrors.hit.edu.cn/rubygems/](https://mirrors.hit.edu.cn/rubygems/)

### Maven

#### Configuration

Java系的工具版本规范如下：

- `JDK：`1.8.0_292
- `MVN：`3.3.9

配置Maven代理，参考配置文件： [settings.xml](https://raw.githubusercontent.com/eryajf/Thanks-Mirror/main/src/settings.xml)

#### Mirrors

- HUAWEI
  - https://repo.huaweicloud.com/repository/maven/
- Maven Central Repository
  - https://repo1.maven.org/maven2/
- [Aliyun](https://developer.aliyun.com/mvn/guide)
  - http://maven.aliyun.com/nexus/content/groups/public/
- Tencent
  - [https://mirrors.cloud.tencent.com/maven/](https://mirrors.cloud.tencent.com/maven/)
- 南京邮电
  - [https://mirrors.njupt.edu.cn/nexus/repository/maven-central](https://mirrors.njupt.edu.cn/nexus/repository/maven-central)
- Apache Maven
  - https://repo.maven.apache.org/maven2
  - https://repository.apache.org/content/groups/snapshots
  - https://repository.apache.org/content/groups/staging/
  - https://repository.apache.org/content/groups/public/
- confluent
  - http://packages.confluent.io/maven/
- cloudera
  - http://repo.hortonworks.com/content/repositories/releases
- jboss
  - https://repository.jboss.org/nexus/content/groups/public
- Lss233's.Mirror（供 Minecraft 开发使用）
  - http://lss233.littleservice.cn/repositories/minecraft

### Yum

#### Configuration

如果`CentOS`服务器要接入私服`yum`源，则清空本地 `/etc/yum.repos.d`的内容，添加如下内容：

```sh
$ cat >> /etc/yum.repos.d/nexus.repo << 'EOF'
[nexus]
name=Nexus Repository
baseurl=http://nexus.eryajf.net/repository/yum/$releasever/os/$basearch/
enabled=1
gpgcheck=0

[nexus-local]
name=Nexus Repository
baseurl=http://nexus.eryajf.net/repository/eryajf-yum-local/
enabled=1
gpgcheck=0
EOF
```

然后执行如下命令：

```sh
yum clean all
yum makecache
```

#### Mirrors

目前代理外部源：

- Aliyun
  - [https://mirrors.aliyun.com/centos/](https://mirrors.aliyun.com/centos/)
- HUAWEI
  - [https://repo.huaweicloud.com/centos/](https://repo.huaweicloud.com/centos/)
- Tencent
  - https://mirrors.cloud.tencent.com/centos/
- 北京交通
  - [https://mirror.bjtu.edu.cn/centos/](https://mirror.bjtu.edu.cn/centos/)
- 东北大学
  - http://mirror.neu.edu.cn/centos/
- 兰州大学
  - https://mirror.lzu.edu.cn/centos/
- 清华
  - https://mirrors.tuna.tsinghua.edu.cn/centos/
- 华中科技大学
  - https://mirrors.ustc.edu.cn/centos/
- 浙江大学
  - http://mirrors.zju.edu.cn/centos/
- souhu
  - http://mirrors.sohu.com/centos/
- 163：
  - http://mirrors.163.com/centos/

### Remi

Remi repository 是包含最新版本 PHP 和 MySQL 包的 Linux 源，由 Remi 提供维护。

官方地址：[https://rpms.remirepo.net/](https://rpms.remirepo.net/)

#### Configuration

详情参考：[https://wiki.eryajf.net/pages/f35986](https://wiki.eryajf.net/pages/f35986)

```bash
yum install -y epel-release
yum install -y https://mirrors.tuna.tsinghua.edu.cn/remi/enterprise/remi-release-7.rpm
```

#### Mirrors

目前代理外部源：

- [Aliyun](https://developer.aliyun.com/mirror/remi)
  - [https://mirrors.aliyun.com/remi/](https://mirrors.aliyun.com/remi/)
- HUAWEI
  - [https://repo.huaweicloud.com/remi/](https://repo.huaweicloud.com/remi/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/remi/](https://mirrors.tuna.tsinghua.edu.cn/remi/)
- 中科大
  - [https://mirrors.ustc.edu.cn/remi/](https://mirrors.ustc.edu.cn/remi/)
- 上海交通
  - [http://ftp.sjtu.edu.cn/remi/](http://ftp.sjtu.edu.cn/remi/)
- 首都在线
  - [http://mirrors.yun-idc.com/remi/](http://mirrors.yun-idc.com/remi/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/remi/](https://mirrors.bfsu.edu.cn/remi/)

### Epel

EPEL 的全称叫 Extra Packages for Enterprise Linux。EPEL 是由 Fedora 社区打造，为 RHEL 及衍生发行版如 CentOS、Scientific Linux 等提供高质量软件包的项目。

官方地址：[https://docs.fedoraproject.org/en-US/epel/](https://docs.fedoraproject.org/en-US/epel/)

#### Configuration

```bash
# 备份
mv /etc/yum.repos.d/epel.repo /etc/yum.repos.d/epel.repo.backup
mv /etc/yum.repos.d/epel-testing.repo /etc/yum.repos.d/epel-testing.repo.backup

# 下载
wget -O /etc/yum.repos.d/epel.repo http://mirrors.aliyun.com/repo/epel-7.repo
```

#### Mirrors

目前代理外部源：

- [Aliyun](https://developer.aliyun.com/mirror/epel)
  - [https://mirrors.aliyun.com/epel/](https://mirrors.aliyun.com/epel/)
- Tencent
  - [https://mirrors.cloud.tencent.com/epel/](https://mirrors.cloud.tencent.com/epel/)
- HUAWEI
  - [https://repo.huaweicloud.com/epel/](https://repo.huaweicloud.com/epel/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/epel/](https://mirrors.tuna.tsinghua.edu.cn/epel/)
- 中科大
  - [https://mirrors.ustc.edu.cn/epel/](https://mirrors.ustc.edu.cn/epel/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/epel/](http://mirrors.zju.edu.cn/epel/)
- 兰州大学
  - [https://mirror.lzu.edu.cn/epel/](https://mirror.lzu.edu.cn/epel/)
- 上海交通
  - [http://ftp.sjtu.edu.cn/epel/](http://ftp.sjtu.edu.cn/epel/)
- 首都在线
  - [http://mirrors.yun-idc.com/epel/](http://mirrors.yun-idc.com/epel/)
- 大连东软
  - [http://mirrors.neusoft.edu.cn/epel/](http://mirrors.neusoft.edu.cn/epel/)
- 大连理工
  - [http://mirror.dlut.edu.cn/epel/](http://mirror.dlut.edu.cn/epel/)
- 南京邮电
  - [http://mirrors.njupt.edu.cn/epel/](http://mirrors.njupt.edu.cn/epel/)
- 重庆大学
  - [https://mirrors.cqu.edu.cn/epel/](https://mirrors.cqu.edu.cn/epel/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/epel/](https://mirrors.bfsu.edu.cn/epel/)


### Homebrew

#### Configuration

如果你使用了zsh，那么配置方式如下：

```sh
echo 'export HOMEBREW_BREW_GIT_REMOTE="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git"' >> ~/.zshrc
echo 'export HOMEBREW_CORE_GIT_REMOTE="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git"' >> ~/.zshrc
echo 'export HOMEBREW_BOTTLE_DOMAIN="https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles"' >> ~/.zshrc

source ~/.zshrc
brew update
```

参考：[Homebrew 替换国内镜像源](https://www.frankindev.com/2020/05/15/replace-homebrew-source/)

#### Mirrors

- Aliyun
  - [https://mirrors.aliyun.com/homebrew/](https://mirrors.aliyun.com/homebrew/)
- Tencent
  - [https://mirrors.cloud.tencent.com/homebrew/](https://mirrors.cloud.tencent.com/homebrew/)
- 清华：
  - https://mirrors.tuna.tsinghua.edu.cn/help/homebrew/
- 重庆大学
  - [https://mirrors.cqu.edu.cn/homebrew/](https://mirrors.cqu.edu.cn/homebrew/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/help/homebrew/](https://mirrors.bfsu.edu.cn/help/homebrew/)


### cargo
rust 包管理镜像源

#### Configuration

修改文件`~/.cargo/config`(没有则新建)
```
[source.crates-io]
replace-with = 'rsproxy'

[source.rsproxy]
registry = "https://rsproxy.cn/crates.io-index"

[registries.rsproxy]
index = "https://rsproxy.cn/crates.io-index"

[net]
git-fetch-with-cli = true
```
#### Mirrors

- 字节
  - [https://rsproxy.cn/crates.io-index](https://rsproxy.cn/crates.io-index)
- 中国科学技术大学
  - git://mirrors.ustc.edu.cn/crates.io-index
- 清华：
  - [https://mirrors.tuna.tsinghua.edu.cn/git/crates.io-index.git](https://mirrors.tuna.tsinghua.edu.cn/git/crates.io-index.git)
- 上海交通大学
  - [https://mirrors.sjtug.sjtu.edu.cn/git/crates.io-index](https://mirrors.sjtug.sjtu.edu.cn/git/crates.io-index)
- 阿里云
  - [https://code.aliyun.com/rustcc/crates.io-index](https://code.aliyun.com/rustcc/crates.io-index)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/git/crates.io-index.git](https://mirrors.bfsu.edu.cn/git/crates.io-index.git)
- rustcc社区
  - git://crates.rustcc.cn/crates.io-index
## Software-Mirror

还有一些软件，直接通过官方下载比较困难，也整理出方便下载的国内优质镜像。

### Docker

#### Official

- https://docs.docker.com/engine/install/

#### Mirrors

- Aliyun
  - [https://developer.aliyun.com/mirror/docker-ce](https://developer.aliyun.com/mirror/docker-ce)
- Tencent
  - [https://mirrors.cloud.tencent.com/docker-ce/](https://mirrors.cloud.tencent.com/docker-ce/)
- HUAWEI
  - [https://repo.huaweicloud.com/docker-ce/](https://repo.huaweicloud.com/docker-ce/)
- 北大
  - [https://mirrors.pku.edu.cn/docker-ce/](https://mirrors.pku.edu.cn/docker-ce/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/docker-ce/](https://mirrors.tuna.tsinghua.edu.cn/docker-ce/)
- 中科大
  - [https://mirrors.ustc.edu.cn/docker-ce/](https://mirrors.ustc.edu.cn/docker-ce/)
- 西北农林科技大学
  - [https://mirrors.nwsuaf.edu.cn/docker-ce/](https://mirrors.nwsuaf.edu.cn/docker-ce/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/docker-ce/](http://mirrors.zju.edu.cn/docker-ce/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/docker-ce/](https://mirrors.bfsu.edu.cn/docker-ce/)
- 哈尔滨工业大学
  - [https://mirrors.hit.edu.cn/docker-ce](https://mirrors.hit.edu.cn/docker-ce)
- 上海交通
  - [https://mirror.sjtu.edu.cn/docker-ce/](https://mirror.sjtu.edu.cn/docker-ce/)

### Kubernetes

#### Official

- [https://kubernetes.io/releases/download/](https://kubernetes.io/releases/download/)

#### Mirrors

- Aliyun
  - [https://developer.aliyun.com/mirror/kubernetes](https://developer.aliyun.com/mirror/kubernetes)
- Tencent
  - [https://mirrors.cloud.tencent.com/kubernetes/](https://mirrors.cloud.tencent.com/kubernetes/)
- HUAWEI
  - [https://repo.huaweicloud.com/kubernetes/](https://repo.huaweicloud.com/kubernetes/)
- 北大
  - [https://mirrors.pku.edu.cn/kubernetes/](https://mirrors.pku.edu.cn/kubernetes/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/kubernetes/](https://mirrors.tuna.tsinghua.edu.cn/kubernetes/)
- 中科大
  - [https://mirrors.ustc.edu.cn/kubernetes/](https://mirrors.ustc.edu.cn/kubernetes/)

### K3s

#### Official

- [https://github.com/k3s-io/k3s/releases/](https://github.com/k3s-io/k3s/releases/)

#### Mirrors

- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/github-release/k3s-io/k3s/](https://mirrors.tuna.tsinghua.edu.cn/github-release/k3s-io/k3s/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/github-release/k3s-io/k3s/](https://mirrors.bfsu.edu.cn/github-release/k3s-io/k3s/)


### Minikube

#### Official

- [https://github.com/kubernetes/minikube/releases](https://github.com/kubernetes/minikube/releases)

#### Mirrors

- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/github-release/kubernetes/minikube/](https://mirrors.tuna.tsinghua.edu.cn/github-release/kubernetes/minikube/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/github-release/kubernetes/minikube/](https://mirrors.bfsu.edu.cn/github-release/kubernetes/minikube/)


### Helm

#### Official

- [https://helm.sh/docs/intro/install/](https://helm.sh/docs/intro/install/)

#### Mirrors

- HUAWEI
  - [https://repo.huaweicloud.com/helm/](https://repo.huaweicloud.com/helm/)

### Harbor

#### Official

- [https://github.com/goharbor/harbor/releases](https://github.com/goharbor/harbor/releases)

#### Mirrors

- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/github-release/goharbor/harbor/](https://mirrors.tuna.tsinghua.edu.cn/github-release/goharbor/harbor/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/github-release/goharbor/harbor/](https://mirrors.bfsu.edu.cn/github-release/goharbor/harbor/)

### Jenkins

#### Official

- 安装包：[https://www.jenkins.io/zh/download/](https://www.jenkins.io/zh/download/)
- 插件：[https://plugins.jenkins.io/](https://plugins.jenkins.io/)

#### Mirrors

- Aliyun
  - 安装包：[https://mirrors.aliyun.com/jenkins/war/](https://mirrors.aliyun.com/jenkins/war/)
  - 插件：[https://mirrors.aliyun.com/jenkins/plugins/](https://mirrors.aliyun.com/jenkins/plugins/)
- Tencent
  - 安装包：[https://mirrors.cloud.tencent.com/jenkins/war/](https://mirrors.cloud.tencent.com/jenkins/war/)
  - 插件：[https://mirrors.cloud.tencent.com/jenkins/plugins/](https://mirrors.cloud.tencent.com/jenkins/plugins/)
- HUAWEI
  - 安装包：[https://repo.huaweicloud.com/jenkins/war/](https://repo.huaweicloud.com/jenkins/war/)
  - 插件：[https://repo.huaweicloud.com/jenkins/plugins/](https://repo.huaweicloud.com/jenkins/plugins/)
- 中科大
  - 安装包：[https://mirrors.ustc.edu.cn/jenkins/war/](https://mirrors.ustc.edu.cn/jenkins/war/)
  - 插件：[https://mirrors.ustc.edu.cn/jenkins/plugins/](https://mirrors.ustc.edu.cn/jenkins/plugins/)
- 清华
  - 安装包：[https://mirrors.tuna.tsinghua.edu.cn/jenkins/war/](https://mirrors.tuna.tsinghua.edu.cn/jenkins/war/)
  - 插件：[https://mirrors.tuna.tsinghua.edu.cn/jenkins/plugins/](https://mirrors.tuna.tsinghua.edu.cn/jenkins/plugins/)
- 北京外国语大学
  - 安装包：[https://mirrors.bfsu.edu.cn/jenkins/war/](https://mirrors.bfsu.edu.cn/jenkins/war/)
  - 插件：[https://mirrors.bfsu.edu.cn/jenkins/plugins/](https://mirrors.bfsu.edu.cn/jenkins/plugins/)


### GitLab-ce

#### Official

- [https://packages.gitlab.com/gitlab/gitlab-ce](https://packages.gitlab.com/gitlab/gitlab-ce)

#### Mirrors

- Aliyun
  - [https://mirrors.aliyun.com/gitlab-ce/](https://mirrors.aliyun.com/gitlab-ce/)
- Tencent
  - [https://mirrors.cloud.tencent.com/gitlab-ce/](https://mirrors.cloud.tencent.com/gitlab-ce/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/gitlab-ce/](https://mirrors.tuna.tsinghua.edu.cn/gitlab-ce/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/gitlab-ce/](https://mirrors.bfsu.edu.cn/gitlab-ce/)


### GitLab-runner

#### Official

- [https://docs.gitlab.com/runner/install/](https://docs.gitlab.com/runner/install/)

#### Mirrors

- Tencent
  - [https://mirrors.cloud.tencent.com/gitlab-runner/](https://mirrors.cloud.tencent.com/gitlab-runner/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/gitlab-runner/](https://mirrors.tuna.tsinghua.edu.cn/gitlab-runner/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/gitlab-runner/](https://mirrors.bfsu.edu.cn/gitlab-runner/)


### ElasticSearch

#### Official

- [https://www.elastic.co/cn/downloads/elasticsearch](https://www.elastic.co/cn/downloads/elasticsearch)

#### Mirrors

- elastic中文社区
  - [https://elasticsearch.cn/download/](https://elasticsearch.cn/download/)
- Aliyun
  - [https://mirrors.aliyun.com/elasticstack/](https://mirrors.aliyun.com/elasticstack/)
- HUAWEI
  - [https://repo.huaweicloud.com/elasticsearch/](https://repo.huaweicloud.com/elasticsearch/)
- Tencent
  - [https://mirrors.cloud.tencent.com/elasticstack/](https://mirrors.cloud.tencent.com/elasticstack/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/elasticstack/](https://mirrors.tuna.tsinghua.edu.cn/elasticstack/)
- 南京邮电
  - [http://mirrors.njupt.edu.cn/elasticstack/](http://mirrors.njupt.edu.cn/elasticstack/)

### Logstash

#### Official

- [https://www.elastic.co/cn/downloads/logstash](https://www.elastic.co/cn/downloads/logstash)

#### Mirrors

- elastic中文社区
  - [https://elasticsearch.cn/download/](https://elasticsearch.cn/download/)
- HUAWEI
  - [https://repo.huaweicloud.com/logstash/](https://repo.huaweicloud.com/logstash/)


### Kibana

#### Official

- [https://www.elastic.co/cn/downloads/kibana](https://www.elastic.co/cn/downloads/kibana)

#### Mirrors

- elastic中文社区
  - [https://elasticsearch.cn/download/](https://elasticsearch.cn/download/)
- HUAWEI
  - [https://repo.huaweicloud.com/kibana/](https://repo.huaweicloud.com/kibana/)

### Filebeat

#### Official

- [https://www.elastic.co/cn/downloads/beats/filebeat](https://www.elastic.co/cn/downloads/beats/filebeat)

#### Mirrors

- elastic中文社区
  - [https://elasticsearch.cn/download/](https://elasticsearch.cn/download/)
- HUAWEI
  - [https://repo.huaweicloud.com/filebeat/](https://repo.huaweicloud.com/filebeat/)

### MySQL

#### Official

- [https://dev.mysql.com/downloads/repo/yum/](https://dev.mysql.com/downloads/repo/yum/)

#### Mirrors

- Aliyun
  - [https://developer.aliyun.com/mirror/mysql](https://developer.aliyun.com/mirror/mysql)
- HUAWEI
  - [https://repo.huaweicloud.com/mysql/Downloads/](https://repo.huaweicloud.com/mysql/Downloads/)
- Tencent
  - [https://mirrors.cloud.tencent.com/mysql/](https://mirrors.cloud.tencent.com/mysql/)
- Souhu
  - [http://mirrors.sohu.com/mysql/](http://mirrors.sohu.com/mysql/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/mysql/](https://mirrors.tuna.tsinghua.edu.cn/mysql/)
- 中科大
  - [https://mirrors.ustc.edu.cn/mysql-ftp/Downloads/](https://mirrors.ustc.edu.cn/mysql-ftp/Downloads/)
- 南阳理工
  - [https://mirror.nyist.edu.cn/mysql/](https://mirror.nyist.edu.cn/mysql/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/mysql/](https://mirrors.bfsu.edu.cn/mysql/)


### MariaDB

#### Official

- [https://mariadb.org/download/](https://mariadb.org/download/?spm=a2c6h.13651104.0.0.3b4d3553pZDrq9&t=mariadb&p=mariadb&r=10.6.7)

#### Mirrors

- Aliyun
  - [https://developer.aliyun.com/mirror/mariadb](https://developer.aliyun.com/mirror/mariadb)
- Tencent
  - [https://mirrors.cloud.tencent.com/mariadb/](https://mirrors.cloud.tencent.com/mariadb/)
- HUAWEI
  - [https://repo.huaweicloud.com/mariadb/](https://repo.huaweicloud.com/mariadb/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/mariadb/](https://mirrors.tuna.tsinghua.edu.cn/mariadb/)
- 中科大
  - [https://mirrors.ustc.edu.cn/mariadb/](https://mirrors.ustc.edu.cn/mariadb/)

### Percona

#### Official

- [https://www.percona.com/downloads/](https://www.percona.com/downloads/)

#### Mirrors

- Tencent
  - [https://mirrors.cloud.tencent.com/percona/](https://mirrors.cloud.tencent.com/percona/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/percona/](https://mirrors.tuna.tsinghua.edu.cn/percona/)
- 中科大
  - [https://mirrors.ustc.edu.cn/percona/](https://mirrors.ustc.edu.cn/percona/)

### MongoDB

#### Official

- [https://www.mongodb.com/try/download/community](https://www.mongodb.com/try/download/community)

#### Mirrors

- Aliyun
  - [https://developer.aliyun.com/mirror/mongodb](https://developer.aliyun.com/mirror/mongodb)
- Tencent
  - [https://mirrors.cloud.tencent.com/mongodb/](https://mirrors.cloud.tencent.com/mongodb/)
- 163
  - [http://mirrors.163.com/mongodb/](http://mirrors.163.com/mongodb/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/mongodb/](https://mirrors.tuna.tsinghua.edu.cn/mongodb/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/mongodb/](https://mirrors.bfsu.edu.cn/mongodb/)

- 上海交通大学
  - [https://mirrors.sjtug.sjtu.edu.cn/mongodb/](https://mirrors.sjtug.sjtu.edu.cn/mongodb/)


### Redis

#### Official

- [https://redis.io/download/](https://redis.io/download/)

#### Mirrors

- HUAWEI
  - [https://repo.huaweicloud.com/redis/](https://repo.huaweicloud.com/redis/)

### PostgreSQL

#### Official

- [https://www.postgresql.org/download/](https://www.postgresql.org/download/)

#### Mirrors

- Aliyun
  - [https://mirrors.aliyun.com/postgresql/](https://mirrors.aliyun.com/postgresql/)
- Tencen
  - [https://mirrors.cloud.tencent.com/postgresql/](https://mirrors.cloud.tencent.com/postgresql/)
- HUAWEI
  - [https://repo.huaweicloud.com/postgresql/](https://repo.huaweicloud.com/postgresql/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/postgresql/](https://mirrors.tuna.tsinghua.edu.cn/postgresql/)
- 中科大
  - [https://mirrors.ustc.edu.cn/postgresql/](https://mirrors.ustc.edu.cn/postgresql/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/postgresql/](http://mirrors.zju.edu.cn/postgresql/)
- 南阳理工
  - [https://mirror.nyist.edu.cn/postgresql/](https://mirror.nyist.edu.cn/postgresql/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/postgresql/](https://mirrors.bfsu.edu.cn/postgresql/)

### Golang

#### Official

- [https://go.dev/dl/](https://go.dev/dl/)

#### Mirrors

- Go语言中文网
  - [https://studygolang.com/dl](https://studygolang.com/dl)
- Aliyun
  - [https://mirrors.aliyun.com/golang/](https://mirrors.aliyun.com/golang/)
- Proxy-io
  - [https://gomirrors.org/](https://gomirrors.org/)
- 中科大
  - [https://mirrors.ustc.edu.cn/golang/](https://mirrors.ustc.edu.cn/golang/)

### Node

#### Official

- [https://nodejs.org/zh-cn/download/](https://nodejs.org/zh-cn/download/)

#### Mirrors

- Aliyun
  - [https://mirrors.aliyun.com/nodejs-release/](https://mirrors.aliyun.com/nodejs-release/)
- HUAWEI
  - [https://repo.huaweicloud.com/nodejs/](https://repo.huaweicloud.com/nodejs/)
- Tencent
  - [https://mirrors.cloud.tencent.com/nodejs-release/](https://mirrors.cloud.tencent.com/nodejs-release/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/nodejs-release/](https://mirrors.tuna.tsinghua.edu.cn/nodejs-release/)
- 中科大
  - [https://mirrors.ustc.edu.cn/node/](https://mirrors.ustc.edu.cn/node/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/nodejs-release/](https://mirrors.bfsu.edu.cn/nodejs-release/)


### Yarn

#### Official

- [https://github.com/yarnpkg/yarn/releases](https://github.com/yarnpkg/yarn/releases)

#### Mirrors

- HUAWEI
  - [https://repo.huaweicloud.com/yarn/](https://repo.huaweicloud.com/yarn/)

### Python

#### Official

- [https://www.python.org/downloads/](https://www.python.org/downloads/)

#### Mirrors

- HUAWEI
  - [https://repo.huaweicloud.com/python/](https://repo.huaweicloud.com/python/)
- 北京交通
  - [https://mirror.bjtu.edu.cn/python/](https://mirror.bjtu.edu.cn/python/)

### Rust

#### Official

- [https://forge.rust-lang.org/infra/other-installation-methods.html](https://forge.rust-lang.org/infra/other-installation-methods.html)

#### Mirrors

- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/rustup/](https://mirrors.tuna.tsinghua.edu.cn/rustup/)
- 上海交通大学
  - [https://mirror.sjtu.edu.cn/rust-static/](https://mirror.sjtu.edu.cn/rust-static/)

### Zabbix

#### Official

- [https://www.zabbix.com/cn/download](https://www.zabbix.com/cn/download)

#### Mirrors

- Aliyun
  - [https://mirrors.aliyun.com/zabbix](https://mirrors.aliyun.com/zabbix)
- HUAWEI
  - [https://repo.huaweicloud.com/zabbix/](https://repo.huaweicloud.com/zabbix/)
- Tencent
  - [https://mirrors.cloud.tencent.com/zabbix/](https://mirrors.cloud.tencent.com/zabbix/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/zabbix/](https://mirrors.tuna.tsinghua.edu.cn/zabbix/)
- 南京邮电
  - [http://mirrors.njupt.edu.cn/zabbix/](http://mirrors.njupt.edu.cn/zabbix/)
- 西北农林科技大学
  - [https://mirrors.nwsuaf.edu.cn/zabbix/](https://mirrors.nwsuaf.edu.cn/zabbix/)
- 南阳理工
  - [https://mirror.nyist.edu.cn/zabbix/](https://mirror.nyist.edu.cn/zabbix/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/zabbix/](https://mirrors.bfsu.edu.cn/zabbix/)

### Prometheus

#### Official

- [https://grafana.com/grafana/download](https://grafana.com/grafana/download)

#### Mirrors

- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/github-release/prometheus/prometheus/](https://mirrors.tuna.tsinghua.edu.cn/github-release/prometheus/prometheus/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/github-release/prometheus/prometheus/](https://mirrors.bfsu.edu.cn/github-release/prometheus/prometheus/)
- 上海交通大学
  - [https://mirror.sjtu.edu.cn/github-release/prometheus/?mirror_intel_list](https://mirror.sjtu.edu.cn/github-release/prometheus/?mirror_intel_list)
    此地址下包含了prometheus应用体系的大部分软件，包含：
    - [alertmanager](https://s3.jcloud.sjtu.edu.cn/899a892efef34b1b944a19981040f55b-oss01/github-release/prometheus/alertmanager/mirror_clone_list.html)
    - [blackbox_exporter](https://s3.jcloud.sjtu.edu.cn/899a892efef34b1b944a19981040f55b-oss01/github-release/prometheus/blackbox_exporter/mirror_clone_list.html)
    - [consul_exporter](https://s3.jcloud.sjtu.edu.cn/899a892efef34b1b944a19981040f55b-oss01/github-release/prometheus/consul_exporter/mirror_clone_list.html)
    - [graphite_exporter](https://s3.jcloud.sjtu.edu.cn/899a892efef34b1b944a19981040f55b-oss01/github-release/prometheus/graphite_exporter/mirror_clone_list.html)
    - [haproxy_exporter](https://s3.jcloud.sjtu.edu.cn/899a892efef34b1b944a19981040f55b-oss01/github-release/prometheus/haproxy_exporter/mirror_clone_list.html)
    - [memcached_exporter](https://s3.jcloud.sjtu.edu.cn/899a892efef34b1b944a19981040f55b-oss01/github-release/prometheus/memcached_exporter/mirror_clone_list.html)
    - [mysqld_exporter](https://s3.jcloud.sjtu.edu.cn/899a892efef34b1b944a19981040f55b-oss01/github-release/prometheus/mysqld_exporter/mirror_clone_list.html)
    - [node_exporter](https://s3.jcloud.sjtu.edu.cn/899a892efef34b1b944a19981040f55b-oss01/github-release/prometheus/node_exporter/mirror_clone_list.html)
    - [prometheus](https://s3.jcloud.sjtu.edu.cn/899a892efef34b1b944a19981040f55b-oss01/github-release/prometheus/prometheus/mirror_clone_list.html)
    - [pushgateway](https://s3.jcloud.sjtu.edu.cn/899a892efef34b1b944a19981040f55b-oss01/github-release/prometheus/pushgateway/mirror_clone_list.html)
    - [statsd_exporter](https://s3.jcloud.sjtu.edu.cn/899a892efef34b1b944a19981040f55b-oss01/github-release/prometheus/statsd_exporter/mirror_clone_list.html)


### Grafana

#### Official

- [https://grafana.com/grafana/download](https://grafana.com/grafana/download)

#### Mirrors

- Aliyun
  - [https://developer.aliyun.com/mirror/grafana](https://developer.aliyun.com/mirror/grafana)
- HUAWEI
  - [https://repo.huaweicloud.com/grafana/](https://repo.huaweicloud.com/grafana/)
- Tencent
  - [https://mirrors.cloud.tencent.com/grafana/](https://mirrors.cloud.tencent.com/grafana/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/grafana/](https://mirrors.tuna.tsinghua.edu.cn/grafana/)
- 西北农林科技大学
  - [https://mirrors.nwsuaf.edu.cn/grafana/](https://mirrors.nwsuaf.edu.cn/grafana/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/grafana/](https://mirrors.bfsu.edu.cn/grafana/)
- 哈尔滨工业大学
  - [https://mirrors.hit.edu.cn/grafana/](https://mirrors.hit.edu.cn/grafana/)

### Pinpoint

#### Official

- [https://github.com/pinpoint-apm/pinpoint/releases](https://github.com/pinpoint-apm/pinpoint/releases)

#### Mirrors

- HUAWEI
  - [https://repo.huaweicloud.com/pinpoint/](https://repo.huaweicloud.com/pinpoint/)

### Apache

#### Official

- [https://httpd.apache.org/download.cgi](https://httpd.apache.org/download.cgi)

#### Mirrors

- Aliyun
  - [https://developer.aliyun.com/mirror/apache](https://developer.aliyun.com/mirror/apache)
- HUAWEI
  - [https://repo.huaweicloud.com/apache/](https://repo.huaweicloud.com/apache/)
- Tencent
  - [https://mirrors.cloud.tencent.com/apache/](https://mirrors.cloud.tencent.com/apache/)
- Souhu
  - [http://mirrors.sohu.com/apache/](http://mirrors.sohu.com/apache/)
- 北大
  - [https://mirrors.pku.edu.cn/apache/](https://mirrors.pku.edu.cn/apache/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/apache/](https://mirrors.tuna.tsinghua.edu.cn/apache/)
- 中科大
  - [https://mirrors.ustc.edu.cn/apache/](https://mirrors.ustc.edu.cn/apache/)
- 北京交通
  - [https://mirror.bjtu.edu.cn/apache/](https://mirror.bjtu.edu.cn/apache/)

### Nginx

#### Official

- [http://nginx.org/en/download.html](http://nginx.org/en/download.html)

#### Mirrors

- HUAWEI
  - [https://repo.huaweicloud.com/nginx/](https://repo.huaweicloud.com/nginx/)
- Souhu
  - [http://mirrors.sohu.com/nginx](http://mirrors.sohu.com/nginx)
- 中科大
  - [https://mirrors.ustc.edu.cn/nginx/](https://mirrors.ustc.edu.cn/nginx/)
- 西北农林科技大学
  - [https://mirrors.nwsuaf.edu.cn/nginx/](https://mirrors.nwsuaf.edu.cn/nginx/)

### OpenResty

#### Official

- [https://openresty.org/cn/download.html](https://openresty.org/cn/download.html)

#### Mirrors

- Tencent
  - [https://mirrors.cloud.tencent.com/openresty/](https://mirrors.cloud.tencent.com/openresty/)
- HUAWEI
  - [https://repo.huaweicloud.com/openresty/](https://repo.huaweicloud.com/openresty/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/openresty/](https://mirrors.tuna.tsinghua.edu.cn/openresty/)
- 中科大
  - [https://mirrors.ustc.edu.cn/openresty/](https://mirrors.ustc.edu.cn/openresty/)
- 西北农林科技大学
  - [https://mirrors.nwsuaf.edu.cn/openresty/](https://mirrors.nwsuaf.edu.cn/openresty/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/openresty/](https://mirrors.bfsu.edu.cn/openresty/)

### Keepalived

#### Official

- [https://www.keepalived.org/download.html](https://www.keepalived.org/download.html)

#### Mirrors

- HUAWEI
  - [https://repo.huaweicloud.com/keepalived/](https://repo.huaweicloud.com/keepalived/)

### Ceph

#### Official

- [https://docs.ceph.com/en/quincy/install/get-packages/](https://docs.ceph.com/en/quincy/install/get-packages/)

#### Mirrors

- Aliyun
  - [https://developer.aliyun.com/mirror/ceph](https://developer.aliyun.com/mirror/ceph)
- Tencent
  - [https://mirrors.cloud.tencent.com/ceph/](https://mirrors.cloud.tencent.com/ceph/)
- HUAWEI
  - [https://repo.huaweicloud.com/ceph/](https://repo.huaweicloud.com/ceph/)
- 163
  - [http://mirrors.163.com/ceph/](http://mirrors.163.com/ceph/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/ceph/](https://mirrors.tuna.tsinghua.edu.cn/ceph/)
- 重庆大学
  - [https://mirrors.cqu.edu.cn/ceph/](https://mirrors.cqu.edu.cn/ceph/)
- 中科大
  - [https://mirrors.ustc.edu.cn/ceph/](https://mirrors.ustc.edu.cn/ceph/)

### Influxdata

#### Official

- [https://portal.influxdata.com/downloads/](https://portal.influxdata.com/downloads/)

#### Mirrors

- Tencent
  - [https://mirrors.cloud.tencent.com/influxdata/](https://mirrors.cloud.tencent.com/influxdata/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/influxdata/](https://mirrors.tuna.tsinghua.edu.cn/influxdata/)
- 中科大
  - [https://mirrors.ustc.edu.cn/influxdata/](https://mirrors.ustc.edu.cn/influxdata/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/influxdata/](https://mirrors.bfsu.edu.cn/influxdata/)

### ClickHouse

#### Official

- [https://clickhouse.com/#quick-start](https://clickhouse.com/#quick-start)

#### Mirrors

- Aliyun
  - [https://mirrors.aliyun.com/clickhouse/](https://mirrors.aliyun.com/clickhouse/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/clickhouse/](https://mirrors.tuna.tsinghua.edu.cn/clickhouse/)

### Rabbitmq

#### Official

- [https://www.rabbitmq.com/download.html](https://www.rabbitmq.com/download.html)

#### Mirrors

- HUAWEI
  - [https://repo.huaweicloud.com/rabbitmq-server/](https://repo.huaweicloud.com/rabbitmq-server/)

### ETCD

#### Official

- [https://github.com/etcd-io/etcd/releases](https://github.com/etcd-io/etcd/releases)

#### Mirrors

- HUAWEI
  - [https://repo.huaweicloud.com/etcd/](https://repo.huaweicloud.com/etcd/)

### WireShark

#### Official

- [https://www.wireshark.org/](https://www.wireshark.org/)

#### Mirrors

- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/wireshark/](https://mirrors.tuna.tsinghua.edu.cn/wireshark/)
- 上海交通大学
  - [https://mirror.sjtu.edu.cn/wireshark/](https://mirror.sjtu.edu.cn/wireshark/)


### Virtualbox

#### Official

- [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)

#### Mirrors

- Tencent
  - [https://mirrors.cloud.tencent.com/virtualbox/](https://mirrors.cloud.tencent.com/virtualbox/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/virtualbox/](https://mirrors.tuna.tsinghua.edu.cn/virtualbox/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/virtualbox/](https://mirrors.bfsu.edu.cn/virtualbox/)
- 哈尔滨工业大学
  - [https://mirrors.hit.edu.cn/virtualbox/](https://mirrors.hit.edu.cn/virtualbox/)

### iina


#### Official

- [https://github.com/iina/iina/releases/](https://github.com/iina/iina/releases/)

#### Mirrors

- Aliyun
  - [https://mirrors.aliyun.com/iina/](https://mirrors.aliyun.com/iina/)
- Tencent
  - [https://mirrors.cloud.tencent.com/iina/](https://mirrors.cloud.tencent.com/iina/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/iina/](https://mirrors.tuna.tsinghua.edu.cn/iina/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/iina/](https://mirrors.bfsu.edu.cn/iina/)


### chromium

#### Official
- [ https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html](https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html)

#### Mirrors
- Aliyun
  - [https://registry.npmmirror.com/binary.html?path=chromium-browser-snapshots/](https://registry.npmmirror.com/binary.html?path=chromium-browser-snapshots/)
- huaweicloud
  - [https://repo.huaweicloud.com/chromium-browser-snapshots/](https://repo.huaweicloud.com/chromium-browser-snapshots/)
- ungoogled-software.github.io(ungoogle chromium)
  - [https://ungoogled-software.github.io/ungoogled-chromium-binaries/releases/](https://ungoogled-software.github.io/ungoogled-chromium-binaries/releases/)


## System-Mirror

系统镜像，又大又远，更需要找到好用优秀的国内镜像。

### CentOS

尽管CentOS不再更新了，但它仍旧并且还将持续是国内企业系统主力军。

可能官方考虑到下载困难的问题，官方也列出了距离使用者更近的镜像列表，可谓贴心。

#### Official

- [https://www.centos.org/download/](https://www.centos.org/download/)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/centos)
  - [https://mirrors.aliyun.com/centos/](https://mirrors.aliyun.com/centos/)
- Tencent
  - [https://mirrors.cloud.tencent.com/centos/](https://mirrors.cloud.tencent.com/centos/)
- HUAWEI
  - [https://repo.huaweicloud.com/centos/](https://repo.huaweicloud.com/centos/)
- 163
  - [http://mirrors.163.com/centos/](http://mirrors.163.com/centos/)
- Souhu
  - [http://mirrors.sohu.com/centos/](http://mirrors.sohu.com/centos/)
- 北大
  - [https://mirrors.pku.edu.cn/centos/](https://mirrors.pku.edu.cn/centos/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/centos/](https://mirrors.tuna.tsinghua.edu.cn/centos/)
- 中科大
  - [https://mirrors.ustc.edu.cn/centos/](https://mirrors.ustc.edu.cn/centos/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/centos/](http://mirrors.zju.edu.cn/centos/)
- 南阳理工
  - [https://mirror.nyist.edu.cn/centos/](https://mirror.nyist.edu.cn/centos/)
- 兰州大学
  - [https://mirror.lzu.edu.cn/centos/](https://mirror.lzu.edu.cn/centos/)
- 东北大学
  - [http://mirror.neu.edu.cn/centos/](http://mirror.neu.edu.cn/centos/)
- 大连东软
  - [http://mirrors.neusoft.edu.cn/centos/](http://mirrors.neusoft.edu.cn/centos/)
- 上海交通
  - [http://ftp.sjtu.edu.cn/centos/](http://ftp.sjtu.edu.cn/centos/)
- 北京交通
  - [https://mirror.bjtu.edu.cn/centos/](https://mirror.bjtu.edu.cn/centos/)
- 大连理工
  - [http://mirror.dlut.edu.cn/centos/](http://mirror.dlut.edu.cn/centos/)
- 首都在线
  - [http://mirrors.yun-idc.com/centos/](http://mirrors.yun-idc.com/centos/)
- 南京邮电
  - [http://mirrors.njupt.edu.cn/centos/](http://mirrors.njupt.edu.cn/centos/)
- 西北农林科技大学
  - [https://mirrors.nwsuaf.edu.cn/centos/](https://mirrors.nwsuaf.edu.cn/centos/)
- 重庆大学
  - [https://mirrors.cqu.edu.cn/centos/](https://mirrors.cqu.edu.cn/centos/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/centos/](https://mirrors.bfsu.edu.cn/centos/)
- 哈尔滨工业大学
  - [https://mirrors.hit.edu.cn/centos/](https://mirrors.hit.edu.cn/centos/)

### CentOS-altarch

ARM架构下的CentOS镜像。

#### Official

- [https://www.centos.org/download/](https://www.centos.org/download/)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/centos-altarch)
  - [https://developer.aliyun.com/mirror/centos-altarch](https://developer.aliyun.com/mirror/centos-altarch)
- Tencent
  - [https://mirrors.cloud.tencent.com/centos-altarch/](https://mirrors.cloud.tencent.com/centos-altarch/)
- HUAWEI
  - [https://repo.huaweicloud.com/centos-altarch/](https://repo.huaweicloud.com/centos-altarch/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/centos-altarch/](https://mirrors.tuna.tsinghua.edu.cn/centos-altarch/)
- 中科大
  - [https://mirrors.ustc.edu.cn/centos-altarch/](https://mirrors.ustc.edu.cn/centos-altarch/)
- 兰州大学
  - [https://mirror.lzu.edu.cn/centos-altarch/](https://mirror.lzu.edu.cn/centos-altarch/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/centos-altarch/](https://mirrors.bfsu.edu.cn/centos-altarch/)

### Ubuntu

#### Official

- 官方镜像：[https://ubuntu.com/download](https://ubuntu.com/download)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/ubuntu)
  - [https://mirrors.aliyun.com/ubuntu/](https://mirrors.aliyun.com/ubuntu/)
- Tencent
  - [https://mirrors.cloud.tencent.com/ubuntu/](https://mirrors.cloud.tencent.com/ubuntu/)
- HUAWEI
  - [https://repo.huaweicloud.com/ubuntu/](https://repo.huaweicloud.com/ubuntu/)
- 163
  - [http://mirrors.163.com/ubuntu/](http://mirrors.163.com/ubuntu/)
- Souhu
  - [http://mirrors.sohu.com/ubuntu/](http://mirrors.sohu.com/ubuntu/)
- 北大
  - [https://mirrors.pku.edu.cn/ubuntu/](https://mirrors.pku.edu.cn/ubuntu/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/ubuntu/](https://mirrors.tuna.tsinghua.edu.cn/ubuntu/)
- 中科大
  - [https://mirrors.ustc.edu.cn/ubuntu/](https://mirrors.ustc.edu.cn/ubuntu/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/ubuntu/](http://mirrors.zju.edu.cn/ubuntu/)
- 兰州大学
  - [https://mirror.lzu.edu.cn/ubuntu/](https://mirror.lzu.edu.cn/ubuntu/)
- 大连东软
  - [http://mirrors.neusoft.edu.cn/ubuntu/](http://mirrors.neusoft.edu.cn/ubuntu/)
- 上海交通
  - [http://ftp.sjtu.edu.cn/ubuntu/](http://ftp.sjtu.edu.cn/ubuntu/)
- 北京交通
  - [https://mirror.bjtu.edu.cn/ubuntu/](https://mirror.bjtu.edu.cn/ubuntu/)
- 大连理工
  - [http://mirror.dlut.edu.cn/ubuntu/](http://mirror.dlut.edu.cn/ubuntu/)
- 首都在线
  - [http://mirrors.yun-idc.com/ubuntu/](http://mirrors.yun-idc.com/ubuntu/)
- 南京邮电
  - [http://mirrors.njupt.edu.cn/ubuntu/](http://mirrors.njupt.edu.cn/ubuntu/)
- 南阳理工
  - [https://mirror.nyist.edu.cn/ubuntu/](https://mirror.nyist.edu.cn/ubuntu/)
- 重庆大学
  - [https://mirrors.cqu.edu.cn/ubuntu/](https://mirrors.cqu.edu.cn/ubuntu/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/ubuntu/](https://mirrors.bfsu.edu.cn/ubuntu/)
- 哈尔滨工业大学
  - [https://mirrors.hit.edu.cn/ubuntu](https://mirrors.hit.edu.cn/ubuntu)

### Debian

#### Official

- 官方镜像：[https://www.debian.org/mirror/](https://www.debian.org/mirror/)
- 全球镜像：[https://www.debian.org/mirror/list](https://www.debian.org/mirror/list)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/debian)
  - [https://mirrors.aliyun.com/debian/](https://mirrors.aliyun.com/debian/)
- Tencent
  - [https://mirrors.cloud.tencent.com/debian/](https://mirrors.cloud.tencent.com/debian/)
- HUAWEI
  - [https://repo.huaweicloud.com/debian/](https://repo.huaweicloud.com/debian/)
- 163
  - [http://mirrors.163.com/debian/](http://mirrors.163.com/debian/)
- Souhu
  - [http://mirrors.sohu.com/debian/](http://mirrors.sohu.com/debian/)
- 北大
  - [https://mirrors.pku.edu.cn/debian/](https://mirrors.pku.edu.cn/debian/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/debian/](https://mirrors.tuna.tsinghua.edu.cn/debian/)
- 中科大
  - [https://mirrors.ustc.edu.cn/debian/](https://mirrors.ustc.edu.cn/debian/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/debian/](http://mirrors.zju.edu.cn/debian/)
- 兰州大学
  - [https://mirror.lzu.edu.cn/debian/](https://mirror.lzu.edu.cn/debian/)
- 大连东软
  - [http://mirrors.neusoft.edu.cn/debian/](http://mirrors.neusoft.edu.cn/debian/)
- 上海交通
  - [http://ftp.sjtu.edu.cn/debian/](http://ftp.sjtu.edu.cn/debian/)
- 北京交通
  - [https://mirror.bjtu.edu.cn/debian/](https://mirror.bjtu.edu.cn/debian/)
- 大连理工
  - [http://mirror.dlut.edu.cn/debian/](http://mirror.dlut.edu.cn/debian/)
- 首都在线
  - [http://mirrors.yun-idc.com/debian/](http://mirrors.yun-idc.com/debian/)
- 南京邮电
  - [http://mirrors.njupt.edu.cn/debian/](http://mirrors.njupt.edu.cn/debian/)
- 南阳理工
  - [https://mirror.nyist.edu.cn/debian/](https://mirror.nyist.edu.cn/debian/)
- 重庆大学
  - [https://mirrors.cqu.edu.cn/debian/](https://mirrors.cqu.edu.cn/debian/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/debian/](https://mirrors.bfsu.edu.cn/debian/)
- 哈尔滨工业大学
  - [https://mirrors.hit.edu.cn/debian/](https://mirrors.hit.edu.cn/debian/)

### Deepin

#### Official

- 官方镜像：[https://www.deepin.org/zh/download/](https://www.deepin.org/zh/download/)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/deepin)
  - [https://mirrors.aliyun.com/deepin/](https://mirrors.aliyun.com/deepin/)
- HUAWEI
  - [https://repo.huaweicloud.com/deepin/](https://repo.huaweicloud.com/deepin/)
- 163
  - [http://mirrors.163.com/deepin/](http://mirrors.163.com/deepin/)
- Souhu
  - [http://mirrors.sohu.com/deepin/](http://mirrors.sohu.com/deepin/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/deepin/](https://mirrors.tuna.tsinghua.edu.cn/deepin/)
- 中科大
  - [https://mirrors.ustc.edu.cn/deepin/](https://mirrors.ustc.edu.cn/deepin/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/deepin/](http://mirrors.zju.edu.cn/deepin/)
- 兰州大学
  - [https://mirror.lzu.edu.cn/deepin/](https://mirror.lzu.edu.cn/deepin/)
- 上海交通
  - [http://ftp.sjtu.edu.cn/deepin/](http://ftp.sjtu.edu.cn/deepin/)
- 南京邮电
  - [http://mirrors.njupt.edu.cn/deepin/](http://mirrors.njupt.edu.cn/deepin/)
- 南阳理工
  - [https://mirror.nyist.edu.cn/deepin/](https://mirror.nyist.edu.cn/deepin/)
- 重庆大学
  - [https://mirrors.cqu.edu.cn/deepin/](https://mirrors.cqu.edu.cn/deepin/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/deepin/](https://mirrors.bfsu.edu.cn/deepin/)
- 哈尔滨工业大学
  - [https://mirrors.hit.edu.cn/deepin/](https://mirrors.hit.edu.cn/deepin/)

### Fedora

#### Official

- 官方镜像：[https://getfedora.org/en/server/download/](https://getfedora.org/en/server/download/)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/fedora)
  - [https://mirrors.aliyun.com/fedora/](https://mirrors.aliyun.com/fedora/)
- Tencent
  - [https://mirrors.cloud.tencent.com/fedora/](https://mirrors.cloud.tencent.com/fedora/)
- HUAWEI
  - [https://repo.huaweicloud.com/fedora/](https://repo.huaweicloud.com/fedora/)
- 163
  - [http://mirrors.163.com/fedora/](http://mirrors.163.com/fedora/)
- Souhu
  - [http://mirrors.sohu.com/fedora/](http://mirrors.sohu.com/fedora/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/fedora/](https://mirrors.tuna.tsinghua.edu.cn/fedora/)
- 中科大
  - [https://mirrors.ustc.edu.cn/fedora/](https://mirrors.ustc.edu.cn/fedora/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/fedora/](http://mirrors.zju.edu.cn/fedora/)
- 兰州大学
  - [https://mirror.lzu.edu.cn/fedora/](https://mirror.lzu.edu.cn/fedora/)
- 上海交通
  - [http://ftp.sjtu.edu.cn/fedora/](http://ftp.sjtu.edu.cn/fedora/)
- 南京邮电
  - [http://mirrors.njupt.edu.cn/fedora/](http://mirrors.njupt.edu.cn/fedora/)
- 南阳理工
  - [https://mirror.nyist.edu.cn/fedora/](https://mirror.nyist.edu.cn/fedora/)
- 重庆大学
  - [https://mirrors.cqu.edu.cn/fedora/](https://mirrors.cqu.edu.cn/fedora/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/fedora/](https://mirrors.bfsu.edu.cn/fedora/)

### Gentoo

#### Official

- 官方镜像：[https://www.gentoo.org/downloads/](https://www.gentoo.org/downloads/)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/gentoo)
  - [https://mirrors.aliyun.com/gentoo/](https://mirrors.aliyun.com/gentoo/)
- Tencent
  - [https://mirrors.cloud.tencent.com/gentoo/](https://mirrors.cloud.tencent.com/gentoo/)
- HUAWEI
  - [https://repo.huaweicloud.com/gentoo/](https://repo.huaweicloud.com/gentoo/)
- 163
  - [http://mirrors.163.com/gentoo/](http://mirrors.163.com/gentoo/)
- Souhu
  - [http://mirrors.sohu.com/gentoo/](http://mirrors.sohu.com/gentoo/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/gentoo/](https://mirrors.tuna.tsinghua.edu.cn/gentoo/)
- 中科大
  - [https://mirrors.ustc.edu.cn/gentoo/](https://mirrors.ustc.edu.cn/gentoo/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/gentoo/](http://mirrors.zju.edu.cn/gentoo/)
- 兰州大学
  - [https://mirror.lzu.edu.cn/gentoo/](https://mirror.lzu.edu.cn/gentoo/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/gentoo/](https://mirrors.bfsu.edu.cn/gentoo/)
- 上海交通
  - [https://mirrors.sjtug.sjtu.edu.cn/gentoo/](https://mirrors.sjtug.sjtu.edu.cn/gentoo/)

### kali

#### Official

- [https://www.kali.org/get-kali/](https://www.kali.org/get-kali/)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/kali)
  - [https://mirrors.aliyun.com/kali/](https://mirrors.aliyun.com/kali/)
- Tencent
  - [https://mirrors.cloud.tencent.com/kali/](https://mirrors.cloud.tencent.com/kali/)
- HUAWEI
  - [https://repo.huaweicloud.com/kali/](https://repo.huaweicloud.com/kali/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/kali/](https://mirrors.tuna.tsinghua.edu.cn/kali/)
- 中科大
  - [https://mirrors.ustc.edu.cn/kali/](https://mirrors.ustc.edu.cn/kali/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/kali/](http://mirrors.zju.edu.cn/kali/)
- 南阳理工
  - [https://mirror.nyist.edu.cn/kali/](https://mirror.nyist.edu.cn/kali/)
- 大连东软
  - [http://mirrors.neusoft.edu.cn/kali/](http://mirrors.neusoft.edu.cn/kali/)
- 北京交通
  - [https://mirror.bjtu.edu.cn/kali/](https://mirror.bjtu.edu.cn/kali/)
- 南京邮电
  - [http://mirrors.njupt.edu.cn/kali/](http://mirrors.njupt.edu.cn/kali/)
- 西北农林科技大学
  - [https://mirrors.nwsuaf.edu.cn/kali/](https://mirrors.nwsuaf.edu.cn/kali/)
- 重庆大学
  - [https://mirrors.cqu.edu.cn/kali-images/](https://mirrors.cqu.edu.cn/kali-images/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/kali/](https://mirrors.bfsu.edu.cn/kali/)
- 哈尔滨工业大学
  - [https://mirrors.hit.edu.cn/kali](https://mirrors.hit.edu.cn/kali)
- 上海交通大学
  - [https://mirrors.sjtug.sjtu.edu.cn/kali/](https://mirrors.sjtug.sjtu.edu.cn/kali/)


### Opensuse

#### Official

- [https://get.opensuse.org/zh-CN/](https://get.opensuse.org/zh-CN/)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/opensuse)
  - [https://mirrors.aliyun.com/opensuse/](https://mirrors.aliyun.com/opensuse/)
- Tencent
  - [https://mirrors.cloud.tencent.com/opensuse/](https://mirrors.cloud.tencent.com/opensuse/)
- HUAWEI
  - [https://repo.huaweicloud.com/opensuse/](https://repo.huaweicloud.com/opensuse/)
- Souhu
  - [http://mirrors.sohu.com/opensuse/](http://mirrors.sohu.com/opensuse/)
- 北大
  - [https://mirrors.pku.edu.cn/opensuse/](https://mirrors.pku.edu.cn/opensuse/)
- openTUNA
  - [https://opentuna.cn/opensuse/](https://opentuna.cn/opensuse/)
- 中科大
  - [https://mirrors.ustc.edu.cn/opensuse/](https://mirrors.ustc.edu.cn/opensuse/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/opensuse/](http://mirrors.zju.edu.cn/opensuse/)
- 兰州大学
  - [https://mirror.lzu.edu.cn/opensuse/](https://mirror.lzu.edu.cn/opensuse/)
- 上海交通
  - [http://ftp.sjtu.edu.cn/opensuse/](http://ftp.sjtu.edu.cn/opensuse/)
- 北京交通
  - [https://mirror.bjtu.edu.cn/opensuse/](https://mirror.bjtu.edu.cn/opensuse/)
- 首都在线
  - [http://mirrors.yun-idc.com/opensuse/](http://mirrors.yun-idc.com/opensuse/)
- 重庆大学
  - [https://mirrors.cqu.edu.cn/opensuse/](https://mirrors.cqu.edu.cn/opensuse/)
- 北京理工
  - [https://mirror.bit.edu.cn/opensuse/](https://mirror.bit.edu.cn/opensuse/)
- 重庆大学
  - [https://mirrors.cqu.edu.cn/opensuse/](https://mirrors.cqu.edu.cn/opensuse/)
- 哈工大
  - [https://mirrors.hit.edu.cn/opensuse/](https://mirrors.hit.edu.cn/opensuse/)
- 南京大学
  - [http://mirrors.nju.edu.cn/opensuse/](http://mirrors.nju.edu.cn/opensuse/)
- 南方科技大学
  - [https://mirrors.sustech.edu.cn/opensuse/](https://mirrors.sustech.edu.cn/opensuse/)
- 北京外国语大学
  - [https://mirrors.bfsu.edu.cn/opensuse/](https://mirrors.bfsu.edu.cn/opensuse/)
- 哈尔滨工业大学
  - [https://mirrors.hit.edu.cn/opensuse/](https://mirrors.hit.edu.cn/opensuse/)


### Freebsd

#### Official

- [https://www.freebsd.org/where/](https://www.freebsd.org/where/)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/freebsd)
  - [https://mirrors.aliyun.com/freebsd/](https://mirrors.aliyun.com/freebsd/)
- Tencent
  - [https://mirrors.cloud.tencent.com/freebsd/](https://mirrors.cloud.tencent.com/freebsd/)
- HUAWEI
  - [https://repo.huaweicloud.com/freebsd/](https://repo.huaweicloud.com/freebsd/)
- 中科大
  - [https://mirrors.ustc.edu.cn/freebsd/](https://mirrors.ustc.edu.cn/freebsd/)
- 兰州大学
  - [https://mirror.lzu.edu.cn/freebsd/](https://mirror.lzu.edu.cn/freebsd/)
- 北京交通
  - [https://mirror.bjtu.edu.cn/freebsd/](https://mirror.bjtu.edu.cn/freebsd/)
- 首都在线
  - [http://mirrors.yun-idc.com/freebsd/](http://mirrors.yun-idc.com/freebsd/)

### GNU

#### Official

- [https://www.gnu.org/software/octave/download](https://www.gnu.org/software/octave/download)

#### Mirrors

- [Aliyun](https://developer.aliyun.com/mirror/gnu)
  - [https://mirrors.aliyun.com/gnu/](https://mirrors.aliyun.com/gnu/)
- Tencent
  - [https://mirrors.cloud.tencent.com/gnu/](https://mirrors.cloud.tencent.com/gnu/)
- HUAWEI
  - [https://repo.huaweicloud.com/gnu/](https://repo.huaweicloud.com/gnu/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/gnu/](https://mirrors.tuna.tsinghua.edu.cn/gnu/)
- 中科大
  - [https://mirrors.ustc.edu.cn/gnu/](https://mirrors.ustc.edu.cn/gnu/)
- 兰州大学
  - [https://mirror.lzu.edu.cn/gnu/](https://mirror.lzu.edu.cn/gnu/)
- 北京交通
  - [https://mirror.bjtu.edu.cn/gnu/](https://mirror.bjtu.edu.cn/gnu/)

## Other-Mirror

### Docker-hub

没有整理Docker-hub的镜像的原因是，鉴于这种仓库的特殊性，国内也确实没有一家将之全站镜像的，果真如此，倒也并不科学了。

不过关于Docker-hub以及GitHub的使用，又的确会经常遇到网络方面的问题，因此也一直在留心这方面的解决方案，目前大多是提供加速的方案，算是镜像方案之下的一个折中策略。

#### Official

- [https://hub.docker.com/](https://hub.docker.com/)

其他的镜像仓库不再单独列出。

#### Mirrors

`使用方式：`

使用方式都是替换原来镜像的前缀域名即可实现加速效果，比如：

```
原来地址： eryajf/centos:7.4  # 这个是官方镜像，省略了前边的域名
替换地址： docker.mirrors.sjtug.sjtu.edu.cn/eryajf/centos:7.4
```

另外，加速通常只是针对某个源站进行的加速，国外对公开放的docker仓库并非官方一家，因此这里就以源站的维度进行区分，整理出经过测试可用的加速站。

- Docker-hub
  - 上海交通大学
    - docker.mirrors.sjtug.sjtu.edu.cn
  - [中科大](https://mirrors.ustc.edu.cn/help/dockerhub.html)
    - docker.mirrors.ustc.edu.cn
  - [docker proxy](https://dockerproxy.com/)
    - dockerproxy.com
- gcr.io
  - [docker proxy](https://dockerproxy.com/)
    - gcr.dockerproxy.com
  - [lank8s](https://github.com/lank8s)：后期可能会转成付费
    - gcr.lank8s.cn
- k8s.gcr.io
  - 上海交通大学
    - k8s-gcr-io.mirrors.sjtug.sjtu.edu.cn
  - [docker proxy](https://dockerproxy.com/)
    - k8s.dockerproxy.com
  - [lank8s](https://github.com/lank8s)
    - lank8s.cn
- ghcr.io
  - [docker proxy](https://dockerproxy.com/)
    - ghcr.dockerproxy.com
- quay.io
  - 中科大
    - quay.mirrors.ustc.edu.cn

## 如何贡献

欢迎大家补充优秀的镜像，让我们一起建设好这个仓库！

贡献内容只需要注意目录的层级与原有内容格式对齐，术业有专攻，大家提交的镜像，最好都是有经过测试验证的！

## 贡献者

<!-- readme: collaborators,contributors -start -->
<table>
<tr>
    <td align="center">
        <a href="https://github.com/eryajf">
            <img src="https://avatars.githubusercontent.com/u/33259379?v=4" width="100;" alt="eryajf"/>
            <br />
            <sub><b>二丫讲梵</b></sub>
        </a>
    </td>
    <td align="center">
        <a href="https://github.com/Hanjingxue-Boling">
            <img src="https://avatars.githubusercontent.com/u/87272716?v=4" width="100;" alt="Hanjingxue-Boling"/>
            <br />
            <sub><b>Hanjingxue Boling</b></sub>
        </a>
    </td>
    <td align="center">
        <a href="https://github.com/colinxu2020">
            <img src="https://avatars.githubusercontent.com/u/63941938?v=4" width="100;" alt="colinxu2020"/>
            <br />
            <sub><b>Colinxu2020</b></sub>
        </a>
    </td>
    <td align="center">
        <a href="https://github.com/danbai225">
            <img src="https://avatars.githubusercontent.com/u/40517872?v=4" width="100;" alt="danbai225"/>
            <br />
            <sub><b>淡白</b></sub>
        </a>
    </td></tr>
</table>
<!-- readme: collaborators,contributors -end -->