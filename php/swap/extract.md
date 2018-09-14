[home][go-home] / [php][go-php] / [swop parameters][go-swap] / **Extract**
---
### Extract

```php
<?php

function swapExtract(&$a, &$b): void
{
  extract(['a' => $b, 'b' => $a]);
}
    
```

[go-swap]: ./index.md
[go-php]: ../index.md
[go-home]: ../../index.md
