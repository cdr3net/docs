---
layout: default
title: "IBCH conda инструкции"
---
Для удобной работы с python с командной строки или через jupiter notebook
на кластере рекомендуется использовать идею разных окружений. Посмотреть 
доступные окружения можно командой *conda-env list*

Для добавления и активации окружений необходимо:
1. Добавить conda.sh в скрипт запуска при логине.
~~~
  echo ". ~/anaconda3/etc/profile.d/conda.sh" >> ~/.rc
~~~
1. Перезайти на сервер для активации профайла.
1. Cоздать окружение (создадим для python2 и python3).
~~~
  conda create -n python2 python=2.7
  conda create -n python3 python=3.6
~~~
1. Для работы с jypiter notebook доставим необоходимые ядра для окружений
~~~
    conda activate python2
  conda install notebook ipykernel
  conda install functools_lru_cache
  ipython kernel install --user
    conda deactivate
  
    conda activate python3
  conda install notebook ipykernel
  ipython kernel install --user
    conda deactivate
~~~
1. Новые окружения с ядрами должны появиться в jupiter notebook после запуска
~~~
  jupyter-notebook
~~~

Если jupyter-notebook не используется, то команды активации окружений надо
вводить в консоли и желательно работать с установщиком пакетов через команду 
*conda install*. Если какое-то окружение используется по умолчанию всегда, то активацию его можно также добавить в rc файл
~~~
  echo "conda activate python3" >> ~/.rc
~~~

