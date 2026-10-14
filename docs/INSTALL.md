# 额度星盘 · Quota Orbit：安装与首次使用

适用于公开试用版 **1.3.6（72）**，Apple 芯片 Mac、macOS 13 或更高版本。[English](INSTALL_EN.md) · [返回 README](../README.md)

完成后，你可以点击桌宠查看个人 Codex 剩余额度、恢复时间及公开重置消息。只想看公开消息时，可直接使用[网页版](https://www.starshoreai.com/quota-orbit/)，无需安装或登录 Codex。

## 1. 准备 Codex CLI 与账号

公开试用包不捆绑 Codex CLI。个人额度依赖本机 CLI 的 **ChatGPT 账号登录**；仅登录 Codex 桌面应用不作为本步骤已完成的依据，API Key 用量也不等同于 ChatGPT 订阅额度。

打开 macOS「终端」，先检查：

```sh
codex --version
```

看到版本号说明终端可以找到 CLI。尚未安装时，按照 [OpenAI 官方 Codex CLI 指南](https://learn.chatgpt.com/docs/codex/cli)安装。官方 macOS 独立安装方式为：

```sh
curl -fsSL https://chatgpt.com/codex/install.sh | sh
```

这条命令会下载并运行 OpenAI 的安装脚本。安装后重新打开终端，再运行 `codex --version`，应显示版本号；若仍提示找不到命令，按安装输出检查路径，不要反复安装。

运行 `codex`，在首次登录提示中选择 **Sign in with ChatGPT**，在官方浏览器页面完成登录后返回终端。已使用 ChatGPT 账号登录的用户无需退出重登；遇到账号问题先查看[官方认证说明](https://developers.openai.com/codex/auth)。不需要为了连接额度星盘提交编码任务。

## 2. 下载并安装额度星盘

1. [下载 Quota Orbit 1.3.6（Apple 芯片）](https://github.com/koi-lee/quota-orbit/releases/download/v1.3.6/Quota-Orbit-1.3.6-arm64.dmg)。版本说明、源码及校验文件见[同一 Release](https://github.com/koi-lee/quota-orbit/releases/tag/v1.3.6)。
2. 如已有 Quota Orbit，先退出正在运行的版本并保留旧安装包。若本机版本高于1.3.6，不要用此包降级覆盖。
3. 打开 DMG，将 Quota Orbit 拖入「应用程序（Applications）」。完成后推出安装磁盘，从「应用程序」启动。

此公开包使用 Developer ID 签名并经 Apple 公证，与 App Store 版分开发行；公开试用不等于 App Store 已上架。若提示损坏或无法验证，请先重新从上述 Release 下载并核对版本、校验值，不要关闭系统保护。

可选校验：同时下载 Release 的 `SHA256SUMS.txt`，在终端输入 `shasum -a 256 `（末尾保留空格），将下载的 DMG 拖入终端并回车；输出摘要应与校验文件中同名DMG的一行一致。不一致时不要运行安装包。

## 3. 查看自己的额度

点击桌宠展开星盘，再进入「额度」。正常结果是显示本机账号的可用额度窗口、剩余比例及恢复时间；具体窗口由服务端实际返回决定。若当前处于演示模式，先退出演示，示例数字不能当成真实额度。

需要操作帮助时，从菜单栏打开「使用指南…」。出现连接提示时，先完成同一 macOS 用户下的 CLI 登录，再点击指南中的「检查连接」。公开消息可以正常显示，也不代表个人账号已经连接。

## 4. 按需开启提醒

在 App 内主动开启需要的消息提醒；系统询问时按自己的需要允许通知。没有提示或横幅时，检查 macOS「系统设置 → 通知」中的 Quota Orbit，以及专注模式设置。

本说明对应1.3.6公开包，不承诺后续本地开发版本的低额度提醒功能。公开“重置完成”消息也不等于检测到你账号的额度已恢复。

## 遇到问题

| 现象 | 先检查什么 | 预期结果 |
| --- | --- | --- |
| `codex: command not found` | 重新打开终端，按官方安装输出检查CLI路径 | `codex --version`显示版本号 |
| CLI可用但App未连接 | 同一用户下完成ChatGPT登录，使用指南中检查连接；必要时退出并重新打开App | 能读到真实额度，或得到可操作的错误提示 |
| 显示失败、过期或没有额度 | 检查网络、CLI账号是否正常，再重试；不要把未知当作0或已恢复 | 新数据恢复后再判断额度 |
| 只看到消息，没看到个人额度 | 检查CLI前提与是否为演示模式 | 分清公开消息和个人数据 |
| 找不到桌宠 | 从菜单栏查看「显示桌宠」入口 | 角色重新可见 |
| 通知没有出现 | 检查App提醒开关、系统通知及专注模式 | 权限/设置明确；不以开关开启证明送达 |

仍未解决，请到[问题反馈](https://github.com/koi-lee/quota-orbit/issues)提供App版本、macOS版本、芯片型号、复现步骤和脱敏截图。不要上传账号凭据、`auth.json`或完整会话日志。

CLI步骤依据2026-10-14核对的官方文档；本轮文档更新没有在干净Mac重新执行安装与登录。历史发布验证和其他设备兼容性边界见对应Release。
