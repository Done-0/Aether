---
title: Privacy Policy — Aether
---

# Privacy Policy

Version 0.1.0 · last updated 2026-10-22 · contact [fenderisfine@gmail.com](mailto:fenderisfine@gmail.com)

This policy explains how the Aether browser extension and its local companion handle your information.

## Overview

Aether is local-first. It requires no account and operates no cloud service that collects user data. There is no analytics, telemetry, advertising or tracking in the extension or the companion. Everything below happens on the machine where you installed it, except the model requests you explicitly trigger.

## What stays on this device

- Conversations and their transcripts, attachments, agent presets, memories, skills, workflows, plans and workspace files live in a local data directory.
- Browser connection state, pairing tokens and model provider settings — including the API keys you enter — are stored locally. An API key is only ever sent to the model endpoint you configured it for.
- Generated files and code-execution artifacts are written to a per-session folder in that data directory.

## What is sent to model services

- When you start a task, the conversation context, the text of pages the agent reads, screenshots it captures and the results of tool actions are sent to the model provider you configured. Nothing leaves the machine before you send a message.
- Page text and screenshots may contain personal or sensitive information. What is sent depends on the task you start and the model you selected.
- We do not operate a relay, proxy or collection service between you and your provider. Your provider processes that data under its own terms and privacy policy.
- You can switch models, remove a provider or stop a task at any time.

## Browser permissions and why they are requested

- `sidePanel` — shows the assistant interface in Chrome's side panel.
- `storage` — keeps settings, drafts and pairing state on this device.
- `activeTab` — lets you hand the current page to the assistant when you ask for it.
- `debugger` — performs clicks, form fills, scrolling and screenshots in the tab a task works on, and reads the page content you asked about. It is attached only while a task runs.
- `tabs`, `tabGroups` — read tab titles and addresses so the assistant can pick the right page and keep the tabs a task owns together.
- `nativeMessaging` — starts and connects to the local companion on this machine.
- `favicon` — shows a site icon next to a page reference in the conversation.
- Content script on page matches — mirrors your text selection into the panel, captures the steps of a recording you started, extracts the article text of the page you asked about, and turns a search result page into structured results. It is idle otherwise and keeps no state between requests.

Aether declares no static host permissions, but it does ship one small content script that runs on pages you visit. It holds no state, sends nothing on its own, and acts only in three situations: when you select text (so the panel can show what you highlighted), while you are recording a workflow, or when the assistant reads the page you asked about. It never runs on Chrome's own pages (`chrome://`, the Web Store, other extensions).

## Local companion, CLI and MCP

The companion, the command-line interface and the MCP server talk to the extension over a local WebSocket bound to the loopback address, authenticated by a one-time pairing secret that is only obtainable from this machine. That traffic never passes through our servers.

## Code execution

When a task runs code, it runs locally inside an operating-system sandbox. By default the sandbox can write only inside that task's workspace, cannot read credential stores or application data such as API keys and pairing secrets, and gets network access only as the call requests. Generated code and its output stay on this machine unless the model provider receives them as part of a request.

## Sharing

We do not sell, rent or share your data, and we have no server that receives it. The only third party that sees anything is the model provider you choose, and only for requests you trigger.

## Retention and deletion

- Deleting a conversation removes its transcript, attachments, sandbox artifacts and evidence from the local data directory.
- Deleting a workspace removes its files and text sources, and cannot be undone.
- Uninstalling the extension, or deleting the application data directory, removes the local data. Back up anything you need first.

## Acceptable use

Aether is intended for lawful personal, commercial and production use, such as browsing, research and workflow automation. It must not be used for unlawful activity, infringement of the rights of others, bypassing access controls or security mechanisms, fraud, or distributing unlawful or harmful content. You must have lawful authority over the pages, data and accounts you process; responsibility for your use rests with you.

## Changes and contact

- This policy may change as the product evolves; material changes are surfaced in the application or in the release notes.
- This policy applies to version 0.1.0, last updated 2026-10-22.
- Questions about this policy, or requests about your data: [fenderisfine@gmail.com](mailto:fenderisfine@gmail.com).

---

# 隐私政策

版本 0.1.0 · 最后更新于 2026-10-22 · 联系 [fenderisfine@gmail.com](mailto:fenderisfine@gmail.com)

