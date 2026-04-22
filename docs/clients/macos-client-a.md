
# macOS 定制客户端

macOS 定制客户端适合 Mac 用户使用，兼容 Apple Silicon 和 Intel 机型。定制客户端已经预先适配本站服务，安装后输入账号密码即可使用，可避免手动复制链接、导入地址和维护复杂配置。

## 下载地址

<a class="doc-button" href="https://down.zcjdgo.de/soft/zcjsmacos.dmg">下载 macOS 定制客户端</a>

## 安装客户端

1. 下载 `.dmg` 安装包。
2. 打开安装包，将应用拖入 `Applications` 文件夹。
3. 如果系统提示应用已损坏或无法打开，请先按下方说明解除限制。

!!! warning "无法打开时的处理方式"
    macOS 对非 App Store 下载的应用可能会提示无法打开。可以打开「终端」，执行以下命令：

    ```bash
    sudo xattr -r -d com.apple.quarantine /Applications/众筹加速器.app
    ```

    如果仍然看不到「任何来源」选项，可以继续执行：

    ```bash
    sudo spctl --master-disable
    ```

    输入密码时终端不会显示字符，输入完成后按回车即可。升级 macOS 后如果再次无法打开客户端，可以重复以上操作。

## 开启代理

打开客户端后，输入账号密码登录，选择可用节点并开启连接。如果浏览器可以访问但其他应用不走代理，请检查客户端内的系统代理开关。

## 常见问题

- 如果客户端卡住或无法启动，请先完全退出后重新打开。
- 如果提示应用已损坏，请执行上方终端命令。
- 如果节点全部超时，请更新配置并更换网络测试。

[返回首页](../index.md)
