# 核心文件地图（File Map）

> 基于 verl **v0.8.0**。目标：按「我想做什么」定位该改的文件，而不是通读整个仓库。

**状态**：WIP

## 三层心智模型

| 层级 | 含义 | 本笔记重点 |
|------|------|------------|
| L1 | 你要改的：Agent / Reward / Data / Config | ✅ |
| L2 | 你要懂但不常改：AgentLoop 调度、mask / TITO 等 | 适度 |
| L3 | 默认忽略：FSDP / Megatron / 调度与性能 | ❌ |

## 任务 → 文件

| 我想… | 去改 / 阅读 | 路径（v0.8.0） | 默认别碰 |
|-------|-------------|----------------|----------|
| 自定义 Agent 逻辑 | <!-- TODO: 如 AgentLoopBase.run --> | <!-- TODO --> | infra / sharding |
| 只用内置 Tool Agent | <!-- TODO --> | <!-- TODO --> | |
| 自定义 Reward | <!-- TODO --> | <!-- TODO --> | |
| 改训练超参 / 算法开关 | Hydra config | <!-- TODO: 常用 key 列表链到专文 --> | |
| 换数据或 prompt 格式 | <!-- TODO --> | <!-- TODO --> | |

## 一张图（可选）

<!-- TODO: 之后可放 assets/ 下的架构简图 -->

```text
Dataset → AgentLoop (rollout) → Reward → Advantage / Update
                ↑
         LLMServer / tools
```

## 相关文档

- [环境准备与常见坑](00-setup-pitfalls.md)
- <!-- TODO: AgentLoop 专文、Reward 专文、Config 最小集 -->
