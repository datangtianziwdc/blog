---
title: 常见报错问题汇总
date: 2020-04-01
tags:
- 错误合集
# categories:
# - 用户 
cover: /covers/vector_landscape_2.svg
thumbnail: /covers/vector_landscape_2.svg
---
记录常用库的报错问题和解决方案
## 目录
<a href="#Vue3-Echart5-legend">Vue3 使用 Echart5 点击 legend 报错</a>
<!-- more -->
<p id='Vue3-Echart5-legend'>Vue3 使用 Echart5 点击 legend 报错<p/>
{% codeblock "报错信息" %}
barPolar.js:63 Uncaught TypeError: Cannot read properties of undefined (reading 'type')
    at barPolar.js:63:38
    at GlobalModel2.<anonymous> (Global.js:682:12)
    at Array.forEach (<anonymous>)
    at each (util.js:205:13)
    at GlobalModel2.eachSeriesByType (Global.js:678:5)
    at Object.barLayoutPolar (barPolar.js:61:11)
    at Object.overallReset (util.js:310:21)
    at Task2.overallTaskReset [as _reset] (Scheduler.js:460:11)
    at Task2._doReset (task.js:202:23)
    at Task2.perform (task.js:117:33)
{% endcodeblock %}
{% codeblock "原有的初始化代码" %}
const init = () => {
  once.value = true;
  // 基于准备好的dom，初始化echarts实例
  // markRaw标记一个对象，使其永远不会再成为响应式对象
  myChart.value =
  // 使用刚指定的配置项和数据显示图表。
  myChart.value!.setOption(echartDataFormatter(setEchartsData()));
};
{% endcodeblock %}
将 Echarts 的实例用`markRaw`包裹起来
{% codeblock "改造后的代码" %}
const init = () => {
  once.value = true;
  // 基于准备好的dom，初始化echarts实例
  // markRaw标记一个对象，使其永远不会再成为响应式对象
  myChart.value =
  markRaw(echarts.init(document.getElementById(props.chartsId)));
  // 使用刚指定的配置项和数据显示图表。
  myChart.value!.setOption(echartDataFormatter(setEchartsData()));
};
{% endcodeblock %}
<hr>