# 项目管理与追踪系统

集中管理所有项目的状态、任务和文档。

## 目录结构

```
project-management/
├── README.md              # 本文件
├── projects/              # 项目列表
│   ├── maclift/          # iOS 端到端测试项目
│   └── voice-input-app/  # WhisperKit 语音输入
├── tasks/                # 任务列表（按项目分类）
└── docs/                 # 文档和规范
```

## 项目状态总览

| 项目 | 状态 | 技术栈 | 位置 |
|------|------|--------|------|
| maclift | 活跃 | iOS/Swift | GitHub: bGl5b25nanVu/MacLift |
| voice-input-app | 活跃 | Swift/WhisperKit | GitHub (待确认) |
| spec-kit | 新建 | Python | 已配置 MCP |

## 工作流程

1. **添加项目**: 在 `projects/` 创建项目文件夹
2. **创建任务**: 在 `tasks/` 创建任务文件
3. **更新状态**: 定期更新项目 README 中的状态
4. **同步到 Nextcloud**: 备份到 `Documents/project_management/`

## 自动化

- 每日 8:30 推送任务摘要
- 每日 20:30 生成工作日报
- Telegram 推送通知

## 联系方式

如有问题，请在 GitHub Issues 中提出。
