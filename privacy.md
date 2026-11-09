---
title: Privacy Policy — Aether
---

# Privacy policy

## Scope

This policy describes data handling by the Aether browser extension, local runtime, CLI and MCP integration. Core features require no Aether account. Conversations and files are primarily stored locally; using models, search, websites and updates sends relevant data to those services.

## Local data and retention

- The browser stores settings, pairing state and drafts. Unfinished attachments are temporarily stored in IndexedDB; their temporary file copies are released after upload. The runtime stores conversations, page associations, attachments, workspaces, presets, memories, skills, workflows, plans and evidence.
- API keys and custom request headers are stored in runtime configuration files and sent to the corresponding provider when used. Local file permissions protect these files; system keychain storage and application-level encryption are not promised.
- Local diagnostic logs record status, timing, usage and filtered errors. Conversation and tool records can still contain page content, request parameters or sensitive information. Logs and execution records follow their own retention rules.

## Models and context

- Your configured model service receives the instructions, tool definitions, conversation, relevant memories and project instructions needed for the request, plus file content, page text or images read by the task. Context compaction also sends earlier records to the selected model.
- A provider may cache inputs or retain requests under its own terms. A cache hit does not mean data stays local. Service addresses, proxies, custom headers and provider data policies depend on your configuration.
- Aether operates no conversation relay or user-data collection service for training. Stopping a task requests cancellation of further work; it cannot recall data already sent to a third party.

## Websites, search and downloads

- Search queries go to the search providers actually used, such as Bing, Baidu, 360 or DuckDuckGo. Page reads and browser actions contact target sites; remote images and site icons can also cause external requests.
- The browser holds login sessions, and page requests may use existing cookies. Network capture and API tests can read request and response bodies. Credential headers are filtered from displayed details, but bodies may still contain sensitive information. Public HTTP fetches do not automatically use browser login sessions.
- Model catalogs, connection tests, updates, installer downloads and optional marketplace operations contact the corresponding provider, GitHub or configured market address. Third parties receive normal request data, such as IP addresses, queries and paths, under their own policies.

## Connections and access

- The extension connects to the local runtime through Native Messaging or pairing. CLI and MCP clients can use that same runtime. Authorized local clients can invoke tools within their task scope; connect only clients you trust.
- Browser permissions cover tab management, page scripts, debugging, screenshots and downloads. Page associations, navigation recovery and selection features may run without a model request; an unsent message does not mean the extension reads no browser metadata.
- Approval mode determines which actions require confirmation. Full access reduces confirmations and may broaden local code execution permissions. Sandbox capabilities depend on the platform and configuration; they are not a virtual machine or an absolute safety guarantee for arbitrary code.

## Your controls and deletion

- You can stop tasks, change approval mode, remove providers, delete conversations or workspaces, and manage memories, skills and presets. Run tasks only on websites, accounts and files you are entitled to access.
- Deleting a conversation removes its records, attachments and associated artifacts. Copies in separate workspaces, downloaded or exported files, backups and data held by third parties are not removed with it.
- Uninstalling the extension removes its browser data but does not automatically remove the local runtime data directory. Removing program files and deleting user data are separate operations; updates retain user data. To remove everything, separately clear extension data, runtime data and any copies you saved.

## Browser permissions

- tabs / tabGroups / webNavigation / activeTab: tab selection, task groups, navigation associations and recovery.
- debugger: DOM and accessibility reads, input, screenshots and network diagnostics.
- scripting / website access: selections, highlights, automation and script reinjection after updates.
- storage / sidePanel / nativeMessaging: settings and connection state, the panel interface and local runtime connection.
- downloads / favicon / offscreen: file and installer downloads, site icons, background parsing and image processing.

## Policy and contact

- Updated: 2026-11-09. Application version: 0.1.6. This page is updated with releases when features or data handling change.
- For privacy questions, contact fenderisfine@gmail.com. Do not include API keys, cookies, private conversation dumps or unredacted request bodies in reports.

# 隐私政策

## 适用范围

本政策说明 Aether 浏览器扩展、本地运行时以及 CLI、MCP 如何处理数据。核心功能无需 Aether 账号。会话和文件以本机存储为主；使用模型、搜索、网页和更新功能时，相关数据会发送到对应服务。

