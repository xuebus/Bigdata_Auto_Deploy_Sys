## 大数据平台自助管理系统

该系统为用户提供一套基于浏览器的可视化大数据平台自助管理系统。用户可以利用该系统方便地管理和维护大数据平台，更加专注于应用的开发。

## 目录结构

```
-- agent(各个节点的守护进程)
-- deploy(安装部署脚本)
-- web(Web服务端程序，部署在Tomcat上)
-- docs(文档)
```

## 安装部署

### 1、下载源代码

```
git clone https://github.com/BryantChang/Bigdata_Auto_Deploy_Sys.git
```

### 2、部署Web应用程序

* 进入deploy目录
* 设置环境变量（编辑env.sh，包括hadoop,spark,tomcat安装目录以及mysql相关配置信息等）
* 执行web程序安装脚本

```
sh install_web.sh
注意：若需要安装mysql则执行-m os选项，其中os代表的是操作系统，可选项为centos或ubuntu。若需要初始化，则执行-i选项。具体使用方式使用: sh install_web.sh -h。
```

### 3、部署agent

* 配置相关节点列表（编辑agent_node_list文件）
* 安装部署agent

```
执行sh install_agent.sh
```

## 相关配置文件编辑方式

### 1、agent_node_list

```
格式：host/ip=passwd
```

### 2、hadoopnodes

```
格式：host:ip:os:sshport:sshuser:sshpassword:issudo_(1/0):namenode_yes:datanode_(1/0):secondarynamenode_(1/0):resourcemanager_(1/0):nodemanager_(1/0):isformatted_(1/0)
```

### 3、sparknodes

```
格式：host:ip:os:sshport:sshuser:sshpassword:master_(1/0):slave_(1/0):issudo_(1/0)
```




