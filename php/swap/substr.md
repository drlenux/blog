### Substr
[home][go-home] / [php][go-php] / [swop parameters][go-swap] / **Substr**

---
```php
<?php

function swapSubstr(&$a, &$b): void
{
  $a = $b.$a;
  $b = substr($a,strlen($b),strlen($a));
  $a = substr($a,0,strlen($a)-strlen($b));
}
    
```

[go-swap]: ./index.md
[go-php]: ../index.md
[go-home]: ../../index.md
