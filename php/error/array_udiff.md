### array_udiff
[home][go-home] / [PHP][go-php] / [Ошибки][go-php-error] / **array_udiff**

---

```php
<?php 
 $a = ['a','b', 'c', 'd', 'e'];
 $b = ['d'];
 
 $out = array_udiff($a, $b, function($a1, $a2) {
   return ($a1 === $a2) ? 0 : 1;
 });
 
 var_dump($out);
 ```

[Результат][php-error-array_udiff-result]

[php-error-array_udiff-result]: ./result/array_udiff.md

[go-home]: ../../index.md
[go-php]: ../index.md
[go-php-error]: ./index.md
