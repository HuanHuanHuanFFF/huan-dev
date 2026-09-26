# huan-dev

`huan-dev` 是一组面向 Codex 的仓库开发 Skills。它既提供从需求校准到证据化交付的完整工作流，也保留各阶段和通用能力的独立入口。

[GitHub Release](https://github.com/HuanHuanHuanFFF/huan-dev/releases/latest) · [skills.sh](https://skills.sh/huanhuanhuanfff/huan-dev/huan-dev) · [OpenAI 插件提交材料](docs/openai-plugin-submission.md)

## Skills

| Skill | 用途 | 调用方式 |
|---|---|---|
| `$huan-dev` | 完整执行需求校准、实现、验证、压力测试、返工与交付 | 仅显式指定 |
| `$requirement-calibration` | 基于仓库事实收敛需求边界和用户决策 | 仅显式指定 |
| `$pressure-review` | 独立压力测试改动并闭环有效发现 | 仅显式指定 |
| `$delivery-brief` | 生成信息密度适当、可直接验收的交付简报 | 仅显式指定 |
| `$execute-from-goal` | 从自然语言目标完成仓库任务 | 自动匹配 |
| `$prompt-entropy` | 编写、审查或压缩通用 Prompt 与 Skill 指令 | 自动匹配 |
| `$estimate-task-time` | 根据任务范围和 AA 同模型实际耗时，快速估算所需小时数 | 自动匹配 |

完整工作流按任务风险选择分支：只有影响结果、范围、职责、验收或权限的未决事项才进入需求校准；只有非简单改动才执行独立压力测试；只有复杂交付或存在验收影响时才额外加载 `delivery-brief`。

用户询问任务耗时、时间预算或剩余时间时，工作流在明确当前范围后调用 `estimate-task-time`。它先判断实际修改与验收工作，再用最多一分钟查询 Artificial Analysis 的同模型实际 Agent 运行时间，根据任务规模给出大致小时数和范围。找不到可用数据时明确给暂估；外部等待单列，混合 benchmark 的均值只作为数量级参照。

主要数字估正常执行路径；额外风险放进范围或条件说明。按可成批完成的修改和串行反馈判断工作量，必要验证照常保留；小时级估算须解释时间具体花在哪里。用户指定开发模型时按指定模型估算，否则默认当前会话模型及执行设置，不额外要求选择模型。若无法识别具体变体，仍以当前模型为目标给暂估，明确 AA 未匹配，不猜测型号。

## 目录

```text
huan-dev/
├── .codex-plugin/plugin.json
├── README.md
├── LICENSE
├── PRIVACY.md
├── TERMS.md
├── docs/
└── skills/
    ├── huan-dev/
    ├── requirement-calibration/
    ├── pressure-review/
    ├── delivery-brief/
    ├── execute-from-goal/
    ├── prompt-entropy/
    └── estimate-task-time/
```

每个目录都是可独立发现和显示的 Skill，包含自己的 `SKILL.md` 与 `agents/openai.yaml`。

## 安装

一键将本仓库中的全部 Skills 全局安装到 Codex，无需交互选择：

```powershell
npx --yes skills add HuanHuanHuanFFF/huan-dev --skill '*' --agent codex --global --yes
```

如需选择具体 Skill、安装范围或目标 Agent，可使用交互式安装：

```powershell
npx skills add HuanHuanHuanFFF/huan-dev
```

也可以通过 GitHub Agent Skills 安装：

```powershell
gh skill install HuanHuanHuanFFF/huan-dev
```

也可以手动安装：

```powershell
git clone https://github.com/HuanHuanHuanFFF/huan-dev.git
Set-Location .\huan-dev

$target = if ($env:CODEX_HOME) {
    Join-Path $env:CODEX_HOME "skills"
} else {
    Join-Path $env:USERPROFILE ".codex\skills"
}

New-Item -ItemType Directory -Force -Path $target | Out-Null
Copy-Item -Recurse -Force ".\skills\*" $target
```

复制会更新目标目录中同名 Skill。安装后重新启动 Codex，使整组 Skills 被重新发现。

仓库同时包含 OpenAI skills-only 插件清单；进入公共 Plugins Directory 仍需完成 OpenAI Platform 审核。

## 使用

完整工作流：

```text
$huan-dev

完成这次仓库改动：<目标、边界和验收要求>。
```

也可以显式选择某个阶段：

```text
$requirement-calibration 校准这次改动的需求和边界。
$pressure-review 对当前改动执行独立压力测试。
$delivery-brief 把当前结果整理成可验收的交付简报。
$estimate-task-time 估算完成这次改动大概需要多少小时，包含必要验证。
```

估时方法参考 [agent-estimation](https://github.com/ZhangHanDong/agent-estimation) 的执行轮次思路、[groundwork](https://github.com/YasMax91/groundwork) 的实际耗时与人工等待边界，以及 [agent-time](https://github.com/ConnorBritain/agent-time) 的过程重估机制；具体时间以当前任务和近期 AA 观测为依据，不继承这些项目的固定速度参数。

## 许可

[MIT](LICENSE)
