# Issue

**Title:** 新增 V2 本地 Web UI：流式输出、Lab Trace、多主题

## Description

## 概述

  为 `local-web` channel 新增一套 V2 UI，与原版完全并存：
  - `/` 默认指向 V2 UI
  - `/v1` 保留原版 UI（页面 / 数据完全不变）
  - `/v2` 作为别名指向 V2

  数据库、会话、群组配置、其他 channel（WhatsApp / 微信 / 飞书等）均不受影响。

  ## 主要功能

  - **流式输出**：回答一字一字渲染；思考过程进 Lab Trace 抽屉，最终答复进聊天框
  - **Lab Trace 抽屉**：实时查看 agent 的 thinking / tool_use 步骤，Compact / Full 两种选项
  - **自然语言步骤摘要**：30+ 生物工具、35+ 数据库、25+ 文件类型的规则映射，便于用户理解
  - **多线程对话**：左侧 Thread 列表可同时管理多个对话
  - **文件预览**：聊天气泡里的文件链接点开后在右边栏预览
  - **可拖拽列宽**：thread rail / chat / trace 三栏宽度可调
  - **9 套主题 + 暗色模式**
  - **中英文自动检测 + 切换**

  ## 改动文件

  | 类型 | 文件 | 说明 |
  |------|------|------|
  | 新增 | `src/channels/local-web/assets/v2/{index.html,app.js,style.css}` | V2 前端
  (~5500 行) |
  | 新增 | `UPGRADE-V2-UI.md` | V2-UI说明文档 |
  | 新增 | `container/Dockerfile.viz` | 多阶段构建：从 `python:3.11-slim-bookworm` 引入
  Python + SSL libs |
  | 修改 | `src/channels/local-web/channel.ts` | 路由：`/` 和 `/v2` → V2，`/v1` → 原版 |
  | 修改 | `container/agent-runner/src/index.ts` | OpenAI 兼容接口 SSE 流式；tool_call
  JSON 校验；ECONNRESET 4 次指数退避重试 |
  | 修改 | `src/index.ts` | streaming chunks 不推送到聊天 |
  | 修改 | `src/container-runner.ts` | `ContainerOutput.status` 加 `'streaming'` 类型 |

  ## 不影响的部分

  - 原版 UI 仅路由从 `/` 换成 `/v1`，页面、数据、行为完全不变
  - 所有聊天记录、会话、群组配置完全兼容
  - WhatsApp / 微信 / 飞书等其他 channel 行为不变
  - `.env` 不会被覆盖

  ## 升级 / 回退

  详细步骤见 `UPGRADE-V2-UI.md`，简要：

  ```bash
  git pull
  ./container/build.sh        # 1-2 分钟（缓存复用）
  npm run stop:web && npm run web
  ```

  回退：`git reset --hard <旧 commit>` + 重建容器，不影响数据存储。

  ## 测试

  - [x] V2 UI：建线程 / 发消息 / 流式回答 / 切换主题 / 中英语言切换 / Compact-Full trace / 文件预览
  - [x] V1 UI：访问 `/v1` 仍为原版页面，对话历史完整可见
  - [x] 路由：`/`、`/v1`、`/v2` 均 200
  - [x] 容器：DashScope SSE 流式输出正常

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `e4aa1e06f27d`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.