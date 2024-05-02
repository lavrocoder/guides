# Настройка управления supervisor'ом без sudo и ввода пароля

###### на примере пользователя `www`

Для этого нужно изменить файл `/etc/supervisor/supervisord.conf`

Открываем
```shell
sudo nano /etc/supervisor/supervisord.conf
```

Изменяем блок `unix_http_server`
```text
[unix_http_server]
file=/var/run/supervisor.sock
chmod=0770
chown=www:www
```

Перезапускаем supervisor
```shell
sudo service supervisor restart
```

Изменяем настройки доступа
```shell
sudo chmod a+rwx /etc/supervisor/conf.d
```
