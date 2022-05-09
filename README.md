# Thanks-Mirror

本项目灵感来自：[FUCK-GFW](https://github.com/comwrg/FUCK-GFW)，FUCK-GFW分享的是包管理器配置代理的方法，这里分享的是包管理器直接可用，质量好，速度快的镜像，以及一些其他常用软件，系统镜像的国内镜像。

在此，对那些提供公共仓库镜像的企业或组织，致以感谢🫡！

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**目录**

- [Package-Mirror](#package-mirror)
  - [Go](#go)
  - [Npm](#npm)
  - [Pip](#pip)
  - [Maven](#maven)
  - [Yum](#yum)
  - [Homebrew](#homebrew)
- [Software-Mirror](#software-mirror)
  - [Docker](#docker)
  - [Jenkins](#jenkins)
  - [ElasticSearch](#elasticsearch)
- [Stargazers over time](#stargazers-over-time)

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

  - https://registry.npmjs.org

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

#### Mirrors

目前代理外部私仓有：

- Aliyun
  - http://mirrors.aliyun.com/pypi/
- douban
  - http://pypi.douban.com/
- 清华
  - https://pypi.tuna.tsinghua.edu.cn/
- 163
  - [https://mirrors.163.com/pypi](https://mirrors.163.com/pypi)
- HUAWEI
  - [https://repo.huaweicloud.com/repository/pypi](https://repo.huaweicloud.com/repository/pypi)
- Tencent
  - https://mirrors.cloud.tencent.com/pypi/

### Maven

#### Configuration

Java系的工具版本规范如下：

- `JDK：`1.8.0_292
- `MVN：`3.3.9

配置Maven代理，需进行如下配置：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0 http://maven.apache.org/xsd/settings-1.0.0.xsd">
  <localRepository>~/.m2/repository</localRepository>
  <pluginGroups>
  </pluginGroups>
  <proxies>
  </proxies>

  <servers>
    <server>
      <id>releases</id>
      <username>username</username>
      <password>password</password>
    </server>
    <server>
      <id>snapshots</id>
      <username>username</username>
      <password>password</password>
   </server>
  </servers>

  <mirrors>
    <mirror>
      <id>nexus-eryajf</id>
      <mirrorOf>*</mirrorOf>
      <name>Nexus osc</name>
      <url>http://nexus.eryajf.net/repository/maven/</url>
    </mirror>
  </mirrors>

  <profiles>
    <profile>
      <id>developer</id>
    <activation>
      <jdk>jdk-1.8</jdk>
    </activation>
    <repositories>
    <repository>
      <id>nexus-eryajf-local</id>
      <name>local private nexus</name>
      <url>http://nexus.eryajf.net/repository/maven/</url>
    <releases>
      <enabled>true</enabled>
    </releases>
    <snapshots>
      <enabled>true</enabled>
      <updatePolicy>always</updatePolicy>
    </snapshots>
    </repository>
    </repositories>
    <pluginRepositories>
    <pluginRepository>
      <id>nexus-eryajf</id>
      <name>local private nexus</name>
      <url>http://nexus.eryajf.net/repository/maven/</url>
    <releases>
      <enabled>true</enabled>
    </releases>
    <snapshots>
      <enabled>true</enabled>
    </snapshots>
    </pluginRepository>
    </pluginRepositories>
    </profile>
  </profiles>

  <activeProfiles>
    <activeProfile>developer</activeProfile>
  </activeProfiles>
</settings>
```

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
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/docker-ce/](https://mirrors.tuna.tsinghua.edu.cn/docker-ce/)
- 中科大
  - [https://mirrors.ustc.edu.cn/docker-ce/](https://mirrors.ustc.edu.cn/docker-ce/)
- 西北农林科技大学
  - [https://mirrors.nwsuaf.edu.cn/docker-ce/](https://mirrors.nwsuaf.edu.cn/docker-ce/)
- 浙江大学
  - [http://mirrors.zju.edu.cn/docker-ce/](http://mirrors.zju.edu.cn/docker-ce/)

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

### ElasticSearch

#### Official

- [https://www.elastic.co/cn/downloads/elasticsearch](https://www.elastic.co/cn/downloads/elasticsearch)

#### Mirrors

- elastic中文社区
  - [https://elasticsearch.cn/download/](https://elasticsearch.cn/download/)
- HUAWEI
  - [https://repo.huaweicloud.com/elasticsearch/](https://repo.huaweicloud.com/elasticsearch/)
- Tencent
  - [https://mirrors.cloud.tencent.com/elasticstack/](https://mirrors.cloud.tencent.com/elasticstack/)
- 清华
  - [https://mirrors.tuna.tsinghua.edu.cn/elasticstack/](https://mirrors.tuna.tsinghua.edu.cn/elasticstack/)
- 南京邮电
  - [http://mirrors.njupt.edu.cn/elasticstack/](http://mirrors.njupt.edu.cn/elasticstack/)

## Stargazers over time

[![Stargazers over time](https://starchart.cc/eryajf/Thanks-Mirror.svg)](https://starchart.cc/eryajf/Thanks-Mirror)