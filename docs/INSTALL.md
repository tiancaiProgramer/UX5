# 从零安装 UX5

## 1. 准备

- 本预览面向 Windows 11 x64；其他 Windows 版本尚未做本轮实际验证。
- 至少预留 8 GB，用于程序、安装临时文件及维护快照；无需创建虚拟机。
- 使用当前桌面管理员账户正常确认 UAC。无需更改 PowerShell 执行策略、系统防火墙或文件夹 ACL。
- 如果电脑已经装有 UX5，先阅读 [已知问题](KNOWN-ISSUES.md)。本包目前按全新安装发布，不作为旧版覆盖升级的推荐包。

## 2. 下载和解压

1. 打开 [Releases](https://github.com/tiancaiProgramer/UX5/releases)。
2. 下载名称为 `UX5-0.3.0-preview-win-x64.zip` 的附件。GitHub 自动生成的 Source code 压缩包不是安装包。
3. 下载同一 Release 的 SHA256 校验文件，与本机文件 SHA256 比较。
4. 解压全部文件，不要直接在压缩包内双击运行。

主要文件：

| 文件 | 用途 |
| --- | --- |
| `OpenCodeBridge.exe` | UX5 主程序，普通双击这一份 |
| `OpenCodeBridge.ModuleWorker.exe` | 配套工作进程，不单独打开 |
| `ModuleWorker.contract.json` | Worker 字节/身份契约，保留在同一目录 |
| `THIRD-PARTY-NOTICES.md` | 第三方声明 |
| `安装与使用.txt`、`release-manifest.json`、`SHA256SUMS.txt` | 使用说明、版本与校验信息 |

## 3. 首次安装

1. 普通双击解压目录的 `OpenCodeBridge.exe`。
2. 如果只看到 UX5 小窗口，点击“打开控制中心”。网页在本机回环地址打开，通常为 `http://127.0.0.1:8790/`。
3. 在网页打开 **设置 → 运行环境与维护 → 系统与运行环境**。
4. 点击“安装”，确认网页提示，等待正常 Windows UAC 并亲自审核。
5. 安装准备可能延迟，等待即可，不要重复发起或切换到其他安装包。
6. 看到安装完成后，退出这次从解压目录启动的控制器，再打开桌面 **UX5** 快捷方式。

安装后的主程序通常为 `C:\Program Files\OpenCodeBridge\OpenCodeBridge.exe`。新装工作目录通常为 `C:\OpenCodeBridge\Sandbox`，以界面实际显示为准；不要手工移动已绑定的运行目录。

## 4. 接下来做什么

进入 [配置与首次使用](CONFIGURATION.md)，先配置可用的执行模型及需要的思考 AI，然后启动后台。工程需要的 Git、SDK 或其他工具按实际任务另行配置，运行 UX5 本身不要求先装完整开发工具链。

若安装失败，保留错误类别和提示，反馈到 Issue；不要反复覆盖安装，也不要通过改安全策略绕过错误。
