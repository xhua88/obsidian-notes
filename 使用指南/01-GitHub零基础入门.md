# 01 - GitHub 零基础入门

> 目标：完成一次性配置，让本地文件能备份到 GitHub 云端。

## 第 0 步：注册 GitHub 账号（如果还没有）

1. 打开浏览器访问 https://github.com
2. 点击右上角 **Sign up**，用邮箱注册（免费）
3. 记住用户名和密码

## 第 1 步：把 SSH 密钥添加到 GitHub（让电脑获得"通行证"）

我已经帮你生成了密钥，你只需要复制粘贴：

1. 复制下面这串公钥（它也在 `C:\Users\1\.ssh\id_ed25519.pub` 文件里）：

```
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIJT/0KCzaV2dxsd9XFekSk11l/XxUAZZzhhpEo6EKXfv github
```

2. 打开 GitHub 网页 → 右上角头像 → **Settings** → 左侧 **SSH and GPG keys** → 点 **New SSH key**
3. Title 随便填（如"我的电脑"），Key 框里粘贴上面那串 → 点 **Add SSH key**

## 第 2 步：配置 Git 的署名（10 秒钟）

按 `Win + R`，输入 `cmd` 回车，在黑窗口里依次输入（引号要保留，替换成你自己的）：

```
git config --global user.name "你的GitHub用户名"
git config --global user.email "你的注册邮箱"
```

> 💡 可以把用户名邮箱告诉我，我帮你执行这两条命令。

## 第 3 步：验证连通性

在黑窗口输入：

```
ssh -T git@github.com
```

- 看到 `Hi 你的用户名! You've successfully authenticated` 就成功了
- 第一次可能问 `Are you sure...`，输入 `yes` 回车

## 核心概念（30 秒理解 Git）

- **仓库（Repository）**：一个被 Git 管理的文件夹
- **提交（Commit）**：给当前状态拍一张"快照"，随时可以回到任何一张快照
- **推送（Push）**：把本地快照上传到 GitHub 云端
- **拉取（Pull）**：把云端的最新内容下载到本地

## 常用命令（收藏备用）

| 想做什么 | 在仓库文件夹里执行 |
|---|---|
| 把文件夹变成 Git 仓库 | `git init` |
| 存档（快照） | `git add .` 然后 `git commit -m "写点说明"` |
| 上传云端 | `git push` |
| 下载云端最新 | `git pull` |
| 查看改了什么 | `git status` |

> 💡 之后装了 Obsidian Git 插件后，这些命令都会**自动执行**，你几乎不用碰命令行。

## 下一步

→ [02-Obsidian零基础入门](02-Obsidian零基础入门.md)
