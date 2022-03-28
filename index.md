---
layout: default
title: "CDR3.Net Руководство Пользователя"
---
# Контакты
**CDR3Net** at Telegram
# Новости
#### 03/09/2021
Для работы на кластере доступен новый вычислительный сервер minew
#### 19/01/2021
Добавлен раздел [FAQ](./faq/faq.html)
#### 12/12/2020
На кластере добавлена команда webshare, позволяющая расшаривать свои папки через веб

# Основное 
Для того чтобы пользоваться серверами вам нужен
1. **VPN** (для доступа во внутреннюю сеть)
2. **SSH ключ** для доступа через консоль или **пароль** для доступа через R-Studio или Jupyter Hub

# Инструкции
- [FAQ](./faq/faq.html)
- Настройка VPN
  - [ОС Windows](./vpn/windows.html)
  - [Mac OS](./vpn/macos.html)
  - [Linux (Unbuntu 18.04)](./vpn/linux.html)
- Настройка SSH
  - [ОС Windows](./ssh/windows.html)
  - [Mac OS](./ssh/macos.html)
  - [Linux (Unbuntu 18.04)](./ssh/linux.html)
- [Настройка VNC](./vnc/setup.html)
- [Настройка singularity](./singularity/setup.html)

# Структура сети и сервера
Вот примерная структура видная для пользователей (еще есть бэкап сервера, и всякая сетевая инфраструктура):
![image-title-here](/img/CDR3.Net.Structure.svg){:class="img-responsive"}

## Счетные сервера и дисковое пространство
Дисковое пространство общее для каждой локации. Ваша домашняя папка лежит на одном из серверов-хранилищ
- IBCH
  - Total storage: 304TiB
  - **mibig.cdr3.net**
    - CPU: 8 Cores, Xeon E5-1620 @ 3.60GHz
    - RAM: 64 Gb
  - **mihuge.cdr3.net**
    - CPU: Total 40/80 Cores, 4 X Xeon CPU E7-4870 @ 2.40GHz
    - RAM: 512 Gb
    - GPU: Titan X, 12 Gb 
  - **milarge.cdr3.net**
    - CPU: Total 24/48 Cores, 2 X Xeon CPU Silver 4116 @ 2.10GHz
    - RAM: 384 Gb
  - **minew.cdr3.net**
    - CPU: Total 20/40 Cores, 2 X Xeon CPU Silver 4210R @ 2.40GHz
    - RAM: 384 Gb
- CZ
  - Total storage: 36.2 Tb  
  - **micz.cdr3.net**
    - CPU: Total 28/56 Cores, 2 X Xeon CPU E5-2683 v3 @ 2.00GHz
    - RAM: 512 Gb
