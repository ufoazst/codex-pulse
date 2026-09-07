<p align="center"><img src="assets/icon.png" width="96" height="96" alt="Codex Pulse 图标"></p>

# Codex Pulse

在 Mac 菜单栏和桌面小组件中查看 Codex 的本地 token 消耗、账户额度和重置时间。

**[下载 v1.1.2 安装包](https://github.com/ufoazst/codex-pulse/releases/download/v1.1.2/CodexPulse-1.1.2-arm64.dmg)** · **[使用说明](docs/使用说明.md)** · **[版本记录](CHANGELOG.md)**

本仓库仅发布安装包、使用说明和版本信息，不包含工程源码。

## 功能

- 原生 macOS 小、中、大三种尺寸桌面小组件。
- 菜单栏显示今日 token；点击查看详情或打开常驻浮窗。
- 按模型统计今日、近 7 天和全部本地记录的输入、缓存与输出 token。
- 显示服务端返回的共享额度、独立额度、重置时间和倒计时。
- 自动同步，显示更新时间；过期数据标记为快照。

## 安装要求

- Apple Silicon Mac（M 系列芯片），macOS 14 或更高版本。
- 已安装并登录 Codex；应用支持查找 ChatGPT.app / Codex.app 中的 Codex 程序。
- 可用的 `/usr/bin/python3`。此安装包不捆绑 Codex 或 Python。

当前版本使用 **ad-hoc 签名，未经过 Apple 公证**，属于实验性本地工具。已在开发者的 macOS 26.6.2 / Apple Silicon 环境验证；尚未覆盖其他 Mac 的安装兼容性。下载后 macOS 可能阻止直接打开，请参阅使用说明中的安装限制。

## 快速开始

1. 从 [Releases](https://github.com/ufoazst/codex-pulse/releases/tag/v1.1.2) 下载 `.dmg`。
2. 若旧版正在运行，先从菜单栏应用的「…」菜单退出。
3. 打开 DMG，把 **CodexPulse.app** 拖到「应用程序」，有旧版时选择替换。
4. 从「应用程序」启动 Codex Pulse，等待同步完成，然后推出安装磁盘。
5. 右键桌面 → **编辑小组件** → 搜索 **CodexPulse** → 添加「Codex 用量」。

请从「应用程序」启动，避免直接运行安装磁盘中的副本。保持菜单栏应用运行才能持续采集数据；关闭浮窗不会退出应用。

## 数据说明

Token 统计来自本机 Codex 会话日志，不包含未同步到本机的其他设备记录。额度来自 Codex 账户接口，两者统计范围不同。缓存包含在输入中，推理包含在输出中，不重复相加。共享额度不能拆成每个模型独立的百分比。

主应用约每 60 秒采集一次；原生小组件的实际刷新时机由 macOS 决定，不能保证分钟级刷新。日志不完整或格式变化可能影响统计结果。

## 隐私

应用不上传会话日志，不保存对话正文，不直接复制或输出 Codex 登录凭据。额度查询由本机 Codex 通过自身登录状态完成。小组件只读取本地汇总快照。

## 校验下载

Release 附有 `SHA256SUMS.txt`，可以核对下载文件：

```sh
shasum -a 256 CodexPulse-1.1.2-arm64.dmg
```

将输出与校验文件中的同名条目比较。校验和验证文件完整性，不等同于 Apple 公证。

## 反馈

请在 [Issues](https://github.com/ufoazst/codex-pulse/issues) 提交系统版本、应用版本和问题描述。不要附上登录凭据或完整 Codex 会话日志。

Codex Pulse 是独立开发的工具，不是 OpenAI 官方应用。
