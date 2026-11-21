---
title: Privacy Policy — Aether
---

# Privacy Policy

Updated November 21, 2026 · Application version 0.1.8

This policy covers the Aether browser extension, its companion runtime, and its command-line and MCP interfaces. Aether requires no Aether account. Conversations and files are stored on the machine running the runtime; tasks can send information to the services described below. Aether does not operate a conversation relay, sell user data, or use it for advertising or model training. The product includes no remote analytics or tracking service.

## Information Aether handles

The browser stores preferences, pairing state, page associations and drafts. Attachments and selected text can be staged in browser storage and transferred to the runtime before a message is sent. Page titles, URLs and text selections support page references and quotation previews; recording captures actions only while recording is enabled. The current page's title and URL are included as a default message reference, which you can remove before sending.

The runtime stores conversations, responses, tool results, attachments, annotations, workspace files, generated files, presets, memories, skills, workflows, goals, plans and evidence. Depending on the pages and files you use, these materials may contain personal details, private communications, authentication information, or financial or health information. Token activity is calculated locally from saved model usage records. Diagnostic logs record status, timing, usage and errors, with credential-field filtering; tool records and error text can still contain sensitive information.

API keys and custom request headers are stored in local configuration files and used for requests to your configured model services. These files rely on operating-system access controls, not application-level encryption or a system keychain.

## Services that receive information

- **Model services:** your configured provider receives instructions, tool definitions, conversation context, relevant memories and workspace information, and the page text, screenshots, files, quotations or results used in a task. Summarizing older context also sends that material to the provider. Returned reasoning may be stored and sent back as required by its API. Retention, caching and training practices depend on that provider and your settings.
- **Search and websites:** queries go to the search services used, including Bing, Baidu, 360, DuckDuckGo, arXiv, Wikipedia, Stack Exchange and GitHub. Browser requests may use your existing website login. Network inspection can read request and response bodies; filtering credential headers does not remove sensitive content from those bodies.
- **Images and downloads:** site icons and expanded source previews can contact external servers. Remote Markdown images load after you click their loading control. Model catalogs, connection checks and installer or update downloads contact the configured provider, GitHub or update endpoint. Network-enabled code may contact other services or package registries. When verifying a proxy's synthetic DNS address, the runtime may send the destination hostname to Cloudflare or Google DNS.

These services receive ordinary connection information, including IP addresses and requested URLs, and apply their own policies. If you contact support, we receive the message and materials you choose to send; public issue reports are visible to others.

## Permissions and execution

Browser permissions provide the sidebar (`sidePanel`), local storage (`storage`, `unlimitedStorage`), page access (`activeTab`, `scripting`, website permissions), page actions and diagnostics (`debugger`), task tabs and navigation (`tabs`, `tabGroups`, `webNavigation`), runtime connection (`nativeMessaging`), site icons (`favicon`), downloads (`downloads`, optional `downloads.open`) and background parsing or image processing (`offscreen`). Page-reference, selection and navigation features can operate without a model request. Aether does not request access to Chrome's browsing-history database.

The runtime normally connects locally with pairing authentication. If you configure a remote runtime, task data is transferred to and stored on that host; its operator and connection security matter. Authorized CLI and MCP clients use the same runtime tools and permissions.

Code execution follows the selected permissions and available platform isolation. Restricted execution limits filesystem access; full access can permit broader host access. Network-enabled code can transmit data it can read. Importing a skill does not run its commands. Loading an enabled skill can activate supported command hooks: approval mode asks first, while full access uses the task's authorization. Hooks may receive prompts, tool inputs and results, errors or replies; their feedback can be stored and included in model context. Restricted hooks do not receive the transcript path. Full access can expose it and files containing credentials. Disabling a skill prevents later activation.

## Your controls and retention

You can stop tasks, remove page references or model providers, and manage saved conversations, files, memories, skills and workflows. Stopping or recalling a message cannot undo website changes or recall data already transmitted.

Saved content remains until deleted. Deleting a conversation removes its associated transcript, attachments, annotations, artifacts and evidence. Recalling messages does not delete their attachments or generated files. Deleting a workspace removes its files. Separate saved copies, exports, backups and third-party records remain; diagnostic logs rotate separately.

Updates preserve user data. Uninstalling the extension does not remove the runtime's data directory, and removing runtime program files does not erase that data. For complete removal, delete extension data, runtime data and any retained copies separately.

## Updates and contact

We update this policy when data handling changes. For privacy questions, contact [fenderisfine@gmail.com](mailto:fenderisfine@gmail.com). Please exclude API keys, cookies and private transcripts from reports.

---

# 隐私政策

更新日期：2026 年 11 月 21 日 · 适用应用版本：0.1.8

