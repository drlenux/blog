### Интервальная сумма
[home][go-home] / [PHP][go-php] / [Интервальная сумма][go-interval-answer] / **Решение**

---

#### Способ перебором:
```php
function method1(int $a, int $b): int
{
  $sum = $a;
  for ($i = $a + 1; $i <= $b; $i++) {
    $sum += $i;
  }
  return $sum;
}
```
![data search](http://apikabu.ru/img_n/2012-11_3/f0m.jpg)

#### Способ массивом:
![array method](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRJAyc_bIEkSSfRkspEei-JD3PDLjFrKcWyPbqVRlmedOEkkx4R)
```php
function method2(int $a, int $b): int
{
  $arr = range($a, $b);
  return array_sum($arr);
}
```
По скорости работы такойже как и `Способ перебором` но при больших значениях будет выбрасывать ошибку о привышении лимита массива

#### Математический способ
![math metod](http://itmozg.ru/old/upload/math.jpg)
```php
function method3(int $a, int $b): int
{
  return ($a + $b)*$b/2;
}
```

[answer]: ./answer.md
[go-php]: ../index.md
[go-home]: ../../index.md
[go-interval-answer]: ./index.md
