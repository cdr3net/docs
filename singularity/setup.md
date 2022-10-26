---
layout: default
title: "Настройка singularity на compute нодах"
---
# Для работы с singularity на compute нодах необходимо: 

Запустить необходимый образ командой
~~~
  singularity run library://sylabsed/examples/lolcow
~~~

# Для запуска docker-контейнера на кластере

* Скачать контейнер и преобразовать его в sif
~~~
  singularity pull docker://brinkmanlab/psortb_commandline:1.0.2
~~~

* Запустить программу в контейнере
~~~
unset LANG
unset LC_ALL
unset LC_TYPE
 singularity exec psortb_commandline_1.0.2.sif /usr/local/psortb/bin/psort --version
PSORTb version 3.0
~~~

* По умолчанию в singularity контейнер пробрасываются некоторые директории
/home, /tmp, текущая директория. Если надо пробросить что-то своё, можно добавить ключ запуска, например:
~~~
singularity exec -B /home/vasilisa/tmp:/tmp:rw psortb_commandline_1.0.2.sif /usr/local/psortb/bin/psort -p -i risk/5_sample/proteins/cancer_wm_proteins_hlaI_+.fasta > risk/5_sample/proteins/cancer_wm_proteins_hlaI_+.txt
~~~
