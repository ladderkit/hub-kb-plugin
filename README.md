# hub-kb-plugin

LadderKit 知识库（hub-kb）的插件仓库。LadderKit 是免费的代理客户端知识库：Clash Verge Rev、v2rayN、sing-box 等客户端的概念、教程与排错（中文）。每份插件都是同一个 skill（`SKILL.md` 与条目目录 `index-min.json`）加一个远程 MCP 服务器，按宿主放在不同子目录或仓库根部；各子目录的 README 写明插件发送什么、取回什么。

| 位置 | 宿主 | 安装 |
|---|---|---|
| `hub-kb/` | Claude Code、CodeBuddy | `/plugin marketplace add https://github.com/ladderkit/hub-kb-plugin.git`，再 `/plugin install hub-kb@ladderkit` |
| `hub-kb-cursor/` | Cursor | 在 Cursor 里 Customize → Add → From GitHub Repository 填 `https://github.com/ladderkit/hub-kb-plugin`，再 Add hub-kb；也可以把 `hub-kb-cursor/` 复制成 `~/.cursor/plugins/local/hub-kb/`，重启 Cursor |
| `hub-kb-grok/` | Grok Build | 准备提交到 xAI 的插件目录，上架后在目录里安装 |
| 仓库根部（`.antigravity-plugin/`、`mcp_config.json`） | Antigravity CLI | `agy plugin install https://github.com/ladderkit/hub-kb-plugin`（skill 取自 `hub-kb/skills/`；发送与记录同 `hub-kb/README.md`，渠道是 `antigravity`） |

别的宿主按 MCP 地址手动配置，见 https://ladderkit.dev/install/ 。

插件本身不运行程序或命令，也不写入任何文件。隐私说明：https://ladderkit.dev/privacy/ 。内容按 CC BY-NC-SA 4.0 发布，全文见 `LICENSE-CONTENT`。

## About

Plugin repository for the LadderKit knowledge base (hub-kb), a free knowledge base for proxy clients such as Clash Verge Rev, v2rayN and sing-box: concepts, guides and troubleshooting, written in Chinese. Every plugin is the same skill (`SKILL.md` plus the entry catalog `index-min.json`) and one remote MCP server, in one subfolder per host or at the repository root; each subfolder's README says what the plugin sends and what it gets back.

- `hub-kb/`: Claude Code and CodeBuddy. Run `/plugin marketplace add https://github.com/ladderkit/hub-kb-plugin.git`, then `/plugin install hub-kb@ladderkit`.
- `hub-kb-cursor/`: Cursor. In Cursor, Customize → Add → From GitHub Repository with `https://github.com/ladderkit/hub-kb-plugin`, then add hub-kb; or copy `hub-kb-cursor/` as `~/.cursor/plugins/local/hub-kb/` and restart Cursor.
- `hub-kb-grok/`: Grok Build. To be submitted to xAI's plugin directory; install from there once it is listed.
- Repository root (`.antigravity-plugin/`, `mcp_config.json`): Antigravity CLI. Run `agy plugin install https://github.com/ladderkit/hub-kb-plugin`; the skill comes from `hub-kb/skills/`, it sends and logs the same as `hub-kb/README.md` describes, and its channel is `antigravity`.

Other hosts can add the MCP server by hand: https://ladderkit.dev/install/ . The plugins themselves run no programs or commands and write no files. Privacy policy: https://ladderkit.dev/privacy/. License: CC BY-NC-SA 4.0, see `LICENSE-CONTENT`.
