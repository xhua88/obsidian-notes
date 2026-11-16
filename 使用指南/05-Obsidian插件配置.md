# 05-Obsidian 插件配置

> 前置条件：已完成 [01-GitHub零基础入门](01-GitHub零基础入门.md)。
> 本文对应的两款插件已经由 AI 助手预先下载安装好，你只需要"打开开关"和"填一次配置"。

## 插件一：Obsidian Git（自动备份）

作用：定时自动把你的笔记提交并推送到 GitHub，彻底告别手动备份。

### 第 1 步：开启社区插件权限

1. 打开 Obsidian（选择 `C:\Users\1\Obsidian笔记库` 作为仓库）
2. 左下角 **齿轮图标**（设置）→ 左侧最下方 **第三方插件（Community plugins）**
3. 如果显示"受限模式"（Restricted mode），点 **Turn on community plugins / 开启第三方插件**
4. 开启后，已安装的插件会出现在列表里（因为文件已经就位）

### 第 2 步：启用 Git 插件

1. 在 **已安装插件（Installed plugins）** 列表里找到 **Git** → 打开开关
2. 回到设置左侧，找到 **Git** 选项（在插件设置组里）
3. 建议改这几项：
   - **Vault backup interval (minutes)**：填 `10`（每 10 分钟自动备份一次）
   - **Auto pull interval**：保持默认或填 `10`
   - **Commit message**：可以留默认

### 第 3 步：手动验证一次

按 `Ctrl + P` 打开命令面板，输入 `git`，选择：

> Git: Commit-and-sync（提交并同步）

看到右上角弹出 "Sync done" 之类的提示就成功了。以后你也可以随时按它手动备份。

> ⚠️ 注意：桌面上那个「备份笔记到GitHub.bat」和这个插件二选一就行，都能用，不会冲突。

## 插件二：Copilot（接本地 Hermes AI）

作用：在笔记里选中一段文字，让 AI 总结 / 改写 / 翻译——用的是你本机的 Hermes，内容不出电脑。

### 第 1 步：先启动 Hermes

双击 `C:\Users\1\WorkBuddy\2026-11-13-14-01-44\hermes-local\启动Hermes服务.bat`，等黑窗口显示模型加载完成（约 30 秒）。

### 第 2 步：启用 Copilot 插件

1. 设置 → 第三方插件 → 找到 **Copilot** → 打开开关
2. 首次启用可能弹出欢迎页，直接关掉

### 第 3 步：配置本地模型（核心步骤）

1. 设置 → 左侧找到 **Copilot** → 点 **模型（Model）** 标签页
2. 点 **添加自定义模型（Add Custom Model）**，按下面填：
   - **Model name**：`hermes3`
   - **Provider**：选 `3rd party (openai-format)` 或 `OpenAI Format`（没有就选 OpenAI Compatible）
   - **Base URL**：`http://127.0.0.1:8899/v1`
   - **API Key**：随便填，比如 `local`（本地服务不校验，但不能留空）
3. 保存后回到聊天面板，**模型列表里选 hermes3**

### 第 4 步：验收

1. 打开任意一篇笔记（比如《00-三件套总览》）
2. 点右侧边栏的对话图标，打开 Copilot 聊天面板
3. 输入：`总结一下这篇笔记的要点`
4. Hermes 回复了就全通了 ✅

## 常见问题

| 现象 | 原因 / 解决 |
|---|---|
| 插件列表是空的 | 没开社区插件权限，回到第 1 步 |
| Copilot 一直转圈无响应 | Hermes 服务没启动，双击 bat 后再试 |
| Copilot 报 404 | Base URL 少了 `/v1`，补上 |
| Git 插件报 permission denied | 网络问题，稍后重试；或用桌面 bat 备份 |

## 下一步

→ [04-三件套协同实操](04-三件套协同实操.md) 把三条工作流真正跑起来
