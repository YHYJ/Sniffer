# Sniffer

Packet sniffing and forwarding tool

---

## Table of Contents

<!-- vim-markdown-toc GFM -->

* [依赖](#依赖)
* [使用](#使用)
* [编译](#编译)

<!-- vim-markdown-toc -->

---

<!-- Object info -->

---

## 依赖

> 使用pipenv进行虚拟环境和包管理

执行以下命令安装依赖包：

```shell
pipenv sync
```

在Linux系统运行无需额外安装除Python包之外的依赖包，但在Windows上运行需要安装下列依赖包：

- [Npcap](https://nmap.org/npcap/#download)：Npcap是Windows的Nmap项目的数据包嗅探和发送库，它基于已经停止维护的WinPcap，具有快速、可移植、安全和高效的优点
- [vc_redist.exe](https://www.microsoft.com/zh-cn/download/details.aspx?id=48145)：命令执行时可能会报"*api-ms-win-crt-runtime-l1-1-0.dll 丢失*"的错误，需要安装vc_redist.exe，注意区分32/64位系统

## 使用

1. 首先运行[nic.py](./nic.py)获取网络接口信息，运行结果示例如下：

    ![NIC IPv4 info](https://gitee.com/YJ1516/MyPic/raw/master/picgo/nic_ipv4.png)

    ![NIC IPv6 info](https://gitee.com/YJ1516/MyPic/raw/master/picgo/nic_ipv6.png)

    ![NIC IPv4 & IPv6 info](https://gitee.com/YJ1516/MyPic/raw/master/picgo/nic_ipv46.png)

    > 具体参数请执行`python nic.py -h`查看

2. 然后根据实际情况修改配置文件[sniff.toml](./conf/sniff.toml)

    > 配置指导已经写到了sniff.toml的注释信息里

3. 最后运行[sniff.py](./sniff.py)即可：

    ![snipper -i](https://gitee.com/YJ1516/MyPic/raw/master/picgo/snipper_i.png)

    ![snipper -s](https://gitee.com/YJ1516/MyPic/raw/master/picgo/snipper_s.png)

    > 具体参数请执行`python sniff.py -h`查看

## 编译

**注意：暂不支持Python3.9+**

如果需要将程序编译为二进制文件，在对应系统平台上执行以下命令：

- 编译nic.py

    ```shell
    pyinstaller -F nic.py --additional-hooks-dir=./hook
    ```

- 编译sniff.py

    ```shell
    pyinstaller -F sniff.py --additional-hooks-dir=./hook
    ```
