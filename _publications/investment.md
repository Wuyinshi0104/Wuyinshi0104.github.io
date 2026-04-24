---
title: "定投年化率"
collection: games
permalink: /small-game/investment
category: games
date: 2026-04-24
---

# 定投收益计算器

## 输入参数
- 初始本金（元）：`principal`
- 每月投入金额（元）：`monthly_invest`
- 预期年化收益率（%）：`annual_rate`
- 投资时长（月）：`months`

## 计算公式
月收益率 = 年化收益率 / 12

最终本息 =
初始本金 × (1 + 月收益率)^months
+ 每月投入 × [ ((1 + 月收益率)^months - 1) / 月收益率 ]

## 使用示例
本金：10000 元
每月定投：2000 元
年化收益率：6%
投资时长：36 个月

月收益率 = 6% / 12 = 0.5%

最终本息 ≈ 91,368 元

## 快速计算（直接替换数字）
本金：`{{ principal }}`
每月投入：`{{ monthly_invest }}`
年化率：`{{ annual_rate }}%`
时长：`{{ months }}` 个月

月收益率 = `{{ annual_rate / 12 }}%`

到期总资产 =
`principal * (1 + monthly_rate) ^ months`
+ `monthly_invest * (((1 + monthly_rate) ^ months - 1) / monthly_rate)`
