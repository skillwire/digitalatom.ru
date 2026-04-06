# Research: Claude Code & Alternatives (March–April 2026)

Только факты и ссылки. Источники: март–апрель 2026.

---

## 1. Changelog Claude Code

### Ключевые обновления (март–апрель 2026)

- **Computer Use** добавлен в Claude Code для Pro и Max пользователей (23 марта 2026)
- **Scheduled tasks (/loop)** — recurring jobs на облачной инфраструктуре Anthropic
- **Push-to-talk voice mode** — hold spacebar to speak (март 2026)
- **1M token context window** в бете для Claude Opus 4.6
- **v2.1.92** (4 апреля 2026): stronger policy controls, Bedrock setup wizard
- Opus 4 и 4.1 удалены из first-party API; auto-migration на 4.6
- PowerShell tool preview для Windows
- **/powerup** command для interactive feature lessons
- Исправлен Bash tool output loss в multiple sessions

### Источники

- https://code.claude.com/docs/en/changelog
- https://github.com/anthropics/claude-code/blob/main/CHANGELOG.md
- https://claudefa.st/blog/guide/changelog
- https://www.builder.io/blog/claude-code-updates
- https://pasqualepillitteri.it/en/news/381/claude-code-march-2026-updates
- https://help.apiyi.com/en/claude-code-2026-new-features-loop-computer-use-remote-control-guide-en.html

---

## 2. OpenClaw: License, Billing, Claude Max

### License & Open Source

- OpenClaw имеет open-source плагин для Claude Code на GitHub
- ClaudeClaw — lightweight open-source версия, встроенная в Claude Code
- OpenClaw переименован из Moltbot 29 января 2026

### Биллинг — критическое изменение 4 апреля 2026

- С 4 апреля 2026 OpenClaw **больше не покрывается** подписками Claude Pro/Max
- Трафик OpenClaw теперь требует API billing (pay-per-token)
- Пользователи должны перейти на Extra Usage (pay-as-you-go) или API Key billing
- Рост стоимости: пользователи, платившие $20–200/мес, столкнулись с 50x увеличением расходов
- Anthropic предлагает one-time credit, равный стоимости месячного плана (до 17 апреля)
- До 30% скидка на pre-purchased extra usage bundles

### Совместимость с Claude Max

- Claude Max **не работает** с OpenClaw с 4 апреля 2026
- Subscription quota access отключён для third-party tools
- Конец 2025: пользователи обнаружили OAuth token extraction для обхода API billing; Anthropic заблокировал в январе 2026
- claude-max-api-proxy существует как community tool, но Anthropic заблокировал часть путей
- Подписки официально покрывают только: Claude Code CLI, claude.ai, Desktop

### Источники

- https://github.com/Enderfga/openclaw-claude-code
- https://docs.openclaw.ai/providers/anthropic
- https://www.heise.de/en/news/Anthropic-is-removing-OpenClaw-from-its-Claude-subscriptions-11246096.html
- https://www.xda-developers.com/claude-subscribers-just-lost-access-to-openclaw-and-other-third-party-toolsunless-they-pay-more/
- https://github.com/moazbuilds/claudeclaw
- https://medium.com/@hugolu87/openclaw-vs-claude-code-in-5-mins-1cf02124bc08
- https://thunderbit.com/blog/openclaw-cost-per-month
- https://www.roborhythms.com/anthropic-blocks-openclaw-claude-subscription-2026/
- https://www.newsbytesapp.com/news/science/anthropic-begins-billing-3rd-party-claude-tools-separately-april-4-2026/tldr
- https://shoofly.dev/blog/openclaw-claude-billing-change/
- https://designsbydaveo.com/claude-max-no-longer-works-with-openclaw-what-happened-and-what-to-do-about-it/

---

## 3. Claude Code CLI vs VS Code Remote vs tmux-first на VPS

### Claude Code CLI

- Standalone Node.js приложение (Bun runtime)
- TypeScript + custom React/Ink TUI
- 50+ tools, MCP integration
- Лучший контроль контекста через message editing
- Checkpoint management, autonomous operation
- AI-модель работает удалённо на серверах Anthropic; локальный процесс — context, file ops, tool execution

### VS Code Extension

