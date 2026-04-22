# openstick-zeroclaw

OpenStick 软路由上的 ZeroClaw Telegram Bot + 自托管 STT

## 基本信息

- **状态**: 活跃
- **设备**: OpenStick (`user@192.168.100.1`)
- **技术栈**: Go, mihomo, zeroclaw, SenseVoice STT

## 项目描述

运行在 OpenStick 软路由上的 Telegram 语音消息处理机器人，支持自托管 SenseVoice STT 语音转写。

## 服务架构

### mihomo 代理
- **混合端口**: 7890 (HTTP)
- **SOCKS5 端口**: 7891
- **API**: http://127.0.0.1:9090/proxies

### zeroclaw Telegram Bot
- **守护进程**: openstick supervisor (非 systemd)
- **进程冲突**: 多次重启会积累僵尸进程，需 `killall zeroclaw` 清理
- **端口**: 42617

## STT 配置

```toml
[transcription]
enabled = true
default_provider = "local_whisper"
model = "SenseVoice"

[transcription.local_whisper]
url = "http://100.100.2.14:7700/v1/audio/transcriptions"
bearer_token = "placeholder"
max_audio_bytes = 25000000
timeout_secs = 120
```

- **STT 服务器**: Mac Studio (100.100.2.14:7700)
- **引擎**: SenseVoice
- **支持格式**: .wav, .mp3, .pcm, .oga, .m4a

## 关键发现

- `local_whisper` 不在 `default_provider` 选项列表中，需同时设置 `default_provider = "local_whisper"` 和 `[transcription.local_whisper]` 子节点
- zeroclaw 拒绝空字符串 bearer_token，需设置为 `"placeholder"`
- zeroclaw 每次启动生成两个进程，都试图绑定 42617 端口，需先清理再重启

## 测试命令

```bash
# 测试 Telegram Bot API
curl -x http://127.0.0.1:7890 https://api.telegram.org/bot{token}/getMe

# 测试 STT 服务器
curl -x http://127.0.0.1:7890 -X POST http://100.100.2.14:7700/v1/audio/transcriptions \
  -H "Authorization: Bearer placeholder" \
  -F "file=@test.wav" \
  -F "model=SenseVoice"
```

## 更新记录

- 2026-04-18: 完成 SenseVoice STT 配置，解决 zeroclaw 进程冲突问题
