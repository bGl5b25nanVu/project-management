# 项目管理与追踪系统

集中管理所有项目的状态、任务和文档。

## 目录结构

```
project-management/
├── README.md              # 本文件
├── projects/              # 项目列表
│   ├── maclift.md         # iOS 自动化测试客户端
│   ├── voice-input-app.md # WhisperKit 语音输入
│   └── spec-kit.md        # Spec 驱动开发工作流
├── tasks/                 # 任务列表（按项目分类）
└── docs/                  # 文档和规范
```

## 项目状态总览

| 项目 | 状态 | 技术栈 | 位置 |
|------|------|--------|------|
| maclift | 活跃 | Swift/iOS/Xcode | GitHub: bGl5b25nanVu/MacLift |
| voice-input-app | 活跃 | Swift/WhisperKit | 待建 |
| spec-kit | 活跃 | Python/specify-cli | GitHub: bGl5b25nanVu/claude-skills |
| tempo | 规划中 | Flutter/RN | 待建 |
| choclift | 规划中 | macOS/Swift | 待建 |

## 目标

**年底 MRR = USD 100k**

## 工作流程

1. **添加项目**: 在 `projects/` 创建项目文档
2. **创建任务**: 在 `tasks/` 按项目分类创建任务文件
3. **更新状态**: 定期更新项目状态和进度
4. **同步到 Nextcloud**: 备份到 `Documents/project_management/`

## 自动化

- cron 每 20 分钟自动迭代当前任务
- 任务完成后自动推进下一个 sprint
- Telegram 推送通知

## 联系方式

GitHub Issues: https://github.com/bGl5b25nanVu/project-management/issues
