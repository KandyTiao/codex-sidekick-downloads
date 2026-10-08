# Codex Sidekick｜Codex 搭子 · Installation & usage

[Overview](../README.md) · [完整中文手册](USER_GUIDE.zh-CN.md)

## Windows

**Tested on Windows.** The ZIP contains the required runtime and launch scripts, not a standalone EXE installer. Official Codex and Node.js are not bundled.

1. Install and sign in to the official Codex desktop app.
2. Install Node.js 24+ or use an already discoverable compatible runtime. Run `node --version` to check it.
3. Extract `CodexSidekick-v0.4.8.zip`. Open the extracted folder containing `package.json` and double-click `安装到软件盘.cmd`.
4. Use the **Codex 搭子** desktop shortcut. Wait for running tasks to finish before normally closing Codex or accepting a repair/reopen prompt.

The default installation path is `D:\Software\CodexSidekick`. If D: is unavailable, the installer asks for a folder; it does not silently fall back to C:.

For a custom path, run this from the extracted folder:

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\scripts\install-windows.ps1 -InstallDir "E:\Software\CodexSidekick"
```

If Node is not discovered, supply its actual path with `-NodeExe`.

### Startup and controls

New installations enable current-user Windows sign-in startup and a tray watcher. The watcher runs independently of Codex, maintains the monitor and can reopen Codex with the integration enabled after the main windows exit. It does not force-close active tasks. Upgrades keep your prior startup choice.

| Launcher | Purpose |
| --- | --- |
| `启动 Codex 增强版.cmd` | Open Codex with Sidekick integration |
| `启动监测.cmd` | Open the local monitoring webpage |
| `开启自动加载.cmd` | Enable sign-in startup and start the watcher |
| `关闭自动加载.cmd` | Disable sign-in startup and stop the watcher; current Codex and monitor remain running |
| `关闭监测.cmd` | Stop the watcher and monitor without closing Codex |
| `创建桌面快捷方式.cmd` | Recreate the desktop shortcut |

Use the tray's pause option before intentionally keeping Codex closed. Exiting Sidekick for the current session does not itself remove the next Windows sign-in startup entry.

To install without sign-in startup:

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\scripts\install-windows.ps1 -NoAutoStart
```

Add `-NoStart` to also prevent the installer from starting processes immediately. `-NoStart` alone does not disable sign-in startup.

### Upgrade

Run the new package's installer with the **same installation directory**. It backs up the existing program and settings and preserves colors, layout and the previous startup choice. Keep the extracted package folder separate from the installation folder.

### If native components are missing

An already running ordinary Codex window cannot acquire new launch parameters. Finish tasks and normally exit, then let Sidekick reopen it or use the desktop shortcut. The shortcut can request a normal close/reopen only after you confirm the repair prompt.

Open `http://127.0.0.1:19766/` for the local monitor or `http://127.0.0.1:19766/analysis` for usage analysis. Check `logs/launch.log` and `logs/watcher.log` in your install folder if integration fails. A Codex update may change the interface or logging format.

### Restore official startup / uninstall

Disable automatic loading, stop monitoring, normally exit Codex, then reopen it with its official shortcut to restore default launch behavior.

The Windows uninstaller removes verified program files and Sidekick's startup entry while retaining configuration, colors, logs and backups:

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\scripts\uninstall-windows.ps1 -RemoveProgramFiles
```

## macOS: unverified compatibility

macOS scripts are supplied, but no Mac real-device installation or use has been verified. Windows startup and tray features are not implemented for macOS.

With Node.js 24+ installed:

```bash
bash scripts/install-macos.sh "/Volumes/Software/CodexSidekick"
```

Choose a writable installation folder. Use `bash /your/install/path/scripts/start-macos.sh` for the monitor. After normally exiting Codex, use `bash /your/install/path/scripts/launch-macos.sh` for native integration. Set `CODEX_APP` if the app is not in its standard location; `NODE_EXE` can specify the runtime.

## What was tested

The v0.4.8 analysis-panel toggle was verified in the Windows desktop app, including hiding, restoring the same tab, preserving the time range and keeping the current chat. Full Windows reboot and exit/reopen recovery still need real-device validation. Automated checks on macOS do not establish Mac GUI compatibility.
