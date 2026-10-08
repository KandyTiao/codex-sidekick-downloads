# Codex Sidekick｜Codex 搭子
### 额度藏在菜单里？把用量、速度和模型建议放回聊天旁。

[English](README.md) · 简体中文

查看剩余额度会打断工作，聊天用量分散，选模型时又缺少直观依据。Codex 搭子把这些信息放到当前聊天旁，需要回顾时，再打开本机算力分析。

**[下载 v0.4.8 Windows 发布包](https://github.com/KandyTiao/codex-sidekick-downloads/releases/download/v0.4.8/CodexSidekick-v0.4.8.zip)** · [详细使用说明](docs/USER_GUIDE.zh-CN.md)

> **仅完成 Windows 实测；macOS 兼容性尚未确认。** 社区工具，与 OpenAI 无官方隶属关系。当前软件界面与入口文件名为中文。

## 装上以后，长什么样？

**聊天照常进行，用量就在旁边。**

| 侧栏里的额度环 | 聊天旁的监控栏 |
| --- | --- |
| <img src="docs/screenshots/quota-ring.png" alt="显示剩余额度和重置时间的 Token 环" width="44"> | <img src="docs/screenshots/chat-monitor.png" alt="显示 Token、模型、响应均速、任务状态和模型建议的浮动监控栏" width="524"> |
| 剩余多少、何时重置，一眼看到。点击可开关算力分析。 | 用了多少 Token、响应多快、正在做什么，还能看到模型建议。 |

**想回顾一段时间的投入？打开本机算力分析。**

![本机算力分析：日期范围、Token 总量、模型调用、活跃天数和使用趋势](docs/screenshots/usage-dashboard.png)

<details>
<summary><strong>再看看：20 种主题和分享九宫格</strong></summary>

额度环与监控栏统一换色，配色自动保存。

<img src="docs/screenshots/theme-picker.png" alt="20 种主题选色，包括活力绿和赛博幻彩" width="292">

把选定时间的使用记录变成 9 张卡片和拼图，也可保存本地 HTML 报告。

![分享导出窗口：九宫格预览、平台尺寸、个人名片开关和 HTML 导出](docs/screenshots/share-grid.png)

</details>

*以上为 v0.4.x Windows 验收中的真实界面截图；示例数值来自当时的本机记录。*

## 解决哪些问题

| 使用中的麻烦 | 搭子提供什么 |
| --- | --- |
| 查额度要反复打开菜单 | Token 环直接显示剩余比例和重置时间 |
| 聊天用了多少、正在做什么不好判断 | 聊天旁显示 Token、模型、响应均速与状态 |
| 不知道该选什么模型 | 根据本地规则给出建议和理由，由你决定 |
| 项目与聊天太多，容易混淆 | 20 种主题，项目和聊天可独立标色 |
| 使用历史不方便回顾和分享 | 本机账单、HTML 报告、分享卡片、九宫格与拼图 |

## v0.4.8：算力分析，点一下打开，再点一下收起

左键点击 Token 环，打开分析；再点隐藏；再点恢复原标签和已选时间范围。不会重复建标签，也不改变当前聊天。

## 三步开始使用

1. 安装并登录官方 Codex，准备 **Node.js 24+**。
2. 下载 ZIP 并解压，双击 **`安装到软件盘.cmd`**。默认安装到 `D:\Software\CodexSidekick`，也可自选目录。
3. 使用桌面 **Codex 搭子** 入口。官方 Codex 已正常运行时，先等任务结束，再正常退出或确认修复并重开。

新安装默认开启 Windows 登录自启动与托盘守护，可用 **`关闭自动加载.cmd`** 关闭；升级保留原来的选择。ZIP 包含必需的运行脚本，不包含 Node.js 或官方 Codex，也不是独立 EXE 安装器。

## 数据与验证范围

监测、模型建议和图片生成不额外调用模型，用量数据保存在本机，不上传作者服务器。完整 HTML 报告包含聊天明细，分享前请检查。

响应均速是最近完整调用的平均值；本机历史不一定完整，Token 不等于精确费用或全账号用量。Codex 更新可能影响原生组件接入。

v0.4.8 的面板切换已在 Windows 原生窗口实测；整机重启与退出后自动接管仍待实机验收。macOS 提供脚本，但尚未确认兼容性。

[设计说明](DESIGN.zh-CN.md) · [更新记录](CHANGELOG.md) · [第三方许可](THIRD-PARTY-NOTICES.md)

**允许免费下载使用；禁止修改程序和再次发布。** [使用许可](LICENSE)。开发源码保留在私有仓库，公开页面提供介绍和下载；使用包中必需的运行脚本受该许可约束。已授予的旧版 MIT 权利及第三方许可仍保留。分享图片署名：**Design by KandyTiao**。