- Native extension, GA с начала 2026
- Inline diffs, @-mentions для файлов, slash commands, workspace integration
- Новички показывают более высокий success rate с визуальным интерфейсом
- Review/edit планов Claude до принятия
- Conversation history в отдельных tabs/windows
- Auto-accept edits as they're made

### VPS + tmux Architecture

- Популярный сетап: VPS + Tailscale + Termius + tmux
- Session persistence: Claude Code продолжает работу после disconnect
- Reattach — возврат к полной conversation history
- Рекомендуется: 4+ vCPU, 8GB RAM
- Setup: Ubuntu 22.04/24.04 LTS, tmux, ripgrep
- Auth: `claude setup-token` → OAuth token → `CLAUDE_CODE_OAUTH_TOKEN` env var
- VPS провайдеры: AWS Lightsail, DigitalOcean, Hetzner, Linode ($10–20/мес)
- Killer feature: закрыть ноутбук, вернуться к готовому diff без потери сессии

### Источники

- https://code.claude.com/docs/en/setup
- https://www.quantvps.com/blog/how-to-install-claude-code-on-vps
- https://medium.com/@0xmega/claude-code-on-a-vps-the-complete-setup-security-tmux-mobile-access-2d214f5a0b3b
- https://claudefa.st/blog/guide/development/infraops-vps-guide
- https://zainhas.github.io/blog/2026/inside-claude-code-architecture/
- https://code.claude.com/docs/en/vs-code
- https://claudelog.com/faqs/claude-code-cli-vs-vscode-extension-comparison/
- https://www.getaiperks.com/en/articles/claude-code-vs-code-extension
- https://www.nxcode.io/resources/news/cursor-vs-claude-code-vs-github-copilot-2026-ultimate-comparison
- https://nuttakitkundum.medium.com/vibe-coding-anytime-anywhere-with-tmux-tailscale-and-claude-code-fda01f3c5cd2
- https://ksingh7.medium.com/watch-claude-code-agents-work-side-by-side-a-tmux-setup-guide-1ef3ba1531c4
- https://gist.github.com/ChrisColeTech/aecf3ddf7e80b5d03040177b4913323e
- https://medium.com/@lexy_eyn/why-and-how-to-run-claude-code-on-a-vps-657daf79e3ea
- https://www.blle.co/blog/claude-code-tmux-beautiful-terminal
- https://code.claude.com/docs/en/terminal-config

---

## 4. VS Code Remote + Claude Code VPS: Issues & Workarounds

### Известные проблемы (GitHub Issues)

