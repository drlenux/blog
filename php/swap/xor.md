[home][go-home] / [php][go-php] / [swop parameters][go-swap] / **XOR**
---
### XOR

```php
<?php

function swapXOR(&$a, &$b) 
{
  $a = $a ^ $b;
  $b = $a ^ $b;
  $a = $a ^ $b;
}
    
```

[go-swap]: ./index.md
[go-php]: ../index.md
[go-home]: ../../index.md
