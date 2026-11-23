# 正式周报：固定格式 v1

每期一份 UTF-8 JSON：`weekly/YYYY-MM-DD.json`。文件名和 `issue_id` 均为北京时间原定发布的周一，补发不改期号。实际收录范围是 `period_start`（前一周周一）到 `period_end`（前一周周日），首尾都含当天。

| 层级 | 固定字段 |
| --- | --- |
| 周报 | `schema_version`（整数 1）、`issue_id`、`title`、`timezone`（Asia/Shanghai）、`period_start`、`period_end`、`sections` |
| 栏目 | `id`、`title`、`items` |
| 主条目 | `title`、`summary`、`sources`、`subitems` |
| 子项 | `title`、`summary`、`sources` |
| 来源 | `label`、`url`（公开 HTTPS 原文） |

栏目总是按以下顺序：`ai-frontier`（AI 前沿）、`smart-hardware`（智能硬件）、`smart-home`（智能家居）、`ai-open-source`（AI 开源热点项目）。

无条目或子项时用空数组，不省略字段。主题组没有总摘要时用空字符串；如果来源都挂在子项上，组的 `sources` 用空数组。每个事实条目至少有一个来源。渲染正文时按栏目顺序连续编号，只计主条目。

首期：[2026-11-16 至 2026-11-22](2026-11-23.json)。编辑规则见 [定时任务提示词](../prompts/weekly-digest.md)。
