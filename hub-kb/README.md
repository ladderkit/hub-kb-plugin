# LadderKit 插件（hub-kb）

LadderKit 是免费的代理客户端知识库：Clash Verge Rev、v2rayN、sing-box 等客户端的概念、教程与排错。装上本插件后，你问代理客户端的问题时，AI 助手会查这个知识库，按条目作答，并在回答末尾给出条目页面的链接。

## 插件里有什么

- `skills/hub-kb/SKILL.md`：什么时候用这个知识库、怎么查、怎么回答。
- `skills/hub-kb/index-min.json`：条目的标题与别名，远程服务连不上时当目录用；不含条目正文。
- `.mcp.json`：登记远程 MCP 服务器 `hub-kb`，地址是 `https://mcp.ladderkit.dev/mcp?ch=plugin`。

## 运行、发送与取回什么

- 插件本身不运行程序或命令，不读取你机器上的状态，也不写入任何文件。
- 你问代理客户端的问题时，AI 助手调用远程 MCP 服务器 `https://mcp.ladderkit.dev/mcp?ch=plugin`：
  - `list_entries`：发送你问题的原话（1–200 字），取回条目目录（id、类型、标题、别名）。
  - `get_entry`：发送条目 id，取回条目正文（Markdown）。
- 远程服务连不上时：你另外装了本地 MCP（npm 包 `@ladderkitlab/hub-kb`）就改用它；也连不上时，只用本目录的 `index-min.json` 挑条目，回答里给出 LadderKit 网站（https://ladderkit.dev）上的条目链接。
- 服务器记录什么、保存多久，见隐私说明：https://ladderkit.dev/privacy/

## 许可

本目录的内容按 CC BY-NC-SA 4.0 发布，全文与署名格式见同目录的 `LICENSE`。

## About

LadderKit is a free knowledge base for proxy clients such as Clash Verge Rev, v2rayN and sing-box, written in Chinese. This plugin adds one skill and one remote MCP server. When you ask about a proxy client, the assistant sends your question (1 to 200 characters) to `https://mcp.ladderkit.dev/mcp?ch=plugin` through the `list_entries` tool, then sends entry ids through the `get_entry` tool to read entries. The plugin itself runs no commands and writes no files. If the server is unreachable, the skill picks entries from `index-min.json` and links to entry pages on https://ladderkit.dev. Privacy policy: https://ladderkit.dev/privacy/. License: CC BY-NC-SA 4.0, see `LICENSE`.
