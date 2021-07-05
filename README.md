# Airport-toolkit
各類方便機場主進行安裝維護的shell腳本    
安裝使用指南請參見 [此鏈接](https://wiki.sspanel.host/#/turnkey-install-for-node?id=%e5%90%8e%e7%ab%af%e4%b8%80%e9%94%ae%e5%ae%89%e8%a3%85%e8%84%9a%e6%9c%ac%ef%bc%88%e5%a4%a7%e7%8c%ab%e7%8c%ab%e7%89%88%ef%bc%89)

后端一键安装脚本（大猫猫版）
本文以 CentOS 7 和 CentOS 8 为例。

脚本功能
可选配置节点为WebAPI模式或MySQL模式
可选配置单端口多用户
可选注册为系统服务
安装
CentOS 7（非主要支持版本，请有条件的优先使用CentOS 8）

yum install wget -y && wget https://raw.githubusercontent.com/M1Screw/Airport-toolkit/master/ssr_node_c7.sh && chmod +x ssr_node_c7.sh && ./ssr_node_c7.sh
复制到剪贴板失败已复制
CentOS 8

dnf install wget -y && wget https://raw.githubusercontent.com/M1Screw/Airport-toolkit/master/ssr_node_c8.sh && chmod +x ssr_node_c8.sh && ./ssr_node_c8.sh
复制到剪贴板失败已复制
卸载
systemctl disable ssr_node && \rm /usr/lib/systemd/system/ssr_node.service && \rm -rf /soft/shadowsocks
复制到剪贴板失败已复制
服务启动
systemctl start ssr_node
复制到剪贴板失败已复制
服务停止
systemctl stop ssr_node
复制到剪贴板失败已复制
注意事项
由于后端最新版本不再支持Python2，在CentOS 7环境中安装时会额外安装Python3.6
所有跟节点安装本身无关的功能会通过单独的脚本提供（例如BBRv1配置在 Airport-toolkit 中有 bbr_c7/c8.sh 可用）

