---
layout: default
title: "Настройка VNC на compute нодах"
---
# Для настройки VNC На compute ноде необходимо: 

1. Создать исполняемый файл
~~~
  cat ~/.vnc/xstartup 
  #!/bin/sh
  dbus-launch --exit-with-session cinnamon-session --session cinnamon &
~~~
2. Запустить свое серверное приложение
~~~
  vncserver  -localhost no :7
  где :X или :XX - означает tcp порт приложения 590X или 59XX
~~~
3. Заходить на сервер любым vnc клиентом на созданный порт
~~~
  vncviewer servername:59XX
~~~
