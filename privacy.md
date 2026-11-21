---
title: Privacy Policy — Aether
---

# Privacy Policy

Version 0.1.8 · last updated 2026-11-19 · contact [fenderisfine@gmail.com](mailto:fenderisfine@gmail.com)

This policy explains how the Aether browser extension, its local runtime, and the CLI and MCP interfaces handle your information.

## Overview

Aether is local-first. It requires no account and operates no cloud service that collects user data. There is no analytics, telemetry, advertising or tracking in the extension or the runtime. Storage and execution primarily take place on this device. Tasks, enabled plugin hooks and the network features described below can contact external services.

## What stays on this device

- Conversations and their transcripts, attachments, annotations (the selected text, comment and number), agent presets, memories, skills, workflows, plans, evidence and workspace files live in a local data directory.
- Browser connection state, pairing tokens and model provider settings — including the API keys you enter — are stored locally. An API key is only ever sent to the model endpoint you configured it for.
- Generated files and code-execution artifacts are written to a per-session folder in that data directory.
- Token activity is computed locally from retained model usage records. No activity data is sent to an analytics service.
- Local diagnostic logs record status, timing, usage and filtered errors. Conversation and tool records may still contain page content, request parameters or other sensitive information.

## What is sent to model services

- When you start a task, the model provider you configured receives the request context: system instructions, tool definitions, the conversation and relevant memories, the bound workspace's name, description and instructions, the page reference carried by that message, and the files, page text, images, selections or comments the task reads. The composer adds the current page's title and URL as that default reference; you can remove it before sending. Context compaction also sends earlier records to the selected model.
- Thinking models may return reasoning content. It is stored with the conversation and, when a request carries tools, sent back to the same provider as its API requires.
- Page text and screenshots may contain personal or sensitive information. What is sent depends on the task you start and the model you selected.
- A provider may cache inputs or retain requests under its own terms. A cache hit does not mean data stays local. Service addresses, proxies, custom headers and provider data policies depend on your configuration.
- We do not operate a relay, proxy or collection service between you and your provider. Your provider processes that data under its own terms and privacy policy.
- You can switch models, remove a provider or stop a task at any time. Stopping a task requests cancellation of further work; it cannot recall data already sent to a third party.

## Search, updates and other network requests

- Search queries go to the search providers actually used, such as Bing, Baidu, 360, DuckDuckGo or arXiv. Page reads and browser actions contact target sites; Markdown images contact their source only after you click to load that image; site icons and expanded source previews can also cause external requests.
- The browser holds login sessions, and page requests may use existing cookies. Public HTTP fetches do not automatically use browser login sessions. Network capture and API tests can read request and response bodies; credential headers are filtered from displayed details, but bodies may still contain sensitive information.
- Model catalog requests, connection tests, software updates and installer downloads contact the corresponding provider, GitHub or configured update address. Those third parties receive normal request data such as IP addresses, queries and paths under their own policies.
- Workspace, skill and workflow retrieval runs inside the local runtime. Only content a task needs is sent with a model request.

## Browser permissions and why they are requested

- `sidePanel` — shows the assistant interface in Chrome's side panel.
- `storage` / `unlimitedStorage` — keeps settings, drafts and pairing state on this device; local data is not subject to a fixed storage quota.
- `activeTab` — grants temporary access to the tab where you invoke the extension; page content is read only as part of a task. The composer's current-page reference contains only the tab title and URL and can be removed before sending.
- `debugger` — performs clicks, form fills, scrolling and screenshots in the tab a task works on, reads page content, and captures or replays network requests for diagnostics and testing. A task or recording holds the connection while it needs it; idle task completion releases that ownership without closing the page. Cancelling Chrome's debugger prompt blocks further access until you explicitly reauthorize that page.
- `tabs`, `tabGroups`, `webNavigation` — read tab titles and addresses, keep the tabs a task owns together, and recover page associations after navigation or restart.
- `nativeMessaging` — starts and connects to the local runtime on this machine.
- `favicon` — shows a site icon next to a page reference in the conversation.
- `downloads` / `offscreen` — download files and installers, and run document parsing or image processing outside the visible page.
- `scripting` and page access — mirrors your text selection into the panel, captures the steps of a recording you started, extracts the article text of the page you asked about, and turns a search result page into structured results. It is idle otherwise and keeps no state between requests.

