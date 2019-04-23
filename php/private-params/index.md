### Question
[home][go-home] / [php][go-php] / **Приватные переменные**

---
```php
<?php

class A {
    private $a;
    private $b;
    
    public function getSum(): int
    {
        return $this->a + $this->b;
    }
    
    public static function instance(int $a, int $b): self
    {
        $class = new A();
        $class->a = $a;
        $class->b = $b;
        return $class;
    }
}

$class = A::instance(1,2);
echo $class->getSum();
```

[Результат][result]

[result]: ./answer.md
[go-php]: ../index.md
[go-home]: ../../index.md
