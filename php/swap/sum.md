[home][go-home] / [php][go-php] / [swop parameters][go-swap] / **Math sum**
---
### Math sum

```php
<?php

function swapInt(int &$a, int &$b): void
{
  $a = $b + $a - ($b = $a);
}
    
```

[go-swap]: ./index.md
[go-php]: ../index.md
[go-home]: ../../index.md
