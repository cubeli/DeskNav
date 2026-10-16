# DeskNav

**本地工具 + 收藏网址的桌面快速入口** · 一键直达

[中文](#中文) | [English](#english)

---

## 中文

DeskNav 是一个 Windows 桌面导航工具：把常用的本地程序和高频网址收拢到一个界面，支持搜索、分类与一键启动，常驻托盘随时唤出。

### 功能特性

| 功能 | 说明 |
|---|---|
| 工具启动 | 一键启动任意本地程序，支持启动参数、工作目录自动设为程序所在目录；需要管理员权限的程序会自动请求提权 |
| 网址收藏 | 分类管理常用网址，自动获取站点图标，支持从浏览器导入 / 导出标准 HTML 书签文件 |
| 全局搜索 | 支持中文拼音首字母检索，输入即可定位到工具或网址 |
| 托盘常驻 | 关闭窗口不退出，驻留系统托盘；支持鼠标中键快速唤出 |
| 窗口行为 | 可设置启动某个工具或打开某个网址后自动收起窗口，减少切换成本 |
| 主题 | 浅色 / 深色主题，跟随系统或手动指定 |
| 操作日志 | 记录启动、增删改、导入导出等操作与结果，便于排查问题 |
| 自动更新 | 启动后自动检查新版本，可在应用内直接下载安装 |

### 系统要求

- Windows 10（1803 及以上）或 Windows 11，64 位
- 需要 WebView2 运行时（Windows 11 已内置；部分 Windows 10 需要单独安装，可从 Microsoft 官网免费获取）

### 下载与安装

前往本仓库的 **Releases** 页面下载最新版的 `DeskNav_x.y.z_x64-setup.exe`，双击安装即可。

- 安装模式为「仅当前用户」，**无需管理员权限**
- 程序与数据默认安装在 `%LOCALAPPDATA%\DeskNav\`
- 配置与数据文件（`config` 目录）与主程序同级存放，卸载前如需保留请自行备份

### 关于安装包未签名

当前发布的安装包**未使用商业代码签名证书签名**，因此首次运行时 Windows SmartScreen 可能提示「Windows 已保护你的电脑」。这是未签名软件的常规提示，不代表程序存在风险。

如遇提示，可点击「更多信息」→「仍要运行」继续。若希望自行校验文件完整性，请对照对应 Release 说明中提供的 **SHA-256** 值：

```
certutil -hashfile DeskNav_x.y.z_x64-setup.exe SHA256
```

### 数据与隐私

- 所有工具、网址与配置数据**仅保存在本机**，不上传任何服务器
- 程序仅在检查更新时访问本仓库的 Releases 地址，不发送任何本地数据
- 操作日志同样仅存于本地 `config` 目录

### 自动更新

程序启动数秒后会自动检查新版本（静默进行，失败不会打扰）。发现新版本时会弹出提示，可选择「稍后」或「立即更新」；更新过程会显示下载进度，完成后自动重启。

### 常见问题

**Q：把程序复制到别的位置，数据和更新怎么算？**
A：配置与数据随主程序所在目录存放。若把主程序复制到其他位置单独使用，会产生独立的数据副本；而自动更新只会更新通过安装包装到 `%LOCALAPPDATA%\DeskNav\` 的那一份，复制出去的副本需要重新下载新版覆盖。

**Q：杀毒软件报毒？**
A：未签名的自研软件偶有误报。可核对 Release 中的 SHA-256 值确认文件完整性；如仍有顾虑，建议先不要运行。

**Q：卸载后数据还在吗？**
A：卸载程序会移除程序文件。如需保留工具与网址配置，请在卸载前备份 `config` 目录。

### 许可证

本软件为专有软件。**安装包可免费下载使用，但源代码不公开**。详细条款见 [LICENSE](LICENSE)。

---

## English

DeskNav is a lightweight Windows desktop launcher that brings your local programs and frequently used websites into one place, with search, categories and one-click launch. It stays in the system tray for quick access.

### Features

| Feature | Description |
|---|---|
| Launch programs | Start any local executable with optional arguments. The working directory is set to the program's own folder; programs requiring elevation will trigger a UAC prompt |
| Bookmark websites | Organize sites by category, fetch site icons automatically, and import / export standard HTML bookmark files from your browser |
| Global search | Pinyin-aware search (including Chinese initials) to locate programs or sites instantly |
| Tray resident | Closing the window keeps DeskNav in the tray; middle mouse button brings it back |
| Auto-hide | Optionally hide the window automatically after launching a program or opening a site |
| Themes | Light / dark theme, following the system or set manually |
| Activity log | Records launches, edits and imports with their results, useful for troubleshooting |
| Auto update | Checks for new versions on startup and installs them from within the app |

### Requirements

- Windows 10 (1803 or later) or Windows 11, 64-bit
- WebView2 runtime (bundled with Windows 11; may need a separate free install on some Windows 10 systems)

### Download & Install

Download the latest `DeskNav_x.y.z_x64-setup.exe` from the **Releases** page of this repository and run it.

- Installs per-user; **no administrator rights required**
- The application is installed to `%LOCALAPPDATA%\DeskNav\`
- Configuration and data (the `config` folder) live next to the executable — back them up before uninstalling if you want to keep them

### About the unsigned installer

The installer is **not signed with a commercial code-signing certificate**, so Windows SmartScreen may show a "Windows protected your PC" warning on first run. This is the standard prompt for unsigned software and does not indicate that the program is unsafe.

If you see the warning, choose "More info" → "Run anyway". To verify file integrity yourself, compare against the **SHA-256** value published in the corresponding Release notes:

```
certutil -hashfile DeskNav_x.y.z_x64-setup.exe SHA256
```

### Data & Privacy

- All programs, bookmarks and settings are stored **locally only**; nothing is uploaded
- The application contacts this repository's Releases URL solely to check for updates, and sends no local data
- The activity log also stays in the local `config` folder

### Auto Update

DeskNav checks for updates a few seconds after startup (silently — failures are not intrusive). When a new version is available it prompts you; you can postpone or update immediately. Download progress is shown and the app restarts when finished.

### FAQ

**Q: What if I copy the program elsewhere?**
A: Configuration lives alongside the executable, so a copied instance keeps its own data. Auto update only updates the copy installed into `%LOCALAPPDATA%\DeskNav\`; a copied instance must be replaced manually.

**Q: Antivirus flags it?**
A: False positives occasionally occur with unsigned independent software. Verify the SHA-256 from the Release; if in doubt, do not run it.

**Q: Does uninstalling remove my data?**
A: The uninstaller removes the program files. Back up the `config` folder beforehand if you want to keep your programs and bookmarks.

### License

Proprietary software. **The installer is free to download and use, but the source code is not public.** See [LICENSE](LICENSE) for details.
