### Профилирование XHProf
[home][go-home] / [PHP][go-php] / [Профилирование][go-profiling] / **XHProf**

---

### Установка

```bash
sudo apt install xhprof
```

**OR**

```bash
sudo yum install php-xdebug
```

### Как с ним работать

#### Включение профилирования

```php
<?
function execute()
{
  # Какой-то PHP код
}


# Инициализируем профайлер
xhprof_enable(XHPROF_FLAGS_CPU + XHPROF_FLAGS_MEMORY);


# Выполняем программу после включения профайлера
execute();


# Останавливаем профайлер после выполнения программы
$xhprof_data = xhprof_disable();
```

- Функция xhprof_enable() принимает в качестве аргументов флаги. XHPROF_FLAGS_CPU для фиксирования статистики процессора, XHPROF_FLAGS_MEMORY — для памяти, XHPROF_FLAGS_NO_BUILTINS — для игнорирования встроенных функций.
- xhprof_disable() выключит профайлер и вернет собранную статистику.

#### Отчеты

##### Генерация

Собранные данные можно проанализировать в интерфейсе XHprof для построения отчетов. Для этого, необходимо скачать [исходники XHprof](http://pecl.php.net/package/xhprof):

```bash
cd /var/www;
wget http://pecl.php.net/get/xhprof-0.9.4.tgz
gzip -d xhprof-0.9.4.tgz
tar -xvf xhprof-0.9.4.tar
```

После этого необходимо внести изменения в скрипт:

```php
<?
//...
$xhprof_data = xhprof_disable();
include_once "/var/www/xhprof-0.9.4/xhprof_lib/utils/xhprof_lib.php";
include_once "/var/www/xhprof-0.9.4/xhprof_lib/utils/xhprof_runs.php";
$xhprof_runs = new XHProfRuns_Default();
$run_id = $xhprof_runs->save_run($xhprof_data, "test");
```

##### Интерфейс для отчетов

Чтобы увидеть отчет, необходимо настроить виртуальный хост на папку `/var/www/xhprof-0.9.4/xhprof_html`. Например, в Nginx:

```apacheconfig
server {
	server_name xh.ruhighload.com;
	root /var/www/xhprof-0.9.4/xhprof_html;
	index index.php;

	location ~* \.(php)$ {
        	fastcgi_pass 127.0.0.1:9000;
	        fastcgi_index index.php;
        	include fastcgi_params;
        	fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
	}
}
```

```bash
nginx -s reload
```


Таблица содержит список функций, которые были выполнены в рамках одной страницы с дополнительной информацией:

- `Calls` — количество и процентное соотношение вызовов функции.
- `Incl. Wall Time` — время выполнения функции с вложенными функциями.
- `Excl. Wall Time` — время выполнения функции без вложенных функций.
- `Incl. CPU` — процессорное время с вложенными функциями.
- `Excl. CPU` — процессорное время без вложенных функций.
- `Incl. MemUse` — потребление памяти с вложенными функциями.
- `Excl. MemUse` — потребление памяти без вложенных функций.
- `Incl. PeakMemUse` — максимальное потребление памяти с вложенными функциями.
- `Excl. PeakMemUse` — максимальное потребление памяти без вложенных функций.

[go-profiling]: ./index.md
[go-home]: ../../index.md
[go-php]: ../index.md
