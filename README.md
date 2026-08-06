# huan-dev

`huan-dev` 是一个轻量的 Codex 开发工作流 Skill。它把一次有边界的仓库改动从需求校准带到实现、验证、独立压力 Review、自动返工与证据化交付，同时尽量避免为简单任务引入沉重流程。

## 工作方式

- 先调查仓库事实、已有实现及职责归属，再决定是否需要追问。
- 只有会改变结果、范围、所有权、验收或权限的未决事项才进入需求确认。
- 对非简单改动，在初次实现和验证后安排至少一个独立 Reviewer。
- 对已确认需求范围内的有效问题自动返工、复验，并重新 Review 受影响部分。
- 新需求、架构选择、权限扩张或与用户决定冲突的事项仍交给用户决定。
- 真实环境无法由 Agent 完成时，明确保留证据缺口和人工签收项。

## 目录

```text
huan-dev/
├── README.md
├── LICENSE
└── skills/
    └── huan-dev/
        ├── SKILL.md
        ├── agents/
        │   └── openai.yaml
        └── references/
            ├── grilling.md
            └── review.md
```

## 安装

克隆仓库，然后把纯 Skill 目录复制到 Codex Skills 目录：

```powershell
git clone https://github.com/HuanHuanHuanFFF/huan-dev.git
$target = "$env:USERPROFILE\.codex\skills\huan-dev"
New-Item -ItemType Directory -Force -Path $target | Out-Null
Copy-Item -Recurse -Force ".\huan-dev\skills\huan-dev\*" $target
```

如果使用自定义的 `CODEX_HOME`：

```powershell
$target = "$env:CODEX_HOME\skills\huan-dev"
New-Item -ItemType Directory -Force -Path $target | Out-Null
Copy-Item -Recurse -Force ".\huan-dev\skills\huan-dev\*" $target
```

安装后重新启动 Codex，使 Skill 被重新发现。

## 使用

```text
$huan-dev

完成这次仓库改动：<描述目标、范围和不希望进入的后续工作>。
```

任务较重时，`huan-dev` 会主动确认是否增加多个独立 Reviewer 进行交叉验证。清晰、局部且低风险的改动可以直接执行，不强制额外问答。

## 许可

[MIT](LICENSE)
