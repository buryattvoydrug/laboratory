---
# Front matter
lang: ru-RU
title: 'Отчёт'
subtitle: 'по лабораторной работе 1'
author: 'Радимов Игорь Ринадович'

# Formatting
toc-title: 'Содержание'
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: Ubuntu
romanfont: Ubuntu
sansfont: Ubuntu
monofont: Ubuntu
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
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

Приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.

# Задание

Лабораторная работа подразумевает установку на виртуальную машину VirtualBox (https://www.virtualbox.org/) операционной системы Linux, дистрибутив Centos.

# Выполнение лабораторной работы

1. Запускаю _Virtual Box_, создаю новую виртуальную машину с именем **_iradimov_**: выбираю тип операционной системы _Linux_, а также версию _Red Hat_ (рис.1).

   ![рис.1. Имя и тип ОС.](images/1.jpg){ #fig:001 width=60% }

2. Указываю объем памяти 2048 МБ (рис.2).

   ![рис.2. Объем памяти.](images/2.jpg){ #fig:002 width=60% }

3. Задаю конфигурацию жесткого диска: создаю новый динамический виртуальный жёсткий диск типа VDI, а также размер диска - 40 ГБ и его расположение (рис.3-6).

   ![рис.3](images/3.jpg){ #fig:003 width=60% }

   ![рис.4](images/4.jpg){ #fig:004 width=60% }

   ![рис.5](images/6.jpg){ #fig:006 width=60% }

   ![рис.6](images/7.jpg){ #fig:007 width=60% }

4. Добавляю во вкладке _"Носители"_ свойств виртулальной машины новый привод оптических дисков, выбираю нужный образ для установки операционной системы (рис.7).

   ![рис.7](images/8.jpg){ #fig:008 width=60% }

5. Запускаю созданную виртуальную машину и начинаю установку. В открытом окне выбираю русский язык как язык интерфейса, а также добавляю русскую раскладку клавиатуры (рис.8).

   ![рис.8](images/9.jpg){ #fig:009 width=60% }

6. Создаю нового пользователя с правами администратора, задаю пароль (рис.9).

   ![рис.9](images/10.jpg){ #fig:010 width=60% }

7. Продолжаю установку операционной системы, перезагружаю виртуальную машину по требованию установщика. Принимаю лицензионное соглашение (рис.10-11).

   ![рис.10](images/13.jpg){ #fig:011 width=60% }

   ![рис.11](images/14.jpg){ #fig:012 width=60% }

8. Вхожу в созданный ранее профиль, открывается привычный графический интерфейс (рис.12).

   ![рис.12](images/15.jpg){ #fig:013 width=60% }

9. Открываю терминал, перехожу на **_root_** пользователя командой _su_, обновляю системные файлы _yum update_, устанавливаю mc командой _yum install mc_ (рис.13).

   ![рис.13](images/16.jpg){ #fig:014 width=60% }

# Выводы

Приобрел практические навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.
