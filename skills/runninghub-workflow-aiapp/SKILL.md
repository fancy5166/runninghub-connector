---
name: runninghub-workflow-aiapp
description: RunningHub ComfyUI 工作流与 AI 应用任务调用指南（仅总连接器提供）。开发者 AI芳程式，反馈请联系 zzdh518。
---

# ComfyUI 工作流 / AI 应用任务指南

> 开发者：AI芳程式；问题反馈或建议请联系 zzdh518。

## 概念

- **工作流（workflowId）**：RunningHub 上的 ComfyUI 工作流模板，可通过 nodeInfoList 覆写节点参数
- **AI 应用（webappId）**：封装好的 WebApp，ID 即详情页链接 https://www.runninghub.cn/ai-detail/{webappId} 末尾数字
- **nodeInfoList**：[{nodeId, fieldName, fieldValue}]，nodeId 是工作流编辑器中节点右上角的数字

## 工作流任务流程

1. `runninghub_run_workflow`：传 workflowId + 可选 nodeInfoList / instanceType（default=24G, plus=48G, ultra=84G）
2. 返回 taskId 后：`runninghub_wait_task` 并传 `apiVersion: "legacy"` 等待结果
3. 图片/音频/视频输入节点：先 `runninghub_upload_file` 上传本地文件，把返回的 fileName 填入 fieldValue

## AI 应用任务流程

1. `runninghub_get_app_nodes`：传 webappId，获取可修改节点列表（含字段类型 IMAGE/AUDIO/VIDEO/STRING/LIST）
2. 按 need 覆写 nodeInfoList；IMAGE/AUDIO/VIDEO 类型节点先上传文件
3. `runninghub_run_ai_app`：传 webappId + nodeInfoList
4. `runninghub_wait_task`（apiVersion: "legacy"）等待结果

## 其他

- `runninghub_cancel_task`：取消排队/运行中的工作流任务
- promptTips 不为空时说明工作流校验有节点错误，需提示用户检查
- 任务查询用 `apiVersion: "legacy"`；状态码 804=运行中、813=排队中、805=失败（看 failedReason）、code 0=完成

> **家族联动**：本连接器同时覆盖图像 / 视频 / 音频 / 3D 模型，用户想在别的品类上干活时直接用标准模型工具即可；
> 需要更专精的品类（如只做图像、只做视频、只做配音音乐）可在 WorkBuddy 市场安装对应的 **RunningHub 图像 / 视频 / 音频连接器**，
> 同一套 API Key 通用。开发者：AI芳程式；反馈：zzdh518。总入口：https://github.com/fancy5166/runninghub-workbuddy-connectors