- [#3153](https://github.com/anthropics/claude-code/issues/3153) — IDE Detection Failure в VS Code Remote SSH Environment
- [#44089](https://github.com/anthropics/claude-code/issues/44089) — VS Code Remote SSH: требует re-login, macOS Keychain недоступен из SSH
- [#9891](https://github.com/anthropics/claude-code/issues/9891) — Remote Authentication via VS Code Remote-SSH Fails macOS
- [#20226](https://github.com/anthropics/claude-code/issues/20226) — Extension не работает с Remote-SSH (всегда использует локальные Windows paths)
- [#21960](https://github.com/anthropics/claude-code/issues/21960) — VSCode Remote SSH: Extremely slow tool execution / UI unresponsive (regression в 2.1.20+)
- [#28951](https://github.com/anthropics/claude-code/issues/28951) — Remote Control (/rc) не поддерживается в VS Code extension
- [#30905](https://github.com/anthropics/claude-code/issues/30905) — Feature Request: Remote Control support для VS Code chat mode
- [#30473](https://github.com/anthropics/claude-code/issues/30473) — Claude Code Remote not connecting
- [#29449](https://github.com/anthropics/claude-code/issues/29449) — Remote Control environments are not available for your account

### Категории проблем

**Authentication & Path:**
- OAuth credentials хранятся в macOS Keychain; SSH сессии не имеют доступа к Keychain
- Extension использует локальные Windows paths вместо remote server paths через Remote-SSH
- IDE detection fails: "The IDE cannot be detected but you did install the Claude Code for VSCODE extension"

**Performance:**
- Shift+Enter keybinding issues в Remote SSH — keypresses submit prematurely
- Extremely slow tool execution и unresponsive UI
- Random lag, rubber-banding, terminal glitching после длинных сессий на VPS

**Remote Control:**
- /rc НЕ поддерживается в VS Code extension (только CLI)
- Permission denied / connection refused от SSH misconfiguration
- 10-минутный network timeout для Remote Control sessions
- `--dangerously-skip-permissions` не работает с Remote Control (намеренно)

### Workarounds

- Рекомендуемый workaround: использовать Claude Code CLI напрямую в терминале на remote server, минуя extension
- https://kane.mx/posts/2025/vscode-remote-ssh-claude-code-keybindings/
- https://smartscope.blog/en/generative-ai/claude/claude-code-remote-ssh-setup-guide/
- https://smartscope.blog/en/generative-ai/claude/claude-code-remote-access/
- https://smartscope.blog/en/generative-ai/claude/claude-code-desktop-ssh-windows-enoent/

### Deployment Guides

- https://www.digitalocean.com/community/tutorials/claude-code-gpu-droplets-vscode
- https://claudefa.st/blog/guide/development/infraops-vps-guide
- https://coder.com/blog/building-for-2026-why-anthropic-engineers-are-running-claude-code-remotely-with-c
- https://dev.to/svenlito/building-a-shared-ai-memory-system-how-i-connected-claude-desktop-and-vs-code-through-vagrant-2280

---

## 5. OpenCode — статус апреля 2026

### Общая информация

- Open-source AI coding agent: CLI, desktop app, IDE extension
- Go-based CLI с TUI на Bubble Tea
- 120K GitHub Stars, 800 Contributors
- Поддержка 75+ LLM providers (не только Claude)
- Не хранит код и context data — privacy-focused

### Релизы апреля 2026

**v1.3.14** (4 апреля 2026):
- Восстановлены git-backed review modes (uncommitted и branch diffs)
- Fixed revert chains
- macOS managed preferences для MDM-enforced config
- Fixed sessions stuck after tool calls с OpenAI-compatible providers
- Compaction summaries сохраняются на языке conversation
- Venice AI добавлен как provider

**v1.3.15**:
- Fixed npm installs failing (Arborist + node-gyp path)

**Другие обновления апреля 2026**:
- Core Subagent tool calls остаются clickable while pending
- Improved storage migration reliability и Catppuccin contrast
- Prompt caching и cache token tracking для Google Vertex Anthropic
- Fixed Azure provider options forwarding после AI SDK v6 migration
- Dedicated Kimi system prompt
- Improved TUI terminal output passthrough

### Возможности

- LSP integration
- Session management, shareable session links
- Vim-like editor
- Parallel multi-session agents
- Multi-agent orchestration platform
- GitHub integration — mention /opencode или /oc в comments для GitHub Actions tasks

### Сравнение с Claude Code

- **Провайдеры**: OpenCode 75+ vs Claude Code только Anthropic
- **Стоимость**: OpenCode бесплатный + локальные модели; Claude Code от $20/мес
- **Архитектура**: OpenCode — agent system (chaining actions); Claude Code — IDE extension/CLI
- **Use case**: OpenCode для команд с нуждой в контроле model choice, execution, cost; Claude Code для smooth experience с strong defaults

### Источники

- https://github.com/opencode-ai/opencode
- https://opencode.ai/
- https://opencode.ai/docs/
- https://opencode.ai/changelog
- https://github.com/anomalyco/opencode/releases
- https://www.datacamp.com/blog/opencode-vs-claude-code
- https://dev.to/tech_croc_f32fbb6ea8ed4/opencode-vs-claude-code-which-ai-cli-coding-agent-wins-in-2026-45md
- https://sanj.dev/post/opencode-deep-dive-2026
- https://aiproductweekly.substack.com/p/claude-code-vs-opencode-the-ultimate
- https://www.builder.io/blog/opencode-vs-claude-code
- https://www.tensorlake.ai/blog-posts/opencode-the-best-claude-code-alternative
- https://www.morphllm.com/comparisons/opencode-vs-claude-code
- https://www.andreagrandi.it/posts/comparing-claude-code-vs-opencode-testing-different-models/
- https://thomas-wiegold.com/blog/i-switched-from-claude-code-to-opencode/
- https://danielmiessler.com/blog/opencode-vs-claude-code
- https://www.xda-developers.com/tested-claude-code-open-source-alternatives-one-came-close/
- https://www.xda-developers.com/found-a-free-open-source-alternative-to-claude-code/
- https://github.com/different-ai/openwork
- https://github.com/awesome-opencode/awesome-opencode
