### Интервальная сумма
[home][go-home] / [PHP][go-php] / [Интервальная сумма][go-interval-answer] / **Решение**

---

#### Способ перебором:

```php
public function method1(int $a, int $b): int
  {
    $sum = $a;
    for ($i = $a + 1; $i <= $b; $i++) {
      $sum += $i;
    }
    return $sum;
  }
```

Способ массивом:

[answer]: ./answer.md
[go-php]: ../index.md
[go-home]: ../../index.md
[go-interval-answer]: ./index.md
