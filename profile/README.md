# LetSeries

**LetSeries** 是 [CubeXMC 研究院](https://cubexmc.org/)（cubexmc.org）旗下的开发组织，专注于为 Minecraft 服务器提供实用、易用的工具与插件。

![LetSeries](https://img.shields.io/badge/LetSeries-CubeXMC%20%E7%A0%94%E7%A9%B6%E9%99%A2-blue?style=for-the-badge)
![GitHub org](https://img.shields.io/github/followers/LetSeries?label=Followers&style=for-the-badge)
![GitHub repos](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fapi.github.com%2Forgs%2FLetSeries&query=$.public_repos&style=for-the-badge&label=Public%20Repos)

## 关于我们

LetSeries 成立于 2026 年，是 CubeXMC 研究院旗下专注于 Minecraft 服务端开发的团队。我们致力于打磨「好用、够用、够稳」的插件与工具，从服务端日常运维到玩家体验细节，覆盖不同版本与服务端（Bukkit / Spigot / Paper / Folia / Purpur）。

## 项目

| 项目 | 说明 | 状态 |
| --- | --- | --- |
| [LetMeDo](https://github.com/LetSeries/LetMeDo) | 多功能 Minecraft 插件，几乎支持所有版本与所有服务端 | ![stars](https://img.shields.io/github/stars/LetSeries/LetMeDo?style=flat-square) |
| [LetMeSee](https://github.com/LetSeries/LetMeSee) | 用指令只读任意箱子，绕过 Lands 和 QuickShop 保护 | ![stars](https://img.shields.io/github/stars/LetSeries/LetMeSee?style=flat-square) |
| [LetMeAsk](https://github.com/LetSeries/LetMeAsk) | 答题插件，玩家答题可赚取金钱 | ![stars](https://img.shields.io/github/stars/LetSeries/LetMeAsk?style=flat-square) |
| [Server-AI](https://github.com/LetSeries/Server-AI) | 在 Minecraft 服务器里使用 AI | ![stars](https://img.shields.io/github/stars/LetSeries/Server-AI?style=flat-square) |
| [HumanVerify](https://github.com/LetSeries/HumanVerify) | 游戏内人机验证插件，支持 Paper、Folia、Purpur | ![stars](https://img.shields.io/github/stars/LetSeries/HumanVerify?style=flat-square) |

### LetMeDo

多功能 Minecraft 插件，几乎支持所有版本与所有服务端（Bukkit / Spigot / Paper / Folia / Velocity / BungeeCord）。采用多模块 Gradle 工程（Gradle Kotlin DSL，Java 21 工具链）：`api` 定义跨平台抽象、`core` 承载平台无关实现、`bukkit` / `velocity` / `bungee` 分别提供各端入口。以 Paper 1.21 API 编译，仅通过反射调用新版本方法并优雅降级，单个 jar 即可在老版本（1.8.8+）到最新版本上启动。内置命令 `/letmedo version`、`/letmedo modules`、`/letmedo reload`。

### LetMeSee

轻量级只读容器查看插件，允许 OP 通过指令**只读**查看任意坐标的容器物品，绕过 Lands、QuickShop、WorldGuard 等保护插件限制。使用 `Bukkit.getRegionScheduler().run()` 在正确的区域线程执行操作，完整支持 Folia 及 Paper。支持箱子、木桶、潜影盒、熔炉、漏斗、投掷器、酿造台等容器，界面自动本地化为中文。命令：`/lms`（查看准星正对的容器）、`/lms <世界> <X> <Y> <Z>`（打开指定坐标容器），权限节点 `letmesee.use`，MIT License。

### LetMeAsk

服务器抢答活动插件，定时在聊天栏出题，玩家抢答可获得金币奖励。支持自动出题、答题超时、Vault 经济集成、答案模糊匹配（相似度阈值可配置）。连续答对过多或回答过快会触发 [HumanVerify](https://github.com/FZAoao/HumanVerify) 人机验证（可选依赖）。支持玩家名、UUID、服务器账户、LittleSkin 等多种支付方式。命令 `/letmeask top / stats / status / start / stop / question / reload`，需 Paper/Spigot 1.20.4+，MIT License。

### Server-AI

面向 Paper/Folia 1.21+ 的 AI 问答插件，兼容 OpenAI Chat Completions 格式 API。`/ask <问题>` 向 AI 提问并广播到服务器，支持 AI Function Calling 控制 Paper 原版实体 NPC（`/npc spawn / remove / say / move / come / stop / info`），不依赖 Citizens。异步 HTTP 请求不占用区域线程，含每玩家冷却、并发上限、超时与长度限制。支持环境变量读取密钥，也支持 Ollama 等无需鉴权的本地 OpenAI 兼容服务。构建产物已重定位 Jackson 避免依赖冲突。

### HumanVerify

游戏内人机验证插件，支持 Paper、Folia、Purpur。玩家进服自动打开验证界面，在背包随机放置唯一方块，点击正确方块即通过。提供 27/36/45/54 格、颜色/材质/顺序/数量/找不同/中心角落等多样验证模式，可固定或随机。支持超时与错误次数限制，通过 Bukkit `ServicesManager` 暴露公共 API 供其他插件调用，使用 `EntityScheduler` 兼容 Folia 区域线程。命令 `/humanverify verify [玩家]`、`/humanverify reload`，需 Java 21+、Paper 1.21.x。

## 推送统计

| 项目 | 最近推送 | 贡献者 |
| --- | --- | --- |
| [LetMeDo](https://github.com/LetSeries/LetMeDo) | ![last-commit](https://img.shields.io/github/last-commit/LetSeries/LetMeDo?style=flat-square&label=%E6%9C%80%E8%BF%91%E6%8E%A8%E9%80%81) | ![contributors](https://img.shields.io/github/contributors/LetSeries/LetMeDo?style=flat-square&label=%E8%B4%A1%E7%8C%AE%E8%80%85) |
| [LetMeSee](https://github.com/LetSeries/LetMeSee) | ![last-commit](https://img.shields.io/github/last-commit/LetSeries/LetMeSee?style=flat-square&label=%E6%9C%80%E8%BF%91%E6%8E%A8%E9%80%81) | ![contributors](https://img.shields.io/github/contributors/LetSeries/LetMeSee?style=flat-square&label=%E8%B4%A1%E7%8C%AE%E8%80%85) |
| [LetMeAsk](https://github.com/LetSeries/LetMeAsk) | ![last-commit](https://img.shields.io/github/last-commit/LetSeries/LetMeAsk?style=flat-square&label=%E6%9C%80%E8%BF%91%E6%8E%A8%E9%80%81) | ![contributors](https://img.shields.io/github/contributors/LetSeries/LetMeAsk?style=flat-square&label=%E8%B4%A1%E7%8C%AE%E8%80%85) |
| [Server-AI](https://github.com/LetSeries/Server-AI) | ![last-commit](https://img.shields.io/github/last-commit/LetSeries/Server-AI?style=flat-square&label=%E6%9C%80%E8%BF%91%E6%8E%A8%E9%80%81) | ![contributors](https://img.shields.io/github/contributors/LetSeries/Server-AI?style=flat-square&label=%E8%B4%A1%E7%8C%AE%E8%80%85) |
| [HumanVerify](https://github.com/LetSeries/HumanVerify) | ![last-commit](https://img.shields.io/github/last-commit/LetSeries/HumanVerify?style=flat-square&label=%E6%9C%80%E8%BF%91%E6%8E%A8%E9%80%81) | ![contributors](https://img.shields.io/github/contributors/LetSeries/HumanVerify?style=flat-square&label=%E8%B4%A1%E7%8C%AE%E8%80%85) |

## 团队

| 成员 | 主页 |
| --- | --- |
| [FZAoao](https://github.com/FZAoao) | [GitHub](https://github.com/FZAoao) |
| [kevin-steve772](https://github.com/kevin-steve772) | [GitHub](https://github.com/kevin-steve772) |
| [angushushu](https://github.com/angushushu) | [GitHub](https://github.com/angushushu) |

## 联系我们

- 官网：[CubeXMC 研究院](https://cubexmc.org/)

## 展望

我们将持续完善现有项目，并在后续拓展更多面向 Minecraft 服务器的实用工具与插件，为服务器运营提供更完善的解决方案。

---

*维护方：[LetSeries](https://github.com/LetSeries) · 隶属：CubeXMC 研究院（[cubexmc.org](https://cubexmc.org/)）*