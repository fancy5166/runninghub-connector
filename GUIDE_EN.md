# RunningHub All-in-One Connector · Beginner's Step-by-Step Guide

> Developer: **AI芳程式 (AI Fangchengshi)** ｜ Feedback & suggestions: **zzdh518**
> Audience: users who have never used any AI product. Follow this guide step by step and you will use the connector like a pro.

---

## 0. What is this? What can it do for me?

**In one sentence**: Image generation, video generation, text-to-speech, music generation, 3D models, ComfyUI workflows, AI apps and LLM chat — all in one connector.

You just **describe your need in plain language**. The AI will automatically: pick the right model → submit the task → wait for generation → hand you the result (image/video/audio link). No technical skills required.

**You only need 3 things to start (prerequisites — all required):**

| Prerequisite | How to get it | Notes |
| --- | --- | --- |
| ① **API Key** | Open the [RunningHub API management page](https://www.runninghub.cn/enterprise-api/consumerApi) and click "**新建**" (Create) | It's the connector's key; pick the "Enterprise-Shared" type for generation model APIs |
| ② **Account balance** | Registering with the invite code gives you **500 RH coins free** (enough for quite a few images/videos); top up at [runninghub.cn](https://www.runninghub.cn) afterwards | **API calls require balance** — pay-as-you-go (an image ≈ a few cents, a video ≈ cents to a few yuan) |
| ③ A computer with internet | Windows / macOS | — |

> 🎁 **No account yet?** Register here: [**RunningHub invite registration link**](https://www.runninghub.cn?inviteCode=zlhtnu0f) — **enter invite code `zlhtnu0f` to get 500 RH coins, enough for quite a few free images and videos!**

> ⚡ **Prefer one-click?** Skip to "**9. One-click install prompt**" at the end — copy that prompt to your AI agent and it will install everything and guide you through the API key setup.

---

## 1. Step 1: Create a RunningHub account

1. Open the [**RunningHub invite registration link**](https://www.runninghub.cn?inviteCode=zlhtnu0f) (invite code `zlhtnu0f`)
   > 🎁 **Enter invite code zlhtnu0f to get 500 RH coins — enough for quite a few free images and videos!**
2. Click "登录 / 注册" (Sign in / Sign up) in the top-right corner
3. Register with your phone number + SMS code

That's it — you now have a personal account.

## 2. Step 2: Get an API Key and top up

**2.1 Create the API Key**

1. After signing in, open the [**RunningHub API management page**](https://www.runninghub.cn/enterprise-api/consumerApi)
2. Click "**新建**" (Create)
3. **Choose the key type** (important!):

| Key type | What it can call | Best for |
| --- | --- | --- |
| Enterprise-Shared ✅ recommended | Everything (model APIs, workflows, AI apps, LLM) | Users who want all features |
| Consumer-Member | Workflows and AI apps only | Workflow-only users |

> ⚠️ Note: the standard model APIs (direct text-to-image / text-to-video / TTS etc.) and LLM chat **only work with an Enterprise-Shared key**. If you see error 1014 (Access Denied), your key type is wrong.
4. **Copy and store the key immediately**. Never share it with anyone or post it online.

**2.2 Make sure you have balance (required, but new users get free credits)**

- 🎁 **New user bonus**: registering with invite code `zlhtnu0f` gives you **500 RH coins** — enough for quite a few images and videos for free; top up after the credits run out.
- **API calls require balance**; insufficient funds returns errors 416 / 812.
- Top up: sign in at [runninghub.cn](https://www.runninghub.cn) → wallet / recharge page.
- Usage details: [Tasks & billing](https://www.runninghub.cn/call-api/bill-task).

## 3. Step 3: Install the connector (pick one)

### Option A: WorkBuddy connector marketplace (easiest)

1. Open WorkBuddy, click "连接器" (Connectors) in the left sidebar
2. Search for "RunningHub"
3. Click Install → Connect
4. Paste the **API Key** from step 2 into the configuration form
5. When it shows "connected", you're done ✅

### Option B: Manual MCP configuration (other MCP clients)

Add this to your client's MCP config file:

```json
{
  "mcpServers": {
    "runninghub": {
      "command": "npx",
      "args": ["-y", "runninghub-mcp@latest"],
      "env": { "RUNNINGHUB_API_KEY": "paste-your-key-here" }
    }
  }
}
```

Restart the client afterwards.

## 4. Step 4: Your first generation (3 minutes)

After installation, just **state your need in plain language**. Copy-paste any example below:

### Example 1: Generate an image

**Say to the AI:**

> "Use RunningHub to generate an image: an astronaut orange cat floating on the moon with Earth in the background, 2K resolution"

**What happens:** The AI automatically picks the seedream text-to-image model → submits the task → waits → hands you the image link.

### Example 2: Animate a photo

**Say to the AI:**

> "Use RunningHub to turn D:/photos/portrait.jpg into a 5-second video with a natural smile and gently moving hair"

**What happens:** The AI uploads your local photo → picks an image-to-video model → returns the video link.

### Example 3: Text to speech

**Say to the AI:**

> "Use RunningHub TTS to read this out loud: Welcome to RunningHub, create anything with one sentence"

**What happens:** The AI calls a TTS model and returns an audio file you can download.

### Example 4: Generate a song

**Say to the AI:**

> "Use RunningHub's Suno to generate an upbeat summer pop song"

**What happens:** The AI submits a music generation task and returns the song link in a few minutes.

### Example 5: Run a ComfyUI workflow

**Say to the AI:**

> "Use RunningHub to run my workflow 1904136902449209346 and change the prompt to '1 girl in classroom'"

**What happens:** The AI overrides workflow node parameters → submits → waits → returns the result.

### Example 6: Chat with an LLM

**Say to the AI:**

> "Use RunningHub's LLM to write marketing copy for my product"

**What happens:** The AI calls the RunningHub LLM API and replies with text directly.

**Where is my result?** The AI replies with one or more file links (png / mp4 / mp3):
- Click a link to preview it online;
- To save it locally, just say: "download the result to D:/output" — the AI will download it for you.

> 💡 Result links **expire after a while** — download anything important soon.

## 5. Everyday phrasebook (copy and use)

| You want | Just say |
| --- | --- |
| A specific model | "Use RunningHub's **Kling** text-to-video…" / "Draw it with **seedream**…" |
| Unsure which model | "I want to make X — what RunningHub model fits?" (the AI searches the catalog first) |
| Use a local file | "Upload D:/assets/pic.jpg and turn it into a video" (the AI uploads automatically) |
| Check progress | "Is my task done yet?" (the AI queries the task status) |
| Batch jobs | "Turn each of these 5 images into a 5-second video" (the AI submits one by one) |

## 6. Wallet & concurrency tips (avoid wasting money)

- **Confirm before big spends**: say "tell me which model you'll use and the rough cost before submitting".
- **Don't over-retry**: generation is random by nature; retry the same task at most 2–3 times.
- **Concurrency limits**: accounts can run a limited number of tasks at once. Errors 421/1520 mean you're at the limit — wait for earlier tasks to finish.
- **Free credits**: new users may receive trial credits; top up on the RunningHub wallet page afterwards.

## 7. Troubleshooting (error cheat sheet)

| Message | Meaning | What to do |
| --- | --- | --- |
| 1002 / 802 | Invalid API Key | Check the key was copied fully and isn't disabled; reconnect |
| 1014 | Key type doesn't support model APIs | Switch to an Enterprise-Shared key |
| 1003 | Rate limited | Wait a few seconds and retry |
| 1011 / 1504 | Model busy / timed out | Retry later |
| 1501 | Content moderation rejected | Rephrase your prompt (avoid policy-violating content) |
| 1007 / 301 | Invalid parameters | Describe your need more specifically or reword it |
| 416 / 812 | Insufficient balance | Top up on RunningHub |
| 421 / 1520 | Concurrency limit reached | Wait for running tasks to finish |
| 810 | Workflow not saved / never run | Open the workflow on runninghub.cn, save and run it once |
| 805 | Task failed | Check the failure reason the AI returns and adjust |
| Wait timeout | Task still running | Ask "is my task done?" later and the AI will check again |

## 8. FAQ

**Q1: Do I need to code?**
Not at all. Everything works through natural conversation.

**Q2: Who owns the generated content?**
Ownership and commercial-use terms follow the RunningHub platform agreement and the respective model providers' terms. Verify before commercial use.

**Q3: How long does a task take?**
Images: usually 10–60 s. Audio: 10–120 s. Video: 1–10 min depending on model and duration. The AI waits automatically and tells you when it's done.

**Q4: Is my API key safe?**
The key is stored only on your own machine (WorkBuddy local storage) and never passes through any third-party cloud.

**Q5: The effect I want isn't in the catalog?**
Ask the AI: "Does RunningHub have a model that can do X?" It will search and suggest. If nothing fits, send the developer a feature request.

## 9. One-click install prompt (recommended: paste it into your AI agent)

For conversational agents such as **WorkBuddy, OpenClaw, Codex, Claude Desktop and Cursor**: copy the whole block below to your agent — it will **install everything automatically** (runtime check + MCP config) and **walk you through the API key setup**.

```text
Please install and configure the **RunningHub connector** for me (developer: AI芳程式 / AI Fangchengshi, feedback: zzdh518) so I can generate images/videos/audio in plain language afterwards.

Steps:
1. Check whether Node.js 20+ is available locally; install it if not.
2. Install the RunningHub MCP connector and write it into my MCP client config (WorkBuddy / OpenClaw / Codex / Claude Desktop / Cursor, etc.):
   Command: npx -y runninghub-mcp@latest
   If my client uses a json config, add:
   {
     "mcpServers": {
       "runninghub": {
         "command": "npx",
         "args": ["-y", "runninghub-mcp@latest"],
         "env": { "RUNNINGHUB_API_KEY": "<my API key, to be filled in later>" }
       }
     }
   }
3. Walk me through the API key setup (if I already have one, just ask me to paste it):
   - Register (invite link): https://www.runninghub.cn?inviteCode=zlhtnu0f (invite code zlhtnu0f)
     💰 Enter the invite code to get 500 RH coins — enough for quite a few free images and videos!
   - Click "新建" (Create) on the API management page: https://www.runninghub.cn/enterprise-api/consumerApi
     (choose the "Enterprise-Shared" key type to unlock all capabilities, including standard model APIs and LLM)
   - Top up my RunningHub balance — **API calls require balance**: https://www.runninghub.cn
   - Put the key into the config above and restart the client
4. After installation, verify the connection for me (e.g. list a few available models) and tell me where to find results.
5. From then on, when I describe a need, automatically: search for a suitable model → submit the task → wait for completion → give me the result links (and download them locally when asked).
```

> Tip: you can also just hand the repo link or this guide to your agent and let it follow along.

---

## Support

- Developer: **AI芳程式 (AI Fangchengshi)**
- Feedback & suggestions: contact **zzdh518**
- Official RunningHub API docs: https://www.runninghub.cn/runninghub-api-doc
- [RunningHub invite registration link](https://www.runninghub.cn?inviteCode=zlhtnu0f) (invite code zlhtnu0f) — 500 RH coins free credits
