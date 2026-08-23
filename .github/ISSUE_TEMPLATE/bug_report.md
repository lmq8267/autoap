---
name: 问题反馈 / Bug report
about: 反馈 AutoAP 运行、扫描、中继、切换、接口识别等问题
title: "[Bug] "
labels: bug
assignees: ""
---

## 问题现象

请说明你遇到的问题、期望结果和实际结果。

## 复现步骤

1. 
2. 
3. 

## 环境信息

- 设备型号：
- OpenWrt / 固件版本：
- CPU 架构：
- AutoAP 版本：
- 问题发生时间：

## 请贴出以下命令输出

隐私信息可以改成 `*`，例如 IP、SSID、BSSID、MAC、密码、Token、地理位置等，但请保留字段名和格式。

```sh
uname -a
cat /etc/openwrt_release 2>/dev/null
/usr/bin/autoap -v 2>/dev/null || /tmp/autoap -v 2>/dev/null
```

```sh
uci show wireless
uci show network
uci show firewall
```

```sh
ls -1 /sys/class/net
iw dev 2>/dev/null
```

```sh
for p in /sys/class/net/*; do
    n="${p##*/}"
    echo "### $n"
    iwinfo "$n" info 2>/dev/null
done
```

```sh
cat /etc/autoap/config.json 2>/dev/null
```

```sh
logread | grep -i autoap | tail -120
```

如果是扫描不到热点，也请补充：

```sh
iwinfo <扫描接口> scan 2>/dev/null | head -120
```

如果是无法联网或自动切换异常，也请补充：

```sh
ip route
ip -6 route
ping -4 -c 3 -W 2 www.baidu.com
ping -4 -c 3 -W 2 114.114.114.114
ping6 -c 3 -W 2 2400:3200::1
```

## 脱敏示例

可以这样处理：

```text
option ssid '******'
option key '********'
option bssid '**:**:**:**:**:**'
IPv4 192.168.*.*
公网 IP：***.***.***.***
```

## 其它补充

可以贴截图、前端页面提示、你已经尝试过的处理方法。
