---
layout: archive
title: "Essays"   # 页面标题
permalink: /essays/  # 网址路径（最重要之一）：https://你的用户名.github.io/experimence/
---
<style>
/* 小日历样式 */
.essay-calendar {
  max-width: 380px;
  margin: 2rem 0;
  padding: 1rem;
  border: 1px solid #eee;
  border-radius: 12px;
  background: #fdfdfd;
  font-family: system-ui, sans-serif;
}
.cal-month {
  text-align: center;
  font-size: 1.2rem;
  font-weight: bold;
  margin-bottom: 0.8rem;
  color: #222;
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
  font-weight: 500;
}
.cal-day {
  padding: 6px 0;
  font-size: 0.9rem;
  border-radius: 6px;
  cursor: pointer;
}
.cal-day.has-essay {
  background: #4a83ef;
  color: white;
  font-weight: bold;
}
.cal-day.empty {
  color: #ccc;
}
</style>

<div class="essay-calendar">
  <div class="cal-month" id="cal-month">加载中...</div>
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
document.addEventListener('DOMContentLoaded', function () {
  // 1. 自动抓取所有随笔日期（你写的 ## 2026-xx-xx）
  const essayDates = [];
  document.querySelectorAll('h2').forEach(el => {
    const text = el.textContent.trim();
    if (/^\d{4}-\d{2}-\d{2}$/.test(text)) {
      essayDates.push(text);
      el.id = text;
    }
  });

  // 2. 自动获取【当前系统年月】→ 到5月自动显示5月，到6月自动显示6月
  const now = new Date();
  const year = now.getFullYear();
  const month = now.getMonth() + 1; // 0=1月，所以+1

  // 3. 自动生成当月日历
  const firstDay = new Date(year, month - 1, 1).getDay();
  const daysInMonth = new Date(year, month, 0).getDate();
  const grid = document.getElementById('cal-grid');
  const monthLabel = document.getElementById('cal-month');
  monthLabel.textContent = `${year} 年 ${month.toString().padStart(2, '0')} 月`;

  // 填充前面空白
  for (let i = 0; i < firstDay; i++) {
    const empty = document.createElement('div');
    empty.className = 'cal-day empty';
    grid.appendChild(empty);
  }

  // 填充日期 + 自动高亮有随笔的日子
  for (let day = 1; day <= daysInMonth; day++) {
    const dateStr = `${year}-${month.toString().padStart(2, '0')}-${day.toString().padStart(2, '0')}`;
    const div = document.createElement('div');
    div.className = 'cal-day';
    div.textContent = day;

    if (essayDates.includes(dateStr)) {
      div.classList.add('has-essay');
      div.onclick = () => {
        document.getElementById(dateStr).scrollIntoView({ behavior: 'smooth' });
      };
    } else {
      div.classList.add('empty');
    }
    grid.appendChild(div);
  }
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
