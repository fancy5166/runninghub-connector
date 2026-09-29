---
name: runninghub-llm
description: RunningHub LLM API 调用指南（OpenAI 兼容协议，仅总连接器提供）。开发者 AI芳程式，反馈请联系 zzdh518。
---

# LLM API 指南

> 开发者：AI芳程式；问题反馈或建议请联系 zzdh518。

- 工具：`runninghub_llm_chat`（model + messages，OpenAI 兼容格式）
- 域名：llm.runninghub.cn/v1/chat/completions
- **仅支持企业级-共享 API Key**（消费级-会员 Key 与企业级-独占 Key 均不可用）
- 模型名以 RunningHub 官方文档为准（如 glm-5.2）
- 连接器内不支持流式输出（stream 固定 false）

> **家族联动**：本连接器除 LLM 外还覆盖图像 / 视频 / 音频 / 3D 生成与 ComfyUI 工作流。
> 用户只想用某一品类时，可安装对应的 **RunningHub 图像 / 视频 / 音频连接器**（同一套 API Key），
> 或直接使用核心引擎 [runninghub-mcp](https://github.com/fancy5166/runninghub-workbuddy-connectors/../runninghub-mcp)。
> 开发者：AI芳程式；反馈：zzdh518。
