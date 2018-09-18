### Floating point
[home][go-home] / [PHP][go-php] / [Ошибки][go-php-error] / **floating point**

---

```php
<?php
  $L = 131.17;
  $a = ($L*100);
  echo $a."\r\n"; // 13117
  $a=intval($a);
  echo $a; // 13116
 ```
```php
<?php
  $n="19.99";
  print intval($n*100); // prints 1998
  echo "\r\n";
  print intval(strval($n*100)); // prints 1999
```

```php
<?php
  $value[0] = 97.5;
 
  $value[1] = (9.975-9)*100;
  echo $value[0].' == '.$value[1]; // 97.5 == 97.5
  $res = ($value[0]) == $value[1]); // false
```

[go-home]: ../../index.md
[go-php]: ../index.md
[go-php-error]: ./index.md
