### Вопросы к собеседованию по PHP
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
 //return [PHP-5.6.20] : ['a','b','c','e']
 //return [PHP-7.0.5] : ['a','b','c','d','e']
 ```


[php-error-array_udiff]: ./array_udiff.md

[go-home]: ../../index.md
[go-php]: ../index.md
[go-php-error]: ./index.md
