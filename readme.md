# Shiroi Deploy to Remote Server Workflow

这是一个利用 GitHub Action 去构建 Shiroi 然后部署到远程服务器的工作流。

## Why?

Shiroi 是 [Shiro](https://github.com/Innei/Shiro) 的闭源开发版本。

开源版本提供了预构建的 Docker 镜像或者编译产物可直接使用，但是闭源版本并没有提供。

因为 Next.js build 需要大量内存，很多服务器并吃不消这样的开销。

因此这里提供利用 GitHub Action 去完成构建然后推送到服务器。

你可以使用定时任务去定时更新 Shiroi。

## How to

开始之前，你的服务器首先需要安装 Node.js, npm, pnpm, pm2, sharp。

关于 sharp 的安装，你可以使用

```sh
npm i -g sharp
```

sharp 不是必须的，但是在运行过程中会出现报错。参考：https://nextjs.org/docs/messages/sharp-missing-in-production

Fork 此项目，然后你需要填写下面的信息。

## Secrets

- `HOST` 服务器地址
- `PASSWORD` 服务器密码
- `PORT` 服务器 SSH 端口
- `KEY` 服务器 SSH Key（可选，密码 key 二选一）
- `GH_PAT` 可访问 Shiroi 仓库的 Github Token

### Github Token

1. 你的账号可以访问 Shiroi 仓库。
2. 进入 [tokens](https://github.com/settings/tokens) - Personal access tokens - Tokens (classic) - Generate new token - Generate new token (classic) 

![](https://github.com/innei-dev/shiroi-deploy-action/assets/41265413/e55d32cb-bd30-46b7-a603-7d00b3f8a413)