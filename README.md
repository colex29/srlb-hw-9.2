# Домашнее задание к занятию "`Система мониторинга Zabbix`" - `Прохоров Семен`

### Задание 1

Установите Zabbix Server с веб-интерфейсом.

1) Прикрепите в файл README.md скриншот авторизации в админке
![alt text](https://github.com/colex29/srlb-hw-9.2/blob/f417d23f4e955f1e2ec3c83eaa74f40a9e08c76a/img/1.PNG)

2) Приложите в файл README.md текст использованных команд в GitHub

```wget https://repo.zabbix.com/zabbix/6.2/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.2-4+ubuntu22.04_all.deb```<br>
```dpkg -i zabbix-release_6.2-4+ubuntu22.04_all.deb```<br>
```sudo dpkg -i zabbix-release_6.2-4+ubuntu22.04_all.deb```<br>
```sudo apt update```<br>
```sudo apt install postgresql```<br>
```sudo apt install zabbix-server-pgsql zabbix-frontend-php php8.1-pgsql zabbix-apache-conf zabbix-sql-scripts```<br>
```sudo -u postgres createuser --pwprompt zabbix```<br>
```sudo -u postgres createdb -O zabbix zabbix```
``` ```

---

### Задание 2

Установите Zabbix Agent на два хоста.

1) Приложите в файл README.md скриншот раздела Configuration > Hosts, где видно, что агенты подключены к серверу


 zabbix-agent
---
