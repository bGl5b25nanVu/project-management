# tmuxper

网页终端管理工具

## 基本信息

- **状态**: 活跃
- **技术栈**: FastAPI, WebSocket, xterm.js

## 项目描述

网页终端管理工具，通过浏览器访问和 管理远程服务器的终端会话。

## 访问地址

- **终端页面**: https://47.106.8.180/tmx/terminal.html

## 登录凭据

- 管理后台: `admin / RfI_ia1Hwqr9wZbqtblS6w`
- 平台登录: `yongjunl / RfI_ia1Hwqr9wZbqtblS6w`

## 架构

```
nginx(443) → auth_proxy:8080(Session验证) → tmuxper:8090 + portal_api:8788
```

## 相关文档

- 详见交接文档 `Documents/agent_handover.md`