本政策说明 Aether 浏览器扩展及其本地伴随程序如何处理你的信息。

## 概述

Aether 采用本地优先设计：不要求注册账号，也不运营收集用户数据的云端服务。扩展与伴随程序中没有任何分析、遥测、广告或跟踪。除你主动发起的模型请求外，下文所述行为都发生在你安装它的这台机器上。

## 保存在本机的内容

- 对话与记录、附件、Agent 预设、记忆、技能、工作流、计划与工作空间文件，都保存在本机数据目录。
- 浏览器连接状态、配对令牌与模型提供方设置（含你填写的 API 密钥）保存在本机；密钥只会发往你为它配置的那个模型服务。
- 生成的文件与代码执行产物写入该数据目录中按会话划分的文件夹。

## 发送给模型服务的内容

- 你发起任务后，对话上下文、Agent 读取的页面文本、截取的屏幕截图与工具执行结果会发送给你自行配置的模型服务；在你发出消息之前，不会有任何数据离开本机。
- 页面文本与截图可能包含个人信息或敏感信息，具体发送什么取决于你发起的任务与你选择的模型。
- 我们不在你与模型服务之间运营中转、代理或收集服务；你的提供方按其自身条款与隐私政策处理这些数据。
- 你可以随时切换模型、移除提供方或停止任务。

## 浏览器权限用途

- `sidePanel`：在 Chrome 侧边栏展示助手界面。
- `storage`：在本机保存设置、草稿与配对状态。
- `activeTab`：在你要求时把当前页面交给助手处理。
- `debugger`：在任务所在的标签页执行点击、填写、滚动与截图，并读取你要求的页面内容；仅在任务执行期间附加。
- `tabs`、`tabGroups`：读取标签页标题与地址，用于选择页面并把任务所属的标签页归组。
- `nativeMessaging`：启动并连接本机伴随程序。
- `favicon`：在对话中的页面引用旁显示站点图标。
- 页面内容脚本：把你选中的文本同步到侧栏、记录你主动开始录制的操作步骤、提取你要求读取的页面正文、把搜索结果页解析成结构化结果；其余时间保持空闲，请求之间不保留状态。

Aether 不声明静态主机权限，但会在你访问的页面中运行一个很小的内容脚本。它不保存状态、不会自行发送任何数据，只在三种情况下动作：你选中文本时（让侧栏显示你高亮的内容）、你正在录制流程时、或助手读取你要求的那一页时。它不会在 Chrome 自身页面（`chrome://`、应用商店、其他扩展页）上运行。

## 本地伴随程序、CLI 与 MCP

伴随程序、命令行工具与 MCP 服务通过绑定在回环地址上的本地 WebSocket 与扩展通信，并使用只能从本机获取的一次性配对密钥认证；这些流量不经过我们的服务器。

## 代码执行

任务需要运行代码时，代码在本机操作系统沙箱内执行。默认情况下沙箱只能写入该任务的工作空间，无法读取凭据目录与应用数据（如 API 密钥、配对密钥），网络访问按调用请求决定。生成代码及其输出留在本机，除非作为请求内容的一部分发送给模型提供方。

## 数据共享

我们不出售、不出租、不共享你的数据，也没有接收这些数据的服务器。唯一会接触到数据的第三方是你选择的模型提供方，且仅限于你触发的请求。

## 保留与删除

- 删除会话会一并移除其记录、附件、沙箱产物与取证数据。
- 删除工作空间会删除其中的项目文件与文本来源，且不可恢复。
- 卸载扩展或删除应用数据目录会移除本机数据；删除前请自行备份。

## 使用边界

本产品面向合法合规的个人、商业及生产场景，用于浏览、资料整理与流程自动化；不得用于违反法律法规、侵害他人权益、绕过访问控制或安全机制、实施欺诈、传播违法有害内容等用途。你应确保对处理的页面、数据与账号拥有合法权限，并对使用行为负责。

## 政策更新与联系

- 本政策可能随功能更新调整，重大变更会在应用内或版本说明中公布。
- 适用版本 0.1.0，最后更新于 2026-10-22。
- 如对本政策有疑问或需要处理你的数据，请联系 [fenderisfine@gmail.com](mailto:fenderisfine@gmail.com)。
