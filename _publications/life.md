---
title: "人生进度条模拟器"
collection: games
permalink: /small-game/life
category: games
date: 2026-04-14
---


<style>
  .calc-container {
    max-width: 700px;
    margin: 30px auto;
    padding: 30px;
    background: #ffffff;
    border-radius: 16px;
    box-shadow: 0 4px 20px rgba(0,0,0,0.08);
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  }

  .calc-container h2 {
    text-align: center;
    margin-top: 0;
    margin-bottom: 20px;
    font-size: 24px;
  }

  .form-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 18px;
  }

  .form-row {
    display: flex;
    flex-direction: column;
    gap: 6px;
  }

  .form-row label {
    font-size: 18px;
  }

  .form-row input {
    padding: 10px;
    border-radius: 8px;
    border: 1px solid #ddd;
    font-size: 16px;
  }

  .calc-btn {
    width: 100%;
    margin-top: 20px;
    padding: 12px;
    background: #4a90e2;
    color: #fff;
    border-radius: 8px;
    border: none;
    font-size: 22px;
    cursor: pointer;
  }

  .calc-btn:hover {
    background: #357abd;
  }

  .progress-bar {
    width: 100%;
    height: 20px;
    background: #eee;
    border-radius: 10px;
    margin: 20px 0;
    overflow: hidden;
  }

  .progress-fill {
    height: 100%;
    width: 0%;
    background: linear-gradient(90deg, #4a90e2, #6fc3ff);
    transition: width 0.6s ease;
  }
</style>

<div class="calc-container">
  <h2>💰 500万资产进度条</h2>

  <div class="form-grid">
    <div class="form-row">
      <label>💴 现金（万）</label>
      <input id="cash" type="number" value="2">
    </div>
    <div class="form-row">
      <label>📈 股票（万）</label>
      <input id="stock" type="number" value="2">
    </div>
    <div class="form-row">
      <label>📊 基金（万）</label>
      <input id="fund" type="number" value="1.2">
    </div>
    <div class="form-row">
      <label>🎯 目标金额（万）</label>
      <input id="target" type="number" value="1000">
    </div>
  </div>

  <button class="calc-btn" id="calcBtn">计算进度</button>

  <div class="progress-bar">
    <div id="progress" class="progress-fill"></div>
  </div>
  
  <div id="percent-num" style="text-align:center; font-size:18px; margin-top:5px;">0.0%</div>

</div>

<script>
function calcAsset() {
  const cash = Number(document.getElementById("cash").value) || 0;
  const stock = Number(document.getElementById("stock").value) || 0;
  const fund = Number(document.getElementById("fund").value) || 0;
  const targetWan = Number(document.getElementById("target").value) || 500;

  const total = cash + stock + fund;
  const target = targetWan;

  const percent = Math.min(100, (total / target) * 100);
  const percentText = percent.toFixed(1);

  document.getElementById("progress").style.width = percentText + "%";

  document.getElementById("percent-num").innerText = percentText + "%";

}

document.getElementById("calcBtn").addEventListener("click", calcAsset);
calcAsset();
</script>
