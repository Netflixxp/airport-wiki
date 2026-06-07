# Linux 定制客户端

Linux 定制客户端适合 x86_64 架构的桌面 Linux 用户使用。安装包提供 `DEB`、`RPM` 和 `AppImage` 三种格式，下载后选择适合自己发行版的文件安装即可。

定制客户端已经预先适配本站服务，安装后输入账号密码即可使用，不需要手动导入订阅地址。

## 下载地址

<a class="doc-button" href="https://down.zcjdgo.de/soft/linux-amd64.zip">下载 Linux x86_64 定制客户端</a>

## 选择安装包

下载压缩包后，通常会看到不同格式的安装文件：

| 系统类型 | 推荐格式 |
| --- | --- |
| Ubuntu / Debian / Linux Mint | `.deb` |
| Fedora / Rocky Linux / openSUSE / CentOS 系 | `.rpm` |
| 不确定发行版或不想安装到系统 | `.AppImage` |

!!! info "架构提示"
    当前 Linux 客户端适用于 `x86_64` / `amd64` 设备。如果你使用的是 ARM 设备，例如树莓派、部分 ARM 迷你主机或 ARM Linux 平板，请不要直接安装该版本。

## 安装方式

### DEB 安装

适合 Ubuntu、Debian、Linux Mint 等发行版：

```sh
sudo apt install ./客户端文件名.deb
```

如果系统提示缺少依赖，可以先执行：

```sh
sudo apt update
sudo apt install -f
```

### RPM 安装

适合 Fedora、Rocky Linux、openSUSE、CentOS 系发行版：

```sh
sudo dnf install ./客户端文件名.rpm
```

如果你的系统使用 `yum`，可以改用：

```sh
sudo yum install ./客户端文件名.rpm
```

### AppImage 运行

适合不想安装到系统、或不确定应选择哪种安装包的用户：

```sh
chmod +x 客户端文件名.AppImage
./客户端文件名.AppImage
```

如果双击无法运行，可以在终端里执行上面的命令。

## 登录使用

打开客户端后，输入官网账号和密码登录，选择可用节点并开启连接。定制客户端会自动处理服务配置，不需要手动复制订阅链接。

## 常见问题

### AppImage 无法启动

- 请确认已经执行 `chmod +x`。
- 如果系统提示缺少 FUSE，可根据发行版安装 `fuse` 或 `libfuse2`。

### 客户端无法联网

- 请确认系统网络本身可以访问互联网。
- 请检查客户端是否已经成功登录。
- 如果节点全部超时，可以更换网络后重新测试。

### 浏览器可以访问，其他软件不走代理

请检查客户端内是否已经开启系统代理。如果某些软件有自己的代理设置，需要在软件内单独配置为使用系统代理。

[返回首页](../index.md)
