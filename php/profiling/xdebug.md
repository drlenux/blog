### Профилирование Xdebug
[home][go-home] / [PHP][go-php] / [Профилирование][go-profiling] / **Xdebug**

---

### Установка

```bash
sudo apt install php-xdebug
```

**OR**

```bash
sudo yum install php-xdebug
```

### Настройка

`xdebug.ini`

```ini
[xdebug]
zend_extension=/usr/lib64/php/modules/xdebug.so
zend_extension=xdebug.so
xdebug.default_enable=1
xdebug.remote_autostart=0
xdebug.remote_enable=1
xdebug.idekey="PHPSTORM"
xdebug.remote_connect_back=0
xdebug.remote_handler="dbgp"
xdebug.remote_host=10.0.2.2
xdebug.remote_port=9000
```

[go-profiling]: ./index.md
[go-home]: ../../index.md
[go-php]: ../index.md
