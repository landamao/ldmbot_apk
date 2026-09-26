# [ldmbot](https://github.com/landamao/ldm_AstrBot) 安卓客户端

ldmbot安卓客户端是一个Android应用，内置 Debian 环境，并提供终端、浏览器和文件管理界面。它主要用于部署和管理[ldmbot](https://github.com/landamao/ldm_AstrBot)，也可以作为运行在Android上的Linux环境使用，例如运行Python服务、网页服务或脚本任务。

- **当前版本**：2.0.11（更新内容见 [更新日志.md](./更新日志.md)）
- **系统要求**：Android 8.0 及以上，arm64架构设备，**主流设备都支持**
- **GitHub**：[https://github.com/landamao/ldmbot_apk](https://github.com/landamao/ldmbot_apk)
- **下载**： [https://github.com/landamao/ldmbot_apk/releases/latest/download/ldmbot-release.apk](https://github.com/landamao/ldmbot_apk/releases/latest/download/ldmbot-release.apk)



## 主要用途与功能

### 1. 部署和管理ldmbot

不需要安装Termux，也不需要手动输入命令，主要操作都可以在界面中完成：

- 主页提供安装、更新、重新安装、启动、停止、重启等按钮，状态卡会显示安装与运行状态；
- 服务启动后，点击“打开”进入WebUI，地址会跟随实际端口；
- 如果忘记 WebUI 密码，可使用“重置WebUI密码”恢复默认密码（ldm/ldm），或交互式设置新密码；
- 安装和重新安装不会删除 `data` 数据，聊天记录和配置会保留。

### 2. Android上的Linux环境

应用内置完整的Debian环境，包含bash、python3、apt、uv等工具，可运行自己的服务或脚本：

- **多标签终端**：支持多个会话并行，互不干扰；支持双指缩放字号、两行快捷键栏、长按复制粘贴；
- **多标签浏览器**：支持本地和外部地址；标签自动保存，重启后恢复；加载失败可重试；支持电脑模式；
- **端口服务访问**：终端中启动 WebUI、网页或 API 后，可在浏览器输入 `127.0.0.1:端口` 访问，不需要来回切换应用；
- **文件浏览器**：支持浏览Linux全目录，以及上传、下载、重命名、移动、修改权限；内置全屏编辑器，带行号、双指缩放和只读开关，可直接修改配置或脚本；
- **挂载到系统文件**：Linux根目录以“ldmbot”名称挂载到系统文件接口，可在系统“文件”App 中看到；也支持第三方文件管理器，推荐 [MT 管理器](https://mt2.cn/)，应用内有图文教程；
- **复制到 ldmbot 内**：在其他App中快速通过“打开方式”将文件导入Linux环境；同名文件可选择覆盖或自动重命名，**以免在聊天app中下载的文件找不到文件路径复制不到ldmbot内**

### 3. 后台保活

如果需要在手机上长期运行服务，可在设置中组合使用以下保活选项：

- 前台服务常驻通知；
- 电池优化豁免；
- 悬浮窗保活；
- 激进保活模式：Root 设备可用，并且提供[`MagiskSU`](https://magiskcn.com/)/[`KernelSU`](https://kernelsu.com/)模块设置指南，并支持一键复制排障信息。


## 快速上手

### 使用 ldmbot

1. 从[GitHub Releases](https://github.com/landamao/ldmbot_apk/releases)下载 APK 并安装，或点击[下载](https://github.com/landamao/ldmbot_apk/releases/latest/download/ldmbot-release.apk)；
2. 首次打开后等待Linux环境初始化完成（约几十秒），阅读并同意免责声明；
3. 在主页点击“安装”自动部署，完成后点击“启动”；
4. 状态卡变绿后，点击“打开”进入 WebUI。

### 作为Linux环境使用

1. 初始化完成后进入“终端”，即为完整的Debian Linux环境；
2. 提供`apt/uv/pip`包管理服务，可用于`安装/同步`依赖，运行服务或脚本；
3. 切换到“浏览器”，输入 `127.0.0.1:端口` 访问服务；
4. 如需长期挂机，在设置中开启保活选项。

## 使用须知

- 关闭终端标签会结束该会话中的全部进程，包括正在运行的服务。不要关闭需要保留的会话；
- 专用“ldmbot”会话由应用接管，不能输入文字，也不能关闭。这是设计行为。管理操作请使用主页按钮或该会话的专属快捷栏，其他终端不受影响；
- “挂载手机存储”默认关闭。在设置中开启后，新开的终端会话可通过`/root/sdcard`访问手机存储；
- 底栏四个页面处于同一层级。在主页按两次返回键退出应用；文件管理等子页面会逐层返回。

## 更多实用功能

- **相关目录直达**：root、ldmbot、data、plugins、backups 可一键进入；目录不存在时自动创建；
- **备份管理**：提供备份目录文件页，支持上传和下载；
- **重置 ldmbot**：两次确认后清空并重新安装，可选择保留 `data`；
- **教程中心**：提供[NapCat](https://github.com/NapNeko/NapCatQQ)安装教程、[MT 管理器](https://mt2.cn/)导入文件教程，图文分步；
- **清除浏览数据**：可按范围清除缓存、Cookie、本地存储和历史记录。