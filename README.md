# Huan Dev

一组把仓库改动从目标带到可验收结果的 Agent Skills。

仓库开发的问题通常不只是写代码：需求可能尚未收敛，事实和用户决策容易混在一起，非简单改动可能缺少独立审查，最终交付也未必足以判断是否可以接受。Huan Dev 将这些环节组织成一条按风险展开、又可以拆分使用的工作流。

## 工作流

```text
huan-dev — 编排完整仓库工作流（显式调用）
       ↓
仓库调查 — 定位行为、职责、规则和验证入口（始终执行）
       ↓
requirement-calibration — 收敛需求与边界（存在关键用户决策时触发）
       ↓
estimate-task-time — 估算任务所需小时数（询问耗时、预算或剩余时间时触发）
       ↓
execute-from-goal — 实现并完成验证（始终触发）
       ↓
pressure-review — 独立压力测试并闭环问题（非简单改动时触发）
       └─ prompt-entropy — 编写派发给子线程的 Reviewer 提示词（派发子线程或编写提示词时触发）
       ↓
delivery-brief — 整理可验收的交付说明（经过压力测试或存在验收影响时触发）
```

显式调用 `huan-dev` 会进入完整的编排判断，但不代表每个子 Skill 都必然运行。目标清晰、局部且低风险的改动可以跳过不必要的校准、压力测试或完整交付简报。

进入[压力测试](skills/pressure-review/SKILL.md)后，默认直接并行派出两位使用新上下文的独立只读子线程，不再确认评审人数；用户明确指定的人数或执行限制优先。至少一位不设侧重点，自行从多个角度检查整个改动；其他评审可以侧重风险，但每位都对整体正确性负责。发现须有证据和实际影响，允许检查重叠，也允许没有发现。

用户询问任务耗时、时间预算或剩余时间时，工作流在明确当前范围后调用 `estimate-task-time`。它先判断实际修改与验收工作，再用最多一分钟查询 Artificial Analysis 的同模型实际 Agent 运行时间，根据任务规模给出大致小时数和范围。找不到可用数据时明确给暂估；外部等待单列，混合 benchmark 的均值只作为数量级参照。

主要数字估正常执行路径；额外风险放进范围或条件说明。按可成批完成的修改和串行反馈判断工作量，必要验证照常保留；小时级估算须解释时间具体花在哪里。用户指定开发模型时按指定模型估算，否则默认当前会话模型及执行设置，不额外要求选择模型。若无法识别目标模型的具体变体，仍以该目标给暂估，明确 AA 未匹配，不猜测型号。

## 选择 Skill

| Skill | 什么时候用 | 触发方式 |
| --- | --- | --- |
| `huan-dev` | 希望一次完成需求校准、实现、验证、压力测试和验收交付 | 仅显式调用 |
| `requirement-calibration` | 仍有会改变结果、范围、职责、验收或权限的用户决策 | 仅显式调用 |
| `execute-from-goal` | 目标已经明确，需要直接完成非简单仓库任务 | 自动匹配或显式调用 |
| `pressure-review` | 改动已经实现，需要独立寻找可能阻止验收的问题 | 仅显式调用 |
| `delivery-brief` | 需要把实际范围、验证证据和剩余缺口整理成验收说明 | 仅显式调用 |
| `prompt-entropy` | 需要编写、审查或压缩 Prompt 与 Skill 指令 | 自动匹配或显式调用 |
| `estimate-task-time` | 需要估算开发任务、时间预算或剩余工作所需的小时数 | 自动匹配或显式调用 |

## 使用示例

执行完整工作流：

```text
$huan-dev

完成这次仓库改动：<目标、边界和验收要求>。
```

也可以只调用需要的阶段：

```text
$requirement-calibration 校准这次改动的需求和边界。
$pressure-review 对当前改动执行独立压力测试。
$delivery-brief 把当前结果整理成可验收的交付简报。
$estimate-task-time 估算完成这次改动大概需要多少小时，包含必要验证。
$prompt-entropy 在不改变意图的前提下压缩这个 Prompt。
```

## 安装

仓库采用标准 skills-only Plugin 结构，可以在 [skills.sh 集合页](https://skills.sh/huanhuanhuanfff/huan-dev) 查看全部七个 Skill。

Skills CLI：

```powershell
npx --yes skills add HuanHuanHuanFFF/huan-dev --skill '*' --agent codex --global --yes
```

让 Agent 安装：

```text
请安装 https://github.com/HuanHuanHuanFFF/huan-dev 仓库中的全部 Skills。
```

如需独立安装，可以要求 Agent 只安装 `skills/` 下的指定 Skill。安装或更新后，请重新启动 Codex 或新建任务，使 Skills 被重新发现。

## 仓库结构

```text
huan-dev/
├── .codex-plugin/plugin.json
├── README.md
├── LICENSE
├── PRIVACY.md
├── TERMS.md
└── skills/
    ├── huan-dev/
    ├── requirement-calibration/
    ├── execute-from-goal/
    ├── pressure-review/
    ├── delivery-brief/
    ├── prompt-entropy/
    └── estimate-task-time/
```

每个 Skill 子目录都包含独立的 `SKILL.md` 和 `agents/openai.yaml`。前者定义执行规则，后者定义界面信息和触发策略。

## 致谢

`requirement-calibration` 的早期需求澄清设计受到 [Matt Pocock 的 grilling Skill](https://github.com/mattpocock/skills/tree/main/skills/productivity/grilling) 和 “Grill Me” 工作方式启发，随后针对仓库事实调查、用户决策边界、依赖关系和验收要求进行了改造。

估时方法参考 [agent-estimation](https://github.com/ZhangHanDong/agent-estimation) 的执行轮次思路、[groundwork](https://github.com/YasMax91/groundwork) 的实际耗时与人工等待边界，以及 [agent-time](https://github.com/ConnorBritain/agent-time) 的过程重估机制；具体时间以当前任务和近期 AA 观测为依据，不继承这些项目的固定速度参数。

## 许可

[MIT](LICENSE) © 2026 HuanHuanHuanFFF
