---
layout: default
title: "IBCH инструкции для работы с jupyter lab"
---
Для работы с кластером из браузера доступен jupyter lab. Доступ на него возможен
по логину/паролю кластера через адрес [http://juplab.cdr3.net](http://juplab.cdr3.net) (только с VPN)

По умолчанию система видит уже настроенные kernels от jupyter notebook.

В общем случае ядра можно добавить по общим инструкциям для jupyter notebook. Примеры добавлений kernels:
1. Для добавления python своём python окружении выполнить команду
~~~
  conda activate "МОЕ ОКРУЖЕНИЕ"
  ipython kernel install --name "ОТОБРАЖАЕМОЕ ИМЯ ОКРУЖЕНИЯ" --user
~~~
1. Для добавления R kernel в R выполнить команды
~~~
    R
  install.packages('IRkernel')
  IRkernel::installspec()
~~~
1. Для добавления ядра, запускаемого на другой машине кластера (например на mihuge с GPU)
~~~
    # активируем нужное окружение
  conda activate ИМЯ-ОКРУЖЕНИЯ
    # ставим пакет remote_ikernel черер pip3
  pip3 install remote_ikernel
    # добавляем ядро с удаленной машины командой
  remote_ikernel manage --add --kernel_cmd="$HOME/.conda-envs/ИМЯ-ОКРУЖЕНИЯ/bin/ipython kernel -f {connection_file}" --name="ОТОБРАЖАЕМОЕ ИМЯ ОКРУЖЕНИЯ" --interface=ssh --host=mihuge
    # проверяем доступ по ssh с mibig на выбранную машину
  ssh mihuge
~~~
1. Посмотреть свои окружения можно командой
~~~
  conda env list
~~~
1. Как настроить свои окружения для python в conda можно посмотреть по [ссылке](/wiki/conda.html).
