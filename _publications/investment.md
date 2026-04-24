---
title: "定投年化率"
collection: games
permalink: /small-game/investment
category: games
date: 2026-04-24
---

## 输入参数
- 初始本金（元）
- 每月投入金额（元）
- 预期年化收益率（%）
- 投资时长（月）

---

## 计算公式
月收益率 = 年化收益率 / 12

最终本息 =
初始本金 × (1 + 月收益率)^n  
+ 每月投入 × [ ((1 + 月收益率)^n - 1) / 月收益率 ]

---

## 使用示例（已修正）
本金：10000 元  
每月定投：2000 元  
年化收益率：6%  
投资时长：36 个月  

月收益率 = 6% / 12 = 0.5%

👉 最终本息 ≈ **88,247 元**

---

## 🧮 快速计算（可交互）

<div style="max-width:500px;margin:auto;padding:20px;border:1px solid #eee;border-radius:12px;box-shadow:0 4px 12px rgba(0,0,0,0.05);font-family:sans-serif;">

<p>本金（元）</p>
<input id="principal" type="number" value="10000">

<p>每月投入（元）</p>
<input id="monthly" type="number" value="2000">

<p>年化收益率（%）</p>
<input id="rate" type="number" value="6">

<p>投资时长（月）</p>
<input id="months" type="number" value="36">

<br><br>
<button onclick="calc()">计算</button>

<h3 id="result">结果：--</h3>

</div>

<script>
function calc() {
  let P = Number(document.getElementById('principal').value);
  let PMT = Number(document.getElementById('monthly').value);
  let r = Number(document.getElementById('rate').value) / 100 / 12;
  let n = Number(document.getElementById('months').value);

  let FV = P * Math.pow(1 + r, n)
          + PMT * (Math.pow(1 + r, n) - 1) / r;

  document.getElementById('result').innerText =
    "最终本息：" + FV.toFixed(2) + " 元";
}
</script>
