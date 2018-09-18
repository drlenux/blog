### Floating point
[home][go-home] / [PHP][go-php] / [Ошибки][go-php-error] / **Ternary operator**

---

```php
<?php
  $arg = 'T';
  $vehicle = ( $arg == 'B' ) ? 'bus' :
    ( $arg == 'A' ) ? 'airplane' :
    ( $arg == 'T' ) ? 'train' :
    ( $arg == 'C' ) ? 'car' :
    ( $arg == 'H' ) ? 'horse' :
    'feet' ;
    
  echo $vehicle;
```

[Результат][result]

[result]: ./result/ternary-operator.md

[go-home]: ../../index.md
[go-php]: ../index.md
[go-php-error]: ./index.md
