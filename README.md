# Домашнее задание к занятию "`Система мониторинга Zabbix. Часть 2`" - `Прохоров Семен`

### Задание 1

Установите Zabbix Server с веб-интерфейсом.

1) Прикрепите в файл README.md скриншот авторизации в админке
![alt text](https://github.com/colex29/srlb-hw-9.2/blob/main/img/1.PNG)

2) Приложите в файл README.md текст использованных команд в GitHub

`wget https://repo.zabbix.com/zabbix/6.2/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.2-4+ubuntu22.04_all.deb`<br>
`dpkg -i zabbix-release_6.2-4+ubuntu22.04_all.deb`<br>
`sudo dpkg -i zabbix-release_6.2-4+ubuntu22.04_all.deb`<br>
`sudo apt update`<br>
`sudo apt install postgresql`<br>
`sudo apt install zabbix-server-pgsql zabbix-frontend-php php8.1-pgsql zabbix-apache-conf zabbix-sql-scripts`<br>
`sudo -u postgres createuser --pwprompt zabbix`<br>
`sudo -u postgres createdb -O zabbix zabbix`

---

### Задание 2

Установите Zabbix Agent на два хоста.

1) Приложите в файл README.md скриншот раздела Configuration > Hosts, где видно, что агенты подключены к серверу
![alt text](https://github.com/colex29/srlb-hw-9.2/blob/main/img/2.PNG)
![alt text](https://github.com/colex29/srlb-hw-9.2/blob/main/img/3.PNG)

2) Приложите в файл README.md скриншот лога zabbix agent, где видно, что он работает с сервером
![alt text](https://github.com/colex29/srlb-hw-9.2/blob/main/img/4.PNG)

3) Приложите в файл README.md скриншот раздела Monitoring > Latest data для обоих хостов, где видны поступающие от агентов данные.
![alt text](https://github.com/colex29/srlb-hw-9.2/blob/main/img/5.PNG)
![alt text](https://github.com/colex29/srlb-hw-9.2/blob/main/img/6.PNG)

4) Приложите в файл README.md текст использованных команд в GitHub

`sudo apt install zabbix-agent -y`<br>
`sudo systemctl restart zabbix-agent`<br>
`sudo systemctl enable zabbix-agent`<br>
`sed -i 's/Server=127.0.0.1/Server=10.10.5.72'/g' /etc/zabbix/zabbix_server.conf`<br>
`sudo systemctl restart zabbix-agent`<br>
`cat /var/log/zabbix/zabbix_agentd.log`