本政策适用于 Aether 浏览器扩展、配套运行时，以及命令行和 MCP 接口。使用 Aether 无需注册 Aether 账号。会话和文件保存在运行时所在设备上；任务可能向下述服务发送相关信息。Aether 不运营对话中转服务，不出售用户数据，也不将其用于广告或模型训练。产品未接入远程统计或跟踪服务。

## Aether 处理的信息

浏览器保存偏好、配对状态、页面关联和草稿。附件与选中的文字可在发送消息前暂存于浏览器并传到运行时。页面标题、网址和选区用于网页引用与引用预览；操作录制仅在启用录制期间进行。输入框默认附带当前页的标题和网址，可在发送前移除。

运行时保存会话、回复、工具结果、附件、注释、工作空间文件、生成文件、预设、记忆、技能、工作流、目标、计划和证据。根据你使用的页面和文件，这些材料可能包含个人信息、私人通信、身份验证信息，以及财务或健康信息。Token 活动根据保存的模型用量在本地计算。诊断日志记录状态、耗时、用量和错误，并过滤凭据字段；工具记录和错误文本仍可能含有敏感信息。

API 密钥和自定义请求头保存在本地配置文件中，用于请求你配置的模型服务。文件依赖操作系统的访问权限保护，未采用应用层加密或系统钥匙串存储。

## 会接收信息的服务

- **模型服务：** 你配置的提供方会收到指令、工具定义、会话上下文、相关记忆和工作空间信息，以及任务使用的页面文本、截图、文件、引用或结果。整理较早上下文时，也会将相应材料发送给提供方。模型返回的思考内容可能被保存，并按接口要求回传。数据保留、缓存和训练规则取决于该提供方及你的设置。
- **搜索与网站：** 查询会发送给实际使用的搜索服务，包括 Bing、百度、360、DuckDuckGo、arXiv、Wikipedia、Stack Exchange 和 GitHub。浏览器请求可能使用已有网站登录态。网络检查可以读取请求和响应正文；过滤凭据头不代表正文中的敏感内容也被移除。
- **图片与下载：** 网站图标和展开的来源预览可能访问外部服务器。远程 Markdown 图片在点击加载入口后获取。模型目录、连接检查、安装包和更新下载会访问配置的提供方、GitHub 或更新地址。允许联网的代码可能访问其他服务或软件包仓库；核验代理返回的合成 DNS 地址时，运行时可能向 Cloudflare 或 Google DNS 发送目标域名。

这些服务会收到 IP 地址、请求网址等正常连接信息，并适用各自的政策。联系支持时，我们会收到你主动发送的消息和材料；公开问题报告可被其他人查看。

## 权限与执行

浏览器权限用于侧栏界面（`sidePanel`）、本地存储（`storage`、`unlimitedStorage`）、页面访问（`activeTab`、`scripting`、网站权限）、页面操作与诊断（`debugger`）、任务标签与导航（`tabs`、`tabGroups`、`webNavigation`）、运行时连接（`nativeMessaging`）、网站图标（`favicon`）、下载（`downloads`、可选 `downloads.open`）及离屏解析或图像处理（`offscreen`）。页面引用、选区和导航功能可以在没有模型请求时工作。Aether 不申请读取 Chrome 浏览历史数据库的权限。

运行时默认通过配对认证在本机连接。如果配置远程运行时，任务数据会传输并保存到该主机，须考虑主机管理方及连接安全。已授权的 CLI 和 MCP 客户端使用同一运行时的工具与权限。

代码执行遵循所选权限和平台可用的隔离能力。受限执行限制文件访问；完全授权可能允许更广的宿主访问。允许联网的代码可以传输其能够读取的数据。导入技能不会执行命令；加载已启用技能后，可能激活受支持的命令 Hook：审批模式先确认，完全授权沿用任务授权。Hook 可能收到问题、工具参数与结果、错误或回复，其反馈可能保存在本机并进入模型上下文。受限 Hook 不获得原始会话文件路径；完全授权可能获得该路径并访问含凭据的文件。停用技能可阻止后续激活。

## 你的控制与数据保留

你可以停止任务、移除页面引用或模型提供方，管理已保存的会话、文件、记忆、技能和工作流。停止任务或撤回消息，不能撤销已发生的网站修改，也不能收回已发送的数据。

保存的内容保留至删除。删除会话会移除其记录、附件、注释、产物和证据。撤回消息不会删除附件或生成文件；删除工作空间会移除其中的文件。单独保存的副本、导出、备份和第三方记录仍会保留，诊断日志另行轮换。

更新保留用户数据。卸载扩展不会删除运行时数据目录，移除运行时程序也不等于删除数据。需要彻底移除时，请分别清理扩展数据、运行时数据及保留的副本。

## 更新与联系

数据处理方式变化时，我们会更新本政策。隐私问题请联系 [fenderisfine@gmail.com](mailto:fenderisfine@gmail.com)。请勿在报告中附带 API 密钥、Cookie 或私密会话。
