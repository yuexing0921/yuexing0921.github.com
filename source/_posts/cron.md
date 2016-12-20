layout: nodejs
title: nodejs中的定时调度模块cron
date: 2016-12-20 17:31:18
tags: 
- nodejs
---
#### 1.介绍

开发过程当中，经常会有定时任务执行，随便一搜，就一堆，下面介绍的是用的最多的[cron](https://github.com/kelektiv/node-cron)模块，这个模块最早fork于
[ padolsey/cron.js](https://github.com/padolsey/cron.js)，语法完全和linux下的cron命令一样。

#### 2.简单应用 

```javascript
var jobFun = function(){
    console.log(new Date());
}
var Job = require("cron").CronJob;  
//每秒钟执行一次  
new Job('* * * * * *', jobFun , null, true, 'Asia/Shanghai'); 

//每隔30秒执行一次，会在0秒和30秒处执行  
new Job('*/30 * * * * *',jobFun , null, true, 'Asia/Shanghai');  

//在每天的00:00:00和02:00:00期间  每半小时执行一次 
new Job('* */30 0-2 * * *', jobFun , null, true, 'Asia/Shanghai');  

//在每天的00:30:00和12:30:00 各执行一次  
new Job('* 30 0,12 * * *', jobFun , null, true, 'Asia/Shanghai');  

// 每周一和周五的11:30:00 执行job
var job = new CronJob({
  cronTime: '00 30 11 * * 1-5',
  onTick: jobFun,
  start: false,
  timeZone: 'Asia/Shanghai'
});
job.start();
```


#### 3.API语法 （翻译很渣，看不懂可以看[原文](https://github.com/kelektiv/node-cron/blob/master/README.md)）
  * `constructor(cronTime, onTick, onComplete, start, timezone, context, runOnInit)` - 可以用json格式传参,也可以不用，具体参加例子.
    * `cronTime` - [必需] - 时间格式 (second minute hour dayOfMonth month dayOfWeek).
    * `onTick` - [必需] - 执行的function.
    * `onComplete` - [可选] - 当onTick执行完成后，执行的函数.
    * `start` - [可选] - 是否立即执行onTick函数，默认是false
    * `timeZone` - [可选] - 指定时区
    * `context` - [可选] - 可以指定上下文，感觉没有啥作用？？
    * `runOnInit` - [可选] - 不清楚？？
  * `start` - Runs your job.
  * `stop` - Stops your job.