Aether declares host access for the pages it may read and act on. The content script runs on pages you visit, holds no state, sends nothing on its own, and acts only when you select text, while you record a workflow, or when the assistant reads a page you asked about. It never runs on Chrome's own pages (`chrome://`, the Web Store, other extensions).

## Local runtime, CLI and MCP

The runtime, the command-line interface and the MCP server talk to the extension over a local WebSocket bound to the loopback address, authenticated by a one-time pairing secret that is only obtainable from this machine. That traffic never passes through our servers. Authorized local clients can invoke tools within their task scope; connect only clients you trust.

## Code execution

When a task runs code, it runs locally inside an operating-system sandbox. By default the sandbox can write only inside that task's workspace, cannot read credential stores or application data such as API keys and pairing secrets, and gets network access only as the call requests. Full access can permit host file access beyond the workspace. Generated code, tool results and plugin feedback may be sent to your model provider when included in context; network-enabled code can also contact destinations chosen by that code.

## Plugin hooks

Importing or updating a skill package preserves its files without executing them. Loading an enabled skill can activate supported command hooks at task events. Full access permits these commands under the task's permissions. In approval mode, a command must first be approved; the same session reuses approval only for the same source revision, command, working directory and permission mode.

Hooks can receive the submitted prompt, tool arguments, tool results, errors and final response, depending on the event. Their feedback can be stored locally and sent to the selected model. In restricted mode they can read the package snapshot and use the task's working directory; the raw transcript path is withheld. Full access can expose that path and permit broader host access. The runtime does not pass provider credentials through the hook environment, but full access is not a guarantee that host files containing credentials are inaccessible. Hooks may make network requests under the execution permissions, so install and activate packages whose code and data handling you trust. Stopping a task cancels pending work but cannot undo completed writes or recall transmitted data. Disabling or deleting a skill prevents its later activation; unsupported plugin components are reported rather than silently executed.

## Sharing

We do not sell, rent or share your data, and we have no server that receives it. The third parties that see data are the model provider you choose and the search, website and update endpoints a task contacts, each only for requests you trigger.

## Retention and deletion

- Deleting a conversation removes its transcript, attachments, annotations, sandbox artifacts and evidence from the local data directory.
- Deleting a workspace removes its files and text sources, and cannot be undone.
- Uninstalling the extension removes browser-side extension data but does not automatically delete the local runtime data directory. Removing program files and deleting user data are separate operations; updates retain user data. To remove everything, clear extension data, runtime data and any copies you saved.

## Acceptable use

Aether is intended for lawful personal, commercial and production use, such as browsing, research and workflow automation. It must not be used for unlawful activity, infringement of the rights of others, bypassing access controls or security mechanisms, fraud, or distributing unlawful or harmful content. You must have lawful authority over the pages, data and accounts you process; responsibility for your use rests with you.

## Changes and contact

