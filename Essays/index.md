---
layout: archive
title: "Essays1"   # 页面标题
permalink: /essays/  # 网址路径（最重要之一）：https://你的用户名.github.io/experimence/
---

<script>
window.addEventListener("load", function () {

  const container = document.getElementById("essays-content");
  if (!container) return;

  const dates = [];

  // ✅ 只找标题（适配 h2/h3）
  container.querySelectorAll("h2, h3").forEach(el => {
    const t = el.textContent.trim();

    if (/^\d{4}-\d{2}-\d{2}$/.test(t)) {
      dates.push(t);
      el.id = t; // 用于跳转
    }
  });

  // ====== 日历生成（不变） ======
  let current = new Date();

  function render(dateObj) {
    const Y = dateObj.getFullYear();
    const M = dateObj.getMonth();

    document.getElementById('cal-month').innerText = `${Y}年${M+1}月`;

    const grid = document.getElementById('cal-grid');

    grid.innerHTML = `
      <div class="cal-week">日</div>
      <div class="cal-week">一</div>
      <div class="cal-week">二</div>
      <div class="cal-week">三</div>
      <div class="cal-week">四</div>
      <div class="cal-week">五</div>
      <div class="cal-week">六</div>
    `;

    const firstDay = new Date(Y, M, 1).getDay();
    const days = new Date(Y, M+1, 0).getDate();

    for (let i = 0; i < firstDay; i++) {
      const d = document.createElement('div');
      d.className = 'cal-day empty';
      grid.appendChild(d);
    }

    for (let day = 1; day <= days; day++) {
      const dateStr = `${Y}-${String(M+1).padStart(2,'0')}-${String(day).padStart(2,'0')}`;

      const d = document.createElement('div');
      d.className = 'cal-day';
      d.innerText = day;

      if (dates.includes(dateStr)) {
        d.classList.add('has-essay');
        d.onclick = () => {
          document.getElementById(dateStr)?.scrollIntoView({ behavior: 'smooth' });
        };
      } else {
        d.classList.add('empty');
      }

      grid.appendChild(d);
    }
  }

  render(current);

  document.getElementById('prev').onclick = () => {
    current.setMonth(current.getMonth() - 1);
    render(current);
  };

  document.getElementById('next').onclick = () => {
    current.setMonth(current.getMonth() + 1);
    render(current);
  };

});
</script>


## 2026-04-18
> 做正确的事，把其他的交给时间，允许慢一点再慢一点。
> —— [知乎用户](https://www.zhihu.com/question/2011481610210546261/answer/2027165282880243397)

## 2026-04-17
纳斯达克好像要12连涨💹了，坚持就是胜利，拿住！！！😁。

## 2026-04-15
今天纳斯达克和标普都是10连涨💹，然而还是存在负收益。但是我已经看到了曙光☀️！。

感悟一：说话之前一定不能被当前的情绪左右，特别是情绪不好的时候，说话一定要三思！！！，切记。

## 2026-04-14
今天用AI写了一下Small Games里边的 “这班上的值不值” 游戏，发现GPT、豆包和Genemi目前都不太适合太长代码的生成，总是无法实现我想要的功能，最后只能一步一步完成。也有可能是我使用方式用问题🤔。
