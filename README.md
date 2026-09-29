# RunningHub 全能连接器 · RunningHub All-in-One Connector

> 开发者：**AI芳程式** ｜ 问题反馈或建议：**zzdh518**
> Developer: **AI芳程式 (AI Fangchengshi)** ｜ Feedback & suggestions: **zzdh518**

图像 · 视频 · 音频 · 3D · ComfyUI 工作流 · AI 应用 · LLM，一个连接器全覆盖

Image · Video · Audio · 3D · ComfyUI workflows · AI apps · LLM — one connector for everything

🧰 **品类 / Category：全能 · 图 + 视 + 音 + 3D + 工作流 + LLM** ｜ 形态 / Form：WorkBuddy 连接器包（MCP + Skill）**＋ 自带 `server/` 源码，可完全独立部署**

面向 **[WorkBuddy](https://www.workbuddy.cn) 连接器市场**的成品提交包（MCP + Skill 方案），同时适用于任意支持 MCP 的客户端。底层 MCP 服务器来自 [runninghub-mcp](https://github.com/fancy5166/runninghub-mcp)（使用全部能力，不限定范围）。

A ready-to-submit **[WorkBuddy](https://www.workbuddy.cn)** connector package (MCP + Skill). The underlying MCP server is [runninghub-mcp](https://github.com/fancy5166/runninghub-mcp) (all capabilities, no scope restriction).

> **30 秒判断要不要用**：做图开一个站、做视频再开一个、配音又换一个；余额分散、提示词风格不统一，来回切换把灵感切碎 —— 这个仓库就是为它准备的。
> **30-second check** (EN): One connector replaces a pile of accounts: 350+ models, switch from images to video to voice in one sentence.
> 下面是它的完整定位、能解决的问题，以及家族里另外 5 个仓库。Below: what this repo is, what it solves, and the other five repos in the family.


## 🧭 本仓库在家族里的位置 / Where this repo fits

| | |
| --- | --- |
| **本仓库 / This repo** | 🧰 **runninghub-connector** — 全能连接器 |
| **品类 / Category** | 全能 · 图 + 视 + 音 + 3D + 工作流 + LLM |
| **形态 / Form** | WorkBuddy 连接器壳（MCP + Skill，引擎经 npm 分发） |
| **独立可用 / Standalone** | ✅ 单独安装即可用，一条 `npx` 命令跑起来（核心引擎经 npm 分发，源码闭源） |
| **联动可用 / Interop** | ✅ 与家族其它 5 个仓库共用同一套 RunningHub 账号与 API Key，可任选组合安装 |
| **适合谁 / Who it's for** | 内容创作者 / 一人公司 / 小团队 / AI 工作流玩家 |
| **解决的痛点 / Pain it kills** | 做图开一个站、做视频再开一个、配音又换一个；余额分散、提示词风格不统一，来回切换把灵感切碎。 |
| **给你的价值 / What you get** | 350+ 模型一个入口，图 / 视频 / 音频 / 3D / 工作流 / AI 应用 / LLM 全通，同一套账号余额、同一套提示词语感。 |

### 🚀 两种用法 / Two ways to use it

**A. 只装这一个（独立部署，最小依赖）** — 你只想在这一个品类上用 AI：

- **WorkBuddy 用户**：在连接器市场搜「RunningHub」，装这一个就行（见下方「安装」）。
- **任意 MCP 客户端 / 开发者**：一条 `npx` 命令，核心引擎经 npm 分发（本仓库是连接器壳，不含引擎源码）：

```bash
# 方式一：npx 直接跑（推荐，需要 runninghub-mcp 已发布到 npm）
npx -y runninghub-mcp@latest

# 方式二：写进 MCP 客户端配置
# { "command": "npx", "args": ["-y", "runninghub-mcp@latest"] }
```

> `--scope` 让后端只加载本品类模型：启动更快、上下文更省、也更不容易挑错模型。

**B. 家族联动（图 + 视频 + 音频一次到位）** — 你想让 AI 一次干完整条链路：

同一个 API Key 下装多个连接器，或在 WorkBuddy 里直接装**全能连接器** [runninghub-connector](https://github.com/fancy5166/runninghub-connector)——一个顶四个；开发者还可以直接用核心引擎 [runninghub-mcp](https://github.com/fancy5166/runninghub-mcp) 自己拼。

### 🔗 家族全部仓库 / The whole family

| | 仓库 / Repo | 品类 / Category | 一句话 / In one line |
| --- | --- | --- | --- |
| 🏠 | **[runninghub-workbuddy-connectors](https://github.com/fancy5166/runninghub-workbuddy-connectors)** | 家族总入口 · 导航与安装指南 | 6 个包的介绍、安装指南与 4 个可直接上传 WorkBuddy 的连接器 zip，一次看全 |
| ⚙️ | **[runninghub-mcp](https://github.com/fancy5166/runninghub-mcp)** | 核心引擎 · MCP 服务器（npm 包，非连接器） | 给任何 MCP 客户端装上 RunningHub 的 350+ 模型双手 |
| 🎨 | **[runninghub-image-connector](https://github.com/fancy5166/runninghub-image-connector)** | 图像 · 90+ 图像模型 | 电商主图、模特换背景、老图 4K 放大，中文提示词直接可用 |
| 🎬 | **[runninghub-video-connector](https://github.com/fancy5166/runninghub-video-connector)** | 视频 · 200+ 视频模型 | 一条片子不用换五个平台，首尾帧与数字人口播全覆盖 |
| 🔊 | **[runninghub-audio-connector](https://github.com/fancy5166/runninghub-audio-connector)** | 音频 · 50+ 音频模型 | 配音、配乐、人声分离一站搞定，不用买音色包 |

> 💡 **不确定装哪个？** 先装全能连接器 [runninghub-connector](https://github.com/fancy5166/runninghub-connector) 一个就够；
> 只做图片就装 [runninghub-image-connector](https://github.com/fancy5166/runninghub-image-connector)，
> 只做视频装 [runninghub-video-connector](https://github.com/fancy5166/runninghub-video-connector)，
> 只做配音/音乐装 [runninghub-audio-connector](https://github.com/fancy5166/runninghub-audio-connector)，
> 要自己二次开发从 [runninghub-mcp](https://github.com/fancy5166/runninghub-mcp) 入手。

> 全部由 **AI芳程式** 开发，问题反馈或建议请联系 **zzdh518**。


## 🐣 保姆级小白指南 / Beginner's guides

- 中文：[GUIDE.md](GUIDE.md) — 完全没用过 AI 产品也能照着用起来
- English: [GUIDE_EN.md](GUIDE_EN.md) — step-by-step for absolute beginners

## 前置条件 / Prerequisites

1. **API Key** — 在 [RunningHub API 管理页面](https://www.runninghub.cn/enterprise-api/consumerApi) 点「**新建**」创建
2. **账户余额** — 用邀请码注册即送 **500 RH 币**（可免费生成不少图片和视频）；用完后到 [RunningHub 官网](https://www.runninghub.cn) 充值
3. 还没有账号？[**RunningHub 邀请注册链接**](https://www.runninghub.cn?inviteCode=zlhtnu0f) —— **填写邀请码 `zlhtnu0f`，可得 500 RH 币，可以免费生成不少图片和视频哦！**

## 安装 / Install

**WorkBuddy 连接器市场**：搜索「全能连接器」安装，连接时粘贴 API Key。

**手动配置 / Manual MCP config**：

```json
{
  "mcpServers": {
    "runninghub": {
      "type": "stdio",
      "command": "npx",
      "args": ["-y", "runninghub-mcp@latest"],
      "env": { "RUNNINGHUB_API_KEY": "你的 API Key / your API key" }
    }
  }
}
```

**一键安装 / One-click install**：把 [INSTALL_PROMPT.md](INSTALL_PROMPT.md) 里的提示词复制给你的 AI Agent，它会自动安装并引导配置。Copy the prompt from [INSTALL_PROMPT.md](INSTALL_PROMPT.md) into your agent.

## 能做什么 / What you can ask

- 「用 RunningHub 的 seedream 文生图，画一只宇航猫，2K 分辨率」
- 「帮我把这张图用可灵图生视频做成 5 秒短片」
- 「用 RunningHub 工作流跑一下这个 workflowId 的图生图任务」
- 「用 RunningHub 的 TTS 把这段文字转成语音」

- "Generate an astronaut cat with RunningHub seedream at 2K"
- "Turn this image into a 5s video with Kling image-to-video"
- "Run my RunningHub ComfyUI workflow with this workflowId"
- "Read this text aloud with RunningHub TTS"

## 工具 / Tools

12 个工具（含工作流 / AI 应用 / 取消任务 / LLM），详见 [skills/all-usage/SKILL.md](skills/) 与 [runninghub-mcp 工具表](https://github.com/fancy5166/runninghub-mcp#工具--tools)。

## 仓库结构 / Repo layout

```
├── connector-meta.json    # WorkBuddy 连接器元信息（中英名称/描述/示例）
├── mcp.json               # MCP 服务器连接配置（指向 npm 上的 runninghub-mcp）
├── token-schema.json      # 用户自填 Token 表单（API Key）
├── icon.svg               # 市场图标（芳字主视觉 + AI芳程式 署名）
├── GUIDE.md / GUIDE_EN.md # 保姆级小白指南（中/英）
├── skills/                # AI 使用说明（SKILL.md）
├── tools/pack.mjs         # 打包成可上传的 zip
└── .github/workflows/     # 打 tag 自动打包发布
```

> 🔒 本仓库是**连接器壳**：只包含安装、配置、指南与使用说明，不包含 MCP 服务器源码。
> 引擎（npm 包 `runninghub-mcp`）由作者另行分发，源码闭源。
>
> 🔒 This repo is a **connector shell**: install/config/guides only. The MCP server engine
> (npm package `runninghub-mcp`) is distributed separately by the author and is closed-source.

## 打包提交 / Package & submit

```bash
node tools/pack.mjs        # 生成 dist/runninghub-<version>.zip
```

把 zip 上传到 WorkBuddy 开发者后台审核即可。Upload the zip to the WorkBuddy developer backend.

## 许可证 / License

[MIT](LICENSE) © AI芳程式
