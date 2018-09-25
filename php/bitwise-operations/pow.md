### Побитовые операции `POW`
[home][go-home] / [PHP][go-php] / [bitwise operations](./index.md) / **Pow**

---

```php
//standart function
pow($a, $b);

//bitwise operations
$a << ($b - 1)
```

### timer
```php
<?php

class Timer {
    private $_start;
    private $_end;
    
    public function run() {
        $this->_start = microtime(true);
    }
    
    public function stop() {
        $this->_end = microtime(true);
    }
    
    public function get() {
        return $this->_end - $this->_start;
    }
}

function a($a, $b) {
    return $a << ($b -1);
}

function b($a, $b) {
    return pow($a, $b);
}

$timer = new Timer();
$time = [];

$a = 2;
$b = 100;
for ($i = 0; $i < 10000; $i++) {
    $timer->run();
    a($a, $b);
    $timer->stop();
    $time['a'][] = $timer->get();
    
    $timer->run();
    b($a, $b);
    $timer->stop();
    $time['b'][] = $timer->get();
}
$time['a'] = array_sum($time['a']) * count($time['a']);
$time['b'] = array_sum($time['b']) * count($time['b']);
asort($time);
var_dump($time);
```
### Result
```php
//array(2) {
//  ["a"]=>
//  float(20.952224731445)
//  ["b"]=>
//  float(24.888515472412)
//}
```


[go-home]: ../../index.md
[go-php]: ../index.md
