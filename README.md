# Autonomous Engineering Skills

面向实际交付的通用 Codex 工程执行 Skill 集合。

## autonomous-execution-closure

[Skill 入口](autonomous-execution-closure/SKILL.md) 要求代理在授权范围内持续执行、基于证据自修复、验证完整流程，并以最终验收决定完成状态。

设计依据：优秀的自主执行应像一次连续承担的工程任务，遇到问题就诊断、修复、实跑、验证并恢复主线，无需用户反复催促。“持续开发到凌晨”的可复用价值是执行连续性，不是要求固定工作时长或无限重试。

低效模式包括：只定位不修复、只改显示不改实际行为、丢失已确认约定、停在局部通过、每个阶段等待用户接力。此 Skill 将这些模式转化为可检查的执行与验收规则；不包含任何特定项目参数、聊天记录或业务实现。

## 文件

```text
autonomous-execution-closure/
├── SKILL.md
└── references/
    ├── execution-loop.md
    ├── debugging-protocol.md
    ├── verification-checklist.md
    └── completion-criteria.md
```

## 安装与调用

将整个 `autonomous-execution-closure` 文件夹复制到 Codex 的用户 Skill 目录：`$CODEX_HOME/skills/`；未设置 `CODEX_HOME` 时通常为 `~/.codex/skills/`。目录名应保持不变，引用文件需一起复制。

在能够发现该 Skill 的新会话中调用：

```text
$autonomous-execution-closure 完成这个任务，遇到问题自行诊断修复，直到最终验收通过；遵守现有授权与项目约束。
```

也可在当前会话直接提供 `SKILL.md` 的绝对路径并要求按其执行。默认允许正常自动选择；用户明确要求只分析、先确认、暂停或取消时，该要求优先。

Skill 不赋予额外权限，不绕过项目规范，也不保证所有任务必然成功。真实阻塞必须有证据，未完成结果不得伪装成通过。
