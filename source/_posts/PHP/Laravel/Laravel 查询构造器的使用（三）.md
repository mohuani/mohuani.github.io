---
title: "Laravel 查询构造器的使用（三）"
date: 2021-03-24T19:36:38+08:00
draft: true
---

查询构造器中的构造函数

```php
	//聚合函数
    public function query5()
    {
        $num = DB::table('student')->count();
        var_dump($num);

        $max = DB::table('student')->max('age');
        var_dump($max);

        $min = DB::table('student')->min('age');
        var_dump($min);

        $avg = DB::table('student')->avg('age');
        var_dump($avg);

        $sum = DB::table('student')->sum('age');
        var_dump($sum);
    }
```