Дан массив слов:
**$words** = `[‘red’, ‘green’, ‘blue’, ‘yellow’, ‘orange’];`

Необходимо:
1. Сгенерировать массив из 10 миллионов не уникальных строк, каждая из которых является случайной последовательностью данных слов, разделенных пробелами, например
“orange blue red yellow green”
Каждая строка должна содержать все пять слов без повторений.

2. Из данного массива выбрать все уникальные строки (т.е. удалить дубли), не используя функцию array_unique. 
```php
function render_strngs(array $words, $count)
{
    // your code here
}

function get_uniques(array $strings)
{
    // your code here
}

$words = ['red', 'green', 'yellow', 'blue', 'orange'];

$t = microtime(true);
$strings = render_strngs($words, 10000000);
echo "T = ".(microtime(true) - $t)."\n";

$t = microtime(true);
$uniques = get_uniques($strings);
echo "T = ".(microtime(true) - $t)."\n";
print_r($uniques);
```

[Решение][decision]

[decision]: ./decision.md
