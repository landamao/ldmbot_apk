# ldmbot Android

ldmbot 的 Android 客户端，面向 arm64 安卓设备，内置独立的 Debian proot Linux 环境，无需安装或依赖 Termux。

## 主要功能

- 内置完整 Linux 终端，支持 Bash、APT、uv 和 Python 环境
- 支持多个终端会话，并在应用进程内保持连接
- 内置浏览器，可访问 ldmbot 与 NapCat 的本地管理页面
- 内置文件管理，并通过 Android DocumentsProvider 接入系统文件选择器
- 支持前台保活、电池优化引导及可选的激进保活策略
- 支持日间、夜间和跟随系统主题

## 安装

请前往 Releases 下载最新版 APK：

https://github.com/landamao/ldmbot_apk/releases/latest

当前仅提供 `arm64-v8a` 正式签名版本。下载后允许浏览器或文件管理器安装未知来源应用，即可进行安装。

## 首次使用

1. 安装并打开 APK
2. 阅读并确认使用须知
3. 进入底部「终端」页面
4. 点击快捷栏中的「安装」，按照提示安装 ldmbot 与 NapCat
5. 安装完成后，可使用快捷栏中的 `ldmbot` 与 `napcat` 启动对应服务
6. 在底部「浏览器」页面访问本地管理页面

默认安装位置：

- ldmbot：`/root/ldmbot`
- NapCat：`/root/NapCat`

## 更新说明

覆盖安装新版 APK 可以保留应用数据和已安装的 Linux 环境。若新版本涉及终端挂载或运行环境修复，请关闭旧终端标签后重新创建终端会话。

## 注意事项

- APK 体积较大，是因为内置了 Debian rootfs 与 proot 运行环境
- 本应用不依赖 Termux，也不能访问 Termux 的私有目录
- 后台保活能力受不同安卓系统和厂商策略影响，无法保证进程永不被系统终止
- debug 与 release 签名不同，不能直接互相覆盖安装

## 相关项目

ldmbot：

https://github.com/landamao/ldm_AstrBot

## 免责声明

本项目仅供学习、研究与个人使用。使用者应自行承担安装、运行及相关操作产生的风险，作者不对任何直接或间接损失负责。

## 版权

版权所有 © 懒大猫
