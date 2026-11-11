# Awesome Claude Fable 5.2 中文导航

这里收集 **Claude Fable 5.2** 的官方资料、提示词实践、GitHub 项目和 X 社区案例。Fable 5.2 是 Anthropic 于 2026 年 11 月 9 日发布的前沿模型（与面向受审核组织的 Claude Mythos 5.2 同源），适合寻找可追溯的学习资料与创作灵感。本仓库由社区独立维护，与 Anthropic 无关联。

[English](README.md) · [官方资料汇总](docs/official-resources.md) · [资料目录](docs/README.md) · [最佳实践](docs/best-practices.md) · [GitHub 项目目录](docs/projects.md) · [X 案例](docs/x-showcases.md) · [参与贡献](CONTRIBUTING.md)

## 常见问题

- **Claude Fable 5.2 是什么？** Anthropic 于 2026 年 11 月 9 日发布的大模型，定位最有野心的开放式技术工作；官方规格为 1M token 上下文、128k 最大输出、始终开启的自适应思考（由 `effort` 参数控制深度）。见[官方发布说明](https://www.anthropic.com/claude-fable-and-mythos-5-2)。
- **它和 Mythos 5.2 什么关系？** 二者是同一底层模型：Fable 5.2 增加网络安全与生物安全防护、对所有用户开放；Mythos 5.2 仅限通过 Anthropic 验证计划的组织使用。
- **如何获取访问？** Fable 5.2 以 `claude-fable-5-2` 向所有 Claude API 客户户开放，也上架 Amazon Bedrock、Google Cloud 与 Microsoft Foundry；定价与数据保留等细节见[官方资料汇总](docs/official-resources.md)。
- **在哪里学提示词？** 先读 [Fable 5.2 官方提示词指南](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2)，再看我们整理的[官方建议摘要与可复用模板](docs/best-practices.md)（effort 校准、提前停止、代码所有权、子代理委派等）。

## 精选入口

- [官方资料汇总](docs/official-resources.md)：Anthropic 官方链接与模型要点（发布、定价、API 变更、安全性），2026-11-11 核查快照
- [资料目录](docs/README.md)：按用途查找官方资料、实践、项目与案例
- [最佳实践与提示词模板](docs/best-practices.md)：目标、约束、验收与复现；新增 Anthropic 官方提示建议摘要（effort 校准、提前停止、审批表述、子代理等），并链接官方资料页
- [GitHub 项目目录](docs/projects.md)：项目用途、来源和星标快照；收录项目已扩充至 48 个（含 X 爆款溯源与可玩 demo 板块），星标为 2026-11-11 GitHub API 快照
- [X 案例](docs/x-showcases.md)：原帖、创作者与提示词来源；扩充至 16 条，主体来自 yihui-dev 视频目录、另 3 条来自网页搜索，排序为收集时判断而非排名
- [用例导航](README.md#use-cases)（英文）：按"想做游戏 / 3D / 视频 / 视觉设计 / 系统原型"查找对应项目
- [参与贡献](CONTRIBUTING.md)：提交链接、修正失效信息

## 精选 GitHub 项目

| 项目                                                                                                    | 用途                             |   星标 |
| ----------------------------------------------------------------------------------------------------- | ------------------------------ | ---: |
| [nativeprompt](https://github.com/edvardgrishin27/nativeprompt)                                       | 离线检查提示词与指令文件是否符合官方模型指南         |  128 |
| [awesome-claude-fable-5-2-use-cases](https://github.com/EvoLinkAI/awesome-claude-fable-5-2-use-cases) | 大量带链接的用例与评测集合                  |   78 |
| [Claude-Fable-5.2-HTML-Files](https://github.com/MiaAI-Lab/Claude-Fable-5.2-HTML-Files)               | HTML 视觉研究，附提示词与截图              |   68 |
| [oh-my-fable](https://github.com/Junhan2/oh-my-fable)                                                 | 将官方提示指南转化为工作规则的 Claude Code 插件 |   61 |
| [saltline-fable-5.2](https://github.com/realcodebear/saltline-fable-5.2)                              | 单 HTML 文件浏览器 FPS（描述为单提示词生成）    |   46 |
| [xray-mirror](https://github.com/MasterOfVFX2070/xray-mirror)                                         | 基于摄像头的交互式 X 光镜像实验              |   36 |

星标为 2026-11-11 GitHub API 快照，仅代表当日计数。[完整项目目录](docs/projects.md)（英文）含分类与收录说明。

## 精选社区案例

- [@kaif9998 动画 showreel](https://x.com/kaif9998/status/2119903824848761287)（[提示词](https://x.com/kaif9998/status/2119904086288118219)）
- [@mattshumer_ 游戏混合创作](https://x.com/mattshumer_/status/2119872098306810226)，附可玩演示
- [@0kncn Blender 动画短片](https://x.com/0kncn/status/2119901782482543073)（[详细提示词](https://x.com/0kncn/status/2119901786060259612)）

案例主体来自第三方目录并经网页搜索补充；原帖互动量与演示效果未独立核验，详见 [X 案例页](docs/x-showcases.md)（英文）。

## 数据说明

资料核查日期：2026-11-11。社区项目的模型使用方式和成果来自作者或二手资料，尚未独立复现；星标数字为当日快照，不代表增长趋势。X 案例的原帖及互动量尚未独立核验。官方规格与定价数字为厂商公布的 2026-11-11 快照，未经独立验证，请以[官方页面](docs/official-resources.md)最新信息为准。
