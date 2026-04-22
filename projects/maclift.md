# MacLift

iOS 自动化测试客户端 — 记录 App UI 测试序列并回放

## 基本信息

- **状态**: 活跃
- **GitHub**: https://github.com/bGl5b25nanVu/MacLift
- **团队 ID**: 公司账号 2BY837L59H (Shenzhen Qisi Network Technology Co., Ltd.)
- **个人账号**: 63B7KK76RG
- **技术栈**: Swift, iOS, Xcode
- **主力机器**: M1 Mac mini (100.100.2.22, SSH: ai/fghj)
- **Xcode**: 26.1.1 / iOS 18.2/18.5/26.1 simulators
- **Swift**: 6.2.1

## 项目描述

iOS App 端到端测试自动化工具，记录用户在 App 上的操作序列并支持回放。App Store 名称为 ChocLift（糖果电梯）。

## 最新进展 (2026-04-22)

- 成功构建到 iOS Simulator
- headless 模式服务器崩溃问题已解决（随机端口配置修复）
- 68个测试全通过
- 正在提交审核：构建 ID `12D16DC1-Apple`（公司 Team 2BY837L59H）

## 技术配置

- **Bundle ID**: com.choclift.app
- **随机端口**: `/tmp/maclift-pin.txt`, `/tmp/maclift-port.txt`
- **测试 UDID**: `D2D1BA0A-C6F6-4208-9C03-96E697744BA4`

## 构建流程

1. M1 Mac (100.100.2.22) 上构建 Xcode 项目
2. Intel Mac (192.168.1.250) 推送 App Store
3. 代码同步：`tar-over-SSH` 方式从 M1 传到 Intel

## 已知问题

- 无重大问题
