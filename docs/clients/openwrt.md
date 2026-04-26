# OpenWrt

OpenWrt 适合需要在路由器侧统一接管设备流量的用户。它的配置方式和普通定制客户端不同，适合已经熟悉 OpenWrt、LuCI 和基础网络配置的用户。

## 适用场景

- 家中多台设备需要统一走同一套代理配置。
- 电视、游戏机等设备不方便单独安装客户端。
- 希望通过路由器实现透明代理或统一分流。

## 说明

OpenWrt 安装包内通常已经包含：

- 预编译好的 `mihomo` 核心二进制
- OpenWrt 启动脚本
- UCI 配置
- 用于透明代理的 `nftables` 防火墙规则

安装完成后，可以通过 LuCI 图形界面或 UCI 命令行进行配置。

## 下载地址

<a class="doc-button" href="https://down.zcjdgo.de/soft/artifact-openwrt.zip">下载 OpenWrt 安装包</a>

!!! info "安装前提示"
    请先确认你的路由器架构，例如 `aarch64`、`arm64`、`x86_64` 等，并下载对应架构的安装包。

## 安装方式 A：使用 opkg 安装（推荐）

如果你拿到的是 `.ipk` 安装包，推荐使用 `opkg` 安装。

先安装核心程序：

```sh
# 安装核心程序
# 请根据你的路由器架构选择对应的 .ipk 文件
opkg install mihomo_*_aarch64_generic.ipk
```

再安装 LuCI 管理界面：

```sh
# 安装 LuCI Web 管理界面
# 该包通常与架构无关
opkg install luci-app-mihomo_*_all.ipk
```

安装完成后，进入：

```text
LuCI -> 服务 -> Mihomo
```

## 安装方式 B：使用自解压 .run 包

如果你拿到的是 `.run` 安装包，可以直接在路由器上执行：

```sh
chmod +x mihomo-openwrt-arm64-*.run
./mihomo-openwrt-arm64-*.run
```

执行完成后，程序和相关文件会自动释放到对应目录。

## 基础配置

安装完成后，可以通过 UCI 命令启用 Mihomo 并设置订阅地址：

```sh
uci set mihomo.config.enabled='1'
uci set mihomo.config.subscription_url='https://your-panel.com/api/v1/client/subscribe?token=xxx'
uci commit mihomo
/etc/init.d/mihomo start
```

说明：

- `enabled='1'` 表示启用 Mihomo
- `subscription_url` 需要替换成你自己的订阅地址
- `uci commit mihomo` 用于保存配置
- `/etc/init.d/mihomo start` 用于启动服务

## 图形界面入口

安装完成后，可以在 LuCI 中找到：

```text
服务 -> Mihomo
```

如果 LuCI 插件安装成功，但菜单里没有显示，请先刷新浏览器，必要时重启路由器或重新登录 LuCI。

## Web Dashboard

Mihomo 默认 Web Dashboard 地址通常为：

```text
http://<router-ip>:9090/ui
```

例如：

```text
http://192.168.1.1:9090/ui
```

请将其中的 `<router-ip>` 替换为你的路由器管理地址。

## 常见问题

### 安装失败

- 请确认安装包架构和路由器 CPU 架构一致。
- 请确认路由器剩余存储空间足够。
- 如果是 `opkg` 安装失败，可以先执行 `opkg update` 后再试。

### LuCI 中看不到 Mihomo

- 请确认 `luci-app-mihomo_*_all.ipk` 已经安装成功。
- 尝试重新登录 LuCI。
- 必要时重启路由器。

### 服务启动失败

- 请检查订阅地址是否填写正确。
- 请检查路由器本身是否可以联网。
- 请确认 `mihomo` 配置已经提交保存。

### Web Dashboard 打不开

- 请确认 Mihomo 服务已经成功启动。
- 请确认本地设备与路由器在同一网段。
- 请检查路由器防火墙是否拦截了 `9090` 端口。

[返回首页](../index.md)
