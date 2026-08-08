# huan-dev

`huan-dev` 是一组面向 Codex 的仓库开发 Skills。它既提供从需求校准到证据化交付的完整工作流，也保留各阶段和通用能力的独立入口。

## Skills

| Skill | 用途 | 调用方式 |
|---|---|---|
| `$huan-dev` | 完整执行需求校准、实现、验证、压力测试、返工与交付 | 仅显式指定 |
| `$requirement-calibration` | 基于仓库事实收敛需求边界和用户决策 | 仅显式指定 |
| `$pressure-review` | 独立压力测试改动并闭环有效发现 | 仅显式指定 |
| `$delivery-brief` | 生成信息密度适当、可直接验收的交付简报 | 仅显式指定 |
| `$execute-from-goal` | 从自然语言目标完成仓库任务 | 保持原 Skill 配置 |
| `$prompt-entropy` | 编写或压缩 Agent 委派提示词 | 保持原 Skill 配置 |

完整工作流按任务风险选择分支：只有影响结果、范围、职责、验收或权限的未决事项才进入需求校准；只有非简单改动才执行独立压力测试；只有复杂交付或存在验收影响时才额外加载 `delivery-brief`。

## 目录

```text
huan-dev/
├── README.md
├── LICENSE
└── skills/
    ├── huan-dev/
    ├── requirement-calibration/
    ├── pressure-review/
    ├── delivery-brief/
    ├── execute-from-goal/
    └── prompt-entropy/
```

每个目录都是可独立发现和显示的 Skill，包含自己的 `SKILL.md` 与 `agents/openai.yaml`。

## 安装

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
```

## 许可

[MIT](LICENSE)
