### Decision DB Log
[home][go-home] / [PHP][go-php] / [DB Log][go-db-log] / **Decision**

---

Допустим имеем таблицу `logs`

### logs

| id | log | created_at  | status_code|
|--- | --- | ----------- | ---------- |
|int | text|int/timestamp|     int    |
|PK |      |     index   |   index    |

1. делаем партицирование
    ```sql
    ALTER TABLE logs PARTITION BY hash( MONTH(created_at) ) PARTITIONS 12;
    ```
2. Получаем список **partitions** для дальнейшего удаления
    ```sql
    SELECT 
      concat('p',PARTITION_ORDINAL_POSITION) as pops
    FROM information_schema.PARTITIONS 
    WHERE 
      TABLE_SCHEMA = 'test' 
      AND TABLE_NAME = 'logs'
      AND PARTITION_ORDINAL_POSITION <> MONTH(NOW());
    ```
3. Псевдокод для очистки **partition**
    ```sql
    for (pop in pops) :
      ALTER TABLE logs TRUNCATE PARTITION :pop
    endfor;
    ```
    
[go-db-log]: ./index.md
[go-php]: ../index.md
[go-home]: ../../index.md
