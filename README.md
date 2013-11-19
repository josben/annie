annie
=====

Django 1.6 + django-bootstrap-toolkit + django-userena

para empezar a trabajarlo sigue los siguientes pasos:

1. Creamos el entorno virtual
=============================

$ virtualenv django6

$ source django6/bin/activate

$ pip install -r requirements/common.txt

2. Ahora instalamos django-userena
==================================

Tienes dos opciones:
- puedes descargar el fork que saque a django-userena, este ya esta con los
cambios para que funcione sin problemas con Django 1.6

$ git clone https://github.com/josben/django-userena

- la segunda opcion es que te descargues del autor original y le parches

$ git clone https://github.com/bread-and-pepper/django-userena/

en el proyecto annie hay una carpeta que dice patches, ahi esta el parche para
django-userena para que realize los cambios necesarios para Django 1.6

$ cp patches/fix_to_django6.patch /path/django-userena

$ cd django-userena

$ git apply --stat fix_to_django6.patch

$ git apply --check fix_to_django6.patch

$ git am --signoff < fix_to_django6.patch

y listo, ya lo tienes parchado

ahora en tu entorno virtual instalas django-userena

(django6)$ python setup.py install

teniendo todo eso empezamos a trabajar con el proyecto:

(django6) annie$ python manage.py syncdb

en ese paso no se olviden crear su cuenta

(django6) annie $ python manage.py runserver

Disfrutenlo!!!

Happy Hacking ;-)
