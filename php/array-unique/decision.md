### Decision Array unique
[home][go-home] / [PHP][go-php] / [Array-unique][go-php-array-unique] / **Decision**

---

```php
<?php
function render_strngs(array $words, $count)
{
    $result = [];
    for ($i = 0; $i < $count; $i++) {
        shuffle($words);
        $result[] = implode(' ', $words);
    }
    return $result;
}
function get_uniques(array $strings)
{
    return array_flip(array_flip($strings));
}
$words = ['red', 'green', 'yellow', 'blue', 'orange'];
$t = microtime(true);
$strings = render_strngs($words, 10000000);
echo "T=" . (microtime(true) - $t) . "\r\n";
$t = microtime(true);
$uniques = get_uniques($strings);
echo "T=" . (microtime(true) - $t) . "\r\n";
var_export($uniques);
```
[go-php-array-unique]: ./index.md
[go-php]: ../index.md
[go-home]: ../../index.md
