---
description: Carbon 是 DateTime 的简单 PHP API 扩展
---

# Carbon

{% embed url="https://carbon.nesbot.com/" %}
官网直达
{% endembed %}

```php
Carbon::now();                            //2022-08-05 10:05:42
Carbon::today();                          //2022-08-05 00:00:00
Carbon::tomorrow();                       //2022-08-06 00:00:00
Carbon::yesterday();                      //2022-08-04 00:00:00
Carbon::now()->toDateString();            //2022-08-05
Carbon::now()->toDayDateTimeString();     //2022-08-05 10:05:42
Carbon::parse('+2 days ago');             //解析任何顺序和类型的日期（结果为 Carbon 类型的日期时间对象）
//todo ps:
Carbon::parse('2016-10-15')->toDateTimeString();
Carbon::parse('2016-10-15 00:10:25')->toDateTimeString();
Carbon::parse('today')->toDateTimeString();
Carbon::parse('yesterday')->toDateTimeString();
Carbon::parse('tomorrow')->toDateTimeString();
Carbon::parse('2 days ago')->toDateTimeString();
Carbon::parse('+3 days')->toDateTimeString();
Carbon::parse('+2 weeks')->toDateTimeString();
Carbon::parse('+4 months')->toDateTimeString();
Carbon::parse('-1 year')->toDateTimeString();
Carbon::parse('next wednesday')->toDateTimeString();
Carbon::parse('last friday')->toDateTimeString();

Carbon::now()->addDays(25);
Carbon::now()->addWeeks(3);
Carbon::now()->addHours(25);
Carbon::now()->subHours(2);
Carbon::now()->addHours(2)->addMinutes(2)->addSeconds(120);
Carbon::now()->modify('+15 days');
Carbon::now()->modify('-2 days');

$year = '2022';
$month = '08';
$day = '05';
$hour = '02';
$minute = '15';
$second = '30';
Carbon::create(null, $month, $day, $hour, $minute, $second);  //2022-08-05 02:15:30   null 默认取当前

$dt = Carbon::now();

$dt->isWeekday();
$dt->isWeekend();
$dt->isYesterday();
$dt->isToday();
$dt->isTomorrow();
$dt->isFuture();
$dt->isPast();
$dt->isLeapYear();
$dt->isSameDay(Carbon::now());
$born = Carbon::createFromDate(1987, 4, 23);
$noCake = Carbon::createFromDate(2014, 9, 26);
$yesCake = Carbon::createFromDate(2014, 4, 23);
$overTheHill = Carbon::now()->subYears(50);
var_dump($born->isBirthday($noCake));              // bool(false)
var_dump($born->isBirthday($yesCake));             // bool(true)
var_dump($overTheHill->isBirthday());              // bool(true) -> default compare it to today!ode
```

&#x20;
