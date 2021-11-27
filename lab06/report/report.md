---
# Front matter
title: "Отчет по лабораторной работе номер 6"
author: "Хамбалеев Булат Галимович"


# Generic otions
lang: ru-RU
toc-title: "Содержание"


# Pdf output format
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
### Fonts
mainfont: Ubuntu
romanfont: Ubuntu
sansfont: Ubuntu
monofont: Ubuntu
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Misc options
indent: true
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Развить навыки администрирования ОС Linux. Получить первое практическое знакомство с технологией SELinux1. Проверить работу SELinx на практике совместно с веб-сервером Apache.

# Задание

Лабораторная работа подразумевает использование некоторых консольных команд для взаимодействия с кодом и веб-сервером.

# Теория

Для запуска веб-сервера Apache нам понадобится установить пакет apache, доступный в оффициальных репозиториях. Затем настроить файл конфигурации, который находится по адресу /etc/httpd/conf. Для старта apache нужно запустить службу httpd.service. 

# Выполнение работы

1. Войдём в систему и убедимся что SELinux работает в режиме enforcing. Убедимся что веб-сервер работает. Найдём веб-сервер Apache в списке процессов. Посмотрим текущее состояние переключателей SELinux для Apache.(рис 1-4)


![рис.1. Getenforce и sestatus.](images/1.jpg){ #fig:001 width=90% }


![рис.2. Проверка работы веб-сервера.](images/2.jpg){ #fig:002 width=90% }


![рис.3. Список процессов.](images/3.jpg){ #fig:003 width=90% }


![рис.4. Переключатели SELinux для Apache.](images/4.jpg){ #fig:004 width=90% }


2. Посмотрим статистику по политике. Определим тип файлов и поддиректорий в /var/www и /var/www/html. Определим круг пользователей, которым разрешено создание файлов в директории /var/www/html. Создадим от имени суперпользователя html файл. Проверим контенкст созданного файла. (рис.5-8)


![рис.5. Seinfo.](images/5.jpg){ #fig:005 width=90% }


![рис.6. Определение типа файлов и круга пользователей.](images/6.jpg){ #fig:006 width=90% }


![рис.7. HTML код для веб сервера.](images/7.jpg){ #fig:007 width=90% }


![рис.8. Проверим контекст созданного файла.](images/8.jpg){ #fig:008 width=90% }


3. Обратимся к файлу через веб-сервер и убедимся, что файл был успешно отображен. Выясним какие контексты файлов определены для httpd. Изменим контекст файла test.html . Попробуем ещё раз получить доступ к файлу через веб-серввер, но получим сообщение об ошибке.(рис.9-13)


![рис.9. Браузер и веб-сервер.](images/9.jpg){ #fig:009 width=90% }


![рис.10. Лог файлы.](images/10.jpg){ #fig:010 width=90% }


![рис.11. Лог файлы(часть 2).](images/11.jpg){ #fig:011 width=90% }


![рис.12. Запрет доступа к веб-серверу.](images/12.jpg){ #fig:012 width=90% }


![рис.13. Анализ ситуации.](images/13.jpg){ #fig:013 width=90% }


4. Посмотрим лог файлы веб-сервера Apache. Попробуем запустить веб-сервер Apache на прослушивание TCP-порта 81. Выполним перезапуск(получен сбой). ( рис.14-17)


![рис.14. Лог веб-сервера.](images/14.jpg){ #fig:014 width=90% }


![рис.15. Listen 81.](images/15.jpg){ #fig:015 width=90% }


![рис.16. Неудачная попытка соединения с веб-сервером через браузер.](images/16.jpg){ #fig:016 width=90% }


![рис.17. Перезапуск сервера.](images/17.jpg){ #fig:017 width=90% }


5. Проанализируем лог файлы. Проверим список портов и убедимся, что 81 появился в списке. Попробуем запустить сервер ещё раз. Успешно.(рис. 18-22)


![рис.18. Лог.](images/18.jpg){ #fig:018 width=90% }


![рис.19. Лог(часть2).](images/19.jpg){ #fig:019 width=90% }


![рис.20. Список портов.](images/20.jpg){ #fig:020 width=90% }


![рис.21. Повторный перезапуск сервера.](images/21.jpg){ #fig:021 width=90% }


![рис.22. Удачная попытка доступа к серверу.](images/22.jpg){ #fig:022 width=90% }


6. Исправим обратно конфигурационный файл apache. Удалим привязку к 81 порту. Удалим файл test.html.(рис. 23-27)


![рис.23. Исправление конфигурационного файла.](images/23.jpg){ #fig:023 width=90% }


![рис.24. Удаление привязки и файла.](images/24.jpg){ #fig:024 width=90% }

# Библиография

1. ТУИС РУДН

2. Статья на сайте "https://wiki.archlinux.org/title/Apache_HTTP_Server_(%D0%A0%D1%83%D1%81%D1%81%D0%BA%D0%B8%D0%B9)"

# Выводы

Во время выполнения лабораторной работы я получил навыки администрирования OC Linux. Получил первое практическое знакомство с технологией SELinux. Проверил работу SELinux на практике совместно с веб-сервером Apache. 








