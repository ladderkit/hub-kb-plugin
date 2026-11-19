# LadderKit 插件（hub-kb）

LadderKit 是免费的代理客户端知识库：Clash Verge Rev、v2rayN、sing-box 等客户端的概念、教程与排错。装上本插件后，你问代理客户端的问题时，AI 助手会查这个知识库，按条目作答，并在回答末尾给出条目页面的链接。

## 插件里有什么

- `skills/hub-kb/SKILL.md`：什么时候用这个知识库、怎么查、怎么回答。
- `skills/hub-kb/index-min.json`：条目的标题与别名，远程服务连不上时当目录用；不含条目正文。
- `.mcp.json`：登记远程 MCP 服务器 `hub-kb`，地址是 `https://mcp.ladderkit.dev/mcp?ch=grok-build`。

## 运行、发送与取回什么

- 插件本身不运行程序或命令，不读取你机器上的状态，也不写入任何文件。
- 你问代理客户端的问题时，AI 助手调用远程 MCP 服务器 `https://mcp.ladderkit.dev/mcp?ch=grok-build`：
  - `list_entries`：发送你问题的原话（1–200 字；插件要求 AI 助手先把其中的订阅链接、密码、令牌、节点地址与账号信息换成「已去掉」，但不保证去全），取回条目目录（id、类型、标题、别名）。
  - `get_entry`：发送条目 id，取回条目正文（Markdown）。
- 远程服务连不上时：你另外装了本地 MCP（npm 包 `@ladderkitlab/hub-kb`）就改用它；也连不上时，只用本目录的 `index-min.json` 挑条目，回答里给出 LadderKit 网站（https://ladderkit.dev）上的条目链接。
- 服务器对每次 `list_entries` 记一条：日期、遮蔽后只留下的词表内的词、内容版本、渠道（地址里的 `ch` 参数，只说明从哪一类来源接入：宿主、插件市场或目录站）和一个把相同问法归到一起的指纹；`get_entry` 成功取回正文时记日期、条目、内容版本与渠道。记录里没有 IP，也没有用户标识；请求很少的渠道，按日期和渠道仍可能与当天的目录请求对上。超过 90 天的记录每天清掉。详见隐私说明：https://ladderkit.dev/privacy/

## 许可

本目录的内容按 CC BY-NC-SA 4.0 发布，全文与署名格式见同目录的 `LICENSE`。

## About

LadderKit is a free knowledge base for proxy clients such as Clash Verge Rev, v2rayN and sing-box, written in Chinese. This plugin adds one skill and one remote MCP server. When you ask about a proxy client, the assistant sends your question (1 to 200 characters; the skill tells the assistant to replace subscription links, passwords, tokens, server addresses and account details with a placeholder first, but this is not guaranteed) to `https://mcp.ladderkit.dev/mcp?ch=grok-build` through the `list_entries` tool, then sends entry ids through the `get_entry` tool to read entries. The plugin itself runs no programs or commands, does not read the state of your machine and writes no files. For each `list_entries` call the server logs the date, the masked words that match its vocabulary, the content version, the channel (the `ch` parameter in the address, which only names the kind of source: a host, a plugin marketplace or a directory) and a fingerprint that groups identical questions; for each `get_entry` call that returns an entry it logs the date, the entry, the content version and the channel. The logs hold no IP address and no user id; for a channel with very few requests, the date and channel can still link an entry read to that day's catalog request. Rows older than 90 days are deleted daily. If the server is unreachable, the skill picks entries from `index-min.json` and links to entry pages on https://ladderkit.dev. Privacy policy: https://ladderkit.dev/privacy/. License: CC BY-NC-SA 4.0, see `LICENSE`.
