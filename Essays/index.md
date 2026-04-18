---
layout: archive
title: "Essays"   # 页面标题
permalink: /essays/  # 网址路径（最重要之一）：https://你的用户名.github.io/experimence/
---

<style>
.essay-calendar {
  max-width: 420px;
  margin: 2rem 0;
  padding: 1rem;
  border: 1px solid #eee;
  border-radius: 12px;
  background: #fdfdfd;
  font-family: system-ui, sans-serif;
}

.cal-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 8px;
}

.cal-month {
  font-size: 1.2rem;
  font-weight: bold;
}

.cal-btn {
  cursor: pointer;
  padding: 2px 8px;
  border-radius: 6px;
  background: #eee;
}

.cal-grid {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
  gap: 6px;
  text-align: center;
}

.cal-week {
  font-size: 0.75rem;
  color: #666;
}

.cal-day {
  padding: 6px 0;
  border-radius: 6px;
  cursor: pointer;
}

.cal-day.has-essay {
  background: #4a83ef;
  color: white;
  font-weight: bold;
}

.cal-day.today {
  border: 1px solid #4a83ef;
}

.cal-day.empty {
  color: #ccc;
  cursor: default;
}
</style>

<div class="essay-calendar">
  <div class="cal-header">
    <div class="cal-btn" id="prev">◀</div>
    <div class="cal-month" id="cal-month">加载中...</div>
    <div class="cal-btn" id="next">▶</div>
  </div>

  <div class="cal-grid" id="cal-grid">
    <div class="cal-week">日</div>
    <div class="cal-week">一</div>
    <div class="cal-week">二</div>
    <div class="cal-week">三</div>
    <div class="cal-week">四</div>
    <div class="cal-week">五</div>
    <div class="cal-week">六</div>
  </div>
</div>

<script>
document.addEventListener("DOMContentLoaded", function () {

  // ✅ 1. 收集所有日期
  const dates = [];
  document.querySelectorAll('*').forEach(el => {
    const t = el.textContent.trim();
    if (/^\d{4}-\d{2}-\d{2}$/.test(t)) {
      dates.push(t);
      el.id = t;
    }
  });

  // ✅ 2. 当前月份
  let current = new Date();

  function renderCalendar(dateObj) {
    const Y = dateObj.getFullYear();
    const M = dateObj.getMonth();

    const monthText = `${Y}年${M+1}月`;
    document.getElementById('cal-month').innerText = monthText;

    const grid = document.getElementById('cal-grid');

    // 清空旧数据（保留星期）
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

    // 补空白
    for (let i = 0; i < firstDay; i++) {
      const d = document.createElement('div');
      d.className = 'cal-day empty';
      grid.appendChild(d);
    }

    const today = new Date();

    for (let day = 1; day <= days; day++) {
      const dateStr = `${Y}-${String(M+1).padStart(2,'0')}-${String(day).padStart(2,'0')}`;

      const d = document.createElement('div');
      d.className = 'cal-day';
      d.innerText = day;

      // 有文章
      if (dates.includes(dateStr)) {
        d.classList.add('has-essay');
        d.onclick = () => {
          document.getElementById(dateStr)
            ?.scrollIntoView({ behavior: 'smooth' });
        };
      } else {
        d.classList.add('empty');
      }

      // 今天高亮
      if (
        day === today.getDate() &&
        M === today.getMonth() &&
        Y === today.getFullYear()
      ) {
        d.classList.add('today');
      }

      grid.appendChild(d);
    }
  }

  // 初始渲染
  renderCalendar(current);

  // 上一个月
  document.getElementById('prev').onclick = () => {
    current.setMonth(current.getMonth() - 1);
    renderCalendar(current);
  };

  // 下一个月
  document.getElementById('next').onclick = () => {
    current.setMonth(current.getMonth() + 1);
    renderCalendar(current);
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