- This policy may change as the product evolves; material changes are surfaced in the application or in the release notes.
- This policy applies to version 0.1.8, last updated 2026-11-19.
- Questions about this policy, or requests about your data: [fenderisfine@gmail.com](mailto:fenderisfine@gmail.com). Do not include API keys, cookies, private conversation dumps or unredacted request bodies in reports.
- Community support: [discord.gg/2TQQaKKWPD](https://discord.gg/2TQQaKKWPD).

---

# 隐私政策

版本 0.1.8 · 最后更新于 2026-11-19 · 联系 [fenderisfine@gmail.com](mailto:fenderisfine@gmail.com)

本政策说明 Aether 浏览器扩展、本地运行时以及 CLI、MCP 接口如何处理你的信息。

## 概述

Aether 采用本地优先设计：不要求注册账号，也不运营收集用户数据的云端服务。扩展与运行时中没有任何分析、遥测、广告或跟踪。存储与执行以本机为主；任务、已激活的插件 Hook 和下述网络功能可能访问外部服务。

## 保存在本机的内容

- 对话与记录、附件、注释（所选原文、评论与编号）、Agent 预设、记忆、技能、工作流、计划、证据与工作空间文件，都保存在本机数据目录。
- 浏览器连接状态、配对令牌与模型提供方设置（含你填写的 API 密钥）保存在本机；密钥只会发往你为它配置的那个模型服务。
- 生成的文件与代码执行产物写入该数据目录中按会话划分的文件夹。
- 本地诊断日志记录状态、耗时、用量和经过过滤的错误；会话与工具记录仍可能包含页面内容、请求参数或其他敏感信息。

## 发送给模型服务的内容

- 你发起任务后，你配置的模型服务会接收本轮请求上下文：系统指令、工具定义、对话及相关记忆、所绑定工作空间的名称、描述和项目指令、该消息携带的页面引用，以及任务读取到的文件内容、页面文本、图片、选择文本或评论。输入框默认把当前页的标题和网址作为第一条页面引用，可在发送前删除。上下文压缩同样会把较早记录发送给所选模型。
- 思考模型可能返回思考内容；它会随会话保存在本机，并在请求携带工具时按接口要求回传给同一提供方。
- 页面文本与截图可能包含个人信息或敏感信息，具体发送什么取决于你发起的任务与你选择的模型。
- 模型提供方可能缓存输入或按其条款保留请求；缓存命中不代表数据只在本地处理。服务地址、代理、自定义请求头及提供方的数据政策由你的配置决定。
- 我们不在你与模型服务之间运营中转、代理或收集服务；你的提供方按其自身条款与隐私政策处理这些数据。
- 你可以随时切换模型、移除提供方或停止任务。停止任务会请求取消后续工作，但无法撤回已发送给第三方的数据。

## 搜索、更新与其他网络请求

- 搜索查询会发送给实际使用的搜索提供方，例如 Bing、百度、360、DuckDuckGo 或 arXiv。网页读取与浏览器操作会访问目标网站；Markdown 图片仅在你点击对应加载入口后访问其来源；网站图标及展开的来源预览也可能产生外部请求。
- 浏览器中的登录态由浏览器持有，页面请求可能使用现有 Cookie；公开 HTTP 抓取不自动携带浏览器登录态。网络捕获与接口测试可读取请求和响应正文，凭据头会在显示结果中过滤，但正文仍可能含有敏感信息。
- 模型目录、连接测试、软件更新及安装包下载会连接对应提供方、GitHub 或配置的更新地址；这些第三方会获得正常请求所需的 IP、查询、路径等信息，并依其自身政策处理。
- 工作空间文件、技能与工作流的检索在本地运行时内完成；只有任务需要的内容会随模型请求发送。

## 浏览器权限用途

- `sidePanel`：在 Chrome 侧边栏展示助手界面。
- `storage` / `unlimitedStorage`：在本机保存设置、草稿与配对状态；本地数据不受固定存储配额限制。
- `activeTab`：在你主动调用扩展时临时访问当前标签页；页面内容只在任务需要时读取。输入框默认的当前页引用只包含标签页标题和网址，可在发送前删除。
- `debugger`：在任务所在的标签页执行点击、填写、滚动与截图，读取页面内容，并为诊断与测试捕获或重放网络请求；任务或录制在需要时持有连接，任务空闲后释放自身占用且不关闭页面；取消 Chrome 调试后阻止后续访问，须明确重新授权该网页才恢复。
- `tabs`、`tabGroups`、`webNavigation`：读取标签页标题与地址，把任务所属的标签页归组，并在导航或重启后恢复页面关联。
- `nativeMessaging`：启动并连接本机运行时。
- `favicon`：在对话中的页面引用旁显示站点图标。
- `downloads` / `offscreen`：下载文件与安装包，在可见页面之外解析文档或处理图像。
- `scripting` 与页面访问权限：把你选中的文本同步到侧栏、记录你主动开始录制的操作步骤、提取你要求读取的页面正文、把搜索结果页解析成结构化结果；其余时间保持空闲，请求之间不保留状态。

Aether 声明的是它可能读取与操作的页面访问权限。内容脚本在你访问的页面中运行，不保存状态、不会自行发送任何数据，只在三种情况下动作：你选中文本时、你正在录制工作流时、或助手读取你要求的那一页时。它不会在 Chrome 自身页面（`chrome://`、应用商店、其他扩展页）上运行。

## 本地运行时、CLI 与 MCP

运行时、命令行工具与 MCP 服务通过绑定在回环地址上的本地 WebSocket 与扩展通信，并使用只能从本机获取的一次性配对密钥认证；这些流量不经过我们的服务器。已授权的本机客户端可以在其任务范围内调用工具，请只连接可信客户端。

## 代码执行

任务需要运行代码时，代码在本机操作系统沙箱内执行。默认情况下沙箱只能写入该任务的工作空间，无法读取凭据目录与应用数据（如 API 密钥、配对密钥），网络访问按调用请求决定。完全授权可能允许工作空间之外的宿主文件访问。生成代码、工具结果和插件反馈在进入上下文时可能发往模型提供方；获准联网的代码也可访问其指定的服务。

## 插件 Hook

导入或更新技能包只保存文件，不执行其中命令。任务加载已启用技能后，可在对应事件激活受支持的命令 Hook。完全授权沿用任务权限；需要审批时先确认命令，同一会话只对相同来源修订、命令、工作目录和权限模式复用批准。

Hook 按事件可能收到用户问题、工具参数、工具结果、错误和最终回复；反馈可能保存在本机并发往所选模型。受限模式可读取包快照并使用任务工作目录，不提供原始会话文件路径；完全授权可提供该路径并允许更广的宿主访问。运行时不会通过 Hook 环境变量传入提供方凭据，但完全授权不保证含凭据的宿主文件不可读。Hook 可以在执行权限内联网，请只导入并激活你信任其代码和数据处理方式的包。停止任务会取消后续工作，不能撤销已完成写入或召回已发送数据；停用或删除技能会阻止后续激活，不支持的插件组件会明确报告。

## 数据共享

我们不出售、不出租、不共享你的数据，也没有接收这些数据的服务器。会接触到数据的第三方只有你选择的模型提供方，以及任务实际访问的搜索、网站与更新服务端点，且仅限于你触发或任务需要的请求。

## 保留与删除

- 删除会话会一并移除其记录、附件、注释、沙箱产物与证据数据。撤回消息仅移除对应对话记录，不删除附件或已生成文件；已交付产物的本机下载地址不按时间过期，删除所属会话后失效。
- 删除工作空间会删除其中的项目文件与文本来源，且不可恢复。
- 卸载扩展会移除浏览器侧的扩展数据，但不会自动删除本地运行时数据目录。移除程序文件与删除用户数据是两件事；程序更新保留用户数据。需要彻底移除时，请分别清理扩展数据、运行时数据和自行保存的副本。

## 使用边界

本产品面向合法合规的个人、商业及生产场景，用于浏览、资料整理与工作流自动化；不得用于违反法律法规、侵害他人权益、绕过访问控制或安全机制、实施欺诈、传播违法有害内容等用途。你应确保对处理的页面、数据与账号拥有合法权限，并对使用行为负责。

## 政策更新与联系

- 本政策可能随功能更新调整，重大变更会在应用内或版本说明中公布。
- 适用版本 0.1.8，最后更新于 2026-11-19。
- 如对本政策有疑问或需要处理你的数据，请发送邮件至 [fenderisfine@gmail.com](mailto:fenderisfine@gmail.com)。请勿在问题报告中附带 API 密钥、Cookie、完整私密会话或未脱敏的请求正文。
- 社区支持与联系频道：[discord.gg/2TQQaKKWPD](https://discord.gg/2TQQaKKWPD)（应用内「设置 → 社区支持」直达）。