## 本机数据与保留

- 浏览器保存设置、配对状态和草稿；未完成的附件暂存于 IndexedDB，恢复上传后释放临时文件副本。运行时保存会话、页面关联、附件、工作空间、预设、记忆、技能、工作流、计划与证据。
- API 密钥和自定义请求头保存在运行时配置文件中，并在调用对应提供方时发送。配置文件使用本机访问权限保护，未承诺系统钥匙串存储或应用层加密。
- 本地诊断日志记录状态、耗时、用量和经过过滤的错误；会话与工具记录仍可能包含页面内容、请求参数或其他敏感信息。日志和执行记录按各自的保留规则管理。

## 模型与上下文

- 你配置的模型服务会接收本次请求需要的系统指令、工具定义、对话、相关记忆与项目指令，以及被读取的文件内容、页面文本或图片。上下文压缩同样会调用所选模型处理较早记录。
- 模型提供方可能缓存输入或按其条款保留请求；缓存命中不代表数据只在本地处理。服务地址、代理、自定义请求头及提供方的数据政策由你的配置决定。
- Aether 不运营对话中转或用于训练的用户数据收集服务。停止任务会请求取消后续工作，但无法撤回已发送给第三方的数据。

## 网页、搜索与下载

- 搜索查询会发送给实际使用的搜索提供方，例如 Bing、百度、360 或 DuckDuckGo。网页读取与浏览器操作会访问目标网站；远程图片和网站图标也可能产生外部请求。
- 浏览器中的登录态由浏览器持有，页面请求可能使用现有 Cookie。网络捕获与接口测试可读取请求和响应正文；凭据头在显示结果中会过滤，但正文仍可能含有敏感信息。公开 HTTP 抓取不自动携带浏览器登录态。
- 模型目录、连接测试、软件更新、安装包下载及可选市场操作会连接对应提供方、GitHub 或配置的市场地址。第三方可获取正常请求所需的 IP、查询、路径等信息，并依其自身政策处理。

## 连接与权限

- 扩展通过原生消息或配对流程连接本地运行时；CLI 和 MCP 也可调用同一运行时。持有已授权连接的本机客户端可以在其任务范围内使用工具，请只连接可信客户端。
- 浏览器权限覆盖标签管理、页面脚本、调试、截图与文件下载。页面关联、导航恢复和选区功能可能在没有模型请求时工作，不能将“未发送消息”理解为扩展完全没有读取浏览器元数据。
- 审批模式决定哪些操作需要确认；完全授权会减少确认，并可能扩大本地代码执行权限。沙箱能力取决于平台与运行配置，不等同于虚拟机或对任意代码的绝对安全保证。

## 你的控制与删除

- 你可以停止任务、调整审批模式、移除提供方、删除会话或工作空间，以及管理记忆、技能和预设。请仅在有权处理的网页、账户和文件上运行任务。
- 删除会话会清理该会话的记录、附件和相关产物；独立工作空间中的副本、已下载或导出的文件、备份及第三方持有的数据不会因此一并删除。
- 卸载扩展会移除浏览器侧的扩展数据，但不会自动删除本地运行时数据目录。移除运行时程序与删除用户数据是两件事；程序更新保留用户数据。需要彻底移除时，请分别清理扩展数据、运行时数据和自行保存的副本。

## 浏览器权限用途

- tabs / tabGroups / webNavigation / activeTab：标签选择、任务分组、导航关联与恢复。
- debugger：读取 DOM 和无障碍结构、输入、截图及网络诊断。
- scripting / 网页访问权限：页面选区、高亮、自动化及更新后的脚本注入。
- storage / sidePanel / nativeMessaging：设置与连接状态、侧栏界面及本机运行时连接。
- downloads / favicon / offscreen：文件和安装包下载、网站图标、离屏解析与图像处理。

## 政策与联系

- 更新日期：2026-11-09。适用应用版本：0.1.6。功能或数据处理变化时，本页会随版本更新。
- 隐私问题可联系 fenderisfine@gmail.com。请勿在问题报告中附带 API 密钥、Cookie、完整私密会话或未脱敏的请求正文。

