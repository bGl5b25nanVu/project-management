# workspace-hub-alicloud

阿里云统一工作平台

## 基本信息

- **状态**: 活跃
- **服务器**: 47.106.8.180 (Ubuntu, 1.7GB RAM, 运行 570+ 天)
- **访问地址**: https://47.106.8.180/
- **技术栈**: Python, nginx, tmux

## 项目描述

在阿里云服务器上构建的统一工作平台，整合 tmuxper 终端会话管理、Homarr 服务仪表盘、Wetty Web SSH 等工具。

## 服务架构

| 路由 | 服务 | 端口 | 说明 |
|------|------|------|------|
| `/` | 平台主页 | - | portal.html 统一入口 |
| `/board/` | Homarr | 7575 | 服务仪表盘 |
| `/tmuxper/` | tmuxper | 8090 | tmux 会话管理 |
| `/wetty` | Wetty | 3000 | Web SSH (HTTP Basic Auth) |
| `/api/sysinfo` | sysinfo API | 8788 | 系统监控数据 |

## 关键文件

| 文件 | 路径 | 用途 |
|------|------|------|
| 平台页面 | `/var/www/workspace-portal.html` | 统一入口 UI |
| sysinfo API | `/home/yongjunl/workspace/sysinfo_server.py` | 系统监控数据 |
| nginx 配置 | `/etc/nginx/conf.d/ip-https.conf` | 路由整合 |
| tmuxper 配置 | `/home/yongjunl/tmuxper/` | 终端会话管理 |

## 已有 tmux 会话

- default, shared-hermes-work, shared-Hermes-home-m1, shared-Hermes-home-intel, test-server, sysinfo

## 维护命令

```bash
# 重启 sysinfo 服务
tmux kill-session -t sysinfo
tmux new-session -d -s sysinfo 'python3 /home/yongjunl/workspace/sysinfo_server.py'

# 重载 nginx
sudo nginx -t && sudo nginx -s reload
```

## 更新记录

- 2026-04-20: 创建统一工作平台页面，整合 nginx 路由，部署 sysinfo API
