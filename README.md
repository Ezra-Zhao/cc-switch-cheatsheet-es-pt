# CC Switch 速查表 | CC Switch Cheatsheet | Guía rápida de CC Switch

> 一页看懂 CC Switch：一个桌面界面管住十几个编程 agent 的供应商与配置——换 API 供应商一键切换，不再手改 JSON/TOML/YAML；MCP、Prompts、Skills 集中管理；本地路由带故障转移，一个供应商挂了自动切下一个；用量和花费看得见。

- 上游项目：[farion1231/cc-switch](https://github.com/farion1231/cc-switch)（2026-10-29 实测 150,028 ★ / 9,856 forks，77 个 release；GitHub 官方 Octoverse 2026 博客列为社区/独立项目「按贡献者增长最快」第 1 名）
- 平台：Windows / macOS / Linux 桌面端
- 本页结构：中文主文 → English → Español → Português

---

Apoyo y más: [GitHub Sponsors](https://github.com/sponsors/Ezra-Zhao) · [Gumroad — plantillas y cuadernos que uso](https://ezraflow28.gumroad.com) · [Ko-fi](https://ko-fi.com/ezra777zhao)

## 它管什么

| 功能 | 一句话说明 |
|---|---|
| 供应商切换 | 每个 agent 的 API 供应商（官方/第三方/自建 endpoint）存成档案，点一下就切换，不再手改配置文件 |
| MCP 管理 | 各 agent 的 MCP server 配置集中增删启停，不用到每个工具里各配一遍 |
| Prompts / Skills 管理 | 提示词与技能统一存放、按 agent 分发 |
| 本地路由与故障转移 | 本地起路由，当前供应商挂了自动切下一个，不用半夜爬起来改配置 |
| 用量与花费追踪 | 各供应商的调用量与花费集中看账，月底不抓瞎 |
| 会话管理 | 各 agent 的会话集中浏览与清理 |

## 安装一行版

| 平台 | 装法 |
|---|---|
| Windows | GitHub Releases 下安装包（exe/msi） |
| macOS | Releases 下 dmg，或按上游 README 的 Homebrew 口径 |
| Linux | Releases 下对应包；另有 Arch（AUR）与 Flatpak 渠道 |

## 支持矩阵（口径说明）

Claude Code、Claude Desktop、Codex、Gemini CLI、OpenCode、Grok Build 等十几个编程 agent 都在支持名单里，但**每个 agent 被管的深度不同**（供应商切换 / MCP / Skills 三项不是每个 agent 都全支持）。装前先在上游 README 的支持矩阵里找到你用的那个 agent，确认你要的那项打勾，再动手。

## 换供应商四步卡

1. **加新供应商**：名称、endpoint、模型名、key 四样填齐。
2. **核对三件套**：endpoint 拼写、模型名与供应商那边的写法**逐字一致**（差一个字符就 404/鉴权失败，这是新手第一大坑）。
3. **完全退出并重启目标 CLI**：不是关窗口，是彻底退出进程再重开——多数 agent 只在启动时读配置，热切换不生效。
4. **先测普通文本、再测工具调用**：先问一句纯文本确认通路，再让它读个文件/跑个命令确认工具调用也正常，两步都过才算切换完成。

### ⚠️ 切换前先备份

- 先备份 `~/.cc-switch` 目录和各 agent 的原配置文件，再做任何切换动作。
- 备份里**含 API key 明文**：只存本地或自己的加密盘，**绝不上传 Git、公共网盘或任何分享链接**。

## 诚实标注区

- **第三方中转供应商的质量、稳定性与计费是供应商自己的事**：本速查只讲切换与管理的方法，**不推荐任何一家中转商**；便宜与否、跑路风险自行判断。
- **本地路由/聚合模式≠官方订阅**：走中转 endpoint 用的是供应商的计费与规则，和 Claude/Codex 官方订阅是两套账、两种保障，别混为一谈。
- **故障转移不是魔法**：备用供应商的模型能力与上下文长度可能不同，切过去后产出质量变了，先查是不是已经转移了。

---

## English (summary)

CC Switch (by farion1231, ~150k stars as of 2026-10-29; named the fastest-growing community project by contributor growth in GitHub's Octoverse 2026 post) is a cross-platform desktop app that manages providers and configuration for a dozen-plus coding agents — Claude Code, Claude Desktop, Codex, Gemini CLI, OpenCode, Grok Build and more. One UI for one-click provider switching (no more hand-editing JSON/TOML/YAML), centralized MCP / Prompts / Skills management, local routing with automatic failover, usage and cost tracking, and session management.

Install from GitHub Releases on Windows/macOS/Linux (Arch via AUR, Flatpak also available). Switching providers safely takes four steps: add the provider, verify endpoint/model name/key character-for-character, fully quit and restart the target CLI (most agents only read config at startup), then test plain text before testing tool calls. **Back up `~/.cc-switch` and the original config files first — backups contain plaintext API keys, so never upload them to Git or public drives.**

Honest notes: support depth varies per agent (check the upstream matrix); third-party relay providers' quality and billing are their own business — this page teaches switching, not shopping; local routing is not an official subscription.

---

## Español (guía rápida — traducción de estudio, pendiente de revisión por un hablante nativo)

CC Switch (de farion1231, ~150 mil estrellas en octubre de 2026; el blog oficial Octoverse 2026 de GitHub lo nombró el proyecto comunitario con mayor crecimiento de contribuidores) es una app de escritorio que centraliza proveedores y configuración de más de una docena de agentes de programación: Claude Code, Claude Desktop, Codex, Gemini CLI, OpenCode, Grok Build y más.

Qué hace por ti:

- **Cambio de proveedor en un clic**: adiós a editar JSON/TOML/YAML a mano.
- **MCP, Prompts y Skills centralizados**: configuras una vez, no una por herramienta.
- **Enrutamiento local con failover**: si un proveedor cae, pasa al siguiente solo.
- **Uso y gasto visibles**: cuánto consumes y cuánto pagas, por proveedor.
- **Gestión de sesiones** de todos tus agentes en un solo lugar.

**Instalación**: desde GitHub Releases en Windows, macOS y Linux (también AUR en Arch y Flatpak).

**Cambiar de proveedor en 4 pasos**: 1) agrega el proveedor (nombre, endpoint, modelo, clave); 2) revisa endpoint y nombre del modelo **letra por letra** — un carácter mal y todo falla; 3) **cierra por completo y reinicia** el CLI destino (la mayoría solo lee la configuración al arrancar); 4) prueba primero texto normal y después una llamada a herramientas.

**Antes de tocar nada, respalda** la carpeta `~/.cc-switch` y los archivos de configuración originales. Esos respaldos contienen tus claves API en texto plano: guárdalos solo en local o en un disco cifrado, **nunca en Git ni en nubes públicas**.

**Notas honestas**: la profundidad de soporte varía según el agente (revisa la matriz oficial); la calidad y los precios de los proveedores intermediarios son asunto de ellos — esta guía enseña a cambiar, no recomienda a ninguno; el enrutamiento local no es lo mismo que una suscripción oficial.

---

## Português (guia rápido — tradução de estudo, aguardando revisão de um falante nativo)

O CC Switch (de farion1231, ~150 mil estrelas em outubro de 2026; o blog oficial Octoverse 2026 do GitHub o apontou como o projeto comunitário com maior crescimento de contribuidores) é um app desktop que centraliza provedores e configuração de mais de uma dúzia de agentes de programação: Claude Code, Claude Desktop, Codex, Gemini CLI, OpenCode, Grok Build e mais.

O que ele faz por você:

- **Troca de provedor em um clique**: adeus a editar JSON/TOML/YAML na mão.
- **MCP, Prompts e Skills centralizados**: você configura uma vez, não uma por ferramenta.
- **Roteamento local com failover**: se um provedor cai, ele passa para o próximo sozinho.
- **Uso e gasto visíveis**: quanto você consome e quanto paga, por provedor.
- **Gerenciamento de sessões** de todos os agentes num só lugar.

**Instalação**: pelo GitHub Releases no Windows, macOS e Linux (também AUR no Arch e Flatpak).

**Trocar de provedor em 4 passos**: 1) adicione o provedor (nome, endpoint, modelo, chave); 2) confira endpoint e nome do modelo **letra por letra** — um caractere errado e tudo quebra; 3) **feche por completo e reinicie** o CLI de destino (a maioria só lê a configuração na inicialização); 4) teste primeiro texto normal e depois uma chamada de ferramenta.

**Antes de mexer, faça backup** da pasta `~/.cc-switch` e dos arquivos de configuração originais. Esses backups contêm suas chaves de API em texto puro: guarde só local ou em disco criptografado, **nunca no Git nem em nuvem pública**.

**Notas honestas**: a profundidade do suporte varia por agente (confira a matriz oficial); qualidade e preço de provedores intermediários são problema deles — este guia ensina a trocar, não recomenda nenhum; roteamento local não é a mesma coisa que assinatura oficial.

---

## 来源与声明

- 灵感来源 / Source / Fuente / Fonte: [farion1231/cc-switch](https://github.com/farion1231/cc-switch)
- 本仓是个人学习整理：内容用我自己的话总结自上游公开文档，不搬运原文；功能与支持矩阵以 2026-10-29 的上游 README 为准，上游迭代很快，请以官方文档为最终依据。
- 西语、葡语部分为学习译稿，待母语校对。Las secciones en español y portugués son traducciones de estudio pendientes de revisión nativa.
- License: MIT © 2026 Guangyi Zhao